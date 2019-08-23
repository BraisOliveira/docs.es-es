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
ms.openlocfilehash: 248f3cf31f686de3af2ea06012aa4a6d4f3f29fc
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942920"
---
# <a name="xml-cdata-literal-visual-basic"></a><span data-ttu-id="c1fa2-102">Literal de CDATA XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c1fa2-102">XML CDATA Literal (Visual Basic)</span></span>
<span data-ttu-id="c1fa2-103">Literal que representa un <xref:System.Xml.Linq.XCData> objeto.</span><span class="sxs-lookup"><span data-stu-id="c1fa2-103">A literal representing an <xref:System.Xml.Linq.XCData> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1fa2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c1fa2-104">Syntax</span></span>  
  
```xml  
<![CDATA[content]]>  
```  
  
## <a name="parts"></a><span data-ttu-id="c1fa2-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="c1fa2-105">Parts</span></span>  
 `<![CDATA[`  
 <span data-ttu-id="c1fa2-106">Necesario.</span><span class="sxs-lookup"><span data-stu-id="c1fa2-106">Required.</span></span> <span data-ttu-id="c1fa2-107">Denota el inicio de la sección XML CDATA.</span><span class="sxs-lookup"><span data-stu-id="c1fa2-107">Denotes the start of the XML CDATA section.</span></span>  
  
 `content`  
 <span data-ttu-id="c1fa2-108">Necesario.</span><span class="sxs-lookup"><span data-stu-id="c1fa2-108">Required.</span></span> <span data-ttu-id="c1fa2-109">Contenido de texto para que aparezca en la sección XML CDATA.</span><span class="sxs-lookup"><span data-stu-id="c1fa2-109">Text content to appear in the XML CDATA section.</span></span>  
  
 `]]>`  
 <span data-ttu-id="c1fa2-110">Necesario.</span><span class="sxs-lookup"><span data-stu-id="c1fa2-110">Required.</span></span> <span data-ttu-id="c1fa2-111">Denota el final de la sección.</span><span class="sxs-lookup"><span data-stu-id="c1fa2-111">Denotes the end of the section.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c1fa2-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c1fa2-112">Return Value</span></span>  
 <span data-ttu-id="c1fa2-113">Un objeto <xref:System.Xml.Linq.XCData>.</span><span class="sxs-lookup"><span data-stu-id="c1fa2-113">An <xref:System.Xml.Linq.XCData> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c1fa2-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c1fa2-114">Remarks</span></span>  
 <span data-ttu-id="c1fa2-115">Las secciones CDATA XML contienen texto sin formato que se debe incluir, pero no analizar, con el XML que lo contiene.</span><span class="sxs-lookup"><span data-stu-id="c1fa2-115">XML CDATA sections contain raw text that should be included, but not parsed, with the XML that contains it.</span></span> <span data-ttu-id="c1fa2-116">Una sección CDATA XML puede contener cualquier texto.</span><span class="sxs-lookup"><span data-stu-id="c1fa2-116">A XML CDATA section can contain any text.</span></span> <span data-ttu-id="c1fa2-117">Esto incluye los caracteres XML reservados.</span><span class="sxs-lookup"><span data-stu-id="c1fa2-117">This includes reserved XML characters.</span></span> <span data-ttu-id="c1fa2-118">La sección CDATA XML finaliza con la secuencia "]] >".</span><span class="sxs-lookup"><span data-stu-id="c1fa2-118">The XML CDATA section ends with the sequence "]]>".</span></span> <span data-ttu-id="c1fa2-119">Esto implica los puntos siguientes:</span><span class="sxs-lookup"><span data-stu-id="c1fa2-119">This implies the following points:</span></span>  
  
- <span data-ttu-id="c1fa2-120">No se puede usar una expresión insertada en un literal CDATA XML porque los delimitadores de expresión incrustados son contenido XML CDATA válido.</span><span class="sxs-lookup"><span data-stu-id="c1fa2-120">You cannot use an embedded expression in an XML CDATA literal because the embedded expression delimiters are valid XML CDATA content.</span></span>  
  
- <span data-ttu-id="c1fa2-121">Las secciones CDATA XML no se pueden anidar `content` porque no pueden contener el valor "]] >".</span><span class="sxs-lookup"><span data-stu-id="c1fa2-121">XML CDATA sections cannot be nested, because `content` cannot contain the value "]]>".</span></span>  
  
 <span data-ttu-id="c1fa2-122">Puede asignar un literal CDATA XML a una variable o incluirlo en un literal de elemento XML.</span><span class="sxs-lookup"><span data-stu-id="c1fa2-122">You can assign an XML CDATA literal to a variable, or include it in an XML element literal.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c1fa2-123">Un literal XML puede abarcar varias líneas, pero no utiliza caracteres de continuación de línea.</span><span class="sxs-lookup"><span data-stu-id="c1fa2-123">An XML literal can span multiple lines but does not use line continuation characters.</span></span> <span data-ttu-id="c1fa2-124">Esto le permite copiar contenido de un documento XML y pegarlo directamente en un programa de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="c1fa2-124">This enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>  
  
 <span data-ttu-id="c1fa2-125">El compilador Visual Basic convierte el literal CDATA XML en una llamada al <xref:System.Xml.Linq.XCData.%23ctor%2A> constructor.</span><span class="sxs-lookup"><span data-stu-id="c1fa2-125">The Visual Basic compiler converts the XML CDATA literal to a call to the <xref:System.Xml.Linq.XCData.%23ctor%2A> constructor.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c1fa2-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c1fa2-126">Example</span></span>  
 <span data-ttu-id="c1fa2-127">En el ejemplo siguiente se crea una sección CDATA que contiene el texto "puede \<contener etiquetas de > XML literal".</span><span class="sxs-lookup"><span data-stu-id="c1fa2-127">The following example creates a CDATA section that contains the text "Can contain literal \<XML> tags".</span></span>  
  
 [!code-vb[VbXMLSamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples11.vb#23)]  
  
## <a name="see-also"></a><span data-ttu-id="c1fa2-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="c1fa2-128">See also</span></span>

- <xref:System.Xml.Linq.XCData>
- [<span data-ttu-id="c1fa2-129">Literal de elemento XML</span><span class="sxs-lookup"><span data-stu-id="c1fa2-129">XML Element Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [<span data-ttu-id="c1fa2-130">Literales XML</span><span class="sxs-lookup"><span data-stu-id="c1fa2-130">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="c1fa2-131">Crear XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c1fa2-131">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
