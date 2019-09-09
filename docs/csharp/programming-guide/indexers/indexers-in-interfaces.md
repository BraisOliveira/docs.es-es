---
title: 'Indizadores en interfaces: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- indexers [C#], in interfaces
- accessors [C#], indexers
ms.assetid: e16b54bd-4a83-4f52-bd75-65819fca79e8
ms.openlocfilehash: 7f52df0283cf057c1cd6cc4fa87c0086da7e61d2
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70253003"
---
# <a name="indexers-in-interfaces-c-programming-guide"></a><span data-ttu-id="c6fa5-102">Indizadores en interfaces (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="c6fa5-102">Indexers in Interfaces (C# Programming Guide)</span></span>
<span data-ttu-id="c6fa5-103">Los indexadores se pueden declarar en una [interfaz](../../language-reference/keywords/interface.md).</span><span class="sxs-lookup"><span data-stu-id="c6fa5-103">Indexers can be declared on an [interface](../../language-reference/keywords/interface.md).</span></span> <span data-ttu-id="c6fa5-104">Los descriptores de acceso de los indexadores de interfaz se diferencian de los descriptores de acceso de los indexadores de [clase](../../language-reference/keywords/class.md) de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="c6fa5-104">Accessors of interface indexers differ from the accessors of [class](../../language-reference/keywords/class.md) indexers in the following ways:</span></span>  
  
- <span data-ttu-id="c6fa5-105">Los descriptores de acceso de interfaz no usan modificadores.</span><span class="sxs-lookup"><span data-stu-id="c6fa5-105">Interface accessors do not use modifiers.</span></span>  
  
- <span data-ttu-id="c6fa5-106">Un descriptor de acceso de interfaz no tiene un cuerpo.</span><span class="sxs-lookup"><span data-stu-id="c6fa5-106">An interface accessor does not have a body.</span></span>  
  
 <span data-ttu-id="c6fa5-107">Por tanto, el propósito del descriptor de acceso es indicar si el indexador es de lectura y escritura, de solo lectura o de solo escritura.</span><span class="sxs-lookup"><span data-stu-id="c6fa5-107">Thus, the purpose of the accessor is to indicate whether the indexer is read-write, read-only, or write-only.</span></span>  
  
 <span data-ttu-id="c6fa5-108">A continuación tiene un ejemplo de un descriptor de acceso de indexador de interfaz:</span><span class="sxs-lookup"><span data-stu-id="c6fa5-108">The following is an example of an interface indexer accessor:</span></span>  
  
 [!code-csharp[csProgGuideIndexers#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideIndexers/CS/Indexers.cs#3)]  
  
 <span data-ttu-id="c6fa5-109">La firma de un indexador debe ser diferente de las firmas de los demás indexadores declarados en la misma interfaz.</span><span class="sxs-lookup"><span data-stu-id="c6fa5-109">The signature of an indexer must differ from the signatures of all other indexers declared in the same interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c6fa5-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c6fa5-110">Example</span></span>  
 <span data-ttu-id="c6fa5-111">En el siguiente ejemplo, se muestra cómo implementar indexadores de interfaz.</span><span class="sxs-lookup"><span data-stu-id="c6fa5-111">The following example shows how to implement interface indexers.</span></span>  
  
 [!code-csharp[csProgGuideIndexers#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideIndexers/CS/Indexers.cs#4)]  
  
 <span data-ttu-id="c6fa5-112">En el ejemplo anterior, podría usar la implementación del miembro de interfaz explícita al usar el nombre completo del miembro de interfaz.</span><span class="sxs-lookup"><span data-stu-id="c6fa5-112">In the preceding example, you could use the explicit interface member implementation by using the fully qualified name of the interface member.</span></span> <span data-ttu-id="c6fa5-113">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c6fa5-113">For example:</span></span>  
  
```csharp  
string ISomeInterface.this[int index]   
{   
}   
```  
  
 <span data-ttu-id="c6fa5-114">En cambio, el nombre completo solo es necesario para evitar la ambigüedad cuando la clase implementa más de una interfaz con la misma firma de indexador.</span><span class="sxs-lookup"><span data-stu-id="c6fa5-114">However, the fully qualified name is only needed to avoid ambiguity when the class is implementing more than one interface with the same indexer signature.</span></span> <span data-ttu-id="c6fa5-115">Por ejemplo, si una clase `Employee` implementa dos interfaces `ICitizen` y `IEmployee` y ambas interfaces tienen la misma firma de indexador, la implementación del miembro de interfaz explícita es necesaria.</span><span class="sxs-lookup"><span data-stu-id="c6fa5-115">For example, if an `Employee` class is implementing two interfaces, `ICitizen` and `IEmployee`, and both interfaces have the same indexer signature, the explicit interface member implementation is necessary.</span></span> <span data-ttu-id="c6fa5-116">Es decir, la siguiente declaración de indexador:</span><span class="sxs-lookup"><span data-stu-id="c6fa5-116">That is, the following indexer declaration:</span></span>  
  
```csharp  
string IEmployee.this[int index]   
{   
}   
```  
  
 <span data-ttu-id="c6fa5-117">implementa el indexador en la interfaz `IEmployee`, mientras que la siguiente declaración:</span><span class="sxs-lookup"><span data-stu-id="c6fa5-117">implements the indexer on the `IEmployee` interface, while the following declaration:</span></span>  
  
```csharp  
string ICitizen.this[int index]
{   
}   
```  
  
 <span data-ttu-id="c6fa5-118">implementa el indexador en la interfaz `ICitizen`.</span><span class="sxs-lookup"><span data-stu-id="c6fa5-118">implements the indexer on the `ICitizen` interface.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6fa5-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="c6fa5-119">See also</span></span>

- [<span data-ttu-id="c6fa5-120">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="c6fa5-120">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="c6fa5-121">Indizadores</span><span class="sxs-lookup"><span data-stu-id="c6fa5-121">Indexers</span></span>](./index.md)
- [<span data-ttu-id="c6fa5-122">Propiedades</span><span class="sxs-lookup"><span data-stu-id="c6fa5-122">Properties</span></span>](../classes-and-structs/properties.md)
- [<span data-ttu-id="c6fa5-123">Interfaces</span><span class="sxs-lookup"><span data-stu-id="c6fa5-123">Interfaces</span></span>](../interfaces/index.md)
