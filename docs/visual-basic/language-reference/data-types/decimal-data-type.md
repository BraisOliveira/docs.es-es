---
title: Decimal (Tipo de datos, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Decimal
helpviewer_keywords:
- literal type characters [Visual Basic], D
- trailing zeros
- real numbers
- trailing 0 characters [Visual Basic]
- Decimal data type
- D literal type character [Visual Basic]
- decimals, Decimal data type
- 0 characters [Visual Basic], trailing
- data types [Visual Basic], assigning
- decimal keyword [Visual Basic]
- numbers [Visual Basic], real
- variable-precision numbers
- zeros, trailing
- '@ identifier type character'
- identifier type characters [Visual Basic], @
ms.assetid: 1d855b45-afe2-45b0-a623-96b6f63a43d5
ms.openlocfilehash: 892824b61cfb6a0172361d220c638cab0a78565d
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700877"
---
# <a name="decimal-data-type-visual-basic"></a>Decimal (Tipo de datos, Visual Basic)

Contiene valores con signo de 128 bits (16 bytes) que representan números enteros de 96 bits (12 bytes) escalados por una potencia variable de 10. El factor de escala especifica el número de dígitos a la derecha del separador decimal; está comprendido entre 0 y 28. Con una escala de 0 (sin posiciones decimales), el mayor valor posible es +/-79.228.162.514.264.337.593.543.950.335 (+/-7.9228162514264337593543950335E + 28). Con 28 posiciones decimales, el valor más grande es +/-7,9228162514264337593543950335 y el menor valor distinto de cero es +/-0,0000000000000000000000000001 (+/-1E-28).

## <a name="remarks"></a>Comentarios

El tipo de datos `Decimal` proporciona el mayor número de dígitos significativos para un número. Admite hasta 29 dígitos significativos y puede representar valores que superan los 7,9228 x 10 ^ 28. Es especialmente adecuado para los cálculos, como finanzas, que requieren un gran número de dígitos, pero no pueden tolerar errores de redondeo.

El valor predeterminado de `Decimal` es 0.

## <a name="programming-tips"></a>Sugerencias de programación

- **Precisión.** `Decimal` no es un tipo de datos de punto flotante. La estructura `Decimal` contiene un valor entero binario, junto con un bit de signo y un factor de escala entero que especifica qué parte del valor es una fracción decimal. Por este motivo, los números `Decimal` tienen una representación más precisa en la memoria que los tipos de punto flotante (`Single` y `Double`).

- **Rendimiento.** El tipo de datos `Decimal` es el más lento de todos los tipos numéricos. Debe sopesar la importancia de la precisión respecto al rendimiento antes de elegir un tipo de datos.

- **Ampliación.** El tipo de datos `Decimal` se amplía a `Single` o `Double`. Esto significa que puede convertir `Decimal` en cualquiera de estos tipos sin encontrar un error <xref:System.OverflowException?displayProperty=nameWithType>.

- **Ceros a la derecha.** Visual Basic no almacena los ceros finales en un literal @no__t 0. Sin embargo, una variable `Decimal` conserva los ceros finales adquiridos de cálculo. Esto se ilustra en el siguiente ejemplo:

  ```vb
  Dim d1, d2, d3, d4 As Decimal
  d1 = 2.375D
  d2 = 1.625D
  d3 = d1 + d2
  d4 = 4.000D
  MsgBox("d1 = " & CStr(d1) & ", d2 = " & CStr(d2) &
        ", d3 = " & CStr(d3) & ", d4 = " & CStr(d4))
  ```

  La salida de `MsgBox` en el ejemplo anterior es la siguiente:

  ```console
  d1 = 2.375, d2 = 1.625, d3 = 4.000, d4 = 4
  ```

- **Caracteres de tipo.** Al agregar el carácter de tipo literal `D` a un literal, el tipo de datos se convierte forzosamente en el tipo de datos `Decimal`. Si se agrega el carácter de tipo identificador `@` a cualquier identificador, se convierte forzosamente al tipo `Decimal`.

- **Tipo de marco.** El tipo correspondiente en .NET Framework es la estructura <xref:System.Decimal?displayProperty=nameWithType>.

## <a name="range"></a>Intervalo
 Es posible que tenga que usar el carácter de tipo `D` para asignar un valor grande a una variable o constante `Decimal`. Este requisito se debe a que el compilador interpreta un literal como `Long` a menos que un carácter de tipo literal siga el literal, como se muestra en el ejemplo siguiente.

```vb
Dim bigDec1 As Decimal = 9223372036854775807   ' No overflow.
Dim bigDec2 As Decimal = 9223372036854775808   ' Overflow.
Dim bigDec3 As Decimal = 9223372036854775808D  ' No overflow.
```

La declaración de `bigDec1` no produce un desbordamiento porque el valor asignado a él está dentro del intervalo de `Long`. El valor `Long` se puede asignar a la variable `Decimal`.

La declaración de `bigDec2` genera un error de desbordamiento porque el valor asignado a él es demasiado grande para `Long`. Dado que el literal numérico no se puede interpretar primero como `Long`, no se puede asignar a la variable `Decimal`.

En el caso de `bigDec3`, el carácter de tipo literal `D` resuelve el problema obligando al compilador a interpretar el literal como `Decimal` en lugar de como `Long`.

## <a name="see-also"></a>Vea también

- <xref:System.Decimal?displayProperty=nameWithType>
- <xref:System.Decimal.%23ctor%2A?displayProperty=nameWithType>
- <xref:System.Math.Round%2A?displayProperty=nameWithType>
- [Tipos de datos](../../../visual-basic/language-reference/data-types/index.md)
- [Single (tipo de datos)](../../../visual-basic/language-reference/data-types/single-data-type.md)
- [Double (tipos de datos)](../../../visual-basic/language-reference/data-types/double-data-type.md)
- [Funciones de conversión de tipos](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Resumen de conversión](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Uso eficiente de tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
