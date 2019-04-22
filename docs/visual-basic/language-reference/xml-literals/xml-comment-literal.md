---
title: Literal de comentario XML (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralComment
helpviewer_keywords:
- comment literal [Visual Basic]
- XML comments, adding [Visual Basic]
- XML comment literal [Visual Basic]
- XML literals [Visual Basic], comment
ms.assetid: 634c1cee-5e01-48d0-88d7-2dd55e4a9e52
ms.openlocfilehash: 149bbac6d301a9c2f166d05698e3780171126cb3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58827281"
---
# <a name="xml-comment-literal-visual-basic"></a><span data-ttu-id="b8d41-102">Literal de comentario XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b8d41-102">XML Comment Literal (Visual Basic)</span></span>
<span data-ttu-id="b8d41-103">Un literal que representa un <xref:System.Xml.Linq.XComment> objeto.</span><span class="sxs-lookup"><span data-stu-id="b8d41-103">A literal representing an <xref:System.Xml.Linq.XComment> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8d41-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b8d41-104">Syntax</span></span>  
  
```xml  
<!-- content -->  
```  
  
## <a name="parts"></a><span data-ttu-id="b8d41-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="b8d41-105">Parts</span></span>  
  
|<span data-ttu-id="b8d41-106">Término</span><span class="sxs-lookup"><span data-stu-id="b8d41-106">Term</span></span>|<span data-ttu-id="b8d41-107">Definición</span><span class="sxs-lookup"><span data-stu-id="b8d41-107">Definition</span></span>|  
|---|---|  
|`<!--`|<span data-ttu-id="b8d41-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="b8d41-108">Required.</span></span> <span data-ttu-id="b8d41-109">Denota el inicio del comentario XML.</span><span class="sxs-lookup"><span data-stu-id="b8d41-109">Denotes the start of the XML comment.</span></span>|  
|`content`|<span data-ttu-id="b8d41-110">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="b8d41-110">Required.</span></span> <span data-ttu-id="b8d41-111">Texto que aparecerá en el comentario XML.</span><span class="sxs-lookup"><span data-stu-id="b8d41-111">Text to appear in the XML comment.</span></span> <span data-ttu-id="b8d41-112">No puede contener una serie de dos guiones (-) ni terminar con un guión adyacente a la etiqueta de cierre.</span><span class="sxs-lookup"><span data-stu-id="b8d41-112">Cannot contain a series of two hyphens (--) or end with a hyphen adjacent to the closing tag.</span></span>|  
|`-->`|<span data-ttu-id="b8d41-113">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="b8d41-113">Required.</span></span> <span data-ttu-id="b8d41-114">Denota el final del comentario XML.</span><span class="sxs-lookup"><span data-stu-id="b8d41-114">Denotes the end of the XML comment.</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="b8d41-115">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b8d41-115">Return Value</span></span>  
 <span data-ttu-id="b8d41-116">Un objeto <xref:System.Xml.Linq.XComment>.</span><span class="sxs-lookup"><span data-stu-id="b8d41-116">An <xref:System.Xml.Linq.XComment> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b8d41-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b8d41-117">Remarks</span></span>  
 <span data-ttu-id="b8d41-118">Los literales de comentario XML no contienen el contenido del documento; que contienen información sobre el documento.</span><span class="sxs-lookup"><span data-stu-id="b8d41-118">XML comment literals do not contain document content; they contain information about the document.</span></span> <span data-ttu-id="b8d41-119">La sección de comentarios XML finaliza con la secuencia "-->".</span><span class="sxs-lookup"><span data-stu-id="b8d41-119">The XML comment section ends with the sequence "-->".</span></span> <span data-ttu-id="b8d41-120">Esto implica los siguientes puntos:</span><span class="sxs-lookup"><span data-stu-id="b8d41-120">This implies the following points:</span></span>  
  
-   <span data-ttu-id="b8d41-121">No se puede usar una expresión incrustada en un literal de comentario XML porque los delimitadores de expresión incrustada son contenido de comentario XML válido.</span><span class="sxs-lookup"><span data-stu-id="b8d41-121">You cannot use an embedded expression in an XML comment literal because the embedded expression delimiters are valid XML comment content.</span></span>  
  
-   <span data-ttu-id="b8d41-122">Las secciones de comentario XML no se pueden anidar, porque `content` no puede contener el valor "-->".</span><span class="sxs-lookup"><span data-stu-id="b8d41-122">XML comment sections cannot be nested, because `content` cannot contain the value "-->".</span></span>  
  
 <span data-ttu-id="b8d41-123">Puede asignar un literal de comentario XML a una variable o incluirlo en un literal de elemento XML.</span><span class="sxs-lookup"><span data-stu-id="b8d41-123">You can assign an XML comment literal to a variable, or you can include it in an XML element literal.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b8d41-124">Un literal XML puede abarcar varias líneas sin usar caracteres de continuación de línea.</span><span class="sxs-lookup"><span data-stu-id="b8d41-124">An XML literal can span multiple lines without using line continuation characters.</span></span> <span data-ttu-id="b8d41-125">Esta característica le permite copiar el contenido de un documento XML y péguelo directamente en un programa de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="b8d41-125">This feature enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>  
  
 <span data-ttu-id="b8d41-126">El compilador de Visual Basic convierte el literal de comentario XML en una llamada a la <xref:System.Xml.Linq.XComment.%23ctor%2A> constructor.</span><span class="sxs-lookup"><span data-stu-id="b8d41-126">The Visual Basic compiler converts the XML comment literal to a call to the <xref:System.Xml.Linq.XComment.%23ctor%2A> constructor.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b8d41-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b8d41-127">Example</span></span>  
 <span data-ttu-id="b8d41-128">El ejemplo siguiente crea un comentario XML que contiene el texto "Este es un comentario".</span><span class="sxs-lookup"><span data-stu-id="b8d41-128">The following example creates an XML comment that contains the text "This is a comment".</span></span>  
  
 [!code-vb[VbXMLSamples#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples4.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="b8d41-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="b8d41-129">See also</span></span>

- <xref:System.Xml.Linq.XComment>
- [<span data-ttu-id="b8d41-130">Literal de elemento XML</span><span class="sxs-lookup"><span data-stu-id="b8d41-130">XML Element Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [<span data-ttu-id="b8d41-131">Literales XML</span><span class="sxs-lookup"><span data-stu-id="b8d41-131">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="b8d41-132">Crear XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b8d41-132">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
