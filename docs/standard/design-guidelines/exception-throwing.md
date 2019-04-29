---
title: Generación de excepciones
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- exceptions, throwing
- explicitly throwing exceptions
- throwing exceptions, design guidelines
ms.assetid: 5388e02b-52f5-460e-a2b5-eeafe60eeebe
author: KrzysztofCwalina
ms.openlocfilehash: 74eee418a3c87b335cdf96557c4e17b95aff7b58
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61669074"
---
# <a name="exception-throwing"></a><span data-ttu-id="773e0-102">Generación de excepciones</span><span class="sxs-lookup"><span data-stu-id="773e0-102">Exception Throwing</span></span>
<span data-ttu-id="773e0-103">Excepciones directrices descritas en esta sección requieren una buena definición del significado del error de ejecución.</span><span class="sxs-lookup"><span data-stu-id="773e0-103">Exception-throwing guidelines described in this section require a good definition of the meaning of execution failure.</span></span> <span data-ttu-id="773e0-104">Se produce un error de ejecución cada vez que un miembro no puede hacer lo que fue diseñado para hacer (lo que el nombre de miembro implica).</span><span class="sxs-lookup"><span data-stu-id="773e0-104">Execution failure occurs whenever a member cannot do what it was designed to do (what the member name implies).</span></span> <span data-ttu-id="773e0-105">Por ejemplo, si la `OpenFile` método no puede devolver un identificador de archivo abierto al llamador, se consideraría un error de ejecución.</span><span class="sxs-lookup"><span data-stu-id="773e0-105">For example, if the `OpenFile` method cannot return an opened file handle to the caller, it would be considered an execution failure.</span></span>  
  
 <span data-ttu-id="773e0-106">La mayoría de los desarrolladores se han vuelto cómodos con el uso de excepciones para errores de uso como la división por cero o referencias nulas.</span><span class="sxs-lookup"><span data-stu-id="773e0-106">Most developers have become comfortable with using exceptions for usage errors such as division by zero or null references.</span></span> <span data-ttu-id="773e0-107">En el marco de trabajo, las excepciones se utilizan para todas las condiciones de error, incluidos los errores de ejecución.</span><span class="sxs-lookup"><span data-stu-id="773e0-107">In the Framework, exceptions are used for all error conditions, including execution errors.</span></span>  
  
 <span data-ttu-id="773e0-108">**X DO NOT** devolver códigos de error.</span><span class="sxs-lookup"><span data-stu-id="773e0-108">**X DO NOT** return error codes.</span></span>  
  
 <span data-ttu-id="773e0-109">Las excepciones son el medio principal para informar de errores en los marcos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="773e0-109">Exceptions are the primary means of reporting errors in frameworks.</span></span>  
  
 <span data-ttu-id="773e0-110">**✓ DO** notificar errores de ejecución iniciando excepciones.</span><span class="sxs-lookup"><span data-stu-id="773e0-110">**✓ DO** report execution failures by throwing exceptions.</span></span>  
  
 <span data-ttu-id="773e0-111">**✓ CONSIDER** la terminación del proceso mediante una llamada a `System.Environment.FailFast` (característica de .NET Framework 2.0) en lugar de producir una excepción si el código encuentra una situación donde no es seguro para la ejecución aún más.</span><span class="sxs-lookup"><span data-stu-id="773e0-111">**✓ CONSIDER** terminating the process by calling `System.Environment.FailFast` (.NET Framework 2.0 feature) instead of throwing an exception if your code encounters a situation where it is unsafe for further execution.</span></span>  
  
 <span data-ttu-id="773e0-112">**X DO NOT** usar excepciones para el flujo normal de control, si es posible.</span><span class="sxs-lookup"><span data-stu-id="773e0-112">**X DO NOT** use exceptions for the normal flow of control, if possible.</span></span>  
  
 <span data-ttu-id="773e0-113">Excepto para los errores del sistema y operaciones con posibles condiciones de carrera, los diseñadores de framework deberían diseñar las API para que los usuarios pueden escribir código que no inicia excepciones.</span><span class="sxs-lookup"><span data-stu-id="773e0-113">Except for system failures and operations with potential race conditions, framework designers should design APIs so users can write code that does not throw exceptions.</span></span> <span data-ttu-id="773e0-114">Por ejemplo, puede proporcionar una manera de comprobar las condiciones previas antes de llamar a un miembro, por lo que los usuarios pueden escribir código que no inicia excepciones.</span><span class="sxs-lookup"><span data-stu-id="773e0-114">For example, you can provide a way to check preconditions before calling a member so users can write code that does not throw exceptions.</span></span>  
  
 <span data-ttu-id="773e0-115">El miembro que se usa para comprobar las condiciones previas de otro miembro a menudo se conoce como una herramienta de comprobación y el miembro que hace realmente el trabajo se llama a una parte de la acción.</span><span class="sxs-lookup"><span data-stu-id="773e0-115">The member used to check preconditions of another member is often referred to as a tester, and the member that actually does the work is called a doer.</span></span>  
  
 <span data-ttu-id="773e0-116">Hay casos Tester-Doer (modelo) puede tener una sobrecarga de rendimiento aceptable.</span><span class="sxs-lookup"><span data-stu-id="773e0-116">There are cases when the Tester-Doer Pattern can have an unacceptable performance overhead.</span></span> <span data-ttu-id="773e0-117">En tales casos, se debe considerar el patrón de Try Parse llamados (consulte [excepciones y rendimiento](../../../docs/standard/design-guidelines/exceptions-and-performance.md) para obtener más información).</span><span class="sxs-lookup"><span data-stu-id="773e0-117">In such cases, the so-called Try-Parse Pattern should be considered (see [Exceptions and Performance](../../../docs/standard/design-guidelines/exceptions-and-performance.md) for more information).</span></span>  
  
 <span data-ttu-id="773e0-118">**✓ CONSIDER** las implicaciones de rendimiento de inicio de excepciones.</span><span class="sxs-lookup"><span data-stu-id="773e0-118">**✓ CONSIDER** the performance implications of throwing exceptions.</span></span> <span data-ttu-id="773e0-119">Las tasas de throw superior a 100 por segundo están probables que afectar considerablemente al rendimiento de mayoría de las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="773e0-119">Throw rates above 100 per second are likely to noticeably impact the performance of most applications.</span></span>  
  
 <span data-ttu-id="773e0-120">**✓ DO** documento todas las excepciones iniciadas por miembros invocables públicamente debido a una infracción del miembro del contrato (en lugar de un error del sistema) y tratan como parte de su contrato.</span><span class="sxs-lookup"><span data-stu-id="773e0-120">**✓ DO** document all exceptions thrown by publicly callable members because of a violation of the member contract (rather than a system failure) and treat them as part of your contract.</span></span>  
  
 <span data-ttu-id="773e0-121">Las excepciones que forman parte del contrato no deben cambiar de una versión a la siguiente (es decir, no debe cambiar el tipo de excepción y no se deben agregar nuevas excepciones).</span><span class="sxs-lookup"><span data-stu-id="773e0-121">Exceptions that are a part of the contract should not change from one version to the next (i.e., exception type should not change, and new exceptions should not be added).</span></span>  
  
 <span data-ttu-id="773e0-122">**X DO NOT** tener miembros públicos que pueden ya sea throw o no en función de alguna opción.</span><span class="sxs-lookup"><span data-stu-id="773e0-122">**X DO NOT** have public members that can either throw or not based on some option.</span></span>  
  
 <span data-ttu-id="773e0-123">**X DO NOT** tiene miembros públicos que devuelven las excepciones como el valor devuelto o un `out` parámetro.</span><span class="sxs-lookup"><span data-stu-id="773e0-123">**X DO NOT** have public members that return exceptions as the return value or an `out` parameter.</span></span>  
  
 <span data-ttu-id="773e0-124">Devolver las excepciones de las API públicas en lugar de escribirlos frustra muchas de las ventajas de informe de errores basado en excepciones.</span><span class="sxs-lookup"><span data-stu-id="773e0-124">Returning exceptions from public APIs instead of throwing them defeats many of the benefits of exception-based error reporting.</span></span>  
  
 <span data-ttu-id="773e0-125">**✓ CONSIDER** mediante métodos de generador de excepciones.</span><span class="sxs-lookup"><span data-stu-id="773e0-125">**✓ CONSIDER** using exception builder methods.</span></span>  
  
 <span data-ttu-id="773e0-126">Es habitual para producir la misma excepción desde distintos lugares.</span><span class="sxs-lookup"><span data-stu-id="773e0-126">It is common to throw the same exception from different places.</span></span> <span data-ttu-id="773e0-127">Para evitar el sobredimensionamiento del código, use métodos auxiliares que crean excepciones e inicializan sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="773e0-127">To avoid code bloat, use helper methods that create exceptions and initialize their properties.</span></span>  
  
 <span data-ttu-id="773e0-128">Además, los miembros que se producen excepciones no obtienen insertadas.</span><span class="sxs-lookup"><span data-stu-id="773e0-128">Also, members that throw exceptions are not getting inlined.</span></span> <span data-ttu-id="773e0-129">Mover la instrucción throw en el generador puede permitir que el miembro se puede insertar.</span><span class="sxs-lookup"><span data-stu-id="773e0-129">Moving the throw statement inside the builder might allow the member to be inlined.</span></span>  
  
 <span data-ttu-id="773e0-130">**X DO NOT** genere excepciones desde bloques de filtro de excepción.</span><span class="sxs-lookup"><span data-stu-id="773e0-130">**X DO NOT** throw exceptions from exception filter blocks.</span></span>  
  
 <span data-ttu-id="773e0-131">Cuando un filtro de excepción produce una excepción, la excepción ha sido detectada por el CLR y el filtro devuelve false.</span><span class="sxs-lookup"><span data-stu-id="773e0-131">When an exception filter raises an exception, the exception is caught by the CLR, and the filter returns false.</span></span> <span data-ttu-id="773e0-132">Este comportamiento es indistinguible de la ejecución del filtro y devuelve false explícitamente y, por tanto, es muy difícil de depurar.</span><span class="sxs-lookup"><span data-stu-id="773e0-132">This behavior is indistinguishable from the filter executing and returning false explicitly and is therefore very difficult to debug.</span></span>  
  
 <span data-ttu-id="773e0-133">**X AVOID** iniciar explícitamente excepciones desde bloques finally.</span><span class="sxs-lookup"><span data-stu-id="773e0-133">**X AVOID** explicitly throwing exceptions from finally blocks.</span></span> <span data-ttu-id="773e0-134">Las excepciones iniciadas implícitamente resultantes de llamar a métodos que inician son aceptables.</span><span class="sxs-lookup"><span data-stu-id="773e0-134">Implicitly thrown exceptions resulting from calling methods that throw are acceptable.</span></span>  
  
 <span data-ttu-id="773e0-135">*Portions © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*</span><span class="sxs-lookup"><span data-stu-id="773e0-135">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="773e0-136">*Reimpreso con permiso de Pearson Education, Inc. de [instrucciones de diseño de Framework: Convenciones, expresiones y patrones para bibliotecas reutilizables. NET, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicada el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="773e0-136">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="773e0-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="773e0-137">See also</span></span>

- [<span data-ttu-id="773e0-138">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="773e0-138">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="773e0-139">Instrucciones de diseño de excepciones</span><span class="sxs-lookup"><span data-stu-id="773e0-139">Design Guidelines for Exceptions</span></span>](../../../docs/standard/design-guidelines/exceptions.md)
