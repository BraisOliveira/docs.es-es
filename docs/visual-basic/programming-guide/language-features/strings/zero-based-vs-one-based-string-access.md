---
title: Acceso a cadenas basado en cero Acceso basado en una cadena en Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], indexing
ms.assetid: 0ed39f35-d68e-421d-ae14-460a5c0373b8
ms.openlocfilehash: cc8f286de41d7e44225e889e73ff3c7b1fdbd881
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2019
ms.locfileid: "65591748"
---
# <a name="zero-based-vs-one-based-string-access-in-visual-basic"></a><span data-ttu-id="a60a5-102">Acceso a cadenas basado en cero Acceso basado en una cadena en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a60a5-102">Zero-based vs. One-based String Access in Visual Basic</span></span>
<span data-ttu-id="a60a5-103">Este tema compara cómo Visual Basic y .NET Framework proporcionan acceso a los caracteres de una cadena.</span><span class="sxs-lookup"><span data-stu-id="a60a5-103">This topic compares how Visual Basic and the .NET Framework provide access to the characters in a string.</span></span> <span data-ttu-id="a60a5-104">.NET Framework siempre proporciona acceso basado en cero para los caracteres en una cadena, mientras que Visual Basic proporciona acceso basado en cero y basado en uno, dependiendo de la función.</span><span class="sxs-lookup"><span data-stu-id="a60a5-104">The .NET Framework always provides zero-based access to the characters in a string, whereas Visual Basic provides zero-based and one-based access, depending on the function.</span></span>  
  
## <a name="one-based"></a><span data-ttu-id="a60a5-105">Basado en uno</span><span class="sxs-lookup"><span data-stu-id="a60a5-105">One-Based</span></span>  
 <span data-ttu-id="a60a5-106">Para obtener un ejemplo de una función de Visual Basic basado en uno, tenga en cuenta el `Mid` función.</span><span class="sxs-lookup"><span data-stu-id="a60a5-106">For an example of a one-based Visual Basic function, consider the `Mid` function.</span></span> <span data-ttu-id="a60a5-107">Toma un argumento que indica la posición del carácter en el que comenzará la subcadena, empezando por la posición 1.</span><span class="sxs-lookup"><span data-stu-id="a60a5-107">It takes an argument that indicates the character position at which the substring will start, starting with position 1.</span></span> <span data-ttu-id="a60a5-108">.NET Framework <xref:System.String.Substring%2A?displayProperty=nameWithType> método toma un índice del carácter en la cadena en la que la subcadena se va a comenzar, empezando por la posición 0.</span><span class="sxs-lookup"><span data-stu-id="a60a5-108">The .NET Framework <xref:System.String.Substring%2A?displayProperty=nameWithType> method takes an index of the character in the string at which the substring is to start, starting with position 0.</span></span> <span data-ttu-id="a60a5-109">Por lo tanto, si tiene una cadena "ABCDE", los caracteres individuales se numeran 1,2,3,4,5 para su uso con el `Mid` función, pero 0,1,2,3,4 para su uso con el <xref:System.String.Substring%2A?displayProperty=nameWithType> método.</span><span class="sxs-lookup"><span data-stu-id="a60a5-109">Thus, if you have a string "ABCDE", the individual characters are numbered 1,2,3,4,5 for use with the `Mid` function, but 0,1,2,3,4 for use with the <xref:System.String.Substring%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="zero-based"></a><span data-ttu-id="a60a5-110">Basado en cero</span><span class="sxs-lookup"><span data-stu-id="a60a5-110">Zero-Based</span></span>  
 <span data-ttu-id="a60a5-111">Para obtener un ejemplo de una función de Visual Basic basado en cero, considere la `Split` función.</span><span class="sxs-lookup"><span data-stu-id="a60a5-111">For an example of a zero-based Visual Basic function, consider the `Split` function.</span></span> <span data-ttu-id="a60a5-112">Divide una cadena y devuelve una matriz que contiene las subcadenas.</span><span class="sxs-lookup"><span data-stu-id="a60a5-112">It splits a string and returns an array containing the substrings.</span></span> <span data-ttu-id="a60a5-113">.NET Framework <xref:System.String.Split%2A?displayProperty=nameWithType> método también divide una cadena y devuelve una matriz que contiene las subcadenas.</span><span class="sxs-lookup"><span data-stu-id="a60a5-113">The .NET Framework <xref:System.String.Split%2A?displayProperty=nameWithType> method also splits a string and returns an array containing the substrings.</span></span> <span data-ttu-id="a60a5-114">Dado que el `Split` función y <xref:System.String.Split%2A> método devolver matrices de .NET Framework, deben ser basado en cero.</span><span class="sxs-lookup"><span data-stu-id="a60a5-114">Because the `Split` function and <xref:System.String.Split%2A> method return .NET Framework arrays, they must be zero-based.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a60a5-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="a60a5-115">See also</span></span>

- <xref:Microsoft.VisualBasic.Strings.Mid%2A>
- <xref:Microsoft.VisualBasic.Strings.Split%2A>
- <xref:System.String.Substring%2A>
- <xref:System.String.Split%2A>
- [<span data-ttu-id="a60a5-116">Introducción a las cadenas en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a60a5-116">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
