---
title: Eventos de LINQ to XML (C#)
ms.date: 07/20/2015
ms.assetid: ce7de951-cba7-4870-9962-733eb01cd680
ms.openlocfilehash: 8278d3eac9d1e149cbfe64e184439ef9ac3cd39b
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2019
ms.locfileid: "66484339"
---
# <a name="linq-to-xml-events-c"></a><span data-ttu-id="539e3-102">Eventos de LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="539e3-102">LINQ to XML Events (C#)</span></span>
<span data-ttu-id="539e3-103">Los eventos de [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] permiten recibir notificaciones cuando se modifica un árbol XML.</span><span class="sxs-lookup"><span data-stu-id="539e3-103">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] events enable you to be notified when an XML tree is altered.</span></span>  
  
 <span data-ttu-id="539e3-104">Puede agregar eventos a una instancia de cualquier <xref:System.Xml.Linq.XObject>.</span><span class="sxs-lookup"><span data-stu-id="539e3-104">You can add events to an instance of any <xref:System.Xml.Linq.XObject>.</span></span> <span data-ttu-id="539e3-105">El controlador de eventos recibirá entonces eventos relacionados con las modificaciones realizadas en ese <xref:System.Xml.Linq.XObject> y en cualquiera de sus descendientes.</span><span class="sxs-lookup"><span data-stu-id="539e3-105">The event handler will then receive events for modifications to that <xref:System.Xml.Linq.XObject> and any of its descendants.</span></span> <span data-ttu-id="539e3-106">Por ejemplo, puede agregar un controlador de evento a la raíz del árbol y controlar todas las modificaciones que se realicen al árbol desde ese controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="539e3-106">For example, you can add an event handler to the root of the tree, and handle all modifications to the tree from that event handler.</span></span>  
  
 <span data-ttu-id="539e3-107">Para obtener ejemplos de eventos [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], vea <xref:System.Xml.Linq.XObject.Changing> y <xref:System.Xml.Linq.XObject.Changed>.</span><span class="sxs-lookup"><span data-stu-id="539e3-107">For examples of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] events, see <xref:System.Xml.Linq.XObject.Changing> and <xref:System.Xml.Linq.XObject.Changed>.</span></span>  
  
## <a name="types-and-events"></a><span data-ttu-id="539e3-108">Tipos y eventos</span><span class="sxs-lookup"><span data-stu-id="539e3-108">Types and Events</span></span>  
 <span data-ttu-id="539e3-109">Puede utilizar los siguientes tipos a la hora de trabajar con eventos:</span><span class="sxs-lookup"><span data-stu-id="539e3-109">You use the following types when working with events:</span></span>  
  
|<span data-ttu-id="539e3-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="539e3-110">Type</span></span>|<span data-ttu-id="539e3-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="539e3-111">Description</span></span>|  
|----------|-----------------|  
|<xref:System.Xml.Linq.XObjectChange>|<span data-ttu-id="539e3-112">Especifica el tipo de evento cuando se genera éste para un <xref:System.Xml.Linq.XObject>.</span><span class="sxs-lookup"><span data-stu-id="539e3-112">Specifies the event type when an event is raised for an <xref:System.Xml.Linq.XObject>.</span></span>|  
|<xref:System.Xml.Linq.XObjectChangeEventArgs>|<span data-ttu-id="539e3-113">Proporciona datos para los eventos <xref:System.Xml.Linq.XObject.Changing> y <xref:System.Xml.Linq.XObject.Changed>.</span><span class="sxs-lookup"><span data-stu-id="539e3-113">Provides data for the <xref:System.Xml.Linq.XObject.Changing> and <xref:System.Xml.Linq.XObject.Changed> events.</span></span>|  
  
 <span data-ttu-id="539e3-114">Los siguientes eventos se generan cuando se modifica un árbol XML:</span><span class="sxs-lookup"><span data-stu-id="539e3-114">The following events are raised when you modify an XML tree:</span></span>  
  
|<span data-ttu-id="539e3-115">evento</span><span class="sxs-lookup"><span data-stu-id="539e3-115">Event</span></span>|<span data-ttu-id="539e3-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="539e3-116">Description</span></span>|  
|-----------|-----------------|  
|<xref:System.Xml.Linq.XObject.Changing>|<span data-ttu-id="539e3-117">Se produce justo antes de que este <xref:System.Xml.Linq.XObject> o cualquiera de sus descendientes se vayan a modificar.</span><span class="sxs-lookup"><span data-stu-id="539e3-117">Occurs just before this <xref:System.Xml.Linq.XObject> or any of its descendants is going to change.</span></span>|  
|<xref:System.Xml.Linq.XObject.Changed>|<span data-ttu-id="539e3-118">Se produce cuando ha cambiado un <xref:System.Xml.Linq.XObject> o cualquiera de sus descendientes.</span><span class="sxs-lookup"><span data-stu-id="539e3-118">Occurs when an <xref:System.Xml.Linq.XObject> has changed or any of its descendants have changed.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="539e3-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="539e3-119">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="539e3-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="539e3-120">Description</span></span>  
 <span data-ttu-id="539e3-121">Los eventos resultan útiles cuando desea mantener cierta información de agregado en un árbol XML.</span><span class="sxs-lookup"><span data-stu-id="539e3-121">Events are useful when you want to maintain some aggregate information in an XML tree.</span></span> <span data-ttu-id="539e3-122">Por ejemplo, quizá desee mantener el total de una factura que es la suma de los conceptos de la factura.</span><span class="sxs-lookup"><span data-stu-id="539e3-122">For example, you may want maintain an invoice total that is the sum of the line items of the invoice.</span></span> <span data-ttu-id="539e3-123">Este ejemplo utiliza eventos para mantener el total de todos los elementos secundarios que se encuentran bajo el elemento complejo `Items`.</span><span class="sxs-lookup"><span data-stu-id="539e3-123">This example uses events to maintain the total of all of the child elements under the complex element `Items`.</span></span>  
  
### <a name="code"></a><span data-ttu-id="539e3-124">Código</span><span class="sxs-lookup"><span data-stu-id="539e3-124">Code</span></span>  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("Total", "0"),  
    new XElement("Items")  
);  
XElement total = root.Element("Total");  
XElement items = root.Element("Items");  
items.Changed += (object sender, XObjectChangeEventArgs cea) =>  
{  
    switch (cea.ObjectChange)  
    {  
        case XObjectChange.Add:  
            if (sender is XElement)  
                total.Value = ((int)total + (int)(XElement)sender).ToString();  
            if (sender is XText)  
                total.Value = ((int)total + (int)((XText)sender).Parent).ToString();  
            break;  
        case XObjectChange.Remove:  
            if (sender is XElement)  
                total.Value = ((int)total - (int)(XElement)sender).ToString();  
            if (sender is XText)  
                total.Value = ((int)total - Int32.Parse(((XText)sender).Value)).ToString();  
            break;  
    }  
    Console.WriteLine("Changed {0} {1}",  
      sender.GetType().ToString(), cea.ObjectChange.ToString());  
};  
items.SetElementValue("Item1", 25);  
items.SetElementValue("Item2", 50);  
items.SetElementValue("Item2", 75);  
items.SetElementValue("Item3", 133);  
items.SetElementValue("Item1", null);  
items.SetElementValue("Item4", 100);  
Console.WriteLine("Total:{0}", (int)total);  
Console.WriteLine(root);  
```  
  
### <a name="comments"></a><span data-ttu-id="539e3-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="539e3-125">Comments</span></span>  
 <span data-ttu-id="539e3-126">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="539e3-126">This code produces the following output:</span></span>  
  
```  
Changed System.Xml.Linq.XElement Add  
Changed System.Xml.Linq.XElement Add  
Changed System.Xml.Linq.XText Remove  
Changed System.Xml.Linq.XText Add  
Changed System.Xml.Linq.XElement Add  
Changed System.Xml.Linq.XElement Remove  
Changed System.Xml.Linq.XElement Add  
Total:308  
<Root>  
  <Total>308</Total>  
  <Items>  
    <Item2>75</Item2>  
    <Item3>133</Item3>  
    <Item4>100</Item4>  
  </Items>  
</Root>  
```  
  