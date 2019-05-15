---
title: 'Procedimiento Devolver subconjuntos de propiedades de elementos en una consulta: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- anonymous types [C#], for subsets of element properties
ms.assetid: fabdf349-f443-4e3f-8368-6c471be1dd7b
ms.openlocfilehash: da4ecb11c51f42c2297b6d40ed9a963590b3f441
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64599988"
---
# <a name="how-to-return-subsets-of-element-properties-in-a-query-c-programming-guide"></a><span data-ttu-id="cd95a-102">Procedimiento Devolver subconjuntos de propiedades de elementos en una consulta (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="cd95a-102">How to: Return Subsets of Element Properties in a Query (C# Programming Guide)</span></span>
<span data-ttu-id="cd95a-103">Use un tipo anónimo en una expresión de consulta cuando se cumplan estas dos condiciones:</span><span class="sxs-lookup"><span data-stu-id="cd95a-103">Use an anonymous type in a query expression when both of these conditions apply:</span></span>  
  
- <span data-ttu-id="cd95a-104">Solo quiere algunas de las propiedades de cada elemento de origen.</span><span class="sxs-lookup"><span data-stu-id="cd95a-104">You want to return only some of the properties of each source element.</span></span>  
  
- <span data-ttu-id="cd95a-105">No es necesario almacenar los resultados de la consulta fuera del ámbito del método en el que se ejecuta la consulta.</span><span class="sxs-lookup"><span data-stu-id="cd95a-105">You do not have to store the query results outside the scope of the method in which the query is executed.</span></span>  
  
 <span data-ttu-id="cd95a-106">Si solo quiere devolver una propiedad o campo de cada elemento de origen, puede usar simplemente el operador de punto en la cláusula `select`.</span><span class="sxs-lookup"><span data-stu-id="cd95a-106">If you only want to return one property or field from each source element, then you can just use the dot operator in the `select` clause.</span></span> <span data-ttu-id="cd95a-107">Por ejemplo, para devolver solo el `ID` de cada `student`, escriba la cláusula `select` como sigue:</span><span class="sxs-lookup"><span data-stu-id="cd95a-107">For example, to return only the `ID` of each `student`, write the `select` clause as follows:</span></span>  
  
```  
select student.ID;  
```  
  
## <a name="example"></a><span data-ttu-id="cd95a-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cd95a-108">Example</span></span>  
 <span data-ttu-id="cd95a-109">En el ejemplo siguiente se muestra cómo usar un tipo anónimo para devolver solo un subconjunto de las propiedades de cada elemento de origen que coincida con la condición especificada.</span><span class="sxs-lookup"><span data-stu-id="cd95a-109">The following example shows how to use an anonymous type to return only a subset of the properties of each source element that matches the specified condition.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#31)]  
  
 <span data-ttu-id="cd95a-110">Tenga en cuenta que, si no se especifica ningún nombre, el tipo anónimo usa los nombres del elemento de origen para sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="cd95a-110">Note that the anonymous type uses the source element's names for its properties if no names are specified.</span></span> <span data-ttu-id="cd95a-111">Para asignar nombres nuevos a las propiedades del tipo anónimo, escriba la instrucción `select` como sigue:</span><span class="sxs-lookup"><span data-stu-id="cd95a-111">To give new names to the properties in the anonymous type, write the `select` statement as follows:</span></span>  
  
```  
select new { First = student.FirstName, Last = student.LastName };  
```  
  
 <span data-ttu-id="cd95a-112">Si lo intenta en el ejemplo anterior, también debe cambiar la instrucción `Console.WriteLine`:</span><span class="sxs-lookup"><span data-stu-id="cd95a-112">If you try this in the previous example, then the `Console.WriteLine` statement must also change:</span></span>  
  
```csharp  
Console.WriteLine(student.First + " " + student.Last);  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="cd95a-113">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="cd95a-113">Compiling the Code</span></span>  
  
- <span data-ttu-id="cd95a-114">Para ejecutar este código, copie y pegue la clase en un proyecto de aplicación de la consola de Visual C# creado en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="cd95a-114">To run this code, copy and paste the class into a Visual C# console application project that has been created in Visual Studio.</span></span> <span data-ttu-id="cd95a-115">De forma predeterminada, este proyecto tiene como destino la versión 3.5 de [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], y tendrá una referencia a System.Core.dll y una directiva `using` para System.Linq.</span><span class="sxs-lookup"><span data-stu-id="cd95a-115">By default, this project targets version 3.5 of the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], and it will have a reference to System.Core.dll and a `using` directive for System.Linq.</span></span> <span data-ttu-id="cd95a-116">Si faltan alguno de estos requisitos del proyecto, se puede agregar manualmente.</span><span class="sxs-lookup"><span data-stu-id="cd95a-116">If one or more of these requirements are missing from the project, you can add them manually.</span></span>   
  
## <a name="see-also"></a><span data-ttu-id="cd95a-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="cd95a-117">See also</span></span>

- [<span data-ttu-id="cd95a-118">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="cd95a-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="cd95a-119">Tipos anónimos</span><span class="sxs-lookup"><span data-stu-id="cd95a-119">Anonymous Types</span></span>](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)
- [<span data-ttu-id="cd95a-120">Expresiones de consulta LINQ</span><span class="sxs-lookup"><span data-stu-id="cd95a-120">LINQ Query Expressions</span></span>](../../../csharp/programming-guide/linq-query-expressions/index.md)
