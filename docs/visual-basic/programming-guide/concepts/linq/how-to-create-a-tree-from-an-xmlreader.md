---
title: 'Cómo: crear un árbol a partir de un objeto XmlReader (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 6de683d8-177d-402b-b0de-d0539f1ce5d8
ms.openlocfilehash: c90fbee29a380824cdc32dd62622e55ea40044fd
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583023"
---
# <a name="how-to-create-a-tree-from-an-xmlreader-visual-basic"></a>Cómo: crear un árbol a partir de un objeto XmlReader (Visual Basic)

En este tema se muestra cómo crear un árbol XML directamente de <xref:System.Xml.XmlReader>. Para crear un <xref:System.Xml.Linq.XElement> de <xref:System.Xml.XmlReader>, debe colocar el <xref:System.Xml.XmlReader> en un nodo de elemento. <xref:System.Xml.XmlReader> omitirá los comentarios y las instrucciones de procesamiento, pero si <xref:System.Xml.XmlReader> se coloca en un nodo de texto, se producirá un error. Para evitar tales errores, coloque siempre <xref:System.Xml.XmlReader> en un elemento ante de crear un árbol XML de <xref:System.Xml.XmlReader>.

## <a name="example"></a>Ejemplo

En este ejemplo se usa el siguiente documento XML: [Archivo XML de muestra: libros (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).

El siguiente código crea un objeto `T:System.Xml.XmlReader` y lee nodos hasta que encuentra el primer nodo de elemento. A continuación, carga el objeto <xref:System.Xml.Linq.XElement>.

```vb
Dim r As XmlReader = XmlReader.Create("books.xml")
Do While r.NodeType <> XmlNodeType.Element
    r.Read()
Loop
Dim e As XElement = XElement.Load(r)
Console.WriteLine(e)
```

Este ejemplo produce el siguiente resultado:

```xml
<Catalog>
   <Book id="bk101">
      <Author>Garghentini, Davide</Author>
      <Title>XML Developer's Guide</Title>
      <Genre>Computer</Genre>
      <Price>44.95</Price>
      <PublishDate>2000-10-01</PublishDate>
      <Description>An in-depth look at creating applications
      with XML.</Description>
   </Book>
   <Book id="bk102">
      <Author>Garcia, Debra</Author>
      <Title>Midnight Rain</Title>
      <Genre>Fantasy</Genre>
      <Price>5.95</Price>
      <PublishDate>2000-12-16</PublishDate>
      <Description>A former architect battles corporate zombies,
      an evil sorceress, and her own childhood to become queen
      of the world.</Description>
   </Book>
</Catalog>
```

## <a name="see-also"></a>Vea también

- [Analizar XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)
