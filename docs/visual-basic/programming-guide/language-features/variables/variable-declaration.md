---
title: Declaración de variable en Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], declaring
- member variables [Visual Basic], declarations
- Dim statement [Visual Basic], variable declaration
- declaring variables [Visual Basic]
- variables [Visual Basic], scope
- variables [Visual Basic], data types
- data types [Visual Basic], variable declarations
- lifetime [Visual Basic], variables
- variables [Visual Basic], lifetime
- access levels [Visual Basic], variables
- scope [Visual Basic], declaration statements
- variables [Visual Basic], access level
- local variables [Visual Basic], declarations
- scope [Visual Basic], variables
ms.assetid: d8f10226-92b1-480f-9f53-df377b2d7e15
ms.openlocfilehash: 726347efc2e12100f7d89348a316037babc785e5
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2019
ms.locfileid: "72003304"
---
# <a name="variable-declaration-in-visual-basic"></a>Declaración de variable en Visual Basic
Declare una variable para especificar su nombre y sus características. La instrucción de declaración para variables es la [instrucción Dim](../../../../visual-basic/language-reference/statements/dim-statement.md). Su ubicación y contenido determinan las características de la variable.  
  
 Para conocer las reglas y consideraciones de nomenclatura de variables, vea [nombres de elementos declarados](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
## <a name="declaration-levels"></a>Niveles de declaración  
  
### <a name="local-and-member-variables"></a>Variables locales y de miembro  
 Una *variable local* es aquella que se declara dentro de un procedimiento. Una *variable miembro* es miembro de un tipo de Visual Basic; se declara en el nivel de módulo, dentro de una clase, estructura o módulo, pero no dentro de ningún procedimiento interno de esa clase, estructura o módulo.  
  
### <a name="shared-and-instance-variables"></a>Variables compartidas y de instancia  
 En una clase o estructura, la categoría de una variable miembro depende de si es o no compartida. Si se declara con la palabra clave [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) , es una *variable compartida*y existe en una sola copia compartida entre todas las instancias de la clase o estructura.  
  
 En caso contrario, es una *variable de instancia*y se crea una copia independiente de la misma para cada instancia de la clase o estructura. Una copia determinada de una variable de instancia solo está disponible para la instancia de la clase o estructura en la que se creó. Es independiente de una copia de la variable de instancia en cualquier otra instancia de la clase o estructura.  
  
## <a name="declaring-data-type"></a>Declarar el tipo de datos  
 La cláusula [as](../../../../visual-basic/language-reference/statements/as-clause.md) de la instrucción de declaración permite definir el tipo de datos o el tipo de objeto de la variable que se está declarando. Puede especificar cualquiera de los siguientes tipos para una variable:  
  
- Un tipo de datos elemental, como `Boolean`, `Long` o `Decimal`  
  
- Un tipo de datos compuesto, como una matriz o una estructura  
  
- Un tipo de objeto, o clase, definido en la aplicación o en otra aplicación  
  
- Una clase .NET Framework, como <xref:System.Windows.Forms.Label> o <xref:System.Windows.Forms.TextBox>  
  
- Un tipo de interfaz, como <xref:System.IComparable> o <xref:System.IDisposable>  
  
 Puede declarar varias variables en una instrucción sin tener que repetir el tipo de datos. En las siguientes instrucciones, las variables `i`, `j` y `k` se declaran como tipo `Integer`, `l` y `m` como `Long`, y `x` y `y` como `Single`:  
  
```vb  
Dim i, j, k As Integer  
' All three variables in the preceding statement are declared as Integer.  
Dim l, m As Long, x, y As Single  
' In the preceding statement, l and m are Long, x and y are Single.  
```  
  
 Para obtener más información sobre los tipos de datos, vea [tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/index.md). Para obtener más información sobre los objetos, vea [objetos y clases](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) y [programación con componentes](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/0ffkdtkf(v=vs.120)).  
  
## <a name="local-type-inference"></a>Inferencia de tipo de variable local  
 La *inferencia de tipos* se usa para determinar los tipos de datos de las variables locales declaradas sin una cláusula `As`. El compilador deduce el tipo de la variable a partir del tipo de la expresión de inicialización. Esto le permite declarar variables sin indicar explícitamente un tipo. En el ejemplo siguiente, `num1` y `num2` están fuertemente tipados como enteros.  
  
 [!code-vb[VbVbalrTypeInference#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#1)]  
  
 Si desea utilizar la inferencia de tipo local, `Option Infer` debe establecerse en `On`. Para obtener más información, vea [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) (Inferencia de tipo de variable local) y [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md) (Instrucción Option Infer).  
  
## <a name="characteristics-of-declared-variables"></a>Características de las variables declaradas  
 La *duración* de una variable es el período de tiempo durante el cual está disponible para su uso. En general, existe una variable siempre que el elemento que la declara (por ejemplo, un procedimiento o una clase) sigue existiendo. Si la variable no necesita continuar ya existente más allá de la duración de su elemento contenedor, no es necesario hacer nada especial en la declaración. Si la variable debe seguir existiendo más tiempo que su elemento contenedor, puede incluir la palabra clave `Static` o `Shared` en su instrucción `Dim`. Para obtener más información, vea [duración en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md).  
  
 El *ámbito* de una variable es el conjunto de todo el código que puede hacer referencia a él sin calificar su nombre. El ámbito de una variable lo determina el lugar en el que se declara. El código ubicado en una región determinada puede usar las variables definidas en esa región sin tener que calificar sus nombres. Para obtener más información, consulta [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md).  
  
 El nivel de *acceso* de una variable es la extensión del código que tiene permiso de acceso. Esto viene determinado por el modificador de acceso (por ejemplo, [público](../../../../visual-basic/language-reference/modifiers/public.md) o [privado](../../../../visual-basic/language-reference/modifiers/private.md)) que se usa en la instrucción `Dim`. Para obtener más información, consulte [niveles de acceso en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## <a name="see-also"></a>Vea también

- [Cómo: Cree una nueva variable @ no__t-0
- [Cómo: Movimiento de datos dentro y fuera de una variable @ no__t-0
- [Tipos de datos](../../../../visual-basic/language-reference/data-types/index.md)
- [Protected](../../../../visual-basic/language-reference/modifiers/protected.md)
- [Friend](../../../../visual-basic/language-reference/modifiers/friend.md)
- [Static](../../../../visual-basic/language-reference/modifiers/static.md)
- [Características de los elementos declarados](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)
- [Inferencia de tipo de variable local](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Option Infer (instrucción)](../../../../visual-basic/language-reference/statements/option-infer-statement.md)
