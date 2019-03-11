---
title: '<see>: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- <see>
- see
helpviewer_keywords:
- cref [C#], <see> tag
- <see> C# XML tag
- cross-references [C#]
- see C# XML tag
ms.assetid: 0200de01-7e2f-45c4-9094-829d61236383
ms.openlocfilehash: 90fd73346d255d195fa7384ebc2f60ebc4f32fba
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57480682"
---
# <a name="see-c-programming-guide"></a><span data-ttu-id="ce53b-102">\<see> (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="ce53b-102">\<see> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="ce53b-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ce53b-103">Syntax</span></span>  
  
```xml  
<see cref="member"/>  
```  
  
## <a name="parameters"></a><span data-ttu-id="ce53b-104">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ce53b-104">Parameters</span></span>  
 <span data-ttu-id="ce53b-105">cref = "`member`"</span><span class="sxs-lookup"><span data-stu-id="ce53b-105">cref = " `member`"</span></span>  
 <span data-ttu-id="ce53b-106">Referencia a un miembro o campo al cual se puede llamar desde el entorno de compilación actual.</span><span class="sxs-lookup"><span data-stu-id="ce53b-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="ce53b-107">El compilador comprueba si el elemento de código dado existe y pasa `member` al nombre de elemento en el resultado XML.</span><span class="sxs-lookup"><span data-stu-id="ce53b-107">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.</span></span> <span data-ttu-id="ce53b-108">Agregue *member* entre comillas dobles (" ").</span><span class="sxs-lookup"><span data-stu-id="ce53b-108">Place *member* within double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ce53b-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ce53b-109">Remarks</span></span>  
 <span data-ttu-id="ce53b-110">La etiqueta \<see> permite especificar un vínculo desde el texto.</span><span class="sxs-lookup"><span data-stu-id="ce53b-110">The \<see> tag lets you specify a link from within text.</span></span> <span data-ttu-id="ce53b-111">Use [\<seealso>](../../../csharp/programming-guide/xmldoc/seealso.md) para indicar que el texto debe colocarse en una sección Vea también.</span><span class="sxs-lookup"><span data-stu-id="ce53b-111">Use [\<seealso>](../../../csharp/programming-guide/xmldoc/seealso.md) to indicate that text should be placed in a See Also section.</span></span> <span data-ttu-id="ce53b-112">Use el [atributo cref](../../../csharp/programming-guide/xmldoc/cref-attribute.md) para crear hipervínculos internos a las páginas de documentación de los elementos de código.</span><span class="sxs-lookup"><span data-stu-id="ce53b-112">Use the [cref Attribute](../../../csharp/programming-guide/xmldoc/cref-attribute.md) to create internal hyperlinks to documentation pages for code elements.</span></span>  
  
 <span data-ttu-id="ce53b-113">Compile con [-doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación de un archivo.</span><span class="sxs-lookup"><span data-stu-id="ce53b-113">Compile with [-doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
 <span data-ttu-id="ce53b-114">En el ejemplo siguiente, se muestra una etiqueta \<see> dentro de una sección de resumen.</span><span class="sxs-lookup"><span data-stu-id="ce53b-114">The following example shows a \<see> tag within a summary section.</span></span>  
  
 [!code-csharp[csProgGuideDocComments#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#12)]  
  
## <a name="see-also"></a><span data-ttu-id="ce53b-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="ce53b-115">See also</span></span>

- [<span data-ttu-id="ce53b-116">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="ce53b-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="ce53b-117">Etiquetas recomendadas para los comentarios de documentación</span><span class="sxs-lookup"><span data-stu-id="ce53b-117">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
