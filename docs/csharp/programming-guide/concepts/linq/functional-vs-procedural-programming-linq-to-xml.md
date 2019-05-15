---
title: Programación funcional frente a programación basada en procedimientos (LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: fc64e39c-a487-4882-9169-da4de97917d9
ms.openlocfilehash: 4c538011ce38708978f8b0f4866af3b3b4195a19
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64597143"
---
# <a name="functional-vs-procedural-programming-linq-to-xml-c"></a><span data-ttu-id="acb7e-102">Programación funcional frente a programación basada en procedimientos (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="acb7e-102">Functional vs. Procedural Programming (LINQ to XML) (C#)</span></span>
<span data-ttu-id="acb7e-103">Existen varios tipos de aplicaciones XML:</span><span class="sxs-lookup"><span data-stu-id="acb7e-103">There are various types of XML applications:</span></span>  
  
- <span data-ttu-id="acb7e-104">Algunas aplicaciones toman los documentos XML de origen y crean nuevos documentos XML que tienen una forma diferente que los documentos de origen.</span><span class="sxs-lookup"><span data-stu-id="acb7e-104">Some applications take source XML documents, and produce new XML documents that are in a different shape than the source documents.</span></span>  
  
- <span data-ttu-id="acb7e-105">Algunas aplicaciones toman documentos XML de origen y crean documentos de resultado de una forma totalmente diferente, como archivos HTML o de texto CSV.</span><span class="sxs-lookup"><span data-stu-id="acb7e-105">Some applications take source XML documents, and produce result documents in an entirely different form, such as HTML or CSV text files.</span></span>  
  
- <span data-ttu-id="acb7e-106">Algunas aplicaciones toman documentos XML de origen e insertan registros en una base de datos.</span><span class="sxs-lookup"><span data-stu-id="acb7e-106">Some applications take source XML documents, and insert records into a database.</span></span>  
  
- <span data-ttu-id="acb7e-107">Algunas aplicaciones toman datos de otro origen de datos, como una base de datos y crean documentos XML a partir de él.</span><span class="sxs-lookup"><span data-stu-id="acb7e-107">Some applications take data from another source, such as a database, and create XML documents from it.</span></span>  
  
 <span data-ttu-id="acb7e-108">Estos no son todos los tipos de aplicaciones XML, pero son un conjunto representativo de los tipos de funcionalidad que un programador XML debe implementar.</span><span class="sxs-lookup"><span data-stu-id="acb7e-108">These are not all of the types of XML applications, but these are a representative set of the types of functionality that an XML programmer has to implement.</span></span>  
  
 <span data-ttu-id="acb7e-109">Con todos esos tipos de aplicaciones un desarrollador puede tomar dos enfoques opuestos:</span><span class="sxs-lookup"><span data-stu-id="acb7e-109">With all of these types of applications, there are two contrasting approaches that a developer can take:</span></span>  
  
- <span data-ttu-id="acb7e-110">Construcción funcional usando un enfoque declarativo.</span><span class="sxs-lookup"><span data-stu-id="acb7e-110">Functional construction using a declarative approach.</span></span>  
  
- <span data-ttu-id="acb7e-111">Modificación del árbol XML en memoria usando código de procedimiento.</span><span class="sxs-lookup"><span data-stu-id="acb7e-111">In-memory XML tree modification using procedural code.</span></span>  
  
 <span data-ttu-id="acb7e-112">LINQ to XML admite ambos enfoques.</span><span class="sxs-lookup"><span data-stu-id="acb7e-112">LINQ to XML supports both approaches.</span></span>  
  
 <span data-ttu-id="acb7e-113">Cuando se utiliza el enfoque funcional, se escriben transformaciones que toman los documentos de origen y generan documentos de resultados completamente nuevos con la forma que se desee.</span><span class="sxs-lookup"><span data-stu-id="acb7e-113">When using the functional approach, you write transformations that take the source documents and generate completely new result documents with the desired shape.</span></span>  
  
 <span data-ttu-id="acb7e-114">Cuando se modifica un árbol XML, se escribe código que atraviese los nodos de un árbol XML y navegue por ellos en memoria para insertar, eliminar y modificar nodos según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="acb7e-114">When modifying an XML tree in place, you write code that traverses and navigates through nodes in an in-memory XML tree, inserting, deleting, and modifying nodes as necessary.</span></span>  
  
 <span data-ttu-id="acb7e-115">Puede usar LINQ to XML con cualquier enfoque.</span><span class="sxs-lookup"><span data-stu-id="acb7e-115">You can use LINQ to XML with either approach.</span></span> <span data-ttu-id="acb7e-116">Se usan las mismas clases y, en algunos casos, los mismos métodos.</span><span class="sxs-lookup"><span data-stu-id="acb7e-116">You use the same classes, and in some cases the same methods.</span></span> <span data-ttu-id="acb7e-117">No obstante, la estructura y los objetivos de los dos enfoques son muy diferentes.</span><span class="sxs-lookup"><span data-stu-id="acb7e-117">However, the structure and goals of the two approaches are very different.</span></span> <span data-ttu-id="acb7e-118">Por ejemplo, en situaciones diferentes, uno u otro enfoque tendrá a menudo un rendimiento mejor y usará más o menos memoria.</span><span class="sxs-lookup"><span data-stu-id="acb7e-118">For example, in different situations, one or the other approach will often have better performance, and use more or less memory.</span></span> <span data-ttu-id="acb7e-119">Asimismo, uno u otro enfoque será más fácil de escribir y proporcionará código más fácil de mantener.</span><span class="sxs-lookup"><span data-stu-id="acb7e-119">In addition, one or the other approach will be easier to write and yield more maintainable code.</span></span>  
  
 <span data-ttu-id="acb7e-120">Para obtener una comparación de los dos enfoques, vea [Diferencias entre la modificación del árbol XML en memoria y la construcción funcional (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/in-memory-xml-tree-modification-vs-functional-construction-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="acb7e-120">To see the two approaches contrasted, see [In-Memory XML Tree Modification vs. Functional Construction (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/in-memory-xml-tree-modification-vs-functional-construction-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="acb7e-121">Para obtener un tutorial sobre la escritura de transformaciones funcionales, vea [Pure Functional Transformations of XML (C#) (Transformaciones funcionales puras de XML (C#))](../../../../csharp/programming-guide/concepts/linq/pure-functional-transformations-of-xml.md).</span><span class="sxs-lookup"><span data-stu-id="acb7e-121">For a tutorial on writing functional transformations, see [Pure Functional Transformations of XML (C#)](../../../../csharp/programming-guide/concepts/linq/pure-functional-transformations-of-xml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acb7e-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="acb7e-122">See also</span></span>

- [<span data-ttu-id="acb7e-123">Información general sobre la programación de LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="acb7e-123">LINQ to XML Programming Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)
