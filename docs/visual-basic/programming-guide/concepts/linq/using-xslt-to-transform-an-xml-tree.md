---
title: Usar XSLT para transformar un árbol XML (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 3390ca68-c270-4e1d-b64b-6a063a77017c
ms.openlocfilehash: 0d6255767b241083f5623a8b379ab6554b03f0e9
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582343"
---
# <a name="using-xslt-to-transform-an-xml-tree-visual-basic"></a>Usar XSLT para transformar un árbol XML (Visual Basic)

Puede crear un árbol XML, crear un objeto <xref:System.Xml.XmlReader> desde el árbol XML, crear un nuevo documento y crear un objeto <xref:System.Xml.XmlWriter> que escribirá en el nuevo documento. A continuación, puede invocar la transformación XSLT y pasar <xref:System.Xml.XmlReader> y <xref:System.Xml.XmlWriter> a la transformación. Después de que se complete correctamente la transformación, se rellenará el nuevo árbol XML con los resultados de la transformación.

## <a name="example"></a>Ejemplo

```vb
Dim xslMarkup As XDocument = _
    <?xml version='1.0'?>
    <xsl:stylesheet xmlns:xsl='http://www.w3.org/1999/XSL/Transform' version='1.0'>
        <xsl:template match='/Parent'>
            <Root>
                <C1>
                    <xsl:value-of select='Child1'/>
                </C1>
                <C2>
                    <xsl:value-of select='Child2'/>
                </C2>
            </Root>
        </xsl:template>
    </xsl:stylesheet>

Dim xmlTree As XElement = _
    <Parent>
        <Child1>Child1 data</Child1>
        <Child2>Child2 data</Child2>
    </Parent>

Dim newTree As XDocument = New XDocument()

Using writer As XmlWriter = newTree.CreateWriter()
    ' Load the style sheet.
    Dim xslt As XslCompiledTransform = _
        New XslCompiledTransform()
    xslt.Load(xslMarkup.CreateReader())

    ' Execute the transform and output the results to a writer.
    xslt.Transform(xmlTree.CreateReader(), writer)
End Using

Console.WriteLine(newTree)
```

Este ejemplo produce el siguiente resultado:

```xml
<Root>
  <C1>Child1 data</C1>
  <C2>Child2 data</C2>
</Root>
```

## <a name="see-also"></a>Vea también

- <xref:System.Xml.Linq.XContainer.CreateWriter%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XNode.CreateReader%2A?displayProperty=nameWithType>
- [Programación de LINQ to XML avanzada (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
