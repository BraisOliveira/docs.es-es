---
title: Diseño de campos
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- fields, design guidelines
- read-only fields
- member design guidelines, fields
ms.assetid: 7cb4b0f3-7a10-4c93-b84d-733f7134fcf8
author: KrzysztofCwalina
ms.openlocfilehash: 3ab8fe279605c4795bb3a26557d0241b186b273a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62026411"
---
# <a name="field-design"></a><span data-ttu-id="2d3a9-102">Diseño de campos</span><span class="sxs-lookup"><span data-stu-id="2d3a9-102">Field Design</span></span>
<span data-ttu-id="2d3a9-103">El principio de encapsulación es una de las nociones más importantes en el diseño orientado a objetos.</span><span class="sxs-lookup"><span data-stu-id="2d3a9-103">The principle of encapsulation is one of the most important notions in object-oriented design.</span></span> <span data-ttu-id="2d3a9-104">Este principio afirma que los datos almacenados dentro de un objeto deben ser accesibles solo a ese objeto.</span><span class="sxs-lookup"><span data-stu-id="2d3a9-104">This principle states that data stored inside an object should be accessible only to that object.</span></span>  
  
 <span data-ttu-id="2d3a9-105">Una manera útil para interpretar el principio es decir que un tipo debe diseñarse para que se pueden realizar cambios a los campos de ese tipo (cambios de nombre o tipo) sin interrumpir el código que no sea para los miembros del tipo.</span><span class="sxs-lookup"><span data-stu-id="2d3a9-105">A useful way to interpret the principle is to say that a type should be designed so that changes to fields of that type (name or type changes) can be made without breaking code other than for members of the type.</span></span> <span data-ttu-id="2d3a9-106">Esta interpretación inmediatamente implica que todos los campos deben ser privados.</span><span class="sxs-lookup"><span data-stu-id="2d3a9-106">This interpretation immediately implies that all fields must be private.</span></span>  
  
 <span data-ttu-id="2d3a9-107">Campos de solo lectura estáticos y constantes se excluyen de esta restricción estricta, porque esos campos, casi por definición, nunca deben cambiar.</span><span class="sxs-lookup"><span data-stu-id="2d3a9-107">We exclude constant and static read-only fields from this strict restriction, because such fields, almost by definition, are never required to change.</span></span>  
  
 <span data-ttu-id="2d3a9-108">**X DO NOT** incluyen campos de instancia que son públicos o protegidos.</span><span class="sxs-lookup"><span data-stu-id="2d3a9-108">**X DO NOT** provide instance fields that are public or protected.</span></span>  
  
 <span data-ttu-id="2d3a9-109">Debe proporcionar propiedades para tener acceso a los campos en lugar de hacerlos públicos o protegidos.</span><span class="sxs-lookup"><span data-stu-id="2d3a9-109">You should provide properties for accessing fields instead of making them public or protected.</span></span>  
  
 <span data-ttu-id="2d3a9-110">**✓ DO** usar los campos constantes para las constantes que no cambia nunca.</span><span class="sxs-lookup"><span data-stu-id="2d3a9-110">**✓ DO** use constant fields for constants that will never change.</span></span>  
  
 <span data-ttu-id="2d3a9-111">El compilador quema los valores de campos constantes directamente en el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="2d3a9-111">The compiler burns the values of const fields directly into calling code.</span></span> <span data-ttu-id="2d3a9-112">Por lo tanto, los valores const nunca pueden cambiarse sin correr el riesgo de interrumpir la compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="2d3a9-112">Therefore, const values can never be changed without the risk of breaking compatibility.</span></span>  
  
 <span data-ttu-id="2d3a9-113">**✓ DO** usar estáticos públicos `readonly` campos para instancias de objetos predefinidas.</span><span class="sxs-lookup"><span data-stu-id="2d3a9-113">**✓ DO** use public static `readonly` fields for predefined object instances.</span></span>  
  
 <span data-ttu-id="2d3a9-114">Si no hay instancias predefinidas del tipo, declarar campos estáticos de sólo lectura como públicos del tipo en Sí.</span><span class="sxs-lookup"><span data-stu-id="2d3a9-114">If there are predefined instances of the type, declare them as public read-only static fields of the type itself.</span></span>  
  
 <span data-ttu-id="2d3a9-115">**X DO NOT** asignar instancias de tipos mutables a `readonly` campos.</span><span class="sxs-lookup"><span data-stu-id="2d3a9-115">**X DO NOT** assign instances of mutable types to `readonly` fields.</span></span>  
  
 <span data-ttu-id="2d3a9-116">Un tipo mutable es un tipo con instancias que puede modificarse una vez que se crean instancias.</span><span class="sxs-lookup"><span data-stu-id="2d3a9-116">A mutable type is a type with instances that can be modified after they are instantiated.</span></span> <span data-ttu-id="2d3a9-117">Por ejemplo, secuencias, mayoría de las colecciones y matrices son tipos mutables, pero <xref:System.Int32?displayProperty=nameWithType>, <xref:System.Uri?displayProperty=nameWithType>, y <xref:System.String?displayProperty=nameWithType> todos son inmutables.</span><span class="sxs-lookup"><span data-stu-id="2d3a9-117">For example, arrays, most collections, and streams are mutable types, but <xref:System.Int32?displayProperty=nameWithType>, <xref:System.Uri?displayProperty=nameWithType>, and <xref:System.String?displayProperty=nameWithType> are all immutable.</span></span> <span data-ttu-id="2d3a9-118">El modificador de solo lectura en un campo de tipo de referencia impide que la instancia almacenada en el campo que se reemplace, pero no impide que los datos de instancia del campo que se va a modificar llamando a los miembros que cambiar la instancia.</span><span class="sxs-lookup"><span data-stu-id="2d3a9-118">The read-only modifier on a reference type field prevents the instance stored in the field from being replaced, but it does not prevent the field’s instance data from being modified by calling members changing the instance.</span></span>  
  
 <span data-ttu-id="2d3a9-119">*Portions © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*</span><span class="sxs-lookup"><span data-stu-id="2d3a9-119">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="2d3a9-120">*Reimpreso con permiso de Pearson Education, Inc. de [instrucciones de diseño de Framework: Convenciones, expresiones y patrones para bibliotecas reutilizables. NET, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicada el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="2d3a9-120">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d3a9-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="2d3a9-121">See also</span></span>

- [<span data-ttu-id="2d3a9-122">Instrucciones de diseño de miembros</span><span class="sxs-lookup"><span data-stu-id="2d3a9-122">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)
- [<span data-ttu-id="2d3a9-123">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="2d3a9-123">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
