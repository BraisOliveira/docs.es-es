---
title: MDA de invalidIUnknownPointer
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), invalid IUnknown pointer
- InvalidIUnknown MDA
- invalid IUnknown pointers
- IUnknown pointers
- managed debugging assistants (MDAs), invalid IUnknown pointer
ms.assetid: c7924771-a16b-40fe-b337-ce51dcdf6a12
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ea7f48ab61c16cb0430717074f1b1feab4827763
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2019
ms.locfileid: "71052594"
---
# <a name="invalidiunknown-mda"></a><span data-ttu-id="73a54-102">MDA de invalidIUnknownPointer</span><span class="sxs-lookup"><span data-stu-id="73a54-102">invalidIUnknown MDA</span></span>
<span data-ttu-id="73a54-103">El asistente para la depuración administrada (MDA) de `invalidIUnknown` se activa cuando un puntero `IUnknown` no válido se pasa a código administrado de código nativo.</span><span class="sxs-lookup"><span data-stu-id="73a54-103">The `invalidIUnknown` managed debugging assistant (MDA) is activated when an invalid `IUnknown` pointer is passed to managed code from native code.</span></span> <span data-ttu-id="73a54-104">Se produce un error en `IUnknown` a la hora de devolver un resultado correctamente cuando se solicita la interfaz `IUnknown`.</span><span class="sxs-lookup"><span data-stu-id="73a54-104">The `IUnknown` fails to return success when queried for the `IUnknown` interface.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="73a54-105">Síntomas</span><span class="sxs-lookup"><span data-stu-id="73a54-105">Symptoms</span></span>  
 <span data-ttu-id="73a54-106">Se produce un error inesperado al calcular referencias de un puntero a una interfaz COM durante el cálculo de referencias del argumento.</span><span class="sxs-lookup"><span data-stu-id="73a54-106">An unexpected error occurs when marshaling a COM interface pointer during argument marshaling.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="73a54-107">Causa</span><span class="sxs-lookup"><span data-stu-id="73a54-107">Cause</span></span>  
 <span data-ttu-id="73a54-108">Implementación de `QueryInterface` incorrecta en la interfaz COM pasada al CLR.</span><span class="sxs-lookup"><span data-stu-id="73a54-108">An incorrect `QueryInterface` implementation on the COM interface passed to the CLR.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="73a54-109">Resolución</span><span class="sxs-lookup"><span data-stu-id="73a54-109">Resolution</span></span>  
 <span data-ttu-id="73a54-110">Corrija la implementación de `QueryInterface`.</span><span class="sxs-lookup"><span data-stu-id="73a54-110">Correct the `QueryInterface` implementation.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="73a54-111">Efecto en el Runtime</span><span class="sxs-lookup"><span data-stu-id="73a54-111">Effect on the Runtime</span></span>  
 <span data-ttu-id="73a54-112">Este MDA no tiene ningún efecto en el CLR.</span><span class="sxs-lookup"><span data-stu-id="73a54-112">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="73a54-113">Resultados</span><span class="sxs-lookup"><span data-stu-id="73a54-113">Output</span></span>  
 <span data-ttu-id="73a54-114">Descripción del error.</span><span class="sxs-lookup"><span data-stu-id="73a54-114">The description of the error.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="73a54-115">Configuración</span><span class="sxs-lookup"><span data-stu-id="73a54-115">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidIUnknown />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="73a54-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="73a54-116">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="73a54-117">Diagnosing Errors with Managed Debugging Assistants (Diagnóstico de errores con asistentes para la depuración administrada)</span><span class="sxs-lookup"><span data-stu-id="73a54-117">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="73a54-118">Serialización de interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="73a54-118">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
