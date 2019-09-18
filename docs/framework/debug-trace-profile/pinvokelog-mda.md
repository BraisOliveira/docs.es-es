---
title: MDA de pInvokeLog
ms.date: 03/30/2017
helpviewer_keywords:
- signatures, platform invoke
- MDAs (managed debugging assistants), platform invoke
- platform invoke, run-time errors
- platform invoke log
- PInvokeLog MDA
- managed debugging assistants (MDAs), platform invoke
ms.assetid: b830444a-5003-49fe-b89b-b8bee22f7b1a
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0883849eee12922601e50c2337bb0048d77cab68
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2019
ms.locfileid: "71052377"
---
# <a name="pinvokelog-mda"></a><span data-ttu-id="1ec1c-102">MDA de pInvokeLog</span><span class="sxs-lookup"><span data-stu-id="1ec1c-102">pInvokeLog MDA</span></span>
<span data-ttu-id="1ec1c-103">El Asistente para la depuración administrada (MDA) `pInvokeLog` se activa para cada firma de invocación de plataforma única que se usa durante la ejecución.</span><span class="sxs-lookup"><span data-stu-id="1ec1c-103">The `pInvokeLog` managed debugging assistant (MDA) is activated for each unique platform invoke signature used during execution.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="1ec1c-104">Efecto en el Runtime</span><span class="sxs-lookup"><span data-stu-id="1ec1c-104">Effect on the Runtime</span></span>  
 <span data-ttu-id="1ec1c-105">Este MDA no tiene ningún efecto en el CLR.</span><span class="sxs-lookup"><span data-stu-id="1ec1c-105">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="1ec1c-106">Resultados</span><span class="sxs-lookup"><span data-stu-id="1ec1c-106">Output</span></span>  
 <span data-ttu-id="1ec1c-107">Un mensaje que indica la firma de invocación de plataforma que se usa durante la ejecución.</span><span class="sxs-lookup"><span data-stu-id="1ec1c-107">A message indicating the platform invoke signature used during execution.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="1ec1c-108">Configuración</span><span class="sxs-lookup"><span data-stu-id="1ec1c-108">Configuration</span></span>  
 <span data-ttu-id="1ec1c-109">Cada elemento coincidente filtra los archivos .dll a los que se realizan llamadas de invocación de plataforma.</span><span class="sxs-lookup"><span data-stu-id="1ec1c-109">Each match element filters the .dll files to which platform invoke calls are made.</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <pInvokeLog>  
      <filter>  
        <match dllName="user32.dll"/>  
        <match dllName="kernel32.dll"/>  
      </filter>  
    </pInvokeLog>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1ec1c-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="1ec1c-110">See also</span></span>

- [<span data-ttu-id="1ec1c-111">Diagnosing Errors with Managed Debugging Assistants (Diagnóstico de errores con asistentes para la depuración administrada)</span><span class="sxs-lookup"><span data-stu-id="1ec1c-111">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="1ec1c-112">Consumir funciones DLL no administradas</span><span class="sxs-lookup"><span data-stu-id="1ec1c-112">Consuming Unmanaged DLL Functions</span></span>](../interop/consuming-unmanaged-dll-functions.md)
