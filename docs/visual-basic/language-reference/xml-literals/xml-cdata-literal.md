---
title: Literal de CDATA XML (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralCdata
helpviewer_keywords:
- CDATA literal [Visual Basic]
- XML CDATA literal [Visual Basic]
- XML literals [Visual Basic], CDATA
ms.assetid: 9eafb6a4-dd9d-4866-85e8-0654c65abc44
ms.openlocfilehash: 889ec7f93d0503edac51652dda217c6a9f654f9b
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64621435"
---
# <a name="xml-cdata-literal-visual-basic"></a><span data-ttu-id="1f26c-102">Literal de CDATA XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1f26c-102">XML CDATA Literal (Visual Basic)</span></span>
<span data-ttu-id="1f26c-103">Un literal que representa un <xref:System.Xml.Linq.XCData> objeto.</span><span class="sxs-lookup"><span data-stu-id="1f26c-103">A literal representing an <xref:System.Xml.Linq.XCData> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f26c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1f26c-104">Syntax</span></span>  
  
```xml  
<![CDATA[content]]>  
```  
  
## <a name="parts"></a><span data-ttu-id="1f26c-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="1f26c-105">Parts</span></span>  
 `<![CDATA[`  
 <span data-ttu-id="1f26c-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="1f26c-106">Required.</span></span> <span data-ttu-id="1f26c-107">Denota el inicio de la sección XML CDATA.</span><span class="sxs-lookup"><span data-stu-id="1f26c-107">Denotes the start of the XML CDATA section.</span></span>  
  
 `content`  
 <span data-ttu-id="1f26c-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="1f26c-108">Required.</span></span> <span data-ttu-id="1f26c-109">Contenido de texto que aparezca en la sección XML CDATA.</span><span class="sxs-lookup"><span data-stu-id="1f26c-109">Text content to appear in the XML CDATA section.</span></span>  
  
 `]]>`  
 <span data-ttu-id="1f26c-110">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="1f26c-110">Required.</span></span> <span data-ttu-id="1f26c-111">Denota el final de la sección.</span><span class="sxs-lookup"><span data-stu-id="1f26c-111">Denotes the end of the section.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1f26c-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1f26c-112">Return Value</span></span>  
 <span data-ttu-id="1f26c-113">Un objeto <xref:System.Xml.Linq.XCData>.</span><span class="sxs-lookup"><span data-stu-id="1f26c-113">An <xref:System.Xml.Linq.XCData> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1f26c-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1f26c-114">Remarks</span></span>  
 <span data-ttu-id="1f26c-115">Secciones de CDATA XML contienen texto sin formato que debe incluir, pero no puede analizar, con el XML que lo contiene.</span><span class="sxs-lookup"><span data-stu-id="1f26c-115">XML CDATA sections contain raw text that should be included, but not parsed, with the XML that contains it.</span></span> <span data-ttu-id="1f26c-116">Una sección CDATA XML puede contener cualquier texto.</span><span class="sxs-lookup"><span data-stu-id="1f26c-116">A XML CDATA section can contain any text.</span></span> <span data-ttu-id="1f26c-117">Esto incluye los caracteres XML reservados.</span><span class="sxs-lookup"><span data-stu-id="1f26c-117">This includes reserved XML characters.</span></span> <span data-ttu-id="1f26c-118">La sección CDATA XML finaliza con la secuencia "]] >".</span><span class="sxs-lookup"><span data-stu-id="1f26c-118">The XML CDATA section ends with the sequence "]]>".</span></span> <span data-ttu-id="1f26c-119">Esto implica los siguientes puntos:</span><span class="sxs-lookup"><span data-stu-id="1f26c-119">This implies the following points:</span></span>  
  
- <span data-ttu-id="1f26c-120">No se puede usar una expresión incrustada en un literal de CDATA XML porque los delimitadores de expresión incrustada son contenido de CDATA XML válido.</span><span class="sxs-lookup"><span data-stu-id="1f26c-120">You cannot use an embedded expression in an XML CDATA literal because the embedded expression delimiters are valid XML CDATA content.</span></span>  
  
- <span data-ttu-id="1f26c-121">No se puede anidar las secciones de CDATA XML porque `content` no puede contener el valor "]] >".</span><span class="sxs-lookup"><span data-stu-id="1f26c-121">XML CDATA sections cannot be nested, because `content` cannot contain the value "]]>".</span></span>  
  
 <span data-ttu-id="1f26c-122">Puede asignar un literal de CDATA XML a una variable o incluirlo en un literal de elemento XML.</span><span class="sxs-lookup"><span data-stu-id="1f26c-122">You can assign an XML CDATA literal to a variable, or include it in an XML element literal.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1f26c-123">Un literal XML puede abarcar varias líneas, pero no usa caracteres de continuación de línea.</span><span class="sxs-lookup"><span data-stu-id="1f26c-123">An XML literal can span multiple lines but does not use line continuation characters.</span></span> <span data-ttu-id="1f26c-124">Esto permite copiar el contenido de un documento XML y péguelo directamente en un programa de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="1f26c-124">This enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>  
  
 <span data-ttu-id="1f26c-125">El compilador de Visual Basic convierte el literal de CDATA XML a una llamada a la <xref:System.Xml.Linq.XCData.%23ctor%2A> constructor.</span><span class="sxs-lookup"><span data-stu-id="1f26c-125">The Visual Basic compiler converts the XML CDATA literal to a call to the <xref:System.Xml.Linq.XCData.%23ctor%2A> constructor.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1f26c-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1f26c-126">Example</span></span>  
 <span data-ttu-id="1f26c-127">En el ejemplo siguiente se crea una sección CDATA que contiene el texto "puede contener literal \<XML > etiquetas".</span><span class="sxs-lookup"><span data-stu-id="1f26c-127">The following example creates a CDATA section that contains the text "Can contain literal \<XML> tags".</span></span>  
  
 [!code-vb[VbXMLSamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples11.vb#23)]  
  
## <a name="see-also"></a><span data-ttu-id="1f26c-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="1f26c-128">See also</span></span>

- <xref:System.Xml.Linq.XCData>
- [<span data-ttu-id="1f26c-129">Literal de elemento XML</span><span class="sxs-lookup"><span data-stu-id="1f26c-129">XML Element Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [<span data-ttu-id="1f26c-130">Literales XML</span><span class="sxs-lookup"><span data-stu-id="1f26c-130">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="1f26c-131">Crear XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1f26c-131">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
