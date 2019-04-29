---
title: 'Servicio: Llamadas por segundo'
ms.date: 03/30/2017
ms.assetid: 6261d28d-d449-425a-b9fc-a4ee14079134
ms.openlocfilehash: 5189a78e2655707d165f187e06ac9a60d055eac0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61773370"
---
# <a name="service-calls-per-second"></a><span data-ttu-id="0dee0-102">Servicio: Llamadas por segundo</span><span class="sxs-lookup"><span data-stu-id="0dee0-102">Service: Calls Per Second</span></span>
<span data-ttu-id="0dee0-103">Nombre del contador: Llamadas por segundo.</span><span class="sxs-lookup"><span data-stu-id="0dee0-103">Counter Name: Calls Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="0dee0-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="0dee0-104">Description</span></span>  
 <span data-ttu-id="0dee0-105">El número de llamadas por segundo a este servicio.</span><span class="sxs-lookup"><span data-stu-id="0dee0-105">Number of calls to this service in a second.</span></span>  
  
 <span data-ttu-id="0dee0-106">Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), cuyo valor se calcula mediante la siguiente fórmula.</span><span class="sxs-lookup"><span data-stu-id="0dee0-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="0dee0-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F), donde el numerador (N) representa el número de operaciones realizadas durante el último intervalo de muestra, el denominador (D) representa el número de pasos transcurridos desde el último intervalo de muestra y F representa la frecuencia de los pasos.</span><span class="sxs-lookup"><span data-stu-id="0dee0-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F) where the numerator (N) represents the number of operations performed during the last sample interval, the denominator (D) represents the number of ticks elapsed during the last sample interval, and F is the frequency of the ticks.</span></span>
