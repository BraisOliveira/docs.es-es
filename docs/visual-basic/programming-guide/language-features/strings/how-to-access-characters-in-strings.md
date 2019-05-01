---
title: Procedimiento Acceso a caracteres en cadenas en Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], accessing characters
- characters [Visual Basic], accessing in strings
ms.assetid: 02c5206c-ffab-494d-b648-3b2ea358dc34
ms.openlocfilehash: 840a769b0bb322ef7b878a312437c5ec200ab074
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62054035"
---
# <a name="how-to-access-characters-in-strings-in-visual-basic"></a><span data-ttu-id="c308b-102">Procedimiento Acceso a caracteres en cadenas en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c308b-102">How to: Access Characters in Strings in Visual Basic</span></span>
<span data-ttu-id="c308b-103">Este ejemplo muestra cómo usar el <xref:System.String.Chars%2A> propiedad para tener acceso el carácter que ocupa la posición especificada en una cadena.</span><span class="sxs-lookup"><span data-stu-id="c308b-103">This example demonstrates how to use the <xref:System.String.Chars%2A> property to access the character at the specified location in a string.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c308b-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c308b-104">Example</span></span>  
 <span data-ttu-id="c308b-105">A veces resulta útil tener información sobre los caracteres de la cadena y las posiciones de los caracteres dentro de la cadena.</span><span class="sxs-lookup"><span data-stu-id="c308b-105">Sometimes it is useful to have data about the characters in your string and the positions of those characters within your string.</span></span> <span data-ttu-id="c308b-106">Puede pensar en una cadena como una matriz de caracteres (`Char` instancias); puede recuperar un carácter concreto haciendo referencia al índice de dicho carácter a través de la <xref:System.String.Chars%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="c308b-106">You can think of a string as an array of characters (`Char` instances); you can retrieve a particular character by referencing the index of that character through the <xref:System.String.Chars%2A> property.</span></span>  
  
 [!code-vb[VbVbalrStrings#49](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#49)]  
  
 <span data-ttu-id="c308b-107">El `index` parámetro de la <xref:System.String.Chars%2A> propiedad está basado en cero.</span><span class="sxs-lookup"><span data-stu-id="c308b-107">The `index` parameter of the <xref:System.String.Chars%2A> property is zero-based.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="c308b-108">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="c308b-108">Robust Programming</span></span>  
 <span data-ttu-id="c308b-109">El <xref:System.String.Chars%2A> propiedad devuelve el carácter que ocupa la posición especificada.</span><span class="sxs-lookup"><span data-stu-id="c308b-109">The <xref:System.String.Chars%2A> property returns the character at the specified position.</span></span> <span data-ttu-id="c308b-110">Sin embargo, algunos caracteres Unicode pueden representarse mediante más de un carácter.</span><span class="sxs-lookup"><span data-stu-id="c308b-110">However, some Unicode characters can be represented by more than one character.</span></span> <span data-ttu-id="c308b-111">Para obtener más información sobre cómo trabajar con caracteres Unicode, vea [Cómo: Convertir una cadena en una matriz de caracteres](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md).</span><span class="sxs-lookup"><span data-stu-id="c308b-111">For more information on how to work with Unicode characters, see [How to: Convert a String to an Array of Characters](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md).</span></span>  
  
 <span data-ttu-id="c308b-112">El <xref:System.String.Chars%2A> propiedad produce una <xref:System.IndexOutOfRangeException> excepción si el `index` parámetro es mayor o igual que la longitud de la cadena, o si es menor que cero</span><span class="sxs-lookup"><span data-stu-id="c308b-112">The <xref:System.String.Chars%2A> property throws an <xref:System.IndexOutOfRangeException> exception if the `index` parameter is greater than or equal to the length of the string, or if it is less than zero</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c308b-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="c308b-113">See also</span></span>

- <xref:System.String.Chars%2A>
- [<span data-ttu-id="c308b-114">Cómo: Convertir una cadena en una matriz de caracteres</span><span class="sxs-lookup"><span data-stu-id="c308b-114">How to: Convert a String to an Array of Characters</span></span>](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md)
- [<span data-ttu-id="c308b-115">Conversión entre cadenas y otros tipos de datos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c308b-115">Converting Between Strings and Other Data Types in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/converting-between-strings-and-other-data-types.md)
- [<span data-ttu-id="c308b-116">Cadenas</span><span class="sxs-lookup"><span data-stu-id="c308b-116">Strings</span></span>](../../../../visual-basic/programming-guide/language-features/strings/index.md)
