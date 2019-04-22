---
title: Expresiones incrustadas (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlEmbeddedExpression
helpviewer_keywords:
- embedded expressions [Visual Basic]
- LINQ to XML [Visual Basic], embedded expressions
- XML literals [Visual Basic], embedded expressions
ms.assetid: bf2eb779-b751-4b7c-854f-9f2161482352
ms.openlocfilehash: 4c96665994a7e56bc70f72b66d5922f5a6472a13
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58827580"
---
# <a name="embedded-expressions-in-xml-visual-basic"></a><span data-ttu-id="9f90d-102">Expresiones incrustadas (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9f90d-102">Embedded Expressions in XML (Visual Basic)</span></span>
<span data-ttu-id="9f90d-103">Expresiones incrustadas le permiten crear literales XML que contienen expresiones que se evalúan en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="9f90d-103">Embedded expressions enable you to create XML literals that contain expressions that are evaluated at run time.</span></span> <span data-ttu-id="9f90d-104">La sintaxis de una expresión incrustada es `<%=` `expression` `%>`, que es la misma que la sintaxis utilizada en [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9f90d-104">The syntax for an embedded expression is `<%=` `expression` `%>`, which is the same as the syntax used in [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)].</span></span>  
  
 <span data-ttu-id="9f90d-105">Por ejemplo, puede crear un elemento XML literal, combinando las expresiones incrustadas con contenido de texto literal.</span><span class="sxs-lookup"><span data-stu-id="9f90d-105">For example, you can create an XML element literal, combining embedded expressions with literal text content.</span></span>  
  
 [!code-vb[VbXMLSamples#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#27)]  
  
 <span data-ttu-id="9f90d-106">Si `isbnNumber` contiene el entero 12345 y `modifiedDate` contiene la fecha 3/5/2006, cuando se ejecuta este código, el valor de `book` es:</span><span class="sxs-lookup"><span data-stu-id="9f90d-106">If `isbnNumber` contains the integer 12345 and `modifiedDate` contains the date 3/5/2006, when this code executes, the value of `book` is:</span></span>  
  
```xml  
<book category="fiction" isbn="12345">  
  <modifiedDate>3/5/2006</modifiedDate>  
</book>  
```  
  
## <a name="embedded-expression-location-and-validation"></a><span data-ttu-id="9f90d-107">Validación y la ubicación de la expresión insertada</span><span class="sxs-lookup"><span data-stu-id="9f90d-107">Embedded Expression Location and Validation</span></span>  
 <span data-ttu-id="9f90d-108">Expresiones incrustadas sólo pueden aparecer en determinadas ubicaciones dentro de expresiones literales XML.</span><span class="sxs-lookup"><span data-stu-id="9f90d-108">Embedded expressions can appear only at certain locations within XML literal expressions.</span></span> <span data-ttu-id="9f90d-109">Los controles de ubicación de la expresión que escribe la expresión pueden devolver y cómo `Nothing` se controla.</span><span class="sxs-lookup"><span data-stu-id="9f90d-109">The expression location controls which types the expression can return and how `Nothing` is handled.</span></span> <span data-ttu-id="9f90d-110">La tabla siguiente describe las ubicaciones permitidas y tipos de expresiones incrustadas.</span><span class="sxs-lookup"><span data-stu-id="9f90d-110">The following table describes the allowed locations and types of embedded expressions.</span></span>  
  
|<span data-ttu-id="9f90d-111">Ubicación en literal</span><span class="sxs-lookup"><span data-stu-id="9f90d-111">Location in literal</span></span>|<span data-ttu-id="9f90d-112">Tipo de expresión</span><span class="sxs-lookup"><span data-stu-id="9f90d-112">Type of expression</span></span>|<span data-ttu-id="9f90d-113">Control de `Nothing`</span><span class="sxs-lookup"><span data-stu-id="9f90d-113">Handling of `Nothing`</span></span>|  
|---|---|---|  
|<span data-ttu-id="9f90d-114">Nombre del elemento XML</span><span class="sxs-lookup"><span data-stu-id="9f90d-114">XML element name</span></span>|<xref:System.Xml.Linq.XName>|<span data-ttu-id="9f90d-115">Error</span><span class="sxs-lookup"><span data-stu-id="9f90d-115">Error</span></span>|  
|<span data-ttu-id="9f90d-116">Contenido del elemento XML</span><span class="sxs-lookup"><span data-stu-id="9f90d-116">XML element content</span></span>|<span data-ttu-id="9f90d-117">`Object` o una matriz de `Object`</span><span class="sxs-lookup"><span data-stu-id="9f90d-117">`Object` or array of `Object`</span></span>|<span data-ttu-id="9f90d-118">Se ignora.</span><span class="sxs-lookup"><span data-stu-id="9f90d-118">Ignored</span></span>|  
|<span data-ttu-id="9f90d-119">Nombre de atributo del elemento XML</span><span class="sxs-lookup"><span data-stu-id="9f90d-119">XML element attribute name</span></span>|<xref:System.Xml.Linq.XName>|<span data-ttu-id="9f90d-120">Error, a menos que el valor del atributo también `Nothing`</span><span class="sxs-lookup"><span data-stu-id="9f90d-120">Error, unless the attribute value is also `Nothing`</span></span>|  
|<span data-ttu-id="9f90d-121">Valor de atributo del elemento XML</span><span class="sxs-lookup"><span data-stu-id="9f90d-121">XML element attribute value</span></span>|`Object`|<span data-ttu-id="9f90d-122">Omite la declaración de atributo</span><span class="sxs-lookup"><span data-stu-id="9f90d-122">Attribute declaration ignored</span></span>|  
|<span data-ttu-id="9f90d-123">Atributo de elemento XML</span><span class="sxs-lookup"><span data-stu-id="9f90d-123">XML element attribute</span></span>|<span data-ttu-id="9f90d-124"><xref:System.Xml.Linq.XAttribute> o una colección de <xref:System.Xml.Linq.XAttribute></span><span class="sxs-lookup"><span data-stu-id="9f90d-124"><xref:System.Xml.Linq.XAttribute> or a collection of <xref:System.Xml.Linq.XAttribute></span></span>|<span data-ttu-id="9f90d-125">Se ignora.</span><span class="sxs-lookup"><span data-stu-id="9f90d-125">Ignored</span></span>|  
|<span data-ttu-id="9f90d-126">Elemento raíz del documento XML</span><span class="sxs-lookup"><span data-stu-id="9f90d-126">XML document root element</span></span>|<span data-ttu-id="9f90d-127"><xref:System.Xml.Linq.XElement> o una colección de uno <xref:System.Xml.Linq.XElement> objeto y un número arbitrario de <xref:System.Xml.Linq.XProcessingInstruction> y <xref:System.Xml.Linq.XComment> objetos</span><span class="sxs-lookup"><span data-stu-id="9f90d-127"><xref:System.Xml.Linq.XElement> or a collection of one <xref:System.Xml.Linq.XElement> object and an arbitrary number of <xref:System.Xml.Linq.XProcessingInstruction> and <xref:System.Xml.Linq.XComment> objects</span></span>|<span data-ttu-id="9f90d-128">Se ignora.</span><span class="sxs-lookup"><span data-stu-id="9f90d-128">Ignored</span></span>|  
  
-   <span data-ttu-id="9f90d-129">Ejemplo de una expresión insertada en un nombre de elemento XML:</span><span class="sxs-lookup"><span data-stu-id="9f90d-129">Example of an embedded expression in an XML element name:</span></span>  
  
     [!code-vb[VbXMLSamples#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#32)]  
  
-   <span data-ttu-id="9f90d-130">Ejemplo de una expresión incrustada en el contenido de un elemento XML:</span><span class="sxs-lookup"><span data-stu-id="9f90d-130">Example of an embedded expression in the content of an XML element:</span></span>  
  
     [!code-vb[VbXMLSamples#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#33)]  
  
-   <span data-ttu-id="9f90d-131">Ejemplo de una expresión insertada en un nombre de atributo del elemento XML:</span><span class="sxs-lookup"><span data-stu-id="9f90d-131">Example of an embedded expression in an XML element attribute name:</span></span>  
  
     [!code-vb[VbXMLSamples#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#34)]  
  
-   <span data-ttu-id="9f90d-132">Ejemplo de una expresión insertada en un valor de atributo del elemento XML:</span><span class="sxs-lookup"><span data-stu-id="9f90d-132">Example of an embedded expression in an XML element attribute value:</span></span>  
  
     [!code-vb[VbXMLSamples#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#35)]  
  
-   <span data-ttu-id="9f90d-133">Ejemplo de una expresión incrustada en el atributo de un elemento XML:</span><span class="sxs-lookup"><span data-stu-id="9f90d-133">Example of an embedded expression in an XML element attribute:</span></span>  
  
     [!code-vb[VbXMLSamples#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#36)]  
  
-   <span data-ttu-id="9f90d-134">Ejemplo de una expresión incrustada en un elemento raíz del documento XML:</span><span class="sxs-lookup"><span data-stu-id="9f90d-134">Example of an embedded expression in an XML document root element:</span></span>  
  
     [!code-vb[VbXMLSamples#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#37)]  
  
 <span data-ttu-id="9f90d-135">Si habilita `Option Strict`, el compilador comprueba que el tipo de cada expresión insertada se amplía al tipo requerido.</span><span class="sxs-lookup"><span data-stu-id="9f90d-135">If you enable `Option Strict`, the compiler checks that the type of each embedded expression widens to the required type.</span></span> <span data-ttu-id="9f90d-136">La única excepción es para el elemento raíz de un documento XML, que se comprueba cuando se ejecuta el código.</span><span class="sxs-lookup"><span data-stu-id="9f90d-136">The only exception is for the root element of an XML document, which is verified when the code runs.</span></span> <span data-ttu-id="9f90d-137">Si se compila sin `Option Strict`, puede incrustar expresiones de tipo `Object` y se comprueba su tipo en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="9f90d-137">If you compile without `Option Strict`, you can embed expressions of type `Object` and their type is verified at run time.</span></span>  
  
 <span data-ttu-id="9f90d-138">En las ubicaciones donde el contenido es opcional, incrustar expresiones que contienen `Nothing` se omiten.</span><span class="sxs-lookup"><span data-stu-id="9f90d-138">In locations where content is optional, embedded expressions that contain `Nothing` are ignored.</span></span> <span data-ttu-id="9f90d-139">Esto significa que no es necesario que comprobar ese contenido del elemento, los valores de atributo, y los elementos de matriz no son `Nothing` antes de utilizar un literal XML.</span><span class="sxs-lookup"><span data-stu-id="9f90d-139">This means you do not have to check that element content, attribute values, and array elements are not `Nothing` before you use an XML literal.</span></span> <span data-ttu-id="9f90d-140">Requiere valores, como los nombres de elemento y atributo, no pueden ser `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="9f90d-140">Required values, such as element and attribute names, cannot be `Nothing`.</span></span>  
  
 <span data-ttu-id="9f90d-141">Para obtener más información sobre cómo usar una expresión incrustada en un determinado tipo de literal, consulte [Literal de documento XML](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md), [Literal de elemento XML](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span><span class="sxs-lookup"><span data-stu-id="9f90d-141">For more information about using an embedded expression in a particular type of literal, see [XML Document Literal](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md), [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span></span>  
  
## <a name="scoping-rules"></a><span data-ttu-id="9f90d-142">Reglas de ámbito</span><span class="sxs-lookup"><span data-stu-id="9f90d-142">Scoping Rules</span></span>  
 <span data-ttu-id="9f90d-143">El compilador convierte cada literal XML en una llamada al constructor para el tipo literal adecuado.</span><span class="sxs-lookup"><span data-stu-id="9f90d-143">The compiler converts each XML literal into a constructor call for the appropriate literal type.</span></span> <span data-ttu-id="9f90d-144">El contenido literal y expresiones incrustadas en un literal XML se pasan como argumentos al constructor.</span><span class="sxs-lookup"><span data-stu-id="9f90d-144">The literal content and embedded expressions in an XML literal are passed as arguments to the constructor.</span></span> <span data-ttu-id="9f90d-145">Esto significa que todos los elementos de programación de Visual Basic disponibles para un literal XML también están disponibles para sus expresiones incrustadas.</span><span class="sxs-lookup"><span data-stu-id="9f90d-145">This means that all Visual Basic programming elements available to an XML literal are also available to its embedded expressions.</span></span>  
  
 <span data-ttu-id="9f90d-146">Dentro de un literal XML, puede tener acceso a espacio de nombres XML prefijos declarados con el `Imports` instrucción.</span><span class="sxs-lookup"><span data-stu-id="9f90d-146">Within an XML literal, you can access the XML namespace prefixes declared with the `Imports` statement.</span></span> <span data-ttu-id="9f90d-147">Puede declarar un nuevo prefijo de espacio de nombres XML o sombrear un prefijo de espacio de nombres XML existente, en un elemento utilizando el `xmlns` atributo.</span><span class="sxs-lookup"><span data-stu-id="9f90d-147">You can declare a new XML namespace prefix, or shadow an existing XML namespace prefix, in an element by using the `xmlns` attribute.</span></span> <span data-ttu-id="9f90d-148">El nuevo espacio de nombres está disponible para los nodos secundarios de ese elemento, pero no para los literales XML en expresiones incrustadas.</span><span class="sxs-lookup"><span data-stu-id="9f90d-148">The new namespace is available to the child nodes of that element, but not to XML literals in embedded expressions.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9f90d-149">Cuando declara un prefijo de espacio de nombres XML mediante el uso de la `xmlns` namespace (atributo), el valor del atributo debe ser una constante de cadena.</span><span class="sxs-lookup"><span data-stu-id="9f90d-149">When you declare an XML namespace prefix by using the `xmlns` namespace attribute, the attribute value must be a constant string.</span></span> <span data-ttu-id="9f90d-150">En este sentido, utilizando el `xmlns` atributo es similar a usar el `Imports` instrucción para declarar un espacio de nombres XML.</span><span class="sxs-lookup"><span data-stu-id="9f90d-150">In this regard, using the `xmlns` attribute is like using the `Imports` statement to declare an XML namespace.</span></span> <span data-ttu-id="9f90d-151">No se puede usar una expresión incrustada para especificar el valor de espacio de nombres XML.</span><span class="sxs-lookup"><span data-stu-id="9f90d-151">You cannot use an embedded expression to specify the XML namespace value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f90d-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="9f90d-152">See also</span></span>

- [<span data-ttu-id="9f90d-153">Crear XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9f90d-153">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="9f90d-154">Literal de documento XML</span><span class="sxs-lookup"><span data-stu-id="9f90d-154">XML Document Literal</span></span>](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)
- [<span data-ttu-id="9f90d-155">Literal de elemento XML</span><span class="sxs-lookup"><span data-stu-id="9f90d-155">XML Element Literal</span></span>](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [<span data-ttu-id="9f90d-156">Option Strict (instrucción)</span><span class="sxs-lookup"><span data-stu-id="9f90d-156">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="9f90d-157">Imports (instrucción), espacio de nombres y tipo .NET</span><span class="sxs-lookup"><span data-stu-id="9f90d-157">Imports Statement (.NET Namespace and Type)</span></span>](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [<span data-ttu-id="9f90d-158">Introducción a literales XML</span><span class="sxs-lookup"><span data-stu-id="9f90d-158">XML Literals Overview</span></span>](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md)
