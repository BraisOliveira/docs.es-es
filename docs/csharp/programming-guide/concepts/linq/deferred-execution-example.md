---
title: Ejemplo de ejecución diferida (C#)
ms.date: 07/20/2015
ms.assetid: 50f4fbac-81fe-4f26-aedf-506e21419b19
ms.openlocfilehash: 08125f8da54db18423f90564a51fcffad8db44c2
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64598021"
---
# <a name="deferred-execution-example-c"></a><span data-ttu-id="1ed95-102">Ejemplo de ejecución diferida (C#)</span><span class="sxs-lookup"><span data-stu-id="1ed95-102">Deferred Execution Example (C#)</span></span>
<span data-ttu-id="1ed95-103">En este tema se muestra cómo la ejecución aplazada y la evaluación diferid afectan a la ejecución de las consultas de LINQ to XML.</span><span class="sxs-lookup"><span data-stu-id="1ed95-103">This topic shows how deferred execution and lazy evaluation affect the execution of your LINQ to XML queries.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1ed95-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1ed95-104">Example</span></span>  
 <span data-ttu-id="1ed95-105">El siguiente ejemplo muestra el orden de ejecución cuando se usa un método de extensión que utiliza la ejecución aplazada.</span><span class="sxs-lookup"><span data-stu-id="1ed95-105">The following example shows the order of execution when using an extension method that uses deferred execution.</span></span> <span data-ttu-id="1ed95-106">El ejemplo declara una matriz de tres cadenas.</span><span class="sxs-lookup"><span data-stu-id="1ed95-106">The example declares an array of three strings.</span></span> <span data-ttu-id="1ed95-107">A continuación recorre en iteración la recopilación devuelta por `ConvertCollectionToUpperCase`.</span><span class="sxs-lookup"><span data-stu-id="1ed95-107">It then iterates through the collection returned by `ConvertCollectionToUpperCase`.</span></span>  
  
```csharp  
public static class LocalExtensions  
{  
    public static IEnumerable<string>  
      ConvertCollectionToUpperCase(this IEnumerable<string> source)  
    {  
        foreach (string str in source)  
        {  
            Console.WriteLine("ToUpper: source {0}", str);  
            yield return str.ToUpper();  
        }  
    }  
}  
  
class Program  
{  
    static void Main(string[] args)  
    {  
        string[] stringArray = { "abc", "def", "ghi" };  
  
        var q = from str in stringArray.ConvertCollectionToUpperCase()  
                select str;  
  
        foreach (string str in q)  
            Console.WriteLine("Main: str {0}", str);  
    }  
}  
```  
  
 <span data-ttu-id="1ed95-108">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="1ed95-108">This example produces the following output:</span></span>  
  
```  
ToUpper: source abc  
Main: str ABC  
ToUpper: source def  
Main: str DEF  
ToUpper: source ghi  
Main: str GHI  
```  
  
 <span data-ttu-id="1ed95-109">Tenga en cuenta que durante el recorrido en iteración de la recopilación devuelta por `ConvertCollectionToUpperCase`, cada elemento se recupera de la matriz de cadenas de origen y se convierte a mayúsculas antes de que se recupere el siguiente elemento de la matriz de cadenas de origen.</span><span class="sxs-lookup"><span data-stu-id="1ed95-109">Notice that when iterating through the collection returned by `ConvertCollectionToUpperCase`, each item is retrieved from the source string array and converted to uppercase before the next item is retrieved from the source string array.</span></span>  
  
 <span data-ttu-id="1ed95-110">Puede ver que no se convierte a mayúsculas toda la matriz de cadenas antes de que se procese cada elemento en el bucle `foreach` de `Main`.</span><span class="sxs-lookup"><span data-stu-id="1ed95-110">You can see that the entire array of strings is not converted to uppercase before each item in the returned collection is processed in the `foreach` loop in `Main`.</span></span>  
  
 <span data-ttu-id="1ed95-111">En el siguiente tema de este tutorial se ilustra el encadenado de cadenas juntas:</span><span class="sxs-lookup"><span data-stu-id="1ed95-111">The next topic in this tutorial illustrates chaining queries together:</span></span>  
  
- <span data-ttu-id="1ed95-112">[Chaining Queries Example (C#)](../../../../csharp/programming-guide/concepts/linq/chaining-queries-example.md) (Ejemplo de encadenamiento de consultas (C#))</span><span class="sxs-lookup"><span data-stu-id="1ed95-112">[Chaining Queries Example (C#)](../../../../csharp/programming-guide/concepts/linq/chaining-queries-example.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ed95-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="1ed95-113">See also</span></span>

- [<span data-ttu-id="1ed95-114">Tutorial: Encadenar cadenas juntas (C#)</span><span class="sxs-lookup"><span data-stu-id="1ed95-114">Tutorial: Chaining Queries Together (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/tutorial-chaining-queries-together.md)
