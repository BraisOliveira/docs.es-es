---
title: Tipos de referencia que aceptan valores NULL
description: En este artículo se proporciona información general sobre los tipos de referencia que aceptan valores NULL, una novedad de C# 8.0. Conocerá cómo esta característica proporciona protección contra excepciones de referencia NULL, tanto para proyectos nuevos como para los existentes.
ms.technology: csharp-null-safety
ms.date: 02/19/2019
ms.openlocfilehash: e20ea6efa389ba1aa0d8432a408c0b2a06a61c30
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/29/2019
ms.locfileid: "73039778"
---
# <a name="nullable-reference-types"></a>Tipos de referencia que aceptan valores NULL

Una de las novedades de C# 8.0 son los **tipos de referencia que aceptan valores NULL** y los **tipos de referencia que no aceptan valores NULL**, que permiten usar instrucciones importantes sobre las propiedades de variables de tipos de referencia:

- **Una referencia no debería ser NULL**. Si las variables no deben ser NULL, el compilador aplica reglas que garantizan que sea seguro desreferenciar dichas variables sin comprobar primero que el valor no sea NULL:
  - La variable debe inicializarse como un valor distinto a NULL.
  - No se puede asignar el valor `null` a la variable.
- **Una referencia puede ser NULL**. Si las variables pueden ser NULL, el compilador aplica reglas para garantizar que haya comprobado correctamente si hay referencias NULL:
  - Solo se puede desreferenciar la variable si el compilador pueda garantizar que el valor no sea NULL.
  - Estas variables se pueden inicializar con el valor `null` predeterminado, y se les puede asignar el valor `null` en otro código.

Esta nueva característica proporciona grandes ventajas sobre el control de variables de referencia con respecto a versiones anteriores de C#, donde la intención del diseño no se podía determinar a partir de la declaración de la variable. El compilador no proporcionaba protección contra excepciones de referencia NULL para los tipos de referencia:

- **Una referencia puede ser NULL**. Si se inicializa un tipo de referencia con un valor NULL, o bien posteriormente se asigna a este, no se emite ninguna advertencia.
- **Se asume que una referencia no es NULL**. Si se desreferencian tipos de referencia, el compilador no emite ninguna advertencia. (Con las referencias que aceptan valores NULL, el compilador emite una advertencia si se desreferencia una variable que puede ser NULL).

Con la incorporación de los tipos de referencia que aceptan valores NULL, puede declarar su intención de forma más clara. El valor `null` es la forma adecuada de representar que una variable que no hace referencia a un valor. No use esta característica para eliminar todos los valores `null` de su código. En su lugar, debería declarar su intención al compilador para que los demás desarrolladores la puedan ver al leer el código. Al declarar su intención, el compilador le informa de cuándo escribe código que no es coherente con esa intención.

Un **tipo de referencia que acepta valores NULL** se anota con la misma sintaxis que los [tipos de valor que aceptan valores NULL](programming-guide/nullable-types/index.md): se agrega `?` junto al tipo de la variable. Por ejemplo, la siguiente declaración de variable representa una variable de cadena que acepta valores NULL, `name`:

```csharp
string? name;
```

Cualquier variable en la que `?` no esté junto al nombre de tipo es un **tipo de referencia que no acepta valores NULL**. Esto incluye todas las variables de tipo de referencia en el código existente en el momento en el que se habilita esta característica.

El compilador usa el análisis estático para determinar si se sabe si una referencia que acepta valores NULL no tiene este tipo de valor. Si desreferencia una referencia que acepta valores NULL cuando esta puede ser NULL, el compilador genera una advertencia. Puede invalidar este comportamiento usando el [operador de limitación de advertencias de valores NULL](language-reference/operators/null-forgiving.md) `!` después del nombre de una variable. Por ejemplo, si sabe que la variable `name` no es NULL, pero el compilador genera una advertencia, puede escribir el código siguiente para invalidar el análisis del compilador:

```csharp
name!.Length;
```

## <a name="nullability-of-types"></a>Nulabilidad de tipos

Cualquier tipo de referencia puede tener una de cuatro *nulabilidades*, que describen cuándo se generan las advertencias:

- *No acepta valores NULL*: no se pueden asignar valores NULL a las variables de este tipo. No es necesario comprobar si estas tienen un valor NULL antes de desreferenciarlas.
- *Acepta valores NULL*: se pueden asignar valores NULL a las variables de este tipo. Si se desreferencian sin comprobar primero la existencia de valores `null`, se producirá una advertencia.
- *Inconsciente*: este es el estado previo a C# 8.0. Las variables de este tipo se pueden desreferenciar o asignar sin advertencias.
- *Desconocido*: este es generalmente el caso de los parámetros de tipo en los que las restricciones no indican al compilador que el tipo debe *aceptar valores NULL* o *no aceptar valores NULL*.

La nulabilidad de un tipo en una declaración de variable se controla mediante el *contexto que acepta valores NULL* en el que se declara la variable.

## <a name="nullable-contexts"></a>Contextos que aceptan valores NULL

Los contextos que aceptan valores NULL permiten un control preciso sobre cómo interpreta el compilador las variables de tipos de referencia. El **contexto de anotación que acepta valores NULL** de cualquier línea de origen está habilitado o deshabilitado. Puede considerar que el compilador anterior al de C# 8.0 compilaba todo el código con el contexto que acepta valores NULL deshabilitado: cualquier tipo de referencia puede tener el valor NULL. El **contexto de advertencia que acepta valores NULL** también se puede habilitar o deshabilitar. Este contexto especifica las advertencias que genera el compilador usando el análisis de flujos.

Tanto el contexto de anotación que acepta valores NULL como el contexto de advertencia que acepta valores NULL pueden establecerse para un proyecto con el elemento `Nullable` del archivo *.csproj*. Este elemento configura la forma en la que el compilador interpreta la nulabilidad de los tipos y las advertencias que se generan. Estos son los valores válidos:

- `enable`: el contexto de anotación que acepta valores NULL es **enabled**. El contexto de advertencia que acepta valores NULL es **enabled**.
  - Las variables de un tipo de referencia, como `string`, no aceptan valores NULL.  Todas las advertencias de nulabilidad están habilitadas.
- `warnings`: el contexto de anotación que acepta valores NULL es **disabled**. El contexto de advertencia que acepta valores NULL es **enabled**.
  - Las variables de un tipo de referencia son inconscientes. Todas las advertencias de nulabilidad están habilitadas.
- `annotations`: el contexto de anotación que acepta valores NULL es **enabled**. el contexto de advertencia que acepta valores NULL es **disabled**.
  - Las variables de un tipo de referencia, como cadena, no admiten un valor NULL. Todas las advertencias de nulabilidad están deshabilitadas.
- `disable`: el contexto de anotación que acepta valores NULL es **disabled**. el contexto de advertencia que acepta valores NULL es **disabled**.
  - Las variables de tipo de referencia son inconscientes, como en versiones anteriores de C#. Todas las advertencias de nulabilidad están deshabilitadas.

**Ejemplo**:

```xml
<Nullable>enable</Nullable>
```

También puede usar directivas para establecer los mismos contextos en cualquier lugar del proyecto:

- `#nullable enable`: establece el contexto de anotación que acepta valores NULL y el contexto de advertencia que acepta valores NULL en **enabled**.
- `#nullable disable`: establece el contexto de anotación que acepta valores NULL y el contexto de advertencia que acepta valores NULL en **disabled**.
- `#nullable restore`: restaura el contexto de anotación que acepta valores NULL y el contexto de advertencia que acepta valores NULL según la configuración del proyecto.
- `#nullable disable warnings`: establece el contexto de advertencia que acepta valores NULL en **disabled**.
- `#nullable enable warnings`: establece el contexto de advertencia que acepta valores NULL en **enabled**.
- `#nullable restore warnings`: restaura el contexto de advertencia que acepta valores NULL según la configuración del proyecto.
- `#nullable disable annotations`: establezca el contexto de anotación que admite un valor NULL en **disabled**.
- `#nullable enable annotations`: establezca el contexto de anotación que admite un valor NULL en **enabled**.
- `#nullable restore annotations`: restaura el contexto de advertencia de anotación según la configuración del proyecto.

De forma predeterminada, los contextos de advertencias y anotaciones que aceptan valores NULL están **deshabilitados**. Esto implica que el código existente se compila sin cambios y sin generar ninguna advertencia nueva.

## <a name="nullable-annotation-context"></a>Contexto de anotación que admite valores NULL

El compilador usa las siguientes reglas en un contexto de anotación deshabilitado que acepta valores NULL:

- No se pueden declarar referencias que aceptan valores NULL en un contexto deshabilitado.
- Todas las variables de referencia se pueden asignar a un valor NULL.
- No se genera ninguna advertencia al desreferenciar una variable de un tipo de referencia.
- El operador de limitación de advertencias de valores NULL no se puede usar en un contexto deshabilitado.

El comportamiento es el mismo que en versiones anteriores de C#.

El compilador usa las siguientes reglas en un contexto de anotación habilitado que acepta valores NULL:

- Todas las variables de tipo de referencia son **referencias que no aceptan valores NULL**.
- Estas referencias se pueden desreferenciar sin problemas.
- Todos los tipos de referencia que aceptan valores NULL (con la anotación de `?` después del tipo en la declaración de la variable) pueden ser NULL. El análisis estático determina si se sabe que el valor no es NULL cuando se desreferencia. Si no, el compilador emite una advertencia.
- Puede usar el operador de limitación de advertencias de valores NULL para declarar que una referencia que acepta valores NULL no tiene un valor NULL.

En un contexto de anotación que acepta valores NULL, el carácter `?` junto a un tipo de referencia declara un **tipo de referencia que acepta valores NULL**. Se puede incorporar un **operador de limitación de advertencias de valores NULL** `!` junto a una expresión para declarar que no tiene un valor NULL.

## <a name="nullable-warning-context"></a>Contexto de advertencia que acepta valores NULL

El contexto de advertencia que acepta valores NULL no es igual al contexto de anotación que acepta valores NULL. Se pueden habilitar las advertencias incluso aunque las nuevas anotaciones estén deshabilitadas. El compilador usa el análisis de flujos estático para determinar el **estado NULL** de cualquier referencia. El estado NULL puede ser **no NULL** o **quizás NULL** cuando el *contexto de advertencia que acepta valores NULL* no está **deshabilitado**. Si desreferencia una referencia cuando el compilador ha determinado el estado **quizás NULL**, el compilador emite una advertencia. El estado de una referencia es **quizás NULL** a menos que el compilador pueda determinar una de estas dos condiciones:

1. La variable se ha asignado definitivamente a un valor distinto a NULL.
1. Se ha comprobado que la variable o la expresión no tiene un valor NULL antes de desreferenciarla.

El compilador genera advertencias cuando se desreferencia una variable o expresión en un estado **quizás NULL** si el contexto de advertencia que acepta valores NULL es está habilitado. Además, se generan advertencias cuando se asigna una variable o expresión **quizás NULL** a un tipo de referencia que no acepta valores NULL con un contexto de anotación que acepta valores NULL habilitado.

## <a name="see-also"></a>Vea también

- [Borrador de especificación de tipos de referencia que aceptan valores NULL](~/_csharplang/proposals/csharp-8.0/nullable-reference-types-specification.md)
- [Tutorial de introducción a las referencias que no aceptan valores NULL](tutorials/nullable-reference-types.md)
- [Migración de un código base existente a referencias que aceptan valores NULL](tutorials/upgrade-to-nullable-references.md)
