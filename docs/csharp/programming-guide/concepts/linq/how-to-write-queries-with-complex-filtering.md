---
title: Procedimiento para escribir consultas con filtrado complejo (C#)
ms.date: 07/20/2015
ms.assetid: 4065d901-cf89-4e47-8bf9-abb65acfb003
ms.openlocfilehash: 7a90a754036008463646321a3e9b9b7d83a3be33
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2019
ms.locfileid: "66484586"
---
# <a name="how-to-write-queries-with-complex-filtering-c"></a><span data-ttu-id="cbc7e-102">Procedimiento para escribir consultas con filtrado complejo (C#)</span><span class="sxs-lookup"><span data-stu-id="cbc7e-102">How to: Write Queries with Complex Filtering (C#)</span></span>
<span data-ttu-id="cbc7e-103">Es posible que desee escribir consultas LINQ to XML con filtros complejos.</span><span class="sxs-lookup"><span data-stu-id="cbc7e-103">Sometimes you want to write LINQ to XML queries with complex filters.</span></span> <span data-ttu-id="cbc7e-104">Por ejemplo, quizás debe buscar todos los elementos que tienen un elemento secundario con un valor y un nombre específicos.</span><span class="sxs-lookup"><span data-stu-id="cbc7e-104">For example, you might have to find all elements that have a child element with a particular name and value.</span></span> <span data-ttu-id="cbc7e-105">En este tema se proporciona un ejemplo de escritura de una consulta con un filtrado complejo.</span><span class="sxs-lookup"><span data-stu-id="cbc7e-105">This topic gives an example of writing a query with complex filtering.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cbc7e-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cbc7e-106">Example</span></span>  
 <span data-ttu-id="cbc7e-107">En este ejemplo se muestra cómo buscar todos los elementos `PurchaseOrder` que tienen un elemento `Address` secundario que tiene un atributo `Type` igual a "Shipping" (envío) y un elemento `State` secundario igual a "NY".</span><span class="sxs-lookup"><span data-stu-id="cbc7e-107">This example shows how to find all `PurchaseOrder` elements that have a child `Address` element that has a `Type` attribute equal to "Shipping" and a child `State` element equal to "NY".</span></span> <span data-ttu-id="cbc7e-108">Utiliza una consulta anidada en la cláusula `Where` y el operador `Any` devuelve `true` si la colección tiene elementos en ella.</span><span class="sxs-lookup"><span data-stu-id="cbc7e-108">It uses a nested query in the `Where` clause, and the `Any` operator returns `true` if the collection has any elements in it.</span></span> <span data-ttu-id="cbc7e-109">Para obtener información sobre cómo usar la sintaxis de consultas basadas en métodos, vea [Query Syntax and Method Syntax in LINQ](../../../../csharp/programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md) (Sintaxis de consultas y sintaxis de métodos en LINQ).</span><span class="sxs-lookup"><span data-stu-id="cbc7e-109">For information about using method-based query syntax, see [Query Syntax and Method Syntax in LINQ](../../../../csharp/programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md).</span></span>  
  
 <span data-ttu-id="cbc7e-110">Este ejemplo utiliza el siguiente documento XML: [Archivo XML de ejemplo: Varios pedidos de compra (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="cbc7e-110">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="cbc7e-111">Para obtener más información sobre el operador `Any`, vea [Quantifier Operations (C#)](../../../../csharp/programming-guide/concepts/linq/quantifier-operations.md) (Operaciones cuantificadoras (C#)).</span><span class="sxs-lookup"><span data-stu-id="cbc7e-111">For more information about the `Any` operator, see [Quantifier Operations (C#)](../../../../csharp/programming-guide/concepts/linq/quantifier-operations.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("PurchaseOrders.xml");  
IEnumerable<XElement> purchaseOrders =  
    from el in root.Elements("PurchaseOrder")  
    where   
        (from add in el.Elements("Address")  
        where  
            (string)add.Attribute("Type") == "Shipping" &&  
            (string)add.Element("State") == "NY"  
        select add)  
        .Any()  
    select el;  
foreach (XElement el in purchaseOrders)  
    Console.WriteLine((string)el.Attribute("PurchaseOrderNumber"));  
```  
  
 <span data-ttu-id="cbc7e-112">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="cbc7e-112">This code produces the following output:</span></span>  
  
```  
99505  
```  
  
## <a name="example"></a><span data-ttu-id="cbc7e-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cbc7e-113">Example</span></span>  
 <span data-ttu-id="cbc7e-114">El siguiente ejemplo muestra la misma consulta sobre un XML que se encuentra en un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="cbc7e-114">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="cbc7e-115">Para obtener más información, vea [Working with XML Namespaces (C#)](../../../../csharp/programming-guide/concepts/linq/namespaces-overview-linq-to-xml.md) (Trabajar con espacios de nombres XML [C#]).</span><span class="sxs-lookup"><span data-stu-id="cbc7e-115">For more information, see [Working with XML Namespaces (C#)](../../../../csharp/programming-guide/concepts/linq/namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="cbc7e-116">Este ejemplo utiliza el siguiente documento XML: [Archivo XML de ejemplo: Varios pedidos de compra en un espacio de nombres](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="cbc7e-116">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders in a Namespace](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-in-a-namespace.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("PurchaseOrdersInNamespace.xml");  
XNamespace aw = "http://www.adventure-works.com";  
IEnumerable<XElement> purchaseOrders =  
    from el in root.Elements(aw + "PurchaseOrder")  
    where  
        (from add in el.Elements(aw + "Address")  
         where  
             (string)add.Attribute(aw + "Type") == "Shipping" &&  
             (string)add.Element(aw + "State") == "NY"  
         select add)  
        .Any()  
    select el;  
foreach (XElement el in purchaseOrders)  
    Console.WriteLine((string)el.Attribute(aw + "PurchaseOrderNumber"));  
```  
  
 <span data-ttu-id="cbc7e-117">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="cbc7e-117">This code produces the following output:</span></span>  
  
```  
99505  
```  
  
## <a name="see-also"></a><span data-ttu-id="cbc7e-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="cbc7e-118">See also</span></span>

- <xref:System.Xml.Linq.XElement.Attribute%2A>
- <xref:System.Xml.Linq.XContainer.Elements%2A>
- <span data-ttu-id="cbc7e-119">[Projection Operations (C#)](../../../../csharp/programming-guide/concepts/linq/projection-operations.md) (Operaciones de proyección [C#])</span><span class="sxs-lookup"><span data-stu-id="cbc7e-119">[Projection Operations (C#)](../../../../csharp/programming-guide/concepts/linq/projection-operations.md)</span></span>
- <span data-ttu-id="cbc7e-120">[Quantifier Operations (C#)](../../../../csharp/programming-guide/concepts/linq/quantifier-operations.md) (Operaciones cuantificadoras (C#))</span><span class="sxs-lookup"><span data-stu-id="cbc7e-120">[Quantifier Operations (C#)](../../../../csharp/programming-guide/concepts/linq/quantifier-operations.md)</span></span>
