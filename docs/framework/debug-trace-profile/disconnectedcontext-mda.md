---
title: MDA de disconnectedContext
ms.date: 03/30/2017
helpviewer_keywords:
- DisconnectedContext MDA
- MDAs (managed debugging assistants), disconnected context
- dead context
- transitioning disconnected apartment or context
- context disconnections
- managed debugging assistants (MDAs), disconnected context
ms.assetid: 1887d31d-7006-4491-93b3-68fd5b05f71d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 670a32b4d198d2762e0bb51e41297836e471e05b
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2019
ms.locfileid: "71052840"
---
# <a name="disconnectedcontext-mda"></a>MDA de disconnectedContext
El asistente para la depuración administrada (MDA, por sus siglas en inglés) `disconnectedContext` se activa cuando el CLR intenta realizar una transición a un contexto o apartamento desconectado mientras atiende una solicitud relativa a un objeto COM.  
  
## <a name="symptoms"></a>Síntomas  
 Las llamadas realizadas en un [contenedor RCW](../../standard/native-interop/runtime-callable-wrapper.md) (RCW) se entregan al componente COM subyacente en el contexto o apartamento actual, en vez de entregarse en el que existen. Esto puede causar daños o pérdida de datos si el componente COM no es multiproceso, como en el caso de componentes de contenedor uniproceso (STA, por sus siglas en inglés). O bien, si el RCW es un proxy, la llamada puede producir una <xref:System.Runtime.InteropServices.COMException> con un HRESULT de RPC_E_WRONG_THREAD.  
  
## <a name="cause"></a>Causa  
 El apartamento o contexto OLE se cierra cuando el CLR intenta realizar una transición hacia él. Con frecuencia, la causa es que los contenedores STA se cierran antes de que todos los componentes COM propiedad del apartamento se liberen completamente. Esto puede deberse a una llamada explícita del código de usuario en un RCW o mientras el CLR manipula el componente COM, por ejemplo, cuando el CLR libera el componente COM si el RCW asociado se ha recolectado por no utilizarse.  
  
## <a name="resolution"></a>Resolución  
 Para evitar este problema, asegúrese de que el subproceso que posee el STA no termina antes de que la aplicación haya finalizado con todos los objetos que habitan en el apartamento. Lo mismo es aplicable a los contextos; asegúrese de que estos no se cierran antes de que la aplicación finalice completamente con todos los componentes COM que habitan en el contexto.  
  
## <a name="effect-on-the-runtime"></a>Efecto en el Runtime  
 Este MDA no tiene ningún efecto en el CLR. Solo recoge datos sobre el contexto desconectado.  
  
## <a name="output"></a>Resultados  
 Recoge la cookie de contexto del apartamento o contexto desconectado.  
  
## <a name="configuration"></a>Configuración  
  
```xml  
<mdaConfig>  
  <assistants>  
    <disconnectedContext />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Vea también

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [Diagnosing Errors with Managed Debugging Assistants (Diagnóstico de errores con asistentes para la depuración administrada)](diagnosing-errors-with-managed-debugging-assistants.md)
- [Serialización de interoperabilidad](../interop/interop-marshaling.md)
