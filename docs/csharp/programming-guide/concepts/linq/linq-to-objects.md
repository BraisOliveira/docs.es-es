---
title: LINQ to Objects (C#)
ms.date: 07/20/2015
ms.assetid: c5c2c178-3529-4f6c-b3df-2d5267af7f22
ms.openlocfilehash: 9e20b2c7278787671c7a27646b7cbaac78b57d5f
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/19/2019
ms.locfileid: "69591854"
---
# <a name="linq-to-objects-c"></a><span data-ttu-id="a18e9-102">LINQ to Objects (C#)</span><span class="sxs-lookup"><span data-stu-id="a18e9-102">LINQ to Objects (C#)</span></span>
<span data-ttu-id="a18e9-103">El término "LINQ to Objects" se refiere al uso de consultas LINQ con cualquier colección <xref:System.Collections.IEnumerable> o <xref:System.Collections.Generic.IEnumerable%601> directamente, sin usar un proveedor o una API de LINQ intermedios como [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md) o [LINQ to XML](./linq-to-xml-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a18e9-103">The term "LINQ to Objects" refers to the use of LINQ queries with any <xref:System.Collections.IEnumerable> or <xref:System.Collections.Generic.IEnumerable%601> collection directly, without the use of an intermediate LINQ provider or API such as [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md) or [LINQ to XML](./linq-to-xml-overview.md).</span></span> <span data-ttu-id="a18e9-104">Puede usar LINQ para consultar cualquier colección enumerable, como <xref:System.Collections.Generic.List%601>, <xref:System.Array> o <xref:System.Collections.Generic.Dictionary%602>.</span><span class="sxs-lookup"><span data-stu-id="a18e9-104">You can use LINQ to query any enumerable collections such as <xref:System.Collections.Generic.List%601>, <xref:System.Array>, or <xref:System.Collections.Generic.Dictionary%602>.</span></span> <span data-ttu-id="a18e9-105">La colección puede ser definida por el usuario o haber sido devuelta por una API de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a18e9-105">The collection may be user-defined or may be returned by a .NET Framework API.</span></span>  
  
 <span data-ttu-id="a18e9-106">Básicamente, LINQ to Objects representa un nuevo enfoque para las colecciones.</span><span class="sxs-lookup"><span data-stu-id="a18e9-106">In a basic sense, LINQ to Objects represents a new approach to collections.</span></span> <span data-ttu-id="a18e9-107">En el sistema antiguo, tenía que escribir complejos bucles `foreach` que especificaban cómo recuperar los datos de una colección.</span><span class="sxs-lookup"><span data-stu-id="a18e9-107">In the old way, you had to write complex `foreach` loops that specified how to retrieve data from a collection.</span></span> <span data-ttu-id="a18e9-108">En el enfoque de LINQ, se escribe código declarativo que describe qué se quiere recuperar.</span><span class="sxs-lookup"><span data-stu-id="a18e9-108">In the LINQ approach, you write declarative code that describes what you want to retrieve.</span></span>  
  
 <span data-ttu-id="a18e9-109">Además, las consultas LINQ ofrecen tres ventajas principales respecto a los bucles `foreach` tradicionales:</span><span class="sxs-lookup"><span data-stu-id="a18e9-109">In addition, LINQ queries offer three main advantages over traditional `foreach` loops:</span></span>  
  
1. <span data-ttu-id="a18e9-110">Son más concisas y legibles, especialmente cuando se filtran varias condiciones.</span><span class="sxs-lookup"><span data-stu-id="a18e9-110">They are more concise and readable, especially when filtering multiple conditions.</span></span>  
  
2. <span data-ttu-id="a18e9-111">Proporcionan funcionalidades eficaces para filtrar, ordenar y agrupar con un código de aplicación mínimo.</span><span class="sxs-lookup"><span data-stu-id="a18e9-111">They provide powerful filtering, ordering, and grouping capabilities with a minimum of application code.</span></span>  
  
3. <span data-ttu-id="a18e9-112">Se pueden migrar a otros orígenes de datos con muy poca o ninguna modificación.</span><span class="sxs-lookup"><span data-stu-id="a18e9-112">They can be ported to other data sources with little or no modification.</span></span>  
  
 <span data-ttu-id="a18e9-113">Por lo general, cuanto más compleja sea la operación que quiere realizar en los datos, más ventajas obtendrá al usar LINQ en lugar de las técnicas de iteración tradicionales.</span><span class="sxs-lookup"><span data-stu-id="a18e9-113">In general, the more complex the operation you want to perform on the data, the more benefit you will realize by using LINQ instead of traditional iteration techniques.</span></span>  
  
 <span data-ttu-id="a18e9-114">El propósito de esta sección es mostrar el enfoque de LINQ con algunos ejemplos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="a18e9-114">The purpose of this section is to demonstrate the LINQ approach with some select examples.</span></span> <span data-ttu-id="a18e9-115">No pretende ser exhaustiva.</span><span class="sxs-lookup"><span data-stu-id="a18e9-115">It is not intended to be exhaustive.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a18e9-116">En esta sección</span><span class="sxs-lookup"><span data-stu-id="a18e9-116">In This Section</span></span>  
 [<span data-ttu-id="a18e9-117">LINQ y cadenas (C#)</span><span class="sxs-lookup"><span data-stu-id="a18e9-117">LINQ and Strings (C#)</span></span>](./linq-and-strings.md)  
 <span data-ttu-id="a18e9-118">Explica cómo se puede usar LINQ para consultar y transformar cadenas y colecciones de cadenas.</span><span class="sxs-lookup"><span data-stu-id="a18e9-118">Explains how LINQ can be used to query and transform strings and collections of strings.</span></span> <span data-ttu-id="a18e9-119">También incluye vínculos a temas que muestran estos principios.</span><span class="sxs-lookup"><span data-stu-id="a18e9-119">Also includes links to topics that demonstrate these principles.</span></span>  
  
 [<span data-ttu-id="a18e9-120">LINQ y reflexión (C#)</span><span class="sxs-lookup"><span data-stu-id="a18e9-120">LINQ and Reflection (C#)</span></span>](./linq-and-reflection.md)  
 <span data-ttu-id="a18e9-121">Vincula a un ejemplo que muestra cómo usa LINQ la reflexión.</span><span class="sxs-lookup"><span data-stu-id="a18e9-121">Links to a sample that demonstrates how LINQ uses reflection.</span></span>  
  
 [<span data-ttu-id="a18e9-122">LINQ y directorios de archivos (C#)</span><span class="sxs-lookup"><span data-stu-id="a18e9-122">LINQ and File Directories (C#)</span></span>](./linq-and-file-directories.md)  
 <span data-ttu-id="a18e9-123">Explica cómo se puede usar LINQ para interactuar con sistemas de archivos.</span><span class="sxs-lookup"><span data-stu-id="a18e9-123">Explains how LINQ can be used to interact with file systems.</span></span> <span data-ttu-id="a18e9-124">También incluye vínculos a temas que muestran estos conceptos.</span><span class="sxs-lookup"><span data-stu-id="a18e9-124">Also includes links to topics that demonstrate these concepts.</span></span>  
  
 [<span data-ttu-id="a18e9-125">Cómo: Consultar un objeto ArrayList con LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="a18e9-125">How to: Query an ArrayList with LINQ (C#)</span></span>](./how-to-query-an-arraylist-with-linq.md)  
 <span data-ttu-id="a18e9-126">Muestra cómo consultar un objeto ArrayList en C#.</span><span class="sxs-lookup"><span data-stu-id="a18e9-126">Demonstrates how to query an ArrayList in C#.</span></span>  
  
 [<span data-ttu-id="a18e9-127">Cómo: Agregar métodos personalizados para las consultas de LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="a18e9-127">How to: Add Custom Methods for LINQ Queries (C#)</span></span>](./how-to-add-custom-methods-for-linq-queries.md)  
 <span data-ttu-id="a18e9-128">Explica cómo extender el conjunto de métodos que puede usar para consultas LINQ agregando métodos de extensión a la interfaz <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="a18e9-128">Explains how to extend the set of methods that you can use for LINQ queries by adding extension methods to the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span>  
  
 [<span data-ttu-id="a18e9-129">Language Integrated Query (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="a18e9-129">Language-Integrated Query (LINQ) (C#)</span></span>](./index.md)  
 <span data-ttu-id="a18e9-130">Proporciona vínculos a temas que explican LINQ y que proporcionan ejemplos de código que realizan consultas.</span><span class="sxs-lookup"><span data-stu-id="a18e9-130">Provides links to topics that explain LINQ and provide examples of code that perform queries.</span></span>
