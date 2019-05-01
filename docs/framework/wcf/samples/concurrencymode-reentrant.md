---
title: ConcurrencyMode reentrante
ms.date: 03/30/2017
ms.assetid: b2046c38-53d8-4a6c-a084-d6c7091d92b1
ms.openlocfilehash: 2170b029f1cb4a85a1b2688fc1143ffcd1682fe6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62002337"
---
# <a name="concurrencymode-reentrant"></a><span data-ttu-id="8b42c-102">ConcurrencyMode reentrante</span><span class="sxs-lookup"><span data-stu-id="8b42c-102">ConcurrencyMode Reentrant</span></span>
<span data-ttu-id="8b42c-103">Este ejemplo muestra la necesidad y las implicaciones de utilizar ConcurrencyMode.Reentrant en una implementación del servicio.</span><span class="sxs-lookup"><span data-stu-id="8b42c-103">This sample demonstrates the necessity and implications of using ConcurrencyMode.Reentrant on a service implementation.</span></span> <span data-ttu-id="8b42c-104">ConcurrencyMode.Reentrant implica que el servicio (o la devolución de llamada) procesa solo uno mensaje en una hora determinada (análogo a `ConcurencyMode.Single`).</span><span class="sxs-lookup"><span data-stu-id="8b42c-104">ConcurrencyMode.Reentrant implies that the service (or callback) processes only one message at a given time (analogous to `ConcurencyMode.Single`).</span></span> <span data-ttu-id="8b42c-105">Para garantizar la seguridad para subprocesos, Windows Communication Foundation (WCF) bloquea la `InstanceContext` procesar un mensaje para que no se puedan procesar ningún otro mensaje.</span><span class="sxs-lookup"><span data-stu-id="8b42c-105">To ensure thread safety, Windows Communication Foundation (WCF) locks the `InstanceContext` processing a message so that no other messages can be processed.</span></span> <span data-ttu-id="8b42c-106">En el caso del modo reentrante, `InstanceContext` se desbloquea justo antes de que el servicio haga una llamada de salida por la que permite la llamada subsiguiente, (que puede ser reentrante como se muestra en el ejemplo) para obtener el bloqueo la próxima vez que entre al servicio.</span><span class="sxs-lookup"><span data-stu-id="8b42c-106">In case of Reentrant mode, the `InstanceContext` is unlocked just before the service makes an outgoing call thereby allowing the subsequent call, (which can be reentrant as demonstrated in the sample) to get the lock next time it comes in to the service.</span></span> <span data-ttu-id="8b42c-107">Para mostrar el comportamiento, el ejemplo muestra cómo un cliente y el servicio pueden enviar los mensajes entre sí utilizando un contrato dúplex.</span><span class="sxs-lookup"><span data-stu-id="8b42c-107">To demonstrate the behavior, the sample shows how a client and service can send messages between each other using a duplex contract.</span></span>  
  
 <span data-ttu-id="8b42c-108">El contrato definido es un contrato dúplex con el método `Ping` siendo implementado por el servicio y el método de devolución de llamada`Pong`siendo implementado por el cliente.</span><span class="sxs-lookup"><span data-stu-id="8b42c-108">The contract defined is a duplex contract with the `Ping` method being implemented by the service and the callback method `Pong` being implemented by the client.</span></span> <span data-ttu-id="8b42c-109">Un cliente invoca el método del servidor `Ping` con un recuento del paso que inicia así la llamada.</span><span class="sxs-lookup"><span data-stu-id="8b42c-109">A client invokes the server's `Ping` method with a tick count thereby initiating the call.</span></span> <span data-ttu-id="8b42c-110">El servicio comprueba si el recuento del paso no es igual a 0 y a continuación, invoca las devoluciones de llamada el método `Pong` disminuyendo el recuento del paso.</span><span class="sxs-lookup"><span data-stu-id="8b42c-110">The service checks whether the tick count is not equal to 0 and then invokes the callbacks `Pong` method while decrementing the tick count.</span></span> <span data-ttu-id="8b42c-111">El código siguiente realiza esta operación en el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="8b42c-111">This is done by the following code in the sample.</span></span>  
  
```csharp
public void Ping(int ticks)  
{  
     Console.WriteLine("Ping: Ticks = " + ticks);  
     //Keep pinging back and forth till Ticks reaches 0.  
     if (ticks != 0)  
     {  
         OperationContext.Current.GetCallbackChannel<IPingPongCallback>().Pong((ticks - 1));  
     }  
}  
```  
  
 La implementación `Pong` de la devolución de llamada tiene la misma lógica que la implementación `Ping`. Es decir, comprueba si el contador no es cero y, a continuación, invoca el método `Ping` en el canal de devolución de llamada (en este caso, es el canal que fue utilizado para enviar el mensaje `Ping` original) con el contador disminuido en 1. El momento en que el contador llegue a 0, el método vuelve y desempaqueta de nuevo todas las respuestas a la primera llamada realizada por el cliente que inició la llamada. <span data-ttu-id="8b42c-115">Esto se muestra en la implementación de devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="8b42c-115">This is shown in the callback implementation.</span></span>  
  
```csharp
public void Pong(int ticks)  
{  
    Console.WriteLine("Pong: Ticks = " + ticks);  
    if (ticks != 0)  
    {  
        //Retrieve the Callback  Channel (in this case the Channel which was used to send the  
        //original message) and make an outgoing call until ticks reaches 0.  
        IPingPong channel = OperationContext.Current.GetCallbackChannel<IPingPong>();  
        channel.Ping((ticks - 1));  
    }  
}  
```  
  
 `Ping` y los métodos `Pong` son solicitud/respuesta, lo cual significa que la primera llamada a `Ping` no vuelve hasta que la llamada `CallbackChannel<T>.Pong()`se devuelve. En el cliente, el método `Pong` no puede devolverse hasta que la siguiente llamada `Ping` que se realizó se devuelva. <span data-ttu-id="8b42c-118">Dado que la devolución de llamada y el servicio deben realizar llamadas de salida de solicitud/respuesta antes de poder responder a la solicitud pendiente, las implementaciones se deben marcar con el comportamiento de ConcurrencyMode.Reentrant.</span><span class="sxs-lookup"><span data-stu-id="8b42c-118">Because both the callback and the service must make outgoing request/reply calls before they can reply for the pending request, both the implementations must be marked with the ConcurrencyMode.Reentrant behavior.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="8b42c-119">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="8b42c-119">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="8b42c-120">Asegúrese de que ha realizado la [procedimiento de instalación de un solo uso para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="8b42c-120">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="8b42c-121">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="8b42c-121">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="8b42c-122">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecutando los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="8b42c-122">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="8b42c-123">Demostraciones</span><span class="sxs-lookup"><span data-stu-id="8b42c-123">Demonstrates</span></span>  
 <span data-ttu-id="8b42c-124">Para ejecutar el ejemplo, compile los proyectos de servidor y cliente.</span><span class="sxs-lookup"><span data-stu-id="8b42c-124">To run the sample, build the client and server projects.</span></span> <span data-ttu-id="8b42c-125">A continuación, abra dos ventanas de comandos y cambie los directorios a la \<ejemplo > \CS\Service\bin\debug y \<ejemplo > \CS\Client\bin\debug directorios.</span><span class="sxs-lookup"><span data-stu-id="8b42c-125">Then open two command windows and change the directories to the \<sample>\CS\Service\bin\debug and \<sample>\CS\Client\bin\debug directories.</span></span> <span data-ttu-id="8b42c-126">A continuación, inicie el servicio escribiendo `service.exe` y, a continuación, invoque Client.exe con el valor inicial de pasos pasado como argumento de entrada.</span><span class="sxs-lookup"><span data-stu-id="8b42c-126">Then start the service by typing `service.exe` and then invoke the Client.exe with the initial value of ticks passed as an input argument.</span></span> <span data-ttu-id="8b42c-127">Se muestra un resultado del ejemplo para 10 pasos.</span><span class="sxs-lookup"><span data-stu-id="8b42c-127">A sample output for 10 ticks is shown.</span></span>  
  
```console  
Prompt>Service.exe  
ServiceHost Started. Press Enter to terminate service.  
Ping: Ticks = 10  
Ping: Ticks = 8  
Ping: Ticks = 6  
Ping: Ticks = 4  
Ping: Ticks = 2  
Ping: Ticks = 0  
  
Prompt>Client.exe 10  
Pong: Ticks = 9  
Pong: Ticks = 7  
Pong: Ticks = 5  
Pong: Ticks = 3  
Pong: Ticks = 1  
```  
  
> [!IMPORTANT]
>  <span data-ttu-id="8b42c-128">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="8b42c-128">The samples may already be installed on your machine.</span></span> <span data-ttu-id="8b42c-129">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="8b42c-129">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="8b42c-130">Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="8b42c-130">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="8b42c-131">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="8b42c-131">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Reentrant`  
