---
title: Procedimiento para validar con XSD (LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: 6a7f83a9-2d74-4c2b-8417-0a8595879516
ms.openlocfilehash: 0e35e12efa9530fd5bbcf7a21e86ed03c1325bc4
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70253248"
---
# <a name="how-to-validate-using-xsd-linq-to-xml-c"></a><span data-ttu-id="e92be-102">Procedimiento para validar con XSD (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="e92be-102">How to: Validate Using XSD (LINQ to XML) (C#)</span></span>
<span data-ttu-id="e92be-103">El espacio de nombres <xref:System.Xml.Schema> contiene métodos de extensión que hacen que sea fácil validar un árbol XML contra un archivo de lenguaje de definición de esquemas XML (XSD).</span><span class="sxs-lookup"><span data-stu-id="e92be-103">The <xref:System.Xml.Schema> namespace contains extension methods that make it easy to validate an XML tree against an XML Schema Definition Language (XSD) file.</span></span> <span data-ttu-id="e92be-104">Para obtener más información, vea la documentación del método <xref:System.Xml.Schema.Extensions.Validate%2A>.</span><span class="sxs-lookup"><span data-stu-id="e92be-104">For more information, see the <xref:System.Xml.Schema.Extensions.Validate%2A> method documentation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e92be-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e92be-105">Example</span></span>  
 <span data-ttu-id="e92be-106">En el ejemplo siguiente se crea un <xref:System.Xml.Schema.XmlSchemaSet>, a continuación, se validan dos objetos <xref:System.Xml.Linq.XDocument> con el esquema establecido.</span><span class="sxs-lookup"><span data-stu-id="e92be-106">The following example creates an <xref:System.Xml.Schema.XmlSchemaSet>, then validates two <xref:System.Xml.Linq.XDocument> objects against the schema set.</span></span> <span data-ttu-id="e92be-107">Uno de los documentos es válido, el otro no.</span><span class="sxs-lookup"><span data-stu-id="e92be-107">One of the documents is valid, the other is not.</span></span>  
  
```csharp  
string xsdMarkup =  
    @"<xsd:schema xmlns:xsd='http://www.w3.org/2001/XMLSchema'>  
       <xsd:element name='Root'>  
        <xsd:complexType>  
         <xsd:sequence>  
          <xsd:element name='Child1' minOccurs='1' maxOccurs='1'/>  
          <xsd:element name='Child2' minOccurs='1' maxOccurs='1'/>  
         </xsd:sequence>  
        </xsd:complexType>  
       </xsd:element>  
      </xsd:schema>";  
XmlSchemaSet schemas = new XmlSchemaSet();  
schemas.Add("", XmlReader.Create(new StringReader(xsdMarkup)));  
  
XDocument doc1 = new XDocument(  
    new XElement("Root",  
        new XElement("Child1", "content1"),  
        new XElement("Child2", "content1")  
    )  
);  
  
XDocument doc2 = new XDocument(  
    new XElement("Root",  
        new XElement("Child1", "content1"),  
        new XElement("Child3", "content1")  
    )  
);  
  
Console.WriteLine("Validating doc1");  
bool errors = false;  
doc1.Validate(schemas, (o, e) =>  
                     {  
                         Console.WriteLine("{0}", e.Message);  
                         errors = true;  
                     });  
Console.WriteLine("doc1 {0}", errors ? "did not validate" : "validated");  
  
Console.WriteLine();  
Console.WriteLine("Validating doc2");  
errors = false;  
doc2.Validate(schemas, (o, e) =>  
                     {  
                         Console.WriteLine("{0}", e.Message);  
                         errors = true;  
                     });  
Console.WriteLine("doc2 {0}", errors ? "did not validate" : "validated");  
```  
  
 <span data-ttu-id="e92be-108">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="e92be-108">This example produces the following output:</span></span>  
  
```output  
Validating doc1  
doc1 validated  
  
Validating doc2  
The element 'Root' has invalid child element 'Child3'. List of possible elements expected: 'Child2'.  
doc2 did not validate  
```  
  
## <a name="example"></a><span data-ttu-id="e92be-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e92be-109">Example</span></span>  
 <span data-ttu-id="e92be-110">En el ejemplo siguiente se valida que el documento XML de [Archivo XML de ejemplo: Clientes y pedidos (LINQ to XML)](./sample-xml-file-customers-and-orders-linq-to-xml-2.md) es válido de acuerdo con el esquema de [Archivo XSD de ejemplo: Clientes y pedidos](./sample-xsd-file-customers-and-orders1.md).</span><span class="sxs-lookup"><span data-stu-id="e92be-110">The following example validates that the XML document from [Sample XML File: Customers and Orders (LINQ to XML)](./sample-xml-file-customers-and-orders-linq-to-xml-2.md) is valid per the schema from [Sample XSD File: Customers and Orders](./sample-xsd-file-customers-and-orders1.md).</span></span> <span data-ttu-id="e92be-111">A continuación modifica el documento XML de origen.</span><span class="sxs-lookup"><span data-stu-id="e92be-111">It then modifies the source XML document.</span></span> <span data-ttu-id="e92be-112">Cambia el atributo `CustomerID` del primer cliente.</span><span class="sxs-lookup"><span data-stu-id="e92be-112">It changes the `CustomerID` attribute on the first customer.</span></span> <span data-ttu-id="e92be-113">Tras el cambio, los pedidos harán referencia a un cliente que no existe, de forma que el documento XML ya no se validará.</span><span class="sxs-lookup"><span data-stu-id="e92be-113">After the change, orders will then refer to a customer that does not exist, so the XML document will no longer validate.</span></span>  
  
 <span data-ttu-id="e92be-114">Este ejemplo utiliza el siguiente documento XML: [Archivo XML de ejemplo: Clientes y pedidos (LINQ to XML)](./sample-xml-file-customers-and-orders-linq-to-xml-2.md).</span><span class="sxs-lookup"><span data-stu-id="e92be-114">This example uses the following XML document: [Sample XML File: Customers and Orders (LINQ to XML)](./sample-xml-file-customers-and-orders-linq-to-xml-2.md).</span></span>  
  
 <span data-ttu-id="e92be-115">En este ejemplo se usa el siguiente esquema XSD: [Archivo XSD de ejemplo: Clientes y pedidos](./sample-xsd-file-customers-and-orders1.md).</span><span class="sxs-lookup"><span data-stu-id="e92be-115">This example uses the following XSD schema: [Sample XSD File: Customers and Orders](./sample-xsd-file-customers-and-orders1.md).</span></span>  
  
```csharp  
XmlSchemaSet schemas = new XmlSchemaSet();  
schemas.Add("", "CustomersOrders.xsd");  
  
Console.WriteLine("Attempting to validate");  
XDocument custOrdDoc = XDocument.Load("CustomersOrders.xml");  
bool errors = false;  
custOrdDoc.Validate(schemas, (o, e) =>  
                     {  
                         Console.WriteLine("{0}", e.Message);  
                         errors = true;  
                     });  
Console.WriteLine("custOrdDoc {0}", errors ? "did not validate" : "validated");  
  
Console.WriteLine();  
// Modify the source document so that it will not validate.  
custOrdDoc.Root.Element("Orders").Element("Order").Element("CustomerID").Value = "AAAAA";  
Console.WriteLine("Attempting to validate after modification");  
errors = false;  
custOrdDoc.Validate(schemas, (o, e) =>  
                     {  
                         Console.WriteLine("{0}", e.Message);  
                         errors = true;  
                     });  
Console.WriteLine("custOrdDoc {0}", errors ? "did not validate" : "validated");  
```  
  
 <span data-ttu-id="e92be-116">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="e92be-116">This example produces the following output:</span></span>  
  
```output  
Attempting to validate  
custOrdDoc validated  
  
Attempting to validate after modification  
The key sequence 'AAAAA' in Keyref fails to refer to some key.  
custOrdDoc did not validate  
```  
  
## <a name="see-also"></a><span data-ttu-id="e92be-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="e92be-117">See also</span></span>

- <xref:System.Xml.Schema.Extensions.Validate%2A>
- <span data-ttu-id="e92be-118">[Creating XML Trees (C#)](creating-xml-trees-linq-to-xml-2.md) (Crear árboles XML (C#))</span><span class="sxs-lookup"><span data-stu-id="e92be-118">[Creating XML Trees (C#)](creating-xml-trees-linq-to-xml-2.md)</span></span>
