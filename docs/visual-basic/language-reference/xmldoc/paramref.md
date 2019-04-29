---
title: <paramref> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- paramref XML tag
- <paramref> XML tag
ms.assetid: 8979d53b-beb1-41b7-b41e-6bbea1c17a03
ms.openlocfilehash: 3e2bf7990343a325bbecc56f6d3754a77f1e08e2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61940847"
---
# <a name="paramref-visual-basic"></a><span data-ttu-id="b5d71-102">\<paramref > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b5d71-102">\<paramref> (Visual Basic)</span></span>
<span data-ttu-id="b5d71-103">Da formato a una palabra como un parámetro.</span><span class="sxs-lookup"><span data-stu-id="b5d71-103">Formats a word as a parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5d71-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b5d71-104">Syntax</span></span>  
  
```xml  
<paramref name="name"/>  
```  
  
## <a name="parameters"></a><span data-ttu-id="b5d71-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b5d71-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="b5d71-106">Nombre del parámetro al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="b5d71-106">The name of the parameter to refer to.</span></span> <span data-ttu-id="b5d71-107">Ponga el nombre entre comillas dobles (" ").</span><span class="sxs-lookup"><span data-stu-id="b5d71-107">Enclose the name in double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b5d71-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b5d71-108">Remarks</span></span>  
 <span data-ttu-id="b5d71-109">El `<paramref>` etiqueta ofrece una manera de indicar que una palabra es un parámetro.</span><span class="sxs-lookup"><span data-stu-id="b5d71-109">The `<paramref>` tag gives you a way to indicate that a word is a parameter.</span></span> <span data-ttu-id="b5d71-110">El archivo XML se puede procesar para dar formato a este parámetro de alguna manera distinta.</span><span class="sxs-lookup"><span data-stu-id="b5d71-110">The XML file can be processed to format this parameter in some distinct way.</span></span>  
  
 <span data-ttu-id="b5d71-111">Compile con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación a un archivo.</span><span class="sxs-lookup"><span data-stu-id="b5d71-111">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b5d71-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b5d71-112">Example</span></span>  
 <span data-ttu-id="b5d71-113">Este ejemplo se usa el `<paramref>` etiqueta para hacer referencia a la `id` parámetro.</span><span class="sxs-lookup"><span data-stu-id="b5d71-113">This example uses the `<paramref>` tag to refer to the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="b5d71-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="b5d71-114">See also</span></span>

- [<span data-ttu-id="b5d71-115">Etiquetas XML para comentarios</span><span class="sxs-lookup"><span data-stu-id="b5d71-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
