---
title: Procedimiento para escuchar solicitudes de cancelación mediante sondeo
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cancellation, how to poll for requests
ms.assetid: c7f2f022-d08e-4e00-b4eb-ae84844cb1bc
ms.openlocfilehash: df76674e3003bbb77ef062e90b1dc3283f681d35
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138020"
---
# <a name="how-to-listen-for-cancellation-requests-by-polling"></a>Procedimiento para escuchar solicitudes de cancelación mediante sondeo
En el ejemplo siguiente se muestra una manera de que el código de usuario pueda sondear un token de cancelación a intervalos regulares para ver si se ha solicitado la cancelación del subproceso que realiza la llamada. En este ejemplo se usa el tipo <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>, pero se aplica el mismo modelo a operaciones asincrónicas creadas directamente por el tipo <xref:System.Threading.ThreadPool?displayProperty=nameWithType> o el tipo <xref:System.Threading.Thread?displayProperty=nameWithType>.  
  
## <a name="example"></a>Ejemplo  
 El sondeo necesita algún tipo de bucle o código recursivo que pueda leer periódicamente el valor de la propiedad booleana <xref:System.Threading.CancellationToken.IsCancellationRequested%2A>. Si usa el tipo <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> y espera a que la tarea se complete en el subproceso que realiza la llamada, puede usar el método <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> para comprobar la propiedad y generar la excepción. Con este método, se asegura de que se produce la excepción correcta en respuesta a una solicitud. Si usa <xref:System.Threading.Tasks.Task>, llamar a este método es mejor que generar <xref:System.OperationCanceledException> manualmente. Si no tiene que generar la excepción, puede comprobar la propiedad y obtener una devolución del método si la propiedad es `true`.  
  
 [!code-csharp[Cancellation#11](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex11.cs#11)]
 [!code-vb[Cancellation#11](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex11.vb#11)]  
  
 Una llamada a <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> es muy rápida y no presenta una sobrecarga significativa en bucles.  
  
 Si llama a <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A>, solo tiene que comprobar explícitamente la propiedad <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> si tiene que hacer otro trabajo para responder a la cancelación, aparte de generar la excepción. En este ejemplo, puede ver que el código realmente tiene acceso a la propiedad dos veces: una vez en el acceso explícito y de nuevo en el método <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A>. Sin embargo, dado que el acto de leer la propiedad <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> conlleva solo una instrucción de lectura volátil por acceso, el acceso doble no es significativo desde una perspectiva de rendimiento. Es preferible llamar al método en lugar de producir manualmente <xref:System.OperationCanceledException>.  
  
## <a name="see-also"></a>Vea también

- [Cancelación en subprocesos administrados](../../../docs/standard/threading/cancellation-in-managed-threads.md)
