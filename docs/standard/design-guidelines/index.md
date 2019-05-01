---
title: Instrucciones de diseño de .NET Framework
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- libraries, .NET Framework class library
- class library design guidelines [.NET Framework], about
- class library design guidelines [.NET Framework]
ms.assetid: 5fbcaf4f-ea2a-4d20-b0d6-e61dee202b4b
author: KrzysztofCwalina
ms.openlocfilehash: c20430f9cdcd71cc2e178d38aeed48f9fa4e75c5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62026385"
---
# <a name="framework-design-guidelines"></a><span data-ttu-id="c8e79-102">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="c8e79-102">Framework Design Guidelines</span></span>
<span data-ttu-id="c8e79-103">Esta sección proporciona directrices para diseñar bibliotecas que extenderán e interactúan con .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c8e79-103">This section provides guidelines for designing libraries that extend and interact with the .NET Framework.</span></span> <span data-ttu-id="c8e79-104">El objetivo es ayudar a los diseñadores de bibliotecas a garantizar la coherencia de la API y facilidad de uso, ya que proporciona un modelo de programación unificado que es independiente del lenguaje de programación usado para el desarrollo.</span><span class="sxs-lookup"><span data-stu-id="c8e79-104">The goal is to help library designers ensure API consistency and ease of use by providing a unified programming model that is independent of the programming language used for development.</span></span> <span data-ttu-id="c8e79-105">Se recomienda que siga estas directrices de diseño al desarrollar clases y componentes que extiendan .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c8e79-105">We recommend that you follow these design guidelines when developing classes and components that extend the .NET Framework.</span></span> <span data-ttu-id="c8e79-106">Diseño de la biblioteca incoherente negativamente afecta a la productividad del desarrollador y disuaden del adopción.</span><span class="sxs-lookup"><span data-stu-id="c8e79-106">Inconsistent library design adversely affects developer productivity and discourages adoption.</span></span>  
  
 <span data-ttu-id="c8e79-107">Las instrucciones se organizan como recomendaciones sencillas precedidas por los términos `Do`, `Consider`, `Avoid`, y `Do not`.</span><span class="sxs-lookup"><span data-stu-id="c8e79-107">The guidelines are organized as simple recommendations prefixed with the terms `Do`, `Consider`, `Avoid`, and `Do not`.</span></span> <span data-ttu-id="c8e79-108">Estas instrucciones están pensadas para ayudar a los diseñadores de bibliotecas de clase a comprender las ventajas y desventajas entre las distintas soluciones.</span><span class="sxs-lookup"><span data-stu-id="c8e79-108">These guidelines are intended to help class library designers understand the trade-offs between different solutions.</span></span> <span data-ttu-id="c8e79-109">Puede haber situaciones donde buen diseño de bibliotecas requiere que infringen estas directrices de diseño.</span><span class="sxs-lookup"><span data-stu-id="c8e79-109">There might be situations where good library design requires that you violate these design guidelines.</span></span> <span data-ttu-id="c8e79-110">Estos casos deberían ser excepcionales y es importante que tenga un motivo claro y atractivo para su decisión.</span><span class="sxs-lookup"><span data-stu-id="c8e79-110">Such cases should be rare, and it is important that you have a clear and compelling reason for your decision.</span></span>  
  
 <span data-ttu-id="c8e79-111">Estas instrucciones son un extracto de la libreta de *instrucciones de diseño de Framework: Convenciones, expresiones y patrones para las bibliotecas reutilizables. NET, 2ª edición*, Krzysztof Cwalina y Brad Abrams.</span><span class="sxs-lookup"><span data-stu-id="c8e79-111">These guidelines are excerpted from the book *Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition*, by Krzysztof Cwalina and Brad Abrams.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c8e79-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="c8e79-112">In This Section</span></span>  
 [<span data-ttu-id="c8e79-113">Instrucciones de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="c8e79-113">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)  
 <span data-ttu-id="c8e79-114">Proporciona directrices para asignar nombres a los ensamblados, espacios de nombres, tipos y miembros en las bibliotecas de clases.</span><span class="sxs-lookup"><span data-stu-id="c8e79-114">Provides guidelines for naming assemblies, namespaces, types, and members in class libraries.</span></span>  
  
 [<span data-ttu-id="c8e79-115">Instrucciones de diseño de tipos</span><span class="sxs-lookup"><span data-stu-id="c8e79-115">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)  
 <span data-ttu-id="c8e79-116">Proporciona instrucciones para utilizar clases estáticas y abstractas, interfaces, enumeraciones, estructuras y otros tipos.</span><span class="sxs-lookup"><span data-stu-id="c8e79-116">Provides guidelines for using static and abstract classes, interfaces, enumerations, structures, and other types.</span></span>  
  
 [<span data-ttu-id="c8e79-117">Instrucciones de diseño de miembros</span><span class="sxs-lookup"><span data-stu-id="c8e79-117">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)  
 <span data-ttu-id="c8e79-118">Proporciona directrices para diseñar y usar las propiedades, métodos, constructores, campos, eventos, operadores y parámetros.</span><span class="sxs-lookup"><span data-stu-id="c8e79-118">Provides guidelines for designing and using properties, methods, constructors, fields, events, operators, and parameters.</span></span>  
  
 [<span data-ttu-id="c8e79-119">Diseño de extensibilidad</span><span class="sxs-lookup"><span data-stu-id="c8e79-119">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
 <span data-ttu-id="c8e79-120">Explica los mecanismos de extensibilidad, como la creación de subclases, mediante eventos, los miembros virtuales y las devoluciones de llamada y cómo elegir los mecanismos que satisfagan los requisitos del marco de trabajo.</span><span class="sxs-lookup"><span data-stu-id="c8e79-120">Discusses extensibility mechanisms such as subclassing, using events, virtual members, and callbacks, and explains how to choose the mechanisms that best meet your framework's requirements.</span></span>  
  
 [<span data-ttu-id="c8e79-121">Instrucciones de diseño de excepciones</span><span class="sxs-lookup"><span data-stu-id="c8e79-121">Design Guidelines for Exceptions</span></span>](../../../docs/standard/design-guidelines/exceptions.md)  
 <span data-ttu-id="c8e79-122">Describe las instrucciones de diseño para diseñar, iniciar y detectar excepciones.</span><span class="sxs-lookup"><span data-stu-id="c8e79-122">Describes design guidelines for designing, throwing, and catching exceptions.</span></span>  
  
 [<span data-ttu-id="c8e79-123">Instrucciones de uso</span><span class="sxs-lookup"><span data-stu-id="c8e79-123">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)  
 <span data-ttu-id="c8e79-124">Describe las instrucciones para el uso de tipos comunes, como matrices, atributos y colecciones, admitir la serialización y la sobrecarga de operadores de igualdad.</span><span class="sxs-lookup"><span data-stu-id="c8e79-124">Describes guidelines for using common types such as arrays, attributes, and collections, supporting serialization, and overloading equality operators.</span></span>  
  
 [<span data-ttu-id="c8e79-125">Patrones de diseño comunes</span><span class="sxs-lookup"><span data-stu-id="c8e79-125">Common Design Patterns</span></span>](../../../docs/standard/design-guidelines/common-design-patterns.md)  
 <span data-ttu-id="c8e79-126">Proporciona directrices para elegir e implemente las propiedades de dependencia.</span><span class="sxs-lookup"><span data-stu-id="c8e79-126">Provides guidelines for choosing and implementing dependency properties.</span></span>  
  
 <span data-ttu-id="c8e79-127">*Portions © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*</span><span class="sxs-lookup"><span data-stu-id="c8e79-127">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="c8e79-128">*Reimpreso con permiso de Pearson Education, Inc. de [instrucciones de diseño de Framework: Convenciones, expresiones y patrones para bibliotecas reutilizables. NET, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicada el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="c8e79-128">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8e79-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="c8e79-129">See also</span></span>

- [<span data-ttu-id="c8e79-130">Información general</span><span class="sxs-lookup"><span data-stu-id="c8e79-130">Overview</span></span>](../../../docs/framework/get-started/overview.md)
- [<span data-ttu-id="c8e79-131">Guía de desarrollo</span><span class="sxs-lookup"><span data-stu-id="c8e79-131">Development Guide</span></span>](../../../docs/framework/development-guide.md)
