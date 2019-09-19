---
title: Eventos ETW de recolección de elementos no utilizados
ms.date: 03/30/2017
helpviewer_keywords:
- GC events
- garbage collection events [.NET Framework]
- ETW, garbage collection events (CLR)
ms.assetid: f14b6fd7-0966-4d87-bc89-54ef3a44a94a
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ec90d022a0c72782f413a84b6fbd2c1b8d663a73
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2019
ms.locfileid: "71046504"
---
# <a name="garbage-collection-etw-events"></a><span data-ttu-id="4ed7a-102">Eventos ETW de recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="4ed7a-102">Garbage Collection ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="4ed7a-103">Estos eventos recopilan información sobre la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-103">These events collect information pertaining to garbage collection.</span></span> <span data-ttu-id="4ed7a-104">Ayudan en el diagnóstico y depuración, así como en la determinación de cuántas veces se realizó la recolección de elementos no utilizados, cuánta memoria se liberó durante la recolección de elementos no utilizados, etc.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-104">They help in diagnostics and debugging, including determining how many times garbage collection was performed, how much memory was freed during garbage collection, and so on.</span></span>  
  
 <span data-ttu-id="4ed7a-105">Esta categoría consta de los siguientes eventos:</span><span class="sxs-lookup"><span data-stu-id="4ed7a-105">This category consists of the following events:</span></span>  
  
- [<span data-ttu-id="4ed7a-106">Evento GCStart_V1</span><span class="sxs-lookup"><span data-stu-id="4ed7a-106">GCStart_V1 Event</span></span>](#gcstart_v1_event)  
  
- [<span data-ttu-id="4ed7a-107">Evento GCEnd_V1</span><span class="sxs-lookup"><span data-stu-id="4ed7a-107">GCEnd_V1 Event</span></span>](#gcend_v1_event)  
  
- [<span data-ttu-id="4ed7a-108">Evento GCHeapStats_V1</span><span class="sxs-lookup"><span data-stu-id="4ed7a-108">GCHeapStats_V1 Event</span></span>](#gcheapstats_v1_event)  
  
- [<span data-ttu-id="4ed7a-109">Evento GCCreateSegment_V1</span><span class="sxs-lookup"><span data-stu-id="4ed7a-109">GCCreateSegment_V1 Event</span></span>](#gccreatesegment_v1_event)  
  
- [<span data-ttu-id="4ed7a-110">Evento GCFreeSegment_V1</span><span class="sxs-lookup"><span data-stu-id="4ed7a-110">GCFreeSegment_V1 Event</span></span>](#gcfreesegment_v1_event)  
  
- [<span data-ttu-id="4ed7a-111">Evento GCRestartEEBegin_V1</span><span class="sxs-lookup"><span data-stu-id="4ed7a-111">GCRestartEEBegin_V1 Event</span></span>](#gcrestarteebegin_v1_event)  
  
- [<span data-ttu-id="4ed7a-112">Evento GCRestartEEEnd_V1</span><span class="sxs-lookup"><span data-stu-id="4ed7a-112">GCRestartEEEnd_V1 Event</span></span>](#gcrestarteeend_v1_event)  
  
- [<span data-ttu-id="4ed7a-113">Evento GCSuspendEE_V1</span><span class="sxs-lookup"><span data-stu-id="4ed7a-113">GCSuspendEE_V1 Event</span></span>](#gcsuspendee_v1_event)  
  
- [<span data-ttu-id="4ed7a-114">Evento GCSuspendEE_V1</span><span class="sxs-lookup"><span data-stu-id="4ed7a-114">GCSuspendEEEnd_V1 Event</span></span>](#gcsuspendeeend_v1_event)  
  
- [<span data-ttu-id="4ed7a-115">Evento GCAllocationTick_V2</span><span class="sxs-lookup"><span data-stu-id="4ed7a-115">GCAllocationTick_V2 Event</span></span>](#gcallocationtick_v2_event)  
  
- [<span data-ttu-id="4ed7a-116">Evento GCFinalizersBegin_V1</span><span class="sxs-lookup"><span data-stu-id="4ed7a-116">GCFinalizersBegin_V1 Event</span></span>](#gcfinalizersbegin_v1_event)  
  
- [<span data-ttu-id="4ed7a-117">Evento GCFinalizersEnd_V1</span><span class="sxs-lookup"><span data-stu-id="4ed7a-117">GCFinalizersEnd_V1 Event</span></span>](#gcfinalizersend_v1_event)  
  
- [<span data-ttu-id="4ed7a-118">Evento GCCreateConcurrentThread_V1</span><span class="sxs-lookup"><span data-stu-id="4ed7a-118">GCCreateConcurrentThread_V1 Event</span></span>](#gccreateconcurrentthread_v1_event)  
  
- [<span data-ttu-id="4ed7a-119">Evento GCCreateConcurrentThread_V1</span><span class="sxs-lookup"><span data-stu-id="4ed7a-119">GCTerminateConcurrentThread_V1 Event</span></span>](#gcterminateconcurrentthread_v1_event)  
  
<a name="gcstart_v1_event"></a>   
## <a name="gcstart_v1-event"></a><span data-ttu-id="4ed7a-120">Evento GCStart_V1</span><span class="sxs-lookup"><span data-stu-id="4ed7a-120">GCStart_V1 Event</span></span>  
 <span data-ttu-id="4ed7a-121">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-121">The following table shows the keyword and level.</span></span> <span data-ttu-id="4ed7a-122">(Para obtener más información, vea [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md)).</span><span class="sxs-lookup"><span data-stu-id="4ed7a-122">(For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="4ed7a-123">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="4ed7a-123">Keyword for raising the event</span></span>|<span data-ttu-id="4ed7a-124">Nivel</span><span class="sxs-lookup"><span data-stu-id="4ed7a-124">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="4ed7a-125">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="4ed7a-125">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="4ed7a-126">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="4ed7a-126">Informational (4)</span></span>|  
  
 <span data-ttu-id="4ed7a-127">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-127">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="4ed7a-128">Evento</span><span class="sxs-lookup"><span data-stu-id="4ed7a-128">Event</span></span>|<span data-ttu-id="4ed7a-129">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="4ed7a-129">Event ID</span></span>|<span data-ttu-id="4ed7a-130">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="4ed7a-130">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCStart_V1`|<span data-ttu-id="4ed7a-131">1</span><span class="sxs-lookup"><span data-stu-id="4ed7a-131">1</span></span>|<span data-ttu-id="4ed7a-132">Se ha iniciado una recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-132">A garbage collection has started.</span></span>|  
  
 <span data-ttu-id="4ed7a-133">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-133">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="4ed7a-134">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="4ed7a-134">Field name</span></span>|<span data-ttu-id="4ed7a-135">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="4ed7a-135">Data type</span></span>|<span data-ttu-id="4ed7a-136">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="4ed7a-136">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="4ed7a-137">Número</span><span class="sxs-lookup"><span data-stu-id="4ed7a-137">Count</span></span>|<span data-ttu-id="4ed7a-138">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="4ed7a-138">win:UInt32</span></span>|<span data-ttu-id="4ed7a-139">Recolección de elementos no utilizados número *n*.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-139">The *n*th garbage collection.</span></span>|  
|<span data-ttu-id="4ed7a-140">Profundidad</span><span class="sxs-lookup"><span data-stu-id="4ed7a-140">Depth</span></span>|<span data-ttu-id="4ed7a-141">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="4ed7a-141">win:UInt32</span></span>|<span data-ttu-id="4ed7a-142">Generación que se está recopilando.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-142">The generation that is being collected.</span></span>|  
|<span data-ttu-id="4ed7a-143">Reason</span><span class="sxs-lookup"><span data-stu-id="4ed7a-143">Reason</span></span>|<span data-ttu-id="4ed7a-144">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="4ed7a-144">win:UInt32</span></span>|<span data-ttu-id="4ed7a-145">¿Por qué se desencadenó la recolección de elementos no utilizados:</span><span class="sxs-lookup"><span data-stu-id="4ed7a-145">Why the garbage collection was triggered:</span></span><br /><br /> <span data-ttu-id="4ed7a-146">0x0: asignación del montón de objetos pequeños.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-146">0x0 - Small object heap allocation.</span></span><br /><br /> <span data-ttu-id="4ed7a-147">0x1: provocada.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-147">0x1 - Induced.</span></span><br /><br /> <span data-ttu-id="4ed7a-148">0x2: memoria insuficiente.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-148">0x2 - Low memory.</span></span><br /><br /> <span data-ttu-id="4ed7a-149">0x3: vacía.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-149">0x3 - Empty.</span></span><br /><br /> <span data-ttu-id="4ed7a-150">0x4: asignación del montón de objetos grandes.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-150">0x4 - Large object heap allocation.</span></span><br /><br /> <span data-ttu-id="4ed7a-151">0x5: espacio insuficiente (para montón de objetos pequeños).</span><span class="sxs-lookup"><span data-stu-id="4ed7a-151">0x5 - Out of space (for small object heap).</span></span><br /><br /> <span data-ttu-id="4ed7a-152">0x6: espacio insuficiente (para montón de objetos grandes).</span><span class="sxs-lookup"><span data-stu-id="4ed7a-152">0x6 - Out of space (for large object heap).</span></span><br /><br /> <span data-ttu-id="4ed7a-153">0x7: provocada pero no forzada como bloqueo.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-153">0x7 - Induced but not forced as blocking.</span></span>|  
|<span data-ttu-id="4ed7a-154">Type</span><span class="sxs-lookup"><span data-stu-id="4ed7a-154">Type</span></span>|<span data-ttu-id="4ed7a-155">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="4ed7a-155">win:UInt32</span></span>|<span data-ttu-id="4ed7a-156">0x0: el bloqueo de la recolección de elementos no utilizados se produjo fuera de recolección de elementos no utilizados en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-156">0x0 - Blocking garbage collection occurred outside background garbage collection.</span></span><br /><br /> <span data-ttu-id="4ed7a-157">0x1: recolección de elementos no utilizados en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-157">0x1 - Background garbage collection.</span></span><br /><br /> <span data-ttu-id="4ed7a-158">0x2: el bloqueo de la recolección de elementos no utilizados se produjo durante la recolección de elementos no utilizados en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-158">0x2 - Blocking garbage collection occurred during background garbage collection.</span></span>|  
|<span data-ttu-id="4ed7a-159">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="4ed7a-159">ClrInstanceID</span></span>|<span data-ttu-id="4ed7a-160">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="4ed7a-160">win:UInt16</span></span>|<span data-ttu-id="4ed7a-161">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-161">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="4ed7a-162">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="4ed7a-162">Back to top</span></span>](#top)  
  
<a name="gcend_v1_event"></a>   
## <a name="gcend_v1-event"></a><span data-ttu-id="4ed7a-163">Evento GCEnd_V1</span><span class="sxs-lookup"><span data-stu-id="4ed7a-163">GCEnd_V1 Event</span></span>  
 <span data-ttu-id="4ed7a-164">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-164">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="4ed7a-165">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="4ed7a-165">Keyword for raising the event</span></span>|<span data-ttu-id="4ed7a-166">Nivel</span><span class="sxs-lookup"><span data-stu-id="4ed7a-166">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="4ed7a-167">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="4ed7a-167">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="4ed7a-168">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="4ed7a-168">Informational (4)</span></span>|  
  
 <span data-ttu-id="4ed7a-169">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-169">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="4ed7a-170">Evento</span><span class="sxs-lookup"><span data-stu-id="4ed7a-170">Event</span></span>|<span data-ttu-id="4ed7a-171">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="4ed7a-171">Event ID</span></span>|<span data-ttu-id="4ed7a-172">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="4ed7a-172">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCEnd_V1`|<span data-ttu-id="4ed7a-173">2</span><span class="sxs-lookup"><span data-stu-id="4ed7a-173">2</span></span>|<span data-ttu-id="4ed7a-174">La recolección de elementos no utilizados ha finalizado.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-174">The garbage collection has ended.</span></span>|  
  
 <span data-ttu-id="4ed7a-175">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-175">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="4ed7a-176">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="4ed7a-176">Field name</span></span>|<span data-ttu-id="4ed7a-177">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="4ed7a-177">Data type</span></span>|<span data-ttu-id="4ed7a-178">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="4ed7a-178">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="4ed7a-179">Número</span><span class="sxs-lookup"><span data-stu-id="4ed7a-179">Count</span></span>|<span data-ttu-id="4ed7a-180">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="4ed7a-180">win:UInt32</span></span>|<span data-ttu-id="4ed7a-181">Recolección de elementos no utilizados número *n*.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-181">The *n*th garbage collection.</span></span>|  
|<span data-ttu-id="4ed7a-182">Profundidad</span><span class="sxs-lookup"><span data-stu-id="4ed7a-182">Depth</span></span>|<span data-ttu-id="4ed7a-183">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="4ed7a-183">win:UInt32</span></span>|<span data-ttu-id="4ed7a-184">Generación que se recopiló.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-184">The generation that was collected.</span></span>|  
|<span data-ttu-id="4ed7a-185">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="4ed7a-185">ClrInstanceID</span></span>|<span data-ttu-id="4ed7a-186">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="4ed7a-186">win:UInt16</span></span>|<span data-ttu-id="4ed7a-187">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-187">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="4ed7a-188">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="4ed7a-188">Back to top</span></span>](#top)  
  
<a name="gcheapstats_v1_event"></a>   
## <a name="gcheapstats_v1-event"></a><span data-ttu-id="4ed7a-189">Evento GCHeapStats_V1</span><span class="sxs-lookup"><span data-stu-id="4ed7a-189">GCHeapStats_V1 Event</span></span>  
 <span data-ttu-id="4ed7a-190">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-190">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="4ed7a-191">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="4ed7a-191">Keyword for raising the event</span></span>|<span data-ttu-id="4ed7a-192">Nivel</span><span class="sxs-lookup"><span data-stu-id="4ed7a-192">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="4ed7a-193">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="4ed7a-193">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="4ed7a-194">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="4ed7a-194">Informational (4)</span></span>|  
  
 <span data-ttu-id="4ed7a-195">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-195">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="4ed7a-196">Evento</span><span class="sxs-lookup"><span data-stu-id="4ed7a-196">Event</span></span>|<span data-ttu-id="4ed7a-197">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="4ed7a-197">Event ID</span></span>|<span data-ttu-id="4ed7a-198">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="4ed7a-198">Description</span></span>|  
|-----------|--------------|-----------------|  
|`GCHeapStats_V1`|<span data-ttu-id="4ed7a-199">4</span><span class="sxs-lookup"><span data-stu-id="4ed7a-199">4</span></span>|<span data-ttu-id="4ed7a-200">Muestra las estadísticas del montón al final de cada recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-200">Shows the heap statistics at the end of each garbage collection.</span></span>|  
  
 <span data-ttu-id="4ed7a-201">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-201">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="4ed7a-202">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="4ed7a-202">Field name</span></span>|<span data-ttu-id="4ed7a-203">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="4ed7a-203">Data type</span></span>|<span data-ttu-id="4ed7a-204">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="4ed7a-204">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="4ed7a-205">GenerationSize0</span><span class="sxs-lookup"><span data-stu-id="4ed7a-205">GenerationSize0</span></span>|<span data-ttu-id="4ed7a-206">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="4ed7a-206">win:UInt64</span></span>|<span data-ttu-id="4ed7a-207">Tamaño, en bytes, de la memoria de la generación 0.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-207">The size, in bytes, of generation 0 memory.</span></span>|  
|<span data-ttu-id="4ed7a-208">TotalPromotedSize0</span><span class="sxs-lookup"><span data-stu-id="4ed7a-208">TotalPromotedSize0</span></span>|<span data-ttu-id="4ed7a-209">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="4ed7a-209">win:UInt64</span></span>|<span data-ttu-id="4ed7a-210">Número de bytes que se promueven de generación 0 a generación 1.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-210">The number of bytes that are promoted from generation 0 to generation 1.</span></span>|  
|<span data-ttu-id="4ed7a-211">GenerationSize1</span><span class="sxs-lookup"><span data-stu-id="4ed7a-211">GenerationSize1</span></span>|<span data-ttu-id="4ed7a-212">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="4ed7a-212">win:UInt64</span></span>|<span data-ttu-id="4ed7a-213">Tamaño, en bytes, de la memoria de la generación 1.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-213">The size, in bytes, of generation 1 memory.</span></span>|  
|<span data-ttu-id="4ed7a-214">TotalPromotedSize1</span><span class="sxs-lookup"><span data-stu-id="4ed7a-214">TotalPromotedSize1</span></span>|<span data-ttu-id="4ed7a-215">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="4ed7a-215">win:UInt64</span></span>|<span data-ttu-id="4ed7a-216">Número de bytes que se promueven de generación 1 a generación 2.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-216">The number of bytes that are promoted from generation 1 to generation 2.</span></span>|  
|<span data-ttu-id="4ed7a-217">GenerationSize2</span><span class="sxs-lookup"><span data-stu-id="4ed7a-217">GenerationSize2</span></span>|<span data-ttu-id="4ed7a-218">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="4ed7a-218">win:UInt64</span></span>|<span data-ttu-id="4ed7a-219">Tamaño, en bytes, de la memoria de la generación 2.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-219">The size, in bytes, of generation 2 memory.</span></span>|  
|<span data-ttu-id="4ed7a-220">TotalPromotedSize2</span><span class="sxs-lookup"><span data-stu-id="4ed7a-220">TotalPromotedSize2</span></span>|<span data-ttu-id="4ed7a-221">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="4ed7a-221">win:UInt64</span></span>|<span data-ttu-id="4ed7a-222">Número de bytes que sobrevivieron en la generación 2 después de la última recolección.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-222">The number of bytes that survived in generation 2 after the last collection.</span></span>|  
|<span data-ttu-id="4ed7a-223">GenerationSize3</span><span class="sxs-lookup"><span data-stu-id="4ed7a-223">GenerationSize3</span></span>|<span data-ttu-id="4ed7a-224">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="4ed7a-224">win:UInt64</span></span>|<span data-ttu-id="4ed7a-225">Tamaño, en bytes, del montón de objetos grandes.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-225">The size, in bytes, of the large object heap.</span></span>|  
|<span data-ttu-id="4ed7a-226">TotalPromotedSize3</span><span class="sxs-lookup"><span data-stu-id="4ed7a-226">TotalPromotedSize3</span></span>|<span data-ttu-id="4ed7a-227">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="4ed7a-227">win:UInt64</span></span>|<span data-ttu-id="4ed7a-228">Número de bytes que sobrevivieron en el montón de objetos grandes después de la última recolección.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-228">The number of bytes that survived in the large object heap after the last collection.</span></span>|  
|<span data-ttu-id="4ed7a-229">FinalizationPromotedSize</span><span class="sxs-lookup"><span data-stu-id="4ed7a-229">FinalizationPromotedSize</span></span>|<span data-ttu-id="4ed7a-230">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="4ed7a-230">win:UInt64</span></span>|<span data-ttu-id="4ed7a-231">Tamaño total, en bytes, de los objetos que están listos para la finalización.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-231">The total size, in bytes, of the objects that are ready for finalization.</span></span>|  
|<span data-ttu-id="4ed7a-232">FinalizationPromotedCount</span><span class="sxs-lookup"><span data-stu-id="4ed7a-232">FinalizationPromotedCount</span></span>|<span data-ttu-id="4ed7a-233">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="4ed7a-233">win:UInt64</span></span>|<span data-ttu-id="4ed7a-234">Número de objetos que están listos para la finalización.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-234">The number of objects that are ready for finalization.</span></span>|  
|<span data-ttu-id="4ed7a-235">PinnedObjectCount</span><span class="sxs-lookup"><span data-stu-id="4ed7a-235">PinnedObjectCount</span></span>|<span data-ttu-id="4ed7a-236">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="4ed7a-236">win:UInt32</span></span>|<span data-ttu-id="4ed7a-237">Número de objetos anclados (inamovibles).</span><span class="sxs-lookup"><span data-stu-id="4ed7a-237">The number of pinned (unmovable) objects.</span></span>|  
|<span data-ttu-id="4ed7a-238">SinkBlockCount</span><span class="sxs-lookup"><span data-stu-id="4ed7a-238">SinkBlockCount</span></span>|<span data-ttu-id="4ed7a-239">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="4ed7a-239">win:UInt32</span></span>|<span data-ttu-id="4ed7a-240">Número de bloques de sincronización en uso.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-240">The number of synchronization blocks in use.</span></span>|  
|<span data-ttu-id="4ed7a-241">GCHandleCount</span><span class="sxs-lookup"><span data-stu-id="4ed7a-241">GCHandleCount</span></span>|<span data-ttu-id="4ed7a-242">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="4ed7a-242">win:UInt32</span></span>|<span data-ttu-id="4ed7a-243">Número de controles de recolección de elementos no utilizados en uso.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-243">The number of garbage collection handles in use.</span></span>|  
|<span data-ttu-id="4ed7a-244">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="4ed7a-244">ClrInstanceID</span></span>|<span data-ttu-id="4ed7a-245">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="4ed7a-245">win:UInt16</span></span>|<span data-ttu-id="4ed7a-246">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-246">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="4ed7a-247">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="4ed7a-247">Back to top</span></span>](#top)  
  
<a name="gccreatesegment_v1_event"></a>   
## <a name="gccreatesegment_v1-event"></a><span data-ttu-id="4ed7a-248">Evento GCCreateSegment_V1</span><span class="sxs-lookup"><span data-stu-id="4ed7a-248">GCCreateSegment_V1 Event</span></span>  
 <span data-ttu-id="4ed7a-249">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-249">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="4ed7a-250">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="4ed7a-250">Keyword for raising the event</span></span>|<span data-ttu-id="4ed7a-251">Nivel</span><span class="sxs-lookup"><span data-stu-id="4ed7a-251">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="4ed7a-252">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="4ed7a-252">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="4ed7a-253">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="4ed7a-253">Informational (4)</span></span>|  
  
 <span data-ttu-id="4ed7a-254">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-254">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="4ed7a-255">Evento</span><span class="sxs-lookup"><span data-stu-id="4ed7a-255">Event</span></span>|<span data-ttu-id="4ed7a-256">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="4ed7a-256">Event ID</span></span>|<span data-ttu-id="4ed7a-257">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="4ed7a-257">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCCreateSegment_V1`|<span data-ttu-id="4ed7a-258">5</span><span class="sxs-lookup"><span data-stu-id="4ed7a-258">5</span></span>|<span data-ttu-id="4ed7a-259">Se ha creado un nuevo segmento de recopilación de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-259">A new garbage collection segment has been created.</span></span> <span data-ttu-id="4ed7a-260">Además, si se habilita el seguimiento en un proceso que ya se está ejecutando, se genera este evento para cada segmento existente.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-260">In addition, when tracing is enabled on a process that is already running, this event is raised for each existing segment.</span></span>|  
  
 <span data-ttu-id="4ed7a-261">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-261">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="4ed7a-262">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="4ed7a-262">Field name</span></span>|<span data-ttu-id="4ed7a-263">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="4ed7a-263">Data type</span></span>|<span data-ttu-id="4ed7a-264">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="4ed7a-264">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="4ed7a-265">Dirección</span><span class="sxs-lookup"><span data-stu-id="4ed7a-265">Address</span></span>|<span data-ttu-id="4ed7a-266">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="4ed7a-266">win:UInt64</span></span>|<span data-ttu-id="4ed7a-267">Dirección del segmento.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-267">The address of the segment.</span></span>|  
|<span data-ttu-id="4ed7a-268">Tamaño</span><span class="sxs-lookup"><span data-stu-id="4ed7a-268">Size</span></span>|<span data-ttu-id="4ed7a-269">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="4ed7a-269">win:UInt64</span></span>|<span data-ttu-id="4ed7a-270">Tamaño del segmento.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-270">The size of the segment.</span></span>|  
|<span data-ttu-id="4ed7a-271">Type</span><span class="sxs-lookup"><span data-stu-id="4ed7a-271">Type</span></span>|<span data-ttu-id="4ed7a-272">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="4ed7a-272">win:UInt32</span></span>|<span data-ttu-id="4ed7a-273">0x0: montón de objetos pequeños.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-273">0x0 - Small object heap.</span></span><br /><br /> <span data-ttu-id="4ed7a-274">0x1: montón de objetos grandes.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-274">0x1 - Large object heap.</span></span><br /><br /> <span data-ttu-id="4ed7a-275">0x2: montón de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-275">0x2 - Read-only heap.</span></span>|  
|<span data-ttu-id="4ed7a-276">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="4ed7a-276">ClrInstanceID</span></span>|<span data-ttu-id="4ed7a-277">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="4ed7a-277">win:UInt16</span></span>|<span data-ttu-id="4ed7a-278">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-278">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 <span data-ttu-id="4ed7a-279">Tenga en cuenta que el tamaño de los segmentos asignados por el recolector de elementos no utilizados es específico de la implementación y está sujeto a cambios en cualquier momento, incluso en las actualizaciones periódicas.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-279">Note that the size of segments allocated by the garbage collector is implementation-specific and is subject to change at any time, including in periodic updates.</span></span> <span data-ttu-id="4ed7a-280">La aplicación nunca debe realizar suposiciones sobre el tamaño de un sector determinado ni depender de él, y tampoco debe intentar configurar la cantidad de memoria disponible para las asignaciones de segmentos.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-280">Your app should never make assumptions about or depend on a particular segment size, nor should it attempt to configure the amount of memory available for segment allocations.</span></span>  
  
 [<span data-ttu-id="4ed7a-281">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="4ed7a-281">Back to top</span></span>](#top)  
  
<a name="gcfreesegment_v1_event"></a>   
## <a name="gcfreesegment_v1-event"></a><span data-ttu-id="4ed7a-282">Evento GCFreeSegment_V1</span><span class="sxs-lookup"><span data-stu-id="4ed7a-282">GCFreeSegment_V1 Event</span></span>  
 <span data-ttu-id="4ed7a-283">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-283">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="4ed7a-284">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="4ed7a-284">Keyword for raising the event</span></span>|<span data-ttu-id="4ed7a-285">Nivel</span><span class="sxs-lookup"><span data-stu-id="4ed7a-285">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="4ed7a-286">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="4ed7a-286">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="4ed7a-287">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="4ed7a-287">Informational (4)</span></span>|  
  
 <span data-ttu-id="4ed7a-288">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-288">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="4ed7a-289">Evento</span><span class="sxs-lookup"><span data-stu-id="4ed7a-289">Event</span></span>|<span data-ttu-id="4ed7a-290">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="4ed7a-290">Event ID</span></span>|<span data-ttu-id="4ed7a-291">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="4ed7a-291">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCFreeSegment_V1`|<span data-ttu-id="4ed7a-292">6</span><span class="sxs-lookup"><span data-stu-id="4ed7a-292">6</span></span>|<span data-ttu-id="4ed7a-293">Se ha liberado un segmento de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-293">A garbage collection segment has been released.</span></span>|  
  
 <span data-ttu-id="4ed7a-294">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-294">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="4ed7a-295">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="4ed7a-295">Field name</span></span>|<span data-ttu-id="4ed7a-296">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="4ed7a-296">Data type</span></span>|<span data-ttu-id="4ed7a-297">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="4ed7a-297">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="4ed7a-298">Dirección</span><span class="sxs-lookup"><span data-stu-id="4ed7a-298">Address</span></span>|<span data-ttu-id="4ed7a-299">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="4ed7a-299">win:UInt64</span></span>|<span data-ttu-id="4ed7a-300">Dirección del segmento.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-300">The address of the segment.</span></span>|  
|<span data-ttu-id="4ed7a-301">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="4ed7a-301">ClrInstanceID</span></span>|<span data-ttu-id="4ed7a-302">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="4ed7a-302">win:UInt16</span></span>|<span data-ttu-id="4ed7a-303">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-303">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="4ed7a-304">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="4ed7a-304">Back to top</span></span>](#top)  
  
<a name="gcrestarteebegin_v1_event"></a>   
## <a name="gcrestarteebegin_v1-event"></a><span data-ttu-id="4ed7a-305">Evento GCRestartEEBegin_V1</span><span class="sxs-lookup"><span data-stu-id="4ed7a-305">GCRestartEEBegin_V1 Event</span></span>  
 <span data-ttu-id="4ed7a-306">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-306">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="4ed7a-307">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="4ed7a-307">Keyword for raising the event</span></span>|<span data-ttu-id="4ed7a-308">Nivel</span><span class="sxs-lookup"><span data-stu-id="4ed7a-308">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="4ed7a-309">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="4ed7a-309">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="4ed7a-310">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="4ed7a-310">Informational (4)</span></span>|  
  
 <span data-ttu-id="4ed7a-311">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-311">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="4ed7a-312">Evento</span><span class="sxs-lookup"><span data-stu-id="4ed7a-312">Event</span></span>|<span data-ttu-id="4ed7a-313">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="4ed7a-313">Event ID</span></span>|<span data-ttu-id="4ed7a-314">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="4ed7a-314">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCRestartEEBegin_V1`|<span data-ttu-id="4ed7a-315">7</span><span class="sxs-lookup"><span data-stu-id="4ed7a-315">7</span></span>|<span data-ttu-id="4ed7a-316">Ha comenzado la reanudación de la suspensión de Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-316">Resumption from common language runtime suspension has begun.</span></span>|  
  
 <span data-ttu-id="4ed7a-317">Sin datos del evento.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-317">No event data.</span></span>  
  
 [<span data-ttu-id="4ed7a-318">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="4ed7a-318">Back to top</span></span>](#top)  
  
<a name="gcrestarteeend_v1_event"></a>   
## <a name="gcrestarteeend_v1-event"></a><span data-ttu-id="4ed7a-319">Evento GCRestartEEEnd_V1</span><span class="sxs-lookup"><span data-stu-id="4ed7a-319">GCRestartEEEnd_V1 Event</span></span>  
 <span data-ttu-id="4ed7a-320">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-320">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="4ed7a-321">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="4ed7a-321">Keyword for raising the event</span></span>|<span data-ttu-id="4ed7a-322">Nivel</span><span class="sxs-lookup"><span data-stu-id="4ed7a-322">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="4ed7a-323">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="4ed7a-323">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="4ed7a-324">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="4ed7a-324">Informational (4)</span></span>|  
  
 <span data-ttu-id="4ed7a-325">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-325">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="4ed7a-326">Evento</span><span class="sxs-lookup"><span data-stu-id="4ed7a-326">Event</span></span>|<span data-ttu-id="4ed7a-327">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="4ed7a-327">Event Id</span></span>|<span data-ttu-id="4ed7a-328">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="4ed7a-328">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCRestartEEEnd_V1`|<span data-ttu-id="4ed7a-329">3</span><span class="sxs-lookup"><span data-stu-id="4ed7a-329">3</span></span>|<span data-ttu-id="4ed7a-330">Ha finalizado la reanudación de la suspensión de Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-330">Resumption from common language runtime suspension has ended.</span></span>|  
  
 <span data-ttu-id="4ed7a-331">Sin datos del evento.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-331">No event data.</span></span>  
  
 [<span data-ttu-id="4ed7a-332">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="4ed7a-332">Back to top</span></span>](#top)  
  
<a name="gcsuspendee_v1_event"></a>   
## <a name="gcsuspendee_v1-event"></a><span data-ttu-id="4ed7a-333">Evento GCSuspendEE_V1</span><span class="sxs-lookup"><span data-stu-id="4ed7a-333">GCSuspendEE_V1 Event</span></span>  
 <span data-ttu-id="4ed7a-334">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-334">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="4ed7a-335">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="4ed7a-335">Keyword for raising the event</span></span>|<span data-ttu-id="4ed7a-336">Nivel</span><span class="sxs-lookup"><span data-stu-id="4ed7a-336">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="4ed7a-337">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="4ed7a-337">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="4ed7a-338">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="4ed7a-338">Informational (4)</span></span>|  
  
 <span data-ttu-id="4ed7a-339">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-339">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="4ed7a-340">Evento</span><span class="sxs-lookup"><span data-stu-id="4ed7a-340">Event</span></span>|<span data-ttu-id="4ed7a-341">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="4ed7a-341">Event ID</span></span>|<span data-ttu-id="4ed7a-342">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="4ed7a-342">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCSuspendEE_V1`|<span data-ttu-id="4ed7a-343">9</span><span class="sxs-lookup"><span data-stu-id="4ed7a-343">9</span></span>|<span data-ttu-id="4ed7a-344">Inicio de la suspensión del motor de ejecución de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-344">Start of suspension of the execution engine for garbage collection.</span></span>|  
  
 <span data-ttu-id="4ed7a-345">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-345">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="4ed7a-346">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="4ed7a-346">Field name</span></span>|<span data-ttu-id="4ed7a-347">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="4ed7a-347">Data type</span></span>|<span data-ttu-id="4ed7a-348">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="4ed7a-348">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="4ed7a-349">Motivo</span><span class="sxs-lookup"><span data-stu-id="4ed7a-349">Reason</span></span>|<span data-ttu-id="4ed7a-350">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="4ed7a-350">win:UInt16</span></span>|<span data-ttu-id="4ed7a-351">0x0: otros.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-351">0x0 - Other.</span></span><br /><br /> <span data-ttu-id="4ed7a-352">0x1: recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-352">0x1 - Garbage collection.</span></span><br /><br /> <span data-ttu-id="4ed7a-353">0x2: cierre del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-353">0x2 - Application domain shutdown.</span></span><br /><br /> <span data-ttu-id="4ed7a-354">0x3: eliminación de código nativo.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-354">0x3 - Code pitching.</span></span><br /><br /> <span data-ttu-id="4ed7a-355">0x4: cierre.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-355">0x4 - Shutdown.</span></span><br /><br /> <span data-ttu-id="4ed7a-356">0x5: depurador.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-356">0x5 - Debugger.</span></span><br /><br /> <span data-ttu-id="4ed7a-357">0x6: preparación para la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-357">0x6 - Preparation for garbage collection.</span></span>|  
|<span data-ttu-id="4ed7a-358">Recuento</span><span class="sxs-lookup"><span data-stu-id="4ed7a-358">Count</span></span>|<span data-ttu-id="4ed7a-359">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="4ed7a-359">win:UInt32</span></span>|<span data-ttu-id="4ed7a-360">El recuento de GC en el momento.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-360">The GC count at the time.</span></span> <span data-ttu-id="4ed7a-361">Normalmente, verá un evento Inicio de GC posterior después de esto, y su recuento será este recuento + 1 a medida que aumentamos el índice de GC durante una recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-361">Usually, you would see a subsequent GC Start event after this, and its Count would be this Count + 1 as we increase the GC index during a garbage collection.</span></span>|  
|<span data-ttu-id="4ed7a-362">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="4ed7a-362">ClrInstanceID</span></span>|<span data-ttu-id="4ed7a-363">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="4ed7a-363">win:UInt16</span></span>|<span data-ttu-id="4ed7a-364">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-364">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="4ed7a-365">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="4ed7a-365">Back to top</span></span>](#top)  
  
<a name="gcsuspendeeend_v1_event"></a>   
## <a name="gcsuspendeeend_v1-event"></a><span data-ttu-id="4ed7a-366">Evento GCSuspendEE_V1</span><span class="sxs-lookup"><span data-stu-id="4ed7a-366">GCSuspendEEEnd_V1 Event</span></span>  
 <span data-ttu-id="4ed7a-367">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-367">The following table shows the keyword and level:</span></span>  
  
|<span data-ttu-id="4ed7a-368">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="4ed7a-368">Keyword for raising the event</span></span>|<span data-ttu-id="4ed7a-369">Nivel</span><span class="sxs-lookup"><span data-stu-id="4ed7a-369">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="4ed7a-370">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="4ed7a-370">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="4ed7a-371">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="4ed7a-371">Informational (4)</span></span>|  
  
 <span data-ttu-id="4ed7a-372">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-372">The following table shows the event information:</span></span>  
  
|<span data-ttu-id="4ed7a-373">Evento</span><span class="sxs-lookup"><span data-stu-id="4ed7a-373">Event</span></span>|<span data-ttu-id="4ed7a-374">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="4ed7a-374">Event ID</span></span>|<span data-ttu-id="4ed7a-375">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="4ed7a-375">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCSuspendEEEnd_V1`|<span data-ttu-id="4ed7a-376">8</span><span class="sxs-lookup"><span data-stu-id="4ed7a-376">8</span></span>|<span data-ttu-id="4ed7a-377">Final de la suspensión del motor de ejecución de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-377">End of suspension of the execution engine for garbage collection.</span></span>|  
  
 <span data-ttu-id="4ed7a-378">Sin datos del evento.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-378">No event data.</span></span>  
  
 [<span data-ttu-id="4ed7a-379">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="4ed7a-379">Back to top</span></span>](#top)  
  
<a name="gcallocationtick_v2_event"></a>   
## <a name="gcallocationtick_v2-event"></a><span data-ttu-id="4ed7a-380">Evento GCAllocationTick_V2</span><span class="sxs-lookup"><span data-stu-id="4ed7a-380">GCAllocationTick_V2 Event</span></span>  
 <span data-ttu-id="4ed7a-381">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-381">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="4ed7a-382">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="4ed7a-382">Keyword for raising the event</span></span>|<span data-ttu-id="4ed7a-383">Nivel</span><span class="sxs-lookup"><span data-stu-id="4ed7a-383">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="4ed7a-384">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="4ed7a-384">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="4ed7a-385">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="4ed7a-385">Informational (4)</span></span>|  
  
 <span data-ttu-id="4ed7a-386">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-386">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="4ed7a-387">Evento</span><span class="sxs-lookup"><span data-stu-id="4ed7a-387">Event</span></span>|<span data-ttu-id="4ed7a-388">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="4ed7a-388">Event ID</span></span>|<span data-ttu-id="4ed7a-389">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="4ed7a-389">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCAllocationTick_V2`|<span data-ttu-id="4ed7a-390">10</span><span class="sxs-lookup"><span data-stu-id="4ed7a-390">10</span></span>|<span data-ttu-id="4ed7a-391">Cada vez se asignan aproximadamente 100 KB.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-391">Each time approximately 100 KB is allocated.</span></span>|  
  
 <span data-ttu-id="4ed7a-392">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-392">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="4ed7a-393">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="4ed7a-393">Field name</span></span>|<span data-ttu-id="4ed7a-394">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="4ed7a-394">Data type</span></span>|<span data-ttu-id="4ed7a-395">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="4ed7a-395">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="4ed7a-396">AllocationAmount</span><span class="sxs-lookup"><span data-stu-id="4ed7a-396">AllocationAmount</span></span>|<span data-ttu-id="4ed7a-397">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="4ed7a-397">win:UInt32</span></span>|<span data-ttu-id="4ed7a-398">Tamaño de la asignación, en bytes.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-398">The allocation size, in bytes.</span></span> <span data-ttu-id="4ed7a-399">Este valor es preciso para las asignaciones que son menores que la longitud de ULONG (4.294.967.295 bytes).</span><span class="sxs-lookup"><span data-stu-id="4ed7a-399">This value is accurate for allocations that are less than the length of a ULONG (4,294,967,295 bytes).</span></span> <span data-ttu-id="4ed7a-400">Si la asignación es mayor, este campo contiene un valor truncado.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-400">If the allocation is greater, this field contains a truncated value.</span></span> <span data-ttu-id="4ed7a-401">Use `AllocationAmount64` para asignaciones muy grandes.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-401">Use `AllocationAmount64` for very large allocations.</span></span>|  
|<span data-ttu-id="4ed7a-402">AllocationKind</span><span class="sxs-lookup"><span data-stu-id="4ed7a-402">AllocationKind</span></span>|<span data-ttu-id="4ed7a-403">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="4ed7a-403">win:UInt32</span></span>|<span data-ttu-id="4ed7a-404">0x0: asignación de objetos pequeños (la asignación está en un montón de objetos pequeños).</span><span class="sxs-lookup"><span data-stu-id="4ed7a-404">0x0 - Small object allocation (allocation is in small object heap).</span></span><br /><br /> <span data-ttu-id="4ed7a-405">0x1: asignación de objetos grandes (la asignación está en un montón de objetos grandes).</span><span class="sxs-lookup"><span data-stu-id="4ed7a-405">0x1 - Large object allocation (allocation is in large object heap).</span></span>|  
|<span data-ttu-id="4ed7a-406">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="4ed7a-406">ClrInstanceID</span></span>|<span data-ttu-id="4ed7a-407">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="4ed7a-407">win:UInt16</span></span>|<span data-ttu-id="4ed7a-408">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-408">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
|<span data-ttu-id="4ed7a-409">AllocationAmount64</span><span class="sxs-lookup"><span data-stu-id="4ed7a-409">AllocationAmount64</span></span>|<span data-ttu-id="4ed7a-410">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="4ed7a-410">win:UInt64</span></span>|<span data-ttu-id="4ed7a-411">Tamaño de la asignación, en bytes.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-411">The allocation size, in bytes.</span></span> <span data-ttu-id="4ed7a-412">Este valor es preciso para asignaciones muy grandes.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-412">This value is accurate for very large allocations.</span></span>|  
|<span data-ttu-id="4ed7a-413">TypeId</span><span class="sxs-lookup"><span data-stu-id="4ed7a-413">TypeId</span></span>|<span data-ttu-id="4ed7a-414">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="4ed7a-414">win:Pointer</span></span>|<span data-ttu-id="4ed7a-415">Dirección de la MethodTable.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-415">The address of the MethodTable.</span></span> <span data-ttu-id="4ed7a-416">Cuando durante este evento se asignaron varios tipos de objetos, esta es la dirección de la MethodTable que corresponde al último objeto asignado (es decir, el objeto que hizo que se supere el umbral de 100 KB).</span><span class="sxs-lookup"><span data-stu-id="4ed7a-416">When there are several types of objects that were allocated during this event, this is the address of the MethodTable that corresponds to the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|  
|<span data-ttu-id="4ed7a-417">TypeName</span><span class="sxs-lookup"><span data-stu-id="4ed7a-417">TypeName</span></span>|<span data-ttu-id="4ed7a-418">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="4ed7a-418">win:UnicodeString</span></span>|<span data-ttu-id="4ed7a-419">Nombre del tipo que se asignó.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-419">The name of the type that was allocated.</span></span> <span data-ttu-id="4ed7a-420">Cuando durante este evento se asignaron varios tipos de objetos, este es el tipo del último objeto asignado (es decir, el objeto que hizo que se supere el umbral de 100 KB).</span><span class="sxs-lookup"><span data-stu-id="4ed7a-420">When there are several types of objects that were allocated during this event, this is the type of the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|  
|<span data-ttu-id="4ed7a-421">HeapIndex</span><span class="sxs-lookup"><span data-stu-id="4ed7a-421">HeapIndex</span></span>|<span data-ttu-id="4ed7a-422">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="4ed7a-422">win:UInt32</span></span>|<span data-ttu-id="4ed7a-423">Montón al que se ha asignado el objeto.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-423">The heap where the object was allocated.</span></span> <span data-ttu-id="4ed7a-424">Este valor es 0 (cero) cuando se ejecuta con la recolección de elementos no utilizados de estación de trabajo.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-424">This value is 0 (zero) when running with workstation garbage collection.</span></span>|  
  
 [<span data-ttu-id="4ed7a-425">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="4ed7a-425">Back to top</span></span>](#top)  
  
<a name="gcfinalizersbegin_v1_event"></a>   
## <a name="gcfinalizersbegin_v1-event"></a><span data-ttu-id="4ed7a-426">Evento GCFinalizersBegin_V1</span><span class="sxs-lookup"><span data-stu-id="4ed7a-426">GCFinalizersBegin_V1 Event</span></span>  
 <span data-ttu-id="4ed7a-427">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-427">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="4ed7a-428">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="4ed7a-428">Keyword for raising the event</span></span>|<span data-ttu-id="4ed7a-429">Nivel</span><span class="sxs-lookup"><span data-stu-id="4ed7a-429">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="4ed7a-430">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="4ed7a-430">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="4ed7a-431">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="4ed7a-431">Informational (4)</span></span>|  
  
 <span data-ttu-id="4ed7a-432">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-432">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="4ed7a-433">Evento</span><span class="sxs-lookup"><span data-stu-id="4ed7a-433">Event</span></span>|<span data-ttu-id="4ed7a-434">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="4ed7a-434">Event ID</span></span>|<span data-ttu-id="4ed7a-435">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="4ed7a-435">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCFinalizersBegin_V1`|<span data-ttu-id="4ed7a-436">14</span><span class="sxs-lookup"><span data-stu-id="4ed7a-436">14</span></span>|<span data-ttu-id="4ed7a-437">Inicio de los finalizadores en ejecución.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-437">The start of running finalizers.</span></span>|  
  
 <span data-ttu-id="4ed7a-438">Sin datos del evento.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-438">No event data.</span></span>  
  
 [<span data-ttu-id="4ed7a-439">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="4ed7a-439">Back to top</span></span>](#top)  
  
<a name="gcfinalizersend_v1_event"></a>   
## <a name="gcfinalizersend_v1-event"></a><span data-ttu-id="4ed7a-440">Evento GCFinalizersEnd_V1</span><span class="sxs-lookup"><span data-stu-id="4ed7a-440">GCFinalizersEnd_V1 Event</span></span>  
 <span data-ttu-id="4ed7a-441">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-441">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="4ed7a-442">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="4ed7a-442">Keyword for raising the event</span></span>|<span data-ttu-id="4ed7a-443">Nivel</span><span class="sxs-lookup"><span data-stu-id="4ed7a-443">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="4ed7a-444">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="4ed7a-444">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="4ed7a-445">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="4ed7a-445">Informational (4)</span></span>|  
  
 <span data-ttu-id="4ed7a-446">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-446">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="4ed7a-447">Evento</span><span class="sxs-lookup"><span data-stu-id="4ed7a-447">Event</span></span>|<span data-ttu-id="4ed7a-448">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="4ed7a-448">Event ID</span></span>|<span data-ttu-id="4ed7a-449">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="4ed7a-449">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCFinalizersEnd_V1`|<span data-ttu-id="4ed7a-450">13</span><span class="sxs-lookup"><span data-stu-id="4ed7a-450">13</span></span>|<span data-ttu-id="4ed7a-451">Final de los finalizadores en ejecución.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-451">The end of running finalizers.</span></span>|  
  
 <span data-ttu-id="4ed7a-452">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-452">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="4ed7a-453">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="4ed7a-453">Field name</span></span>|<span data-ttu-id="4ed7a-454">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="4ed7a-454">Data type</span></span>|<span data-ttu-id="4ed7a-455">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="4ed7a-455">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="4ed7a-456">Número</span><span class="sxs-lookup"><span data-stu-id="4ed7a-456">Count</span></span>|<span data-ttu-id="4ed7a-457">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="4ed7a-457">win:UInt32</span></span>|<span data-ttu-id="4ed7a-458">Número de finalizadores que se ejecutó.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-458">The number of finalizers that were run.</span></span>|  
|<span data-ttu-id="4ed7a-459">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="4ed7a-459">ClrInstanceID</span></span>|<span data-ttu-id="4ed7a-460">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="4ed7a-460">win:UInt16</span></span>|<span data-ttu-id="4ed7a-461">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-461">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="4ed7a-462">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="4ed7a-462">Back to top</span></span>](#top)  
  
<a name="gccreateconcurrentthread_v1_event"></a>   
## <a name="gccreateconcurrentthread_v1-event"></a><span data-ttu-id="4ed7a-463">Evento GCCreateConcurrentThread_V1</span><span class="sxs-lookup"><span data-stu-id="4ed7a-463">GCCreateConcurrentThread_V1 Event</span></span>  
 <span data-ttu-id="4ed7a-464">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-464">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="4ed7a-465">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="4ed7a-465">Keyword for raising the event</span></span>|<span data-ttu-id="4ed7a-466">Nivel</span><span class="sxs-lookup"><span data-stu-id="4ed7a-466">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="4ed7a-467">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="4ed7a-467">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="4ed7a-468">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="4ed7a-468">Informational (4)</span></span>|  
|<span data-ttu-id="4ed7a-469">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="4ed7a-469">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="4ed7a-470">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="4ed7a-470">Informational (4)</span></span>|  
  
 <span data-ttu-id="4ed7a-471">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-471">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="4ed7a-472">Evento</span><span class="sxs-lookup"><span data-stu-id="4ed7a-472">Event</span></span>|<span data-ttu-id="4ed7a-473">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="4ed7a-473">Event ID</span></span>|<span data-ttu-id="4ed7a-474">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="4ed7a-474">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCCreateConcurrentThread_V1`|<span data-ttu-id="4ed7a-475">11</span><span class="sxs-lookup"><span data-stu-id="4ed7a-475">11</span></span>|<span data-ttu-id="4ed7a-476">El subproceso de recolección de elementos no utilizados simultánea se creó.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-476">Concurrent garbage collection thread was created.</span></span>|  
  
 <span data-ttu-id="4ed7a-477">Sin datos del evento.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-477">No event data.</span></span>  
  
 [<span data-ttu-id="4ed7a-478">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="4ed7a-478">Back to top</span></span>](#top)  
  
<a name="gcterminateconcurrentthread_v1_event"></a>   
## <a name="gcterminateconcurrentthread_v1-event"></a><span data-ttu-id="4ed7a-479">Evento GCCreateConcurrentThread_V1</span><span class="sxs-lookup"><span data-stu-id="4ed7a-479">GCTerminateConcurrentThread_V1 Event</span></span>  
 <span data-ttu-id="4ed7a-480">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-480">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="4ed7a-481">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="4ed7a-481">Keyword for raising the event</span></span>|<span data-ttu-id="4ed7a-482">Nivel</span><span class="sxs-lookup"><span data-stu-id="4ed7a-482">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="4ed7a-483">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="4ed7a-483">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="4ed7a-484">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="4ed7a-484">Informational (4)</span></span>|  
|<span data-ttu-id="4ed7a-485">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="4ed7a-485">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="4ed7a-486">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="4ed7a-486">Informational (4)</span></span>|  
  
 <span data-ttu-id="4ed7a-487">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-487">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="4ed7a-488">Evento</span><span class="sxs-lookup"><span data-stu-id="4ed7a-488">Event</span></span>|<span data-ttu-id="4ed7a-489">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="4ed7a-489">Event ID</span></span>|<span data-ttu-id="4ed7a-490">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="4ed7a-490">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCTerminateConcurrentThread_V1`|<span data-ttu-id="4ed7a-491">12</span><span class="sxs-lookup"><span data-stu-id="4ed7a-491">12</span></span>|<span data-ttu-id="4ed7a-492">El subproceso de recolección de elementos no utilizados simultánea finalizó.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-492">Concurrent garbage collection thread was terminated.</span></span>|  
  
 <span data-ttu-id="4ed7a-493">Sin datos del evento.</span><span class="sxs-lookup"><span data-stu-id="4ed7a-493">No event data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ed7a-494">Vea también</span><span class="sxs-lookup"><span data-stu-id="4ed7a-494">See also</span></span>

- [<span data-ttu-id="4ed7a-495">CLR ETW Events (Eventos ETW de CLR)</span><span class="sxs-lookup"><span data-stu-id="4ed7a-495">CLR ETW Events</span></span>](clr-etw-events.md)
