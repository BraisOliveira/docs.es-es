---
title: Agrupar datos (C#)
ms.date: 07/20/2015
ms.assetid: e414e9e4-343a-4e6e-858f-4a30c5e64492
ms.openlocfilehash: a85babc43f673711fe1bdfa5cec1836a5073c785
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64753921"
---
# <a name="grouping-data-c"></a><span data-ttu-id="163de-102">Agrupar datos (C#)</span><span class="sxs-lookup"><span data-stu-id="163de-102">Grouping Data (C#)</span></span>
<span data-ttu-id="163de-103">El agrupamiento hace referencia a la operación de colocar los datos en grupos de manera que los elementos de cada grupo compartan un atributo común.</span><span class="sxs-lookup"><span data-stu-id="163de-103">Grouping refers to the operation of putting data into groups so that the elements in each group share a common attribute.</span></span>  
  
 <span data-ttu-id="163de-104">La ilustración siguiente muestra los resultados de agrupar una secuencia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="163de-104">The following illustration shows the results of grouping a sequence of characters.</span></span> <span data-ttu-id="163de-105">La clave de cada grupo es el carácter.</span><span class="sxs-lookup"><span data-stu-id="163de-105">The key for each group is the character.</span></span>  
  
 ![Diagrama que muestra una operación de agrupación de LINQ.](./media/grouping-data/linq-group-operation.png)  
  
 <span data-ttu-id="163de-107">Los métodos de operador de consulta estándar que agrupan elementos de datos se enumeran en la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="163de-107">The standard query operator methods that group data elements are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="163de-108">Métodos</span><span class="sxs-lookup"><span data-stu-id="163de-108">Methods</span></span>  
  
|<span data-ttu-id="163de-109">Nombre del método</span><span class="sxs-lookup"><span data-stu-id="163de-109">Method Name</span></span>|<span data-ttu-id="163de-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="163de-110">Description</span></span>|<span data-ttu-id="163de-111">Sintaxis de la expresión de consulta de C#</span><span class="sxs-lookup"><span data-stu-id="163de-111">C# Query Expression Syntax</span></span>|<span data-ttu-id="163de-112">Más información</span><span class="sxs-lookup"><span data-stu-id="163de-112">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="163de-113">GroupBy</span><span class="sxs-lookup"><span data-stu-id="163de-113">GroupBy</span></span>|<span data-ttu-id="163de-114">Agrupa los elementos que comparten un atributo común.</span><span class="sxs-lookup"><span data-stu-id="163de-114">Groups elements that share a common attribute.</span></span> <span data-ttu-id="163de-115">Cada grupo se representa mediante un objeto <xref:System.Linq.IGrouping%602>.</span><span class="sxs-lookup"><span data-stu-id="163de-115">Each group is represented by an <xref:System.Linq.IGrouping%602> object.</span></span>|`group … by`<br /><br /> <span data-ttu-id="163de-116">o bien</span><span class="sxs-lookup"><span data-stu-id="163de-116">-or-</span></span><br /><br /> `group … by … into …`|<xref:System.Linq.Enumerable.GroupBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.GroupBy%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="163de-117">ToLookup</span><span class="sxs-lookup"><span data-stu-id="163de-117">ToLookup</span></span>|<span data-ttu-id="163de-118">Inserta elementos a una <xref:System.Linq.Lookup%602> (un diccionario uno a varios) basándose en una función de selector de claves.</span><span class="sxs-lookup"><span data-stu-id="163de-118">Inserts elements into a <xref:System.Linq.Lookup%602> (a one-to-many dictionary) based on a key selector function.</span></span>|<span data-ttu-id="163de-119">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="163de-119">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="163de-120">Ejemplo de sintaxis de expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="163de-120">Query Expression Syntax Example</span></span>  
 <span data-ttu-id="163de-121">El ejemplo de código siguiente usa la cláusula `group by` para agrupar los enteros de una lista según sean pares o impares.</span><span class="sxs-lookup"><span data-stu-id="163de-121">The following code example uses the `group by` clause to group integers in a list according to whether they are even or odd.</span></span>  
  
```csharp  
List<int> numbers = new List<int>() { 35, 44, 200, 84, 3987, 4, 199, 329, 446, 208 };  
  
IEnumerable<IGrouping<int, int>> query = from number in numbers  
                                         group number by number % 2;  
  
foreach (var group in query)  
{  
    Console.WriteLine(group.Key == 0 ? "\nEven numbers:" : "\nOdd numbers:");  
    foreach (int i in group)  
        Console.WriteLine(i);  
}  
  
/* This code produces the following output:  
  
    Odd numbers:  
    35  
    3987  
    199  
    329  
  
    Even numbers:  
    44  
    200  
    84  
    4  
    446  
    208  
*/  
```  
  
## <a name="see-also"></a><span data-ttu-id="163de-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="163de-122">See also</span></span>

- <xref:System.Linq>
- <span data-ttu-id="163de-123">[Standard Query Operators Overview (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) (Información general sobre operadores de consulta estándar (C#))</span><span class="sxs-lookup"><span data-stu-id="163de-123">[Standard Query Operators Overview (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)</span></span>
- [<span data-ttu-id="163de-124">group (cláusula)</span><span class="sxs-lookup"><span data-stu-id="163de-124">group clause</span></span>](../../../../csharp/language-reference/keywords/group-clause.md)
- [<span data-ttu-id="163de-125">Cómo: Crear un grupo anidado</span><span class="sxs-lookup"><span data-stu-id="163de-125">How to: Create a Nested Group</span></span>](../../../../csharp/programming-guide/linq-query-expressions/how-to-create-a-nested-group.md)
- [<span data-ttu-id="163de-126">Cómo: Agrupar archivos por extensión (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="163de-126">How to: Group Files by Extension (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-group-files-by-extension-linq.md)
- [<span data-ttu-id="163de-127">Cómo: Agrupar los resultados de consultas</span><span class="sxs-lookup"><span data-stu-id="163de-127">How to: Group Query Results</span></span>](../../../../csharp/programming-guide/linq-query-expressions/how-to-group-query-results.md)
- [<span data-ttu-id="163de-128">Cómo: Realizar una subconsulta en una operación de agrupación</span><span class="sxs-lookup"><span data-stu-id="163de-128">How to: Perform a Subquery on a Grouping Operation</span></span>](../../../../csharp/programming-guide/linq-query-expressions/how-to-perform-a-subquery-on-a-grouping-operation.md)
- [<span data-ttu-id="163de-129">Cómo: Dividir un archivo en varios mediante el uso de grupos (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="163de-129">How to: Split a File Into Many Files by Using Groups (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-split-a-file-into-many-files-by-using-groups-linq.md)
