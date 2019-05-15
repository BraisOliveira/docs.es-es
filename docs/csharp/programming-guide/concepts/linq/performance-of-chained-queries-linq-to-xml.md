---
title: Rendimiento de consultas encadenadas (LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: b2f1d715-8946-4dc0-8d56-fb3d1bba54a6
ms.openlocfilehash: da01901a8c4208965a339cb3cf446f054f65638b
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64596849"
---
# <a name="performance-of-chained-queries-linq-to-xml-c"></a><span data-ttu-id="a5825-102">Rendimiento de consultas encadenadas (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="a5825-102">Performance of Chained Queries (LINQ to XML) (C#)</span></span>
<span data-ttu-id="a5825-103">Una de las ventajas más importantes de LINQ (y LINQ to XML) es que las consultas encadenadas funcionan igual de bien que una sola consulta más grande y complicada.</span><span class="sxs-lookup"><span data-stu-id="a5825-103">One of the most important benefits of LINQ (and LINQ to XML) is that chained queries can perform as well as a single larger, more complicated query.</span></span>  
  
 <span data-ttu-id="a5825-104">Una consulta encadenada es una consulta que usa otra consulta como su origen.</span><span class="sxs-lookup"><span data-stu-id="a5825-104">A chained query is a query that uses another query as its source.</span></span> <span data-ttu-id="a5825-105">Por ejemplo, en el siguiente código simple, `query2` es el origen de `query1`:</span><span class="sxs-lookup"><span data-stu-id="a5825-105">For example, in the following simple code, `query2` has `query1` as its source:</span></span>  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("Child", 1),  
    new XElement("Child", 2),  
    new XElement("Child", 3),  
    new XElement("Child", 4)  
);  
  
var query1 = from x in root.Elements("Child")  
             where (int)x >= 3  
             select x;  
  
var query2 = from e in query1  
             where (int)e % 2 == 0  
             select e;  
  
foreach (var i in query2)  
    Console.WriteLine("{0}", (int)i);  
```  
  
 <span data-ttu-id="a5825-106">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="a5825-106">This example produces the following output:</span></span>  
  
```  
4  
```  
  
 <span data-ttu-id="a5825-107">Esta consulta encadenada proporciona el mismo perfil de rendimiento que si se recorriese en iteración una lista vinculada.</span><span class="sxs-lookup"><span data-stu-id="a5825-107">This chained query provides the same performance profile as iterating through a linked list.</span></span>  
  
- <span data-ttu-id="a5825-108">El eje <xref:System.Xml.Linq.XContainer.Elements%2A> tiene básicamente el mismo rendimiento que si se recorriese en iteración una lista vinculada.</span><span class="sxs-lookup"><span data-stu-id="a5825-108">The <xref:System.Xml.Linq.XContainer.Elements%2A> axis has essentially the same performance as iterating through a linked list.</span></span> <span data-ttu-id="a5825-109"><xref:System.Xml.Linq.XContainer.Elements%2A> se implementa como iterador con ejecución aplazada.</span><span class="sxs-lookup"><span data-stu-id="a5825-109"><xref:System.Xml.Linq.XContainer.Elements%2A> is implemented as an iterator with deferred execution.</span></span> <span data-ttu-id="a5825-110">Es decir, realiza trabajo adicional además de recorrer en iteración la lista vinculada, como asignar el objeto iterador y mantener el seguimiento del estado de la ejecución.</span><span class="sxs-lookup"><span data-stu-id="a5825-110">This means that it does some work in addition to iterating through the linked list, such as allocating the iterator object and keeping track of execution state.</span></span> <span data-ttu-id="a5825-111">Este trabajo se puede dividir en dos categorías: el trabajo que se realiza cuando se configura el iterador y el que se lleva a cabo durante cada iteración.</span><span class="sxs-lookup"><span data-stu-id="a5825-111">This work can be divided into two categories: the work that is done at the time the iterator is set up, and the work that is done during each iteration.</span></span> <span data-ttu-id="a5825-112">El trabajo de configuración es un trabajo mínimo y fijo, mientras que el realizado durante cada iteración es proporcional al número de elementos de la colección de origen.</span><span class="sxs-lookup"><span data-stu-id="a5825-112">The setup work is a small, fixed amount of work and the work done during each iteration is proportional to the number of items in the source collection.</span></span>  
  
- <span data-ttu-id="a5825-113">En `query1`, la cláusula `where` provoca la llamada al método <xref:System.Linq.Enumerable.Where%2A> por parte de la consulta.</span><span class="sxs-lookup"><span data-stu-id="a5825-113">In `query1`, the `where` clause causes the query to call the <xref:System.Linq.Enumerable.Where%2A> method.</span></span> <span data-ttu-id="a5825-114">Este método también se implementa como iterador.</span><span class="sxs-lookup"><span data-stu-id="a5825-114">This method is also implemented as an iterator.</span></span> <span data-ttu-id="a5825-115">El trabajo de configuración está formado por la creación de una instancia del delegado que hará referencia a la expresión lambda, más la configuración normal de un iterador.</span><span class="sxs-lookup"><span data-stu-id="a5825-115">The setup work consists of instantiating the delegate that will reference the lambda expression, plus the normal setup for an iterator.</span></span> <span data-ttu-id="a5825-116">Con cada iteración, se llama al delegado para que ejecute el predicado.</span><span class="sxs-lookup"><span data-stu-id="a5825-116">With each iteration, the delegate is called to execute the predicate.</span></span> <span data-ttu-id="a5825-117">El trabajo de configuración y el realizado durante cada iteración es parecido al llevado a cabo mientras se recorre en iteración el eje.</span><span class="sxs-lookup"><span data-stu-id="a5825-117">The setup work and the work done during each iteration is the similar to the work done while iterating through the axis.</span></span>  
  
- <span data-ttu-id="a5825-118">En `query1`, la cláusula Select provoca la llamada al método <xref:System.Linq.Enumerable.Select%2A> por parte de la consulta.</span><span class="sxs-lookup"><span data-stu-id="a5825-118">In `query1`, the select clause causes the query to call the <xref:System.Linq.Enumerable.Select%2A> method.</span></span> <span data-ttu-id="a5825-119">Este método tiene el mismo perfil de rendimiento que el método <xref:System.Linq.Enumerable.Where%2A>.</span><span class="sxs-lookup"><span data-stu-id="a5825-119">This method has the same performance profile as the <xref:System.Linq.Enumerable.Where%2A> method.</span></span>  
  
- <span data-ttu-id="a5825-120">En `query2`, tanto la cláusula `where` como la cláusula `select` tienen el mismo perfil de rendimiento que en `query1`.</span><span class="sxs-lookup"><span data-stu-id="a5825-120">In `query2`, both the `where` clause and the `select` clause have the same performance profile as in `query1`.</span></span>  
  
 <span data-ttu-id="a5825-121">Por lo tanto, la iteración por `query2` es directamente proporcional al número de elementos del origen de la primera consulta, es decir, tiempo lineal.</span><span class="sxs-lookup"><span data-stu-id="a5825-121">The iteration through `query2` is therefore directly proportional to the number of items in the source of the first query, in other words, linear time.</span></span> <span data-ttu-id="a5825-122">Un ejemplo de Visual Basic correspondiente tendría el mismo perfil de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="a5825-122">A corresponding Visual Basic example would have the same performance profile.</span></span>  
  
 <span data-ttu-id="a5825-123">Para más información sobre iteradores, vea [yield](../../../../csharp/language-reference/keywords/yield.md).</span><span class="sxs-lookup"><span data-stu-id="a5825-123">For more information on iterators, see [yield](../../../../csharp/language-reference/keywords/yield.md).</span></span>  
  
 <span data-ttu-id="a5825-124">Para obtener un tutorial más detallado sobre el encadenamiento de consultas, vea [Tutorial: Encadenar consultas juntas](../../../../csharp/programming-guide/concepts/linq/tutorial-chaining-queries-together.md).</span><span class="sxs-lookup"><span data-stu-id="a5825-124">For a more detailed tutorial on chaining queries together, see [Tutorial: Chaining Queries Together](../../../../csharp/programming-guide/concepts/linq/tutorial-chaining-queries-together.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5825-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="a5825-125">See also</span></span>

- [<span data-ttu-id="a5825-126">Rendimiento (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="a5825-126">Performance (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/performance-linq-to-xml.md)
