---
title: Literal de documento XML (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralDocument
helpviewer_keywords:
- XML document literal [Visual Basic]
- XML literals [Visual Basic], document
- XML documents [Visual Basic], creating
- document literal [Visual Basic]
ms.assetid: f7bbee56-0911-41de-b907-96f20450137b
ms.openlocfilehash: f58c1365e145166dfe122d455854d44526300a1e
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58814632"
---
# <a name="xml-document-literal-visual-basic"></a><span data-ttu-id="d8ea5-102">Literal de documento XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d8ea5-102">XML Document Literal (Visual Basic)</span></span>
<span data-ttu-id="d8ea5-103">Un literal que representa un <xref:System.Xml.Linq.XDocument> objeto.</span><span class="sxs-lookup"><span data-stu-id="d8ea5-103">A literal representing an <xref:System.Xml.Linq.XDocument> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8ea5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d8ea5-104">Syntax</span></span>  
  
```xml  
<?xml version="1.0" [encoding="encoding"] [standalone="standalone"] ?>  
[ piCommentList ]  
rootElement  
[ piCommentList ]  
```  
  
## <a name="parts"></a><span data-ttu-id="d8ea5-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="d8ea5-105">Parts</span></span>  
  
|<span data-ttu-id="d8ea5-106">Término</span><span class="sxs-lookup"><span data-stu-id="d8ea5-106">Term</span></span>|<span data-ttu-id="d8ea5-107">de esquema JSON</span><span class="sxs-lookup"><span data-stu-id="d8ea5-107">Definition</span></span>|  
|---|---|  
|`encoding`|<span data-ttu-id="d8ea5-108">Opcional.</span><span class="sxs-lookup"><span data-stu-id="d8ea5-108">Optional.</span></span> <span data-ttu-id="d8ea5-109">Se utiliza el texto literal que declara la codificación que el documento.</span><span class="sxs-lookup"><span data-stu-id="d8ea5-109">Literal text declaring which encoding the document uses.</span></span>|  
|`standalone`|<span data-ttu-id="d8ea5-110">Opcional.</span><span class="sxs-lookup"><span data-stu-id="d8ea5-110">Optional.</span></span> <span data-ttu-id="d8ea5-111">Texto literal.</span><span class="sxs-lookup"><span data-stu-id="d8ea5-111">Literal text.</span></span> <span data-ttu-id="d8ea5-112">Debe ser "yes" o "no".</span><span class="sxs-lookup"><span data-stu-id="d8ea5-112">Must be "yes" or "no".</span></span>|  
|`piCommentList`|<span data-ttu-id="d8ea5-113">Opcional.</span><span class="sxs-lookup"><span data-stu-id="d8ea5-113">Optional.</span></span> <span data-ttu-id="d8ea5-114">Lista de instrucciones de procesamiento XML y los comentarios XML.</span><span class="sxs-lookup"><span data-stu-id="d8ea5-114">List of XML processing instructions and XML comments.</span></span> <span data-ttu-id="d8ea5-115">Tiene el formato siguiente:</span><span class="sxs-lookup"><span data-stu-id="d8ea5-115">Takes the following format:</span></span><br /><br /> <span data-ttu-id="d8ea5-116">`piComment [` `piComment` `... ]`</span><span class="sxs-lookup"><span data-stu-id="d8ea5-116">`piComment [` `piComment` `... ]`</span></span><br /><br /> <span data-ttu-id="d8ea5-117">Cada `piComment` puede ser uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="d8ea5-117">Each `piComment` can be one of the following:</span></span><br /><br /> <span data-ttu-id="d8ea5-118">-   [Literal de instrucción de procesamiento XML](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).</span><span class="sxs-lookup"><span data-stu-id="d8ea5-118">-   [XML Processing Instruction Literal](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).</span></span><br /><span data-ttu-id="d8ea5-119">-   [Literal de comentario XML](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).</span><span class="sxs-lookup"><span data-stu-id="d8ea5-119">-   [XML Comment Literal](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).</span></span>|  
|`rootElement`|<span data-ttu-id="d8ea5-120">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="d8ea5-120">Required.</span></span> <span data-ttu-id="d8ea5-121">Elemento raíz del documento.</span><span class="sxs-lookup"><span data-stu-id="d8ea5-121">Root element of the document.</span></span> <span data-ttu-id="d8ea5-122">El formato es uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="d8ea5-122">The format is one of the following:</span></span><br /><br /> <ul><li><span data-ttu-id="d8ea5-123">[Literal de elemento XML](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span><span class="sxs-lookup"><span data-stu-id="d8ea5-123">[XML Element Literal](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span></span></li><li><span data-ttu-id="d8ea5-124">La forma expresión incrustada `<%=` `elementExp` `%>`.</span><span class="sxs-lookup"><span data-stu-id="d8ea5-124">Embedded expression of the form `<%=` `elementExp` `%>`.</span></span> <span data-ttu-id="d8ea5-125">El `elementExp` devuelve uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="d8ea5-125">The `elementExp` returns one of the following:</span></span><br /><br /> <ul><li><span data-ttu-id="d8ea5-126">Un objeto <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="d8ea5-126">An <xref:System.Xml.Linq.XElement> object.</span></span></li><li><span data-ttu-id="d8ea5-127">Una colección que contiene un <xref:System.Xml.Linq.XElement> objeto y cualquier número de <xref:System.Xml.Linq.XProcessingInstruction> y <xref:System.Xml.Linq.XComment> objetos.</span><span class="sxs-lookup"><span data-stu-id="d8ea5-127">A collection that contains one <xref:System.Xml.Linq.XElement> object and any number of <xref:System.Xml.Linq.XProcessingInstruction> and <xref:System.Xml.Linq.XComment> objects.</span></span></li></ul></li></ul><br /> <span data-ttu-id="d8ea5-128">Para obtener más información, consulte [expresiones incrustadas en XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span><span class="sxs-lookup"><span data-stu-id="d8ea5-128">For more information, see [Embedded Expressions in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="d8ea5-129">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d8ea5-129">Return Value</span></span>  
 <span data-ttu-id="d8ea5-130">Un objeto <xref:System.Xml.Linq.XDocument>.</span><span class="sxs-lookup"><span data-stu-id="d8ea5-130">An <xref:System.Xml.Linq.XDocument> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d8ea5-131">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d8ea5-131">Remarks</span></span>  
 <span data-ttu-id="d8ea5-132">Un literal de documento XML se identifica mediante la declaración XML al principio del literal.</span><span class="sxs-lookup"><span data-stu-id="d8ea5-132">An XML document literal is identified by the XML declaration at the start of the literal.</span></span> <span data-ttu-id="d8ea5-133">Aunque cada literal de documento XML debe tener exactamente un elemento XML de raíz, puede tener cualquier número de instrucciones de procesamiento XML y los comentarios XML.</span><span class="sxs-lookup"><span data-stu-id="d8ea5-133">Although each XML document literal must have exactly one root XML element, it can have any number of XML processing instructions and XML comments.</span></span>  
  
 <span data-ttu-id="d8ea5-134">Un literal de documento XML no puede aparecer en un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="d8ea5-134">An XML document literal cannot appear in an XML element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d8ea5-135">Un literal XML puede abarcar varias líneas sin usar caracteres de continuación de línea.</span><span class="sxs-lookup"><span data-stu-id="d8ea5-135">An XML literal can span multiple lines without using line continuation characters.</span></span> <span data-ttu-id="d8ea5-136">Esto permite copiar el contenido de un documento XML y péguelo directamente en un programa de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="d8ea5-136">This enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>  
  
 <span data-ttu-id="d8ea5-137">El compilador de Visual Basic convierte el literal de documento XML en llamadas a la <xref:System.Xml.Linq.XDocument.%23ctor%2A> y <xref:System.Xml.Linq.XDeclaration.%23ctor%2A> constructores.</span><span class="sxs-lookup"><span data-stu-id="d8ea5-137">The Visual Basic compiler converts the XML document literal into calls to the <xref:System.Xml.Linq.XDocument.%23ctor%2A> and <xref:System.Xml.Linq.XDeclaration.%23ctor%2A> constructors.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d8ea5-138">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d8ea5-138">Example</span></span>  
 <span data-ttu-id="d8ea5-139">El ejemplo siguiente crea un documento XML que tiene una declaración XML, una instrucción de procesamiento, un comentario y un elemento que contiene otro elemento.</span><span class="sxs-lookup"><span data-stu-id="d8ea5-139">The following example creates an XML document that has an XML declaration, a processing instruction, a comment, and an element that contains another element.</span></span>  
  
 [!code-vb[VbXMLSamples#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#30)]  
  
## <a name="see-also"></a><span data-ttu-id="d8ea5-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="d8ea5-140">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- <xref:System.Xml.Linq.XProcessingInstruction>
- <xref:System.Xml.Linq.XComment>
- <xref:System.Xml.Linq.XDocument>
- [<span data-ttu-id="d8ea5-141">Literal de instrucción de procesamiento XML</span><span class="sxs-lookup"><span data-stu-id="d8ea5-141">XML Processing Instruction Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md)
- [<span data-ttu-id="d8ea5-142">Literal de comentario XML</span><span class="sxs-lookup"><span data-stu-id="d8ea5-142">XML Comment Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md)
- [<span data-ttu-id="d8ea5-143">Literal de elemento XML</span><span class="sxs-lookup"><span data-stu-id="d8ea5-143">XML Element Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [<span data-ttu-id="d8ea5-144">Literales XML</span><span class="sxs-lookup"><span data-stu-id="d8ea5-144">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="d8ea5-145">Crear XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d8ea5-145">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="d8ea5-146">Expresiones incrustadas en XML</span><span class="sxs-lookup"><span data-stu-id="d8ea5-146">Embedded Expressions in XML</span></span>](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)
