---
title: 'Procedimiento Definir propiedades abstractas: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- properties [C#], abstract
- abstract properties [C#]
ms.assetid: 672a90eb-47b9-4ae0-9914-af53852fddcb
ms.openlocfilehash: 57fd2ed3a26bf5986f9c8a1a6cae6b041811e84c
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2019
ms.locfileid: "70970900"
---
# <a name="how-to-define-abstract-properties-c-programming-guide"></a><span data-ttu-id="7b639-102">Procedimiento Definir propiedades abstractas (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="7b639-102">How to: Define Abstract Properties (C# Programming Guide)</span></span>
<span data-ttu-id="7b639-103">En el ejemplo siguiente se muestra cómo definir las propiedades [abstract](../../language-reference/keywords/abstract.md).</span><span class="sxs-lookup"><span data-stu-id="7b639-103">The following example shows how to define [abstract](../../language-reference/keywords/abstract.md) properties.</span></span> <span data-ttu-id="7b639-104">Una declaración de propiedad abstracta no proporciona una implementación de los descriptores de acceso de propiedad, declara que la clase admite propiedades, pero deja la implementación del descriptor de acceso a las clases derivadas.</span><span class="sxs-lookup"><span data-stu-id="7b639-104">An abstract property declaration does not provide an implementation of the property accessors -- it declares that the class supports properties, but leaves the accessor implementation to derived classes.</span></span> <span data-ttu-id="7b639-105">En el ejemplo siguiente se muestra cómo implementar las propiedades abstractas heredadas de una clase base.</span><span class="sxs-lookup"><span data-stu-id="7b639-105">The following example demonstrates how to implement the abstract properties inherited from a base class.</span></span>  
  
 <span data-ttu-id="7b639-106">Este ejemplo consta de tres archivos, cada uno de los cuales se compila individualmente y se hace referencia a su ensamblado resultante mediante la siguiente compilación:</span><span class="sxs-lookup"><span data-stu-id="7b639-106">This sample consists of three files, each of which is compiled individually and its resulting assembly is referenced by the next compilation:</span></span>  
  
- <span data-ttu-id="7b639-107">abstractshape.cs: la clase `Shape` que contiene una propiedad `Area` abstracta.</span><span class="sxs-lookup"><span data-stu-id="7b639-107">abstractshape.cs: the `Shape` class that contains an abstract `Area` property.</span></span>  
  
- <span data-ttu-id="7b639-108">shapes.cs: las subclases de la clase `Shape`.</span><span class="sxs-lookup"><span data-stu-id="7b639-108">shapes.cs: The subclasses of the `Shape` class.</span></span>  
  
- <span data-ttu-id="7b639-109">shapetest.cs: un programa de prueba para mostrar las áreas de algunos objetos derivados de `Shape`.</span><span class="sxs-lookup"><span data-stu-id="7b639-109">shapetest.cs: A test program to display the areas of some `Shape`-derived objects.</span></span>  
  
 <span data-ttu-id="7b639-110">Para compilar el ejemplo, use el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="7b639-110">To compile the example, use the following command:</span></span>  
  
 `csc abstractshape.cs shapes.cs shapetest.cs`  
  
 <span data-ttu-id="7b639-111">Esto creará el archivo ejecutable shapetest.exe.</span><span class="sxs-lookup"><span data-stu-id="7b639-111">This will create the executable file shapetest.exe.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7b639-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7b639-112">Example</span></span>  
 <span data-ttu-id="7b639-113">Este archivo declara la clase `Shape` que contiene la propiedad `Area` del tipo `double`.</span><span class="sxs-lookup"><span data-stu-id="7b639-113">This file declares the `Shape` class that contains the `Area` property of the type `double`.</span></span>  
  
 [!code-csharp[csProgGuideInheritance#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#1)]  
  
- <span data-ttu-id="7b639-114">Los modificadores de la propiedad se colocan en la propia declaración de propiedad.</span><span class="sxs-lookup"><span data-stu-id="7b639-114">Modifiers on the property are placed on the property declaration itself.</span></span> <span data-ttu-id="7b639-115">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="7b639-115">For example:</span></span>  
  
    ```csharp  
    public abstract double Area  
    ```  
  
- <span data-ttu-id="7b639-116">Al declarar una propiedad abstracta (como `Area` en este ejemplo), simplemente indica qué descriptores de acceso de propiedad están disponibles, pero no los implementa.</span><span class="sxs-lookup"><span data-stu-id="7b639-116">When declaring an abstract property (such as `Area` in this example), you simply indicate what property accessors are available, but do not implement them.</span></span> <span data-ttu-id="7b639-117">En este ejemplo, solo está disponible un descriptor de acceso [get](../../language-reference/keywords/get.md), por lo que la propiedad es de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="7b639-117">In this example, only a [get](../../language-reference/keywords/get.md) accessor is available, so the property is read-only.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7b639-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7b639-118">Example</span></span>  
 <span data-ttu-id="7b639-119">En el siguiente código se muestran tres subclases de `Shape` y cómo invalidan la propiedad `Area` para proporcionar su propia implementación.</span><span class="sxs-lookup"><span data-stu-id="7b639-119">The following code shows three subclasses of `Shape` and how they override the `Area` property to provide their own implementation.</span></span>  
  
 [!code-csharp[csProgGuideInheritance#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#2)]  
  
## <a name="example"></a><span data-ttu-id="7b639-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7b639-120">Example</span></span>  
 <span data-ttu-id="7b639-121">En el siguiente código se muestra un programa de prueba que crea un número de objetos derivados de `Shape` e imprime sus áreas.</span><span class="sxs-lookup"><span data-stu-id="7b639-121">The following code shows a test program that creates a number of `Shape`-derived objects and prints out their areas.</span></span>  
  
 [!code-csharp[csProgGuideInheritance#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#3)]  
  
## <a name="see-also"></a><span data-ttu-id="7b639-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="7b639-122">See also</span></span>

- [<span data-ttu-id="7b639-123">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="7b639-123">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="7b639-124">Clases y structs</span><span class="sxs-lookup"><span data-stu-id="7b639-124">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="7b639-125">Clases y miembros de clase abstractos y sellados</span><span class="sxs-lookup"><span data-stu-id="7b639-125">Abstract and Sealed Classes and Class Members</span></span>](./abstract-and-sealed-classes-and-class-members.md)
- [<span data-ttu-id="7b639-126">Propiedades</span><span class="sxs-lookup"><span data-stu-id="7b639-126">Properties</span></span>](./properties.md)
