---
title: MDA de fatalExecutionError
ms.date: 03/30/2017
helpviewer_keywords:
- corrupted CLR
- fatal execution error
- terminated processes
- unexpected terminations
- fatal errors
- MDAs (managed debugging assistants), fatal errors
- process termination
- FatalExecutionEngineError MDA
- managed debugging assistants (MDAs), fatal errors
ms.assetid: 8b559e44-2393-4e4e-8160-7558d37a4a89
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3fd58ae8f73fd932df641ea96a44ff618dd139e2
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2019
ms.locfileid: "71052808"
---
# <a name="fatalexecutionengineerror-mda"></a>MDA de fatalExecutionError
El Ayudante para la depuración administrada (MDA) de `fatalExecutionEngineError` se activa cuando se detecta un error grave en Common Language Runtime (CLR). Esto finaliza el proceso.  
  
## <a name="symptoms"></a>Síntomas  
 Finalización de proceso inesperada. No se pueden determinar otros síntomas porque los errores de CLR pueden ser debidos a distintos motivos.  
  
## <a name="cause"></a>Causa  
 CLR ha sufrido un daño grave. En la mayoría de los casos, esto se debe a los daños en los datos, lo que puede deberse a distintos problemas como, por ejemplo, llamar a funciones de invocación de plataforma incorrectas o pasar datos no válidos a CLR.  
  
## <a name="resolution"></a>Resolución  
 Si se habilitan Ayudantes para la depuración administrada adicionales, se podría ayudar a identificar el problema. Los siguientes Ayudantes para la depuración administrada pueden resultar especialmente útiles a la hora de diagnosticar el problema:  
  
- [invalidOverlappedToPinvoke](invalidoverlappedtopinvoke-mda.md)  
  
- [overlappedFreeError](overlappedfreeerror-mda.md)  
  
- [pInvokeStackImbalance](pinvokestackimbalance-mda.md)  
  
- [gcUnmanagedToManaged](gcunmanagedtomanaged-mda.md)  
  
- [gcManagedToUnmanaged](gcmanagedtounmanaged-mda.md)  
  
- [callbackOnCollectedDelegate](callbackoncollecteddelegate-mda.md)  
  
- [reportAvOnComRelease](reportavoncomrelease-mda.md)  
  
- [invalidVariant](invalidvariant-mda.md)  
  
- [invalidIUnknown](invalidiunknown-mda.md)  
  
- [raceOnRCWCleanup](raceonrcwcleanup-mda.md)  
  
- [invalidFunctionPointerInDelegate](invalidfunctionpointerindelegate-mda.md)  
  
- [invalidGCHandleCookie](invalidgchandlecookie-mda.md)  
  
## <a name="effect-on-the-runtime"></a>Efecto en el Runtime  
 Este MDA no tiene ningún efecto en el comportamiento del tiempo de ejecución.  
  
## <a name="output"></a>Resultados  
 La dirección de la función de CLR que ha producido el error grave, el identificador del subproceso donde se ha producido el error y el código de error.  
  
## <a name="configuration"></a>Configuración  
  
```xml  
<mdaConfig>  
  <assistants>  
    <fatalExecutionEngineError />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Vea también

- <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A>
- <xref:System.Runtime.ConstrainedExecution.Cer>
- [Diagnosing Errors with Managed Debugging Assistants (Diagnóstico de errores con asistentes para la depuración administrada)](diagnosing-errors-with-managed-debugging-assistants.md)
