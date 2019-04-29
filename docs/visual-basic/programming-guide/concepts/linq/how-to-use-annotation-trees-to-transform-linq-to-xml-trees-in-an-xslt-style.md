---
title: Procedimiento Usar anotaciones para transformar árboles LINQ to XML en un estilo XSLT (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 08e91fa2-dac2-4463-9ef1-87b1ac3fa890
ms.openlocfilehash: a8db5f9dc29b4053321c81c9da58e12610ef63c7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61613458"
---
# <a name="how-to-use-annotations-to-transform-linq-to-xml-trees-in-an-xslt-style-visual-basic"></a><span data-ttu-id="72da3-102">Procedimiento Usar anotaciones para transformar árboles LINQ to XML en un estilo XSLT (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="72da3-102">How to: Use Annotations to Transform LINQ to XML Trees in an XSLT Style (Visual Basic)</span></span>
<span data-ttu-id="72da3-103">Se puede usar anotaciones para facilitar transformaciones de un árbol XML.</span><span class="sxs-lookup"><span data-stu-id="72da3-103">Annotations can be used to facilitate transforms of an XML tree.</span></span>  
  
 <span data-ttu-id="72da3-104">Algunos documentos XML están "basados en el documento con contenido mixto".</span><span class="sxs-lookup"><span data-stu-id="72da3-104">Some XML documents are "document centric with mixed content."</span></span> <span data-ttu-id="72da3-105">Con estos documentos no se conoce necesariamente la forma de los nodos secundarios de un elemento.</span><span class="sxs-lookup"><span data-stu-id="72da3-105">With such documents, you don't necessarily know the shape of child nodes of an element.</span></span> <span data-ttu-id="72da3-106">Por ejemplo, un nodo que contiene texto puede tener el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="72da3-106">For instance, a node that contains text may look like this:</span></span>  
  
```xml  
<text>A phrase with <b>bold</b> and <i>italic</i> text.</text>  
```  
  
 <span data-ttu-id="72da3-107">Para cualquier nodo de texto dado puede haber cualquier número de elementos secundarios `<b>` y `<i>`.</span><span class="sxs-lookup"><span data-stu-id="72da3-107">For any given text node, there may be any number of child `<b>` and `<i>` elements.</span></span> <span data-ttu-id="72da3-108">Este enfoque se extiende a otras situaciones: por ejemplo, las páginas que pueden contener varios elementos secundarios, como párrafos normales, párrafos con viñetas o mapas de bits.</span><span class="sxs-lookup"><span data-stu-id="72da3-108">This approach extends to a number of other situations: such as, pages that can contain a variety of child elements, such as regular paragraphs, bulleted paragraphs, and bitmaps.</span></span> <span data-ttu-id="72da3-109">Las celdas de una tabla pueden contener texto, listas desplegables o mapas de bits.</span><span class="sxs-lookup"><span data-stu-id="72da3-109">Cells in a table may contain text, drop down lists, or bitmaps.</span></span> <span data-ttu-id="72da3-110">Una de las características principal del XML centrado en documentos es que no se sabe qué elemento secundario puede tener cualquier elemento particular.</span><span class="sxs-lookup"><span data-stu-id="72da3-110">One of the primary characteristics of document centric XML is that you do not know which child element any particular element will have.</span></span>  
  
 <span data-ttu-id="72da3-111">Si desea transformar elementos de un árbol en el que no conoce el elemento secundario de los elementos que desea transformar, entonces este enfoque que usa anotaciones en un enfoque efectivo.</span><span class="sxs-lookup"><span data-stu-id="72da3-111">If you want to transform elements in a tree where you don't necessarily know much about the children of the elements that you want to transform, then this approach that uses annotations is an effective approach.</span></span>  
  
 <span data-ttu-id="72da3-112">El resumen del enfoque es:</span><span class="sxs-lookup"><span data-stu-id="72da3-112">The summary of the approach is:</span></span>  
  
- <span data-ttu-id="72da3-113">En primer lugar, anote elementos en el árbol con un elemento de sustitución.</span><span class="sxs-lookup"><span data-stu-id="72da3-113">First, annotate elements in the tree with a replacement element.</span></span>  
  
- <span data-ttu-id="72da3-114">En segundo lugar, recorra en iteración todo el árbol, creando un nuevo árbol en el que se reemplaza cada elemento son su anotación.</span><span class="sxs-lookup"><span data-stu-id="72da3-114">Second, iterate through the entire tree, creating a new tree where you replace each element with its annotation.</span></span> <span data-ttu-id="72da3-115">Este ejemplo implementa la iteración y la creación de un nuevo árbol en una función con el nombre `XForm`.</span><span class="sxs-lookup"><span data-stu-id="72da3-115">This example implements the iteration and creation of the new tree in a function named `XForm`.</span></span>  
  
 <span data-ttu-id="72da3-116">En detalle, el enfoque consiste en:</span><span class="sxs-lookup"><span data-stu-id="72da3-116">In detail, the approach consists of:</span></span>  
  
- <span data-ttu-id="72da3-117">Ejecutar una o más consultas LINQ to XML que devuelvan el conjunto de elementos que desea transformar de una forma a otra.</span><span class="sxs-lookup"><span data-stu-id="72da3-117">Execute one or more LINQ to XML queries that return the set of elements that you want to transform from one shape to another.</span></span> <span data-ttu-id="72da3-118">Para cada elemento de la consulta, agregue un nuevo objeto <xref:System.Xml.Linq.XElement> como anotación al elemento.</span><span class="sxs-lookup"><span data-stu-id="72da3-118">For each element in the query, add a new <xref:System.Xml.Linq.XElement> object as an annotation to the element.</span></span> <span data-ttu-id="72da3-119">Este nuevo elemento sustituirá el elemento anotado en el nuevo árbol transformado.</span><span class="sxs-lookup"><span data-stu-id="72da3-119">This new element will replace the annotated element in the new, transformed tree.</span></span> <span data-ttu-id="72da3-120">Es un código sencillo de escribir, tal como lo demuestra el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="72da3-120">This is simple code to write, as demonstrated by the example.</span></span>  
  
- <span data-ttu-id="72da3-121">El nuevo elemento que se agrega como anotación puede contener nodos secundarios; puede formar un subárbol con cualquier forma que se desee.</span><span class="sxs-lookup"><span data-stu-id="72da3-121">The new element that is added as an annotation can contain new child nodes; it can form a sub-tree with any desired shape.</span></span>  
  
- <span data-ttu-id="72da3-122">Hay una regla especial: si un nodo secundario del nuevo elemento está en otro espacio de nombres, un espacio de nombres creado con esa finalidad (en este ejemplo, el espacio de nombres es `http://www.microsoft.com/LinqToXmlTransform/2007`), entonces el elemento secundario no se copia al árbol nuevo.</span><span class="sxs-lookup"><span data-stu-id="72da3-122">There is a special rule: If a child node of the new element is in a different namespace, a namespace that is made up for this purpose (in this example, the namespace is `http://www.microsoft.com/LinqToXmlTransform/2007`), then that child element is not copied to the new tree.</span></span> <span data-ttu-id="72da3-123">En su lugar, si el espacio de nombres es el espacio de nombres especial mencionado anteriormente y el nombre local del elemento es `ApplyTransforms`, los nodos secundarios del elemento del árbol de origen se recorren en iteración y se copian al nuevo árbol (con la excepción que los elementos secundarios anotados se transforman de acuerdo con esas reglas).</span><span class="sxs-lookup"><span data-stu-id="72da3-123">Instead, if the namespace is the above mentioned special namespace, and the local name of the element is `ApplyTransforms`, then the child nodes of the element in the source tree are iterated, and copied to the new tree (with the exception that annotated child elements are themselves transformed according to these rules).</span></span>  
  
- <span data-ttu-id="72da3-124">Esto es parecido a la especificación de transformaciones en XSL.</span><span class="sxs-lookup"><span data-stu-id="72da3-124">This is somewhat analogous to the specification of transforms in XSL.</span></span> <span data-ttu-id="72da3-125">La consulta que selecciona un conjunto de nodos es análoga a la expresión XPath para una plantilla.</span><span class="sxs-lookup"><span data-stu-id="72da3-125">The query that selects a set of nodes is analogous to the XPath expression for a template.</span></span> <span data-ttu-id="72da3-126">El código para crear el nuevo <xref:System.Xml.Linq.XElement> que se guarda como anotación es análogo al constructor de secuencias en XSL y el elemento `ApplyTransforms` es análogo en función al elemento `xsl:apply-templates` en XSL.</span><span class="sxs-lookup"><span data-stu-id="72da3-126">The code to create the new <xref:System.Xml.Linq.XElement> that is saved as an annotation is analogous to the sequence constructor in XSL, and the `ApplyTransforms` element is analogous in function to the `xsl:apply-templates` element in XSL.</span></span>  
  
- <span data-ttu-id="72da3-127">Una ventaja de este enfoque es que al formular consultas siempre se escriben consultas en el árbol de origen sin modificar.</span><span class="sxs-lookup"><span data-stu-id="72da3-127">One advantage to taking this approach - as you formulate queries, you are always writing queries on the unmodified source tree.</span></span> <span data-ttu-id="72da3-128">No hay que preocuparse de cómo afectan a las consultas que se están escribiendo las modificaciones del árbol.</span><span class="sxs-lookup"><span data-stu-id="72da3-128">You need not worry about how modifications to the tree affect the queries that you are writing.</span></span>  
  
## <a name="transforming-a-tree"></a><span data-ttu-id="72da3-129">Transformar un árbol</span><span class="sxs-lookup"><span data-stu-id="72da3-129">Transforming a Tree</span></span>  
 <span data-ttu-id="72da3-130">El primer ejemplo cambia el nombre de todos los nodos `Paragraph` a `para`.</span><span class="sxs-lookup"><span data-stu-id="72da3-130">This first example renames all `Paragraph` nodes to `para`.</span></span>  
  
```vb  
Imports <xmlns:xf="http://www.microsoft.com/LinqToXmlTransform/2007">  
  
Module Module1  
    Dim at As XName = GetXmlNamespace(xf) + "ApplyTransforms"  
  
    Sub Main()  
        Dim root As XElement = _  
            <Root>  
                <Paragraph>This is a sentence with <b>bold</b> and <i>italic</i> text.</Paragraph>  
                <Paragraph>More text.</Paragraph>  
            </Root>  
  
        ' Replace Paragraph with p.  
        For Each el In root...<Paragraph>  
            ' same idea as xsl:apply-templates  
            el.AddAnnotation( _  
                <para>  
                    <<%= at %>></>  
                </para>)  
        Next  
  
        ' The XForm function, shown later in this topic, accomplishes the transform  
        Dim newRoot As XElement = XForm(root)  
        Console.WriteLine(newRoot)  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="72da3-131">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="72da3-131">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <para>This is a sentence with <b>bold</b> and <i>italic</i> text.</para>  
  <para>More text.</para>  
</Root>  
```  
  
## <a name="a-more-complicated-transform"></a><span data-ttu-id="72da3-132">Una transformación más complicada</span><span class="sxs-lookup"><span data-stu-id="72da3-132">A More Complicated Transform</span></span>  
 <span data-ttu-id="72da3-133">El siguiente ejemplo consulta el árbol y calcula la media y la suma de los elementos `Data` y los agrega como nuevos elementos al árbol.</span><span class="sxs-lookup"><span data-stu-id="72da3-133">The following example queries the tree and calculates the average and sum of the `Data` elements, and adds them as new elements to the tree.</span></span>  
  
```vb  
Imports <xmlns:xf="http://www.microsoft.com/LinqToXmlTransform/2007">  
  
Module Module1  
    Dim at As XName = GetXmlNamespace(xf) + "ApplyTransforms"  
  
    Sub Main()  
        Dim data As XElement = _  
            <Root>  
                <Data>20</Data>  
                <Data>10</Data>  
                <Data>3</Data>  
            </Root>  
  
        ' While adding annotations, you can query the source tree all you want,  
        ' as the tree is not mutated while annotating.  
        data.AddAnnotation( _  
            <Root>  
                <<%= at %>/>  
                <Average>  
                    <%= _  
                        String.Format("{0:F4}", _  
                        data.Elements("Data") _  
                        .Select(Function(z) CDec(z)).Average()) _  
                    %>  
                </Average>  
                <Sum>  
                    <%= _  
                        data.Elements("Data").Select(Function(z) CInt(z)).Sum() _  
                    %>  
                </Sum>  
            </Root> _  
        )  
  
        Console.WriteLine("Before Transform")  
        Console.WriteLine("----------------")  
        Console.WriteLine(data)  
        Console.WriteLine(vbNewLine)  
  
        ' The XForm function, shown later in this topic, accomplishes the transform  
        Dim newData As XElement = XForm(data)  
  
        Console.WriteLine("After Transform")  
        Console.WriteLine("----------------")  
        Console.WriteLine(newData)  
    End Sub  
End Module   
```  
  
 <span data-ttu-id="72da3-134">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="72da3-134">This example produces the following output:</span></span>  
  
```  
Before Transform  
----------------  
<Root>  
  <Data>20</Data>  
  <Data>10</Data>  
  <Data>3</Data>  
</Root>  
  
After Transform  
----------------  
<Root>  
  <Data>20</Data>  
  <Data>10</Data>  
  <Data>3</Data>  
  <Average>11.0000</Average>  
  <Sum>33</Sum>  
</Root>  
```  
  
## <a name="effecting-the-transform"></a><span data-ttu-id="72da3-135">Llevar a cabo la transformación</span><span class="sxs-lookup"><span data-stu-id="72da3-135">Effecting the Transform</span></span>  
 <span data-ttu-id="72da3-136">Una pequeña función, `XForm`, crea un nuevo árbol transformado a partir del árbol original anotado.</span><span class="sxs-lookup"><span data-stu-id="72da3-136">A small function, `XForm`, creates a new transformed tree from the original, annotated tree.</span></span>  
  
- <span data-ttu-id="72da3-137">El pseudocódigo para la función es bastante sencillo:</span><span class="sxs-lookup"><span data-stu-id="72da3-137">The pseudo code for the function is quite simple:</span></span>  
  
```  
The function takes an XElement as an argument and returns an XElement.   
If an element has an XElement annotation, then  
    Return a new XElement  
        The name of the new XElement is the annotation element's name.  
        All attributes are copied from the annotation to the new node.  
        All child nodes are copied from the annotation, with the  
            exception that the special node xf:ApplyTransforms is  
            recognized, and the source element's child nodes are  
            iterated. If the source child node is not an XElement, it  
            is copied to the new tree. If the source child is an  
            XElement, then it is transformed by calling this function  
            recursively.  
If an element is not annotated  
    Return a new XElement  
        The name of the new XElement is the source element's name  
        All attributes are copied from the source element to the  
            destination's element.  
        All child nodes are copied from the source element.  
        If the source child node is not an XElement, it is copied to  
            the new tree. If the source child is an XElement, then it  
            is transformed by calling this function recursively.  
```  
  
 <span data-ttu-id="72da3-138">A continuación se muestra la implementación de esta función:</span><span class="sxs-lookup"><span data-stu-id="72da3-138">Following is the implementation of this function:</span></span>  
  
```vb  
' Build a transformed XML tree per the annotations.  
Function XForm(ByVal source As XElement) As XElement  
    If source.Annotation(Of XElement)() IsNot Nothing Then  
        Dim anno As XElement = source.Annotation(Of XElement)()  
        Return _  
            <<%= anno.Name.ToString() %>>  
                <%= anno.Attributes() %>  
                <%= anno.Nodes().Select(Function(n As XNode) _  
                    GetSubNodes(n, source)) %>  
            </>  
    Else  
        Return _  
            <<%= source.Name %>>  
                <%= source.Attributes() %>  
                <%= source.Nodes().Select(Function(n) GetExpandedNodes(n)) %>  
            </>  
    End If  
End Function  
  
Private Function GetSubNodes(ByVal n As XNode, ByVal s As XElement) As Object  
    Dim annoEl As XElement = TryCast(n, XElement)  
    If annoEl IsNot Nothing Then  
        If annoEl.Name = at Then  
            Return s.Nodes().Select(Function(n2 As XNode) GetExpandedNodes(n2))  
        End If  
    End If  
    Return n  
End Function  
  
Private Function GetExpandedNodes(ByVal n2 As XNode) As XNode  
    Dim e2 As XElement = TryCast(n2, XElement)  
    If e2 Is Nothing Then  
        Return n2  
    Else  
        Return XForm(e2)  
    End If  
End Function  
```  
  
## <a name="complete-example"></a><span data-ttu-id="72da3-139">Ejemplo completo</span><span class="sxs-lookup"><span data-stu-id="72da3-139">Complete Example</span></span>  
 <span data-ttu-id="72da3-140">El siguiente código es un ejemplo completo que incluye la función `XForm`.</span><span class="sxs-lookup"><span data-stu-id="72da3-140">The following code is a complete example that includes the `XForm` function.</span></span> <span data-ttu-id="72da3-141">Incluye unos pocos usos típicos de este tipo de transformación:</span><span class="sxs-lookup"><span data-stu-id="72da3-141">It includes a few of the typical uses of this type of transform:</span></span>  
  
```vb  
Imports System  
Imports System.Collections.Generic  
Imports System.Linq  
Imports System.Text  
Imports System.Xml  
Imports System.Xml.Linq  
  
Imports <xmlns:xf="http://www.microsoft.com/LinqToXmlTransform/2007">  
  
Module Module1  
    Dim at As XName = GetXmlNamespace(xf) + "ApplyTransforms"  
  
    ' Build a transformed XML tree per the annotations.  
    Function XForm(ByVal source As XElement) As XElement  
        If source.Annotation(Of XElement)() IsNot Nothing Then  
            Dim anno As XElement = source.Annotation(Of XElement)()  
            Return _  
                <<%= anno.Name.ToString() %>>  
                    <%= anno.Attributes() %>  
                    <%= anno.Nodes().Select(Function(n As XNode) _  
                        GetSubNodes(n, source)) %>  
                </>  
        Else  
            Return _  
                <<%= source.Name %>>  
                    <%= source.Attributes() %>  
                    <%= source.Nodes().Select(Function(n) GetExpandedNodes(n)) %>  
                </>  
        End If  
    End Function  
  
    Private Function GetSubNodes(ByVal n As XNode, ByVal s As XElement) As Object  
        Dim annoEl As XElement = TryCast(n, XElement)  
        If annoEl IsNot Nothing Then  
            If annoEl.Name = at Then  
                Return s.Nodes().Select(Function(n2 As XNode) GetExpandedNodes(n2))  
            End If  
        End If  
        Return n  
    End Function  
  
    Private Function GetExpandedNodes(ByVal n2 As XNode) As XNode  
        Dim e2 As XElement = TryCast(n2, XElement)  
        If e2 Is Nothing Then  
            Return n2  
        Else  
            Return XForm(e2)  
        End If  
    End Function  
  
    Sub Main()  
        Dim root As XElement = _  
<Root Att1='123'>  
    <!--A comment-->  
    <Child>1</Child>  
    <Child>2</Child>  
    <Other>  
        <GC>3</GC>  
        <GC>4</GC>  
    </Other>  
    <SomeMixedContent>This is <i>an</i> element that <b>has</b> some mixed content</SomeMixedContent>  
    <AnUnchangedElement>42</AnUnchangedElement>  
</Root>  
  
        ' Each of the following serves the same semantic purpose as  
        ' XSLT templates and sequence constructors.  
  
        ' Replace Child with NewChild.  
        For Each el In root.<Child>  
            el.AddAnnotation(<NewChild><%= CStr(el) %></NewChild>)  
        Next  
  
        ' Replace first GC with GrandChild, add an attribute.  
        For Each el In root...<GC>.Take(1)  
            el.AddAnnotation(<GrandChild ANewAttribute='999'><%= CStr(el) %></GrandChild>)  
        Next  
  
        ' Replace Other with NewOther, add new child elements around original content.  
        For Each el In root.<Other>  
            el.AddAnnotation( _  
                <NewOther>  
                    <MyNewChild>1</MyNewChild>  
                    <<%= at %>></>  
                    <ChildThatComesAfter/>  
                </NewOther>)  
        Next  
  
        ' Change name of element that has mixed content.  
        root...<SomeMixedContent>(0).AddAnnotation( _  
                <MixedContent><<%= at %>></></MixedContent>)  
  
        ' Replace <b> with <Bold>.  
        For Each el In root...<b>  
            el.AddAnnotation(<Bold><<%= at %>></></Bold>)  
        Next  
  
        ' Replace <i> with <Italic>.  
        For Each el In root...<i>  
            el.AddAnnotation(<Italic><<%= at %>></></Italic>)  
        Next  
  
        Console.WriteLine("Before Transform")  
        Console.WriteLine("----------------")  
        Console.WriteLine(root)  
        Console.WriteLine(vbNewLine)  
        Dim newRoot As XElement = XForm(root)  
  
        Console.WriteLine("After Transform")  
        Console.WriteLine("----------------")  
        Console.WriteLine(newRoot)  
    End Sub  
End Module   
```  
  
 <span data-ttu-id="72da3-142">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="72da3-142">This example produces the following output:</span></span>  
  
```  
Before Transform  
----------------  
<Root Att1="123">  
  <!--A comment-->  
  <Child>1</Child>  
  <Child>2</Child>  
  <Other>  
    <GC>3</GC>  
    <GC>4</GC>  
  </Other>  
  <SomeMixedContent>This is <i>an</i> element that <b>has</b> some mixed content</SomeMixedContent>  
  <AnUnchangedElement>42</AnUnchangedElement>  
</Root>  
  
After Transform  
----------------  
<Root Att1="123">  
  <!--A comment-->  
  <NewChild>1</NewChild>  
  <NewChild>2</NewChild>  
  <NewOther>  
    <MyNewChild>1</MyNewChild>  
    <GrandChild ANewAttribute="999">3</GrandChild>  
    <GC>4</GC>  
    <ChildThatComesAfter />  
  </NewOther>  
  <MixedContent>This is <Italic>an</Italic> element that <Bold>has</Bold> some mixed content</MixedContent>  
  <AnUnchangedElement>42</AnUnchangedElement>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="72da3-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="72da3-143">See also</span></span>

- [<span data-ttu-id="72da3-144">Avanzada de LINQ to XML (Visual Basic) de programación</span><span class="sxs-lookup"><span data-stu-id="72da3-144">Advanced LINQ to XML Programming (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
