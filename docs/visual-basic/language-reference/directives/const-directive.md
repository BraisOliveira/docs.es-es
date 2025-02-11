---
title: '#Const (Directiva) (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.#Const
- '#vb.Const'
- '#Const'
helpviewer_keywords:
- '#Const directive'
- conditional compilation [Visual Basic], directives
- Const directive (#Const)
- Visual Basic compiler, compiler directives
- constants [Visual Basic], Const directive
- constants [Visual Basic], declaring
- Const statement [Visual Basic], directive (#Const)
- 'declaring constants [Visual Basic], #const directive'
ms.assetid: 707669e5-23f9-4f17-8622-a0d534429386
ms.openlocfilehash: 031f35df24fd52aeeafcb7b4c0208806d7fc5fc4
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2019
ms.locfileid: "72774754"
---
# <a name="const-directive"></a>#Const (Directiva)
Define constantes de compilador condicionales para Visual Basic.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
#Const constname = expression  
```  
  
## <a name="parts"></a>Elementos  
 `constname`  
 Requerido. Nombre de la constante que se está definiendo.  
  
 `expression`  
 Requerido. Literal, otra constante del compilador condicional o cualquier combinación que incluya todos o todos los operadores aritméticos o lógicos excepto `Is`.  
  
## <a name="remarks"></a>Comentarios  
 Las constantes de compilador condicionales siempre son privadas en el archivo en el que aparecen. No se pueden crear constantes del compilador públicas mediante la Directiva `#Const`; solo puede crearlos en la interfaz de usuario o con la opción del compilador `/define`.  
  
 Solo se pueden usar constantes y literales de compilador condicionales en `expression`. El uso de una constante estándar definida con `Const` produce un error. Por el contrario, puede usar constantes definidas con la palabra clave `#Const` solo para la compilación condicional. Las constantes también pueden ser undefined, en cuyo caso tienen un valor de `Nothing`.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se usa la directiva `#Const`.  
  
 [!code-vb[VbVbalrConditionalComp#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#3)]  
  
## <a name="see-also"></a>Vea también

- [-define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md)
- [#If...Then...#Else (directivas)](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [Const (instrucción)](../../../visual-basic/language-reference/statements/const-statement.md)
- [Compilación condicional](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- [If...Then...Else (instrucción)](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
