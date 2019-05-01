---
title: Procedimiento para usar zonas horarias en operaciones aritméticas de fecha y hora
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], arithmetic operations
- arithmetic operations [.NET Framework], dates and times
- dates [.NET Framework], adding and subtracting
ms.assetid: 83dd898d-1338-415d-8cd6-445377ab7871
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 053ca2d10deadf58d5bb8b4628fb5dee815d82c8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62026502"
---
# <a name="how-to-use-time-zones-in-date-and-time-arithmetic"></a><span data-ttu-id="e33af-102">Procedimiento para usar zonas horarias en operaciones aritméticas de fecha y hora</span><span class="sxs-lookup"><span data-stu-id="e33af-102">How to: Use time zones in date and time arithmetic</span></span>

<span data-ttu-id="e33af-103">Normalmente, al realizar la fecha y hora aritmético mediante <xref:System.DateTime> o <xref:System.DateTimeOffset> valores, el resultado no refleja las reglas de ajuste de zona horaria.</span><span class="sxs-lookup"><span data-stu-id="e33af-103">Ordinarily, when you perform date and time arithmetic using <xref:System.DateTime> or <xref:System.DateTimeOffset> values, the result does not reflect any time zone adjustment rules.</span></span> <span data-ttu-id="e33af-104">Esto es cierto incluso cuando la zona horaria del valor de fecha y hora es claramente identificable (por ejemplo, cuando el <xref:System.DateTime.Kind%2A> propiedad está establecida en <xref:System.DateTimeKind.Local>).</span><span class="sxs-lookup"><span data-stu-id="e33af-104">This is true even when the time zone of the date and time value is clearly identifiable (for example, when the <xref:System.DateTime.Kind%2A> property is set to <xref:System.DateTimeKind.Local>).</span></span> <span data-ttu-id="e33af-105">En este tema se muestra cómo realizar operaciones aritméticas en valores de fecha y hora que pertenecen a una zona horaria determinada.</span><span class="sxs-lookup"><span data-stu-id="e33af-105">This topic shows how to perform arithmetic operations on date and time values that belong to a particular time zone.</span></span> <span data-ttu-id="e33af-106">Los resultados de las operaciones aritméticas reflejarán las reglas de ajuste de la zona horaria.</span><span class="sxs-lookup"><span data-stu-id="e33af-106">The results of the arithmetic operations will reflect the time zone's adjustment rules.</span></span>

### <a name="to-apply-adjustment-rules-to-date-and-time-arithmetic"></a><span data-ttu-id="e33af-107">Para aplicar las reglas de ajuste a la fecha y hora aritmético</span><span class="sxs-lookup"><span data-stu-id="e33af-107">To apply adjustment rules to date and time arithmetic</span></span>

1. <span data-ttu-id="e33af-108">Implemente algún método para acoplar estrechamente un valor de fecha y hora con la zona horaria a la que pertenece.</span><span class="sxs-lookup"><span data-stu-id="e33af-108">Implement some method of closely coupling a date and time value with the time zone to which it belongs.</span></span> <span data-ttu-id="e33af-109">Por ejemplo, declare una estructura que incluya tanto el valor de fecha y hora como su zona horaria.</span><span class="sxs-lookup"><span data-stu-id="e33af-109">For example, declare a structure that includes both the date and time value and its time zone.</span></span> <span data-ttu-id="e33af-110">En el ejemplo siguiente se usa este enfoque para vincular un <xref:System.DateTime> valor con su zona horaria.</span><span class="sxs-lookup"><span data-stu-id="e33af-110">The following example uses this approach to link a <xref:System.DateTime> value with its time zone.</span></span>

   [!code-csharp[System.DateTimeOffset.Conceptual#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual6.cs#6)]
   [!code-vb[System.DateTimeOffset.Conceptual#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual6.vb#6)]

2. <span data-ttu-id="e33af-111">Convertir una hora en hora Universal coordinada (UTC) llamando el <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A> método o la <xref:System.TimeZoneInfo.ConvertTime%2A> método.</span><span class="sxs-lookup"><span data-stu-id="e33af-111">Convert a time to Coordinated Universal Time (UTC) by calling either the <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A> method or the <xref:System.TimeZoneInfo.ConvertTime%2A> method.</span></span>

3. <span data-ttu-id="e33af-112">Realice la operación aritmética en la hora UTC.</span><span class="sxs-lookup"><span data-stu-id="e33af-112">Perform the arithmetic operation on the UTC time.</span></span>

4. <span data-ttu-id="e33af-113">Convertir la hora a la hora UTC a la zona horaria asociada de la hora original llamando a la <xref:System.TimeZoneInfo.ConvertTime%28System.DateTime%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType> método.</span><span class="sxs-lookup"><span data-stu-id="e33af-113">Convert the time from UTC to the original time's associated time zone by calling the <xref:System.TimeZoneInfo.ConvertTime%28System.DateTime%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType> method.</span></span>

## <a name="example"></a><span data-ttu-id="e33af-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e33af-114">Example</span></span>

<span data-ttu-id="e33af-115">En el ejemplo siguiente se agregan dos horas y treinta minutos al 9 de marzo de 2008, a la 1:30 A.M.</span><span class="sxs-lookup"><span data-stu-id="e33af-115">The following example adds two hours and thirty minutes to March 9, 2008, at 1:30 A.M.</span></span> <span data-ttu-id="e33af-116">zona horaria estándar central.</span><span class="sxs-lookup"><span data-stu-id="e33af-116">Central Standard Time.</span></span> <span data-ttu-id="e33af-117">La transición de esa zona horaria al horario de verano se produce treinta minutos más tarde, a las 2:00 A.M.</span><span class="sxs-lookup"><span data-stu-id="e33af-117">The time zone's transition to daylight saving time occurs thirty minutes later, at 2:00 A.M.</span></span> <span data-ttu-id="e33af-118">del 9 de marzo de 2008.</span><span class="sxs-lookup"><span data-stu-id="e33af-118">on March 9, 2008.</span></span> <span data-ttu-id="e33af-119">Puesto que el ejemplo sigue los cuatro pasos indicados en la sección anterior, se notifica correctamente la hora resultante como las 5:00 A.M.</span><span class="sxs-lookup"><span data-stu-id="e33af-119">Because the example follows the four steps listed in the previous section, it correctly reports the resulting time as 5:00 A.M.</span></span> <span data-ttu-id="e33af-120">del 9 de marzo de 2008.</span><span class="sxs-lookup"><span data-stu-id="e33af-120">on March 9, 2008.</span></span>

[!code-csharp[System.DateTimeOffset.Conceptual#8](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual8.cs#8)]
[!code-vb[System.DateTimeOffset.Conceptual#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual8.vb#8)]

<span data-ttu-id="e33af-121">Ambos <xref:System.DateTime> y <xref:System.DateTimeOffset> valores están desasociados de cualquier zona horaria a la que puedan pertenecer.</span><span class="sxs-lookup"><span data-stu-id="e33af-121">Both <xref:System.DateTime> and <xref:System.DateTimeOffset> values are disassociated from any time zone to which they might belong.</span></span> <span data-ttu-id="e33af-122">Para realizar operaciones aritméticas de fecha y hora de tal manera que apliquen automáticamente las reglas de ajuste de una zona horaria, la zona horaria a la que pertenezca cualquier valor de fecha y hora debe ser identificable de forma inmediata.</span><span class="sxs-lookup"><span data-stu-id="e33af-122">To perform date and time arithmetic in a way that automatically applies a time zone's adjustment rules, the time zone to which any date and time value belongs must be immediately identifiable.</span></span> <span data-ttu-id="e33af-123">Esto significa que un valor de fecha y hora y su zona horaria asociada deben estar estrechamente acoplados.</span><span class="sxs-lookup"><span data-stu-id="e33af-123">This means that a date and time and its associated time zone must be tightly coupled.</span></span> <span data-ttu-id="e33af-124">Hay varias maneras de hacer esto, que incluyen las siguientes:</span><span class="sxs-lookup"><span data-stu-id="e33af-124">There are several ways to do this, which include the following:</span></span>

* <span data-ttu-id="e33af-125">Suponer que todas las horas usadas en una aplicación pertenecen a una zona horaria determinada.</span><span class="sxs-lookup"><span data-stu-id="e33af-125">Assume that all times used in an application belong to a particular time zone.</span></span> <span data-ttu-id="e33af-126">Aunque es adecuado en algunos casos, este enfoque tiene una flexibilidad limitada y posiblemente, una portabilidad limitada.</span><span class="sxs-lookup"><span data-stu-id="e33af-126">Although appropriate in some cases, this approach offers limited flexibility and possibly limited portability.</span></span>

* <span data-ttu-id="e33af-127">Definir un tipo que acople estrechamente una fecha y hora con su zona horaria asociada, incluyendo ambas como campos del tipo.</span><span class="sxs-lookup"><span data-stu-id="e33af-127">Define a type that tightly couples a date and time with its associated time zone by including both as fields of the type.</span></span> <span data-ttu-id="e33af-128">Este enfoque es el que se usa en el ejemplo de código, que define una estructura para almacenar la fecha y hora y la zona horaria en dos campos de miembro.</span><span class="sxs-lookup"><span data-stu-id="e33af-128">This approach is used in the code example, which defines a structure to store the date and time and the time zone in two member fields.</span></span>

<span data-ttu-id="e33af-129">El ejemplo muestra cómo realizar operaciones aritméticas en <xref:System.DateTime> valores para que se aplican las reglas de ajuste de zona horaria al resultado.</span><span class="sxs-lookup"><span data-stu-id="e33af-129">The example illustrates how to perform arithmetic operations on <xref:System.DateTime> values so that time zone adjustment rules are applied to the result.</span></span> <span data-ttu-id="e33af-130">Sin embargo, <xref:System.DateTimeOffset> valores se pueden usar fácilmente.</span><span class="sxs-lookup"><span data-stu-id="e33af-130">However, <xref:System.DateTimeOffset> values can be used just as easily.</span></span> <span data-ttu-id="e33af-131">El ejemplo siguiente muestra cómo el código en el ejemplo original se podría adaptarse para su uso <xref:System.DateTimeOffset> en lugar de <xref:System.DateTime> valores.</span><span class="sxs-lookup"><span data-stu-id="e33af-131">The following example illustrates how the code in the original example might be adapted to use <xref:System.DateTimeOffset> instead of <xref:System.DateTime> values.</span></span>

[!code-csharp[System.DateTimeOffset.Conceptual#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual6.cs#7)]
[!code-vb[System.DateTimeOffset.Conceptual#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual6.vb#7)]

<span data-ttu-id="e33af-132">Tenga en cuenta que si esta suma se realiza simplemente en el <xref:System.DateTimeOffset> valor sin convertirlo antes a UTC, el resultado refleja el punto correcto en el tiempo en primer lugar pero su desplazamiento no reflejará el de la zona horaria designada para esa hora.</span><span class="sxs-lookup"><span data-stu-id="e33af-132">Note that if this addition is simply performed on the <xref:System.DateTimeOffset> value without first converting it to UTC, the result reflects the correct point in time but its offset does not reflect that of the designated time zone for that time.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="e33af-133">Compilación del código</span><span class="sxs-lookup"><span data-stu-id="e33af-133">Compiling the code</span></span>

<span data-ttu-id="e33af-134">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="e33af-134">This example requires:</span></span>

* <span data-ttu-id="e33af-135">Que se agregarán al proyecto una referencia a System.Core.dll.</span><span class="sxs-lookup"><span data-stu-id="e33af-135">That a reference to System.Core.dll be added to the project.</span></span>

* <span data-ttu-id="e33af-136">Que el <xref:System> se importan el espacio de nombres con el `using` instrucción (obligatorio en el código de C#).</span><span class="sxs-lookup"><span data-stu-id="e33af-136">That the <xref:System> namespace be imported with the `using` statement (required in C# code).</span></span>

## <a name="see-also"></a><span data-ttu-id="e33af-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="e33af-137">See also</span></span>

- [<span data-ttu-id="e33af-138">Fechas, horas y zonas horarias</span><span class="sxs-lookup"><span data-stu-id="e33af-138">Dates, times, and time zones</span></span>](../../../docs/standard/datetime/index.md)
- [<span data-ttu-id="e33af-139">Efectuar operaciones aritméticas con fechas y horas</span><span class="sxs-lookup"><span data-stu-id="e33af-139">Performing arithmetic operations with dates and times</span></span>](../../../docs/standard/datetime/performing-arithmetic-operations.md)
