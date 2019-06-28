---
title: Comportamiento de transacción de servicio
ms.date: 03/30/2017
helpviewer_keywords:
- Service Transaction Behavior Sample [Windows Communication Foundation]
ms.assetid: 1a9842a3-e84d-427c-b6ac-6999cbbc2612
ms.openlocfilehash: fc71d077e219481281be8f8bf22352bd19baebac
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/28/2019
ms.locfileid: "67425479"
---
# <a name="service-transaction-behavior"></a><span data-ttu-id="7d2cf-102">Comportamiento de transacción de servicio</span><span class="sxs-lookup"><span data-stu-id="7d2cf-102">Service Transaction Behavior</span></span>

<span data-ttu-id="7d2cf-103">Este ejemplo muestra el uso de una transacción coordinada por el cliente y la configuración de ServiceBehaviorAttribute y OperationBehaviorAttribute para controlar el comportamiento de las transacciones de servicio.</span><span class="sxs-lookup"><span data-stu-id="7d2cf-103">This sample demonstrates the use of a client-coordinated transaction and the settings of ServiceBehaviorAttribute and OperationBehaviorAttribute to control service transaction behavior.</span></span> <span data-ttu-id="7d2cf-104">En este ejemplo se basa en el [Introducción](../../../../docs/framework/wcf/samples/getting-started-sample.md) que implementa un servicio de calculadora, pero se extiende para mantener un registro del servidor de las operaciones realizadas en una tabla de base de datos y una con estado ejecutando total para las operaciones de cálculo.</span><span class="sxs-lookup"><span data-stu-id="7d2cf-104">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) that implements a calculator service, but is extended to maintain a server log of the performed operations in a database table and a stateful running total for the calculator operations.</span></span> <span data-ttu-id="7d2cf-105">Las escrituras guardadas en la tabla de registro del servidor dependen del resultado de una transacción coordinada del cliente. Si la transacción del cliente no se completa, la transacción del servicio Web garantiza que las actualizaciones de la base de datos no se confirman.</span><span class="sxs-lookup"><span data-stu-id="7d2cf-105">Persisted writes to the server log table are dependent upon the outcome of a client coordinated transaction - if the client transaction does not complete, the Web service transaction ensures that the updates to the database are not committed.</span></span>

> [!NOTE]
> <span data-ttu-id="7d2cf-106">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="7d2cf-106">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

<span data-ttu-id="7d2cf-107">El contrato para el servicio define que todas las operaciones exigen que una transacción fluya con solicitudes:</span><span class="sxs-lookup"><span data-stu-id="7d2cf-107">The contract for the service defines that all of the operations require a transaction to be flowed with requests:</span></span>

```csharp
[ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples",
                    SessionMode = SessionMode.Required)]
public interface ICalculator
{
    [OperationContract]
    [TransactionFlow(TransactionFlowOption.Mandatory)]
    double Add(double n);
    [OperationContract]
    [TransactionFlow(TransactionFlowOption.Mandatory)]
    double Subtract(double n);
    [OperationContract]
    [TransactionFlow(TransactionFlowOption.Mandatory)]
    double Multiply(double n);
    [OperationContract]
    [TransactionFlow(TransactionFlowOption.Mandatory)]
    double Divide(double n);
}
```

<span data-ttu-id="7d2cf-108">Para habilitar el flujo de la transacción entrante, el servicio se configura con el wsHttpBinding proporcionado por el sistema con el atributo transactionFlow establecido en `true`.</span><span class="sxs-lookup"><span data-stu-id="7d2cf-108">To enable the incoming transaction flow, the service is configured with the system-provided wsHttpBinding with the transactionFlow attribute set to `true`.</span></span> <span data-ttu-id="7d2cf-109">Este enlace utiliza el protocolo WSAtomicTransactionOctober2004 interoperable:</span><span class="sxs-lookup"><span data-stu-id="7d2cf-109">This binding uses the interoperable WSAtomicTransactionOctober2004 protocol:</span></span>

```xml
<bindings>
  <wsHttpBinding>
    <binding name="transactionalBinding" transactionFlow="true" />
  </wsHttpBinding>
</bindings>
```

<span data-ttu-id="7d2cf-110">Después de iniciar tanto una conexión con el servicio como una transacción, el cliente tiene acceso a varias operaciones de servicio dentro del ámbito de esa transacción y, a continuación, completa la transacción y cierra la conexión:</span><span class="sxs-lookup"><span data-stu-id="7d2cf-110">After initiating both a connection to the service and a transaction, the client accesses several service operations within the scope of that transaction and then completes the transaction and closes the connection:</span></span>

```csharp
// Create a client
CalculatorClient client = new CalculatorClient();

// Create a transaction scope with the default isolation level of Serializable
using (TransactionScope tx = new TransactionScope())
{
    Console.WriteLine("Starting transaction");

    // Call the Add service operation.
    double value = 100.00D;
    Console.WriteLine("  Adding {0}, running total={1}",
                                        value, client.Add(value));

    // Call the Subtract service operation.
    value = 45.00D;
    Console.WriteLine("  Subtracting {0}, running total={1}",
                                        value, client.Subtract(value));

    // Call the Multiply service operation.
    value = 9.00D;
    Console.WriteLine("  Multiplying by {0}, running total={1}",
                                        value, client.Multiply(value));

    // Call the Divide service operation.
    value = 15.00D;
    Console.WriteLine("  Dividing by {0}, running total={1}",
                                        value, client.Divide(value));

    Console.WriteLine("  Completing transaction");
    tx.Complete();
}

Console.WriteLine("Transaction committed");

// Closing the client gracefully closes the connection and cleans up resources
client.Close();
```

<span data-ttu-id="7d2cf-111">En el servicio, hay tres atributos que afectan al comportamiento de las transacciones de servicio y lo hacen de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="7d2cf-111">On the service, there are three attributes that affect the service transaction behavior, and they do so in the following ways:</span></span>

- <span data-ttu-id="7d2cf-112">En `ServiceBehaviorAttribute`:</span><span class="sxs-lookup"><span data-stu-id="7d2cf-112">On the `ServiceBehaviorAttribute`:</span></span>

  - <span data-ttu-id="7d2cf-113">La propiedad `TransactionTimeout` especifica el período dentro del cual debe completarse una transacción.</span><span class="sxs-lookup"><span data-stu-id="7d2cf-113">The `TransactionTimeout` property specifies the time period within which a transaction must complete.</span></span> <span data-ttu-id="7d2cf-114">En este ejemplo, está establecido en 30 segundos.</span><span class="sxs-lookup"><span data-stu-id="7d2cf-114">In this sample it is set to 30 seconds.</span></span>

  - <span data-ttu-id="7d2cf-115">La propiedad `TransactionIsolationLevel` especifica el nivel de aislamiento que el servicio admite.</span><span class="sxs-lookup"><span data-stu-id="7d2cf-115">The `TransactionIsolationLevel` property specifies the isolation level that the service supports.</span></span> <span data-ttu-id="7d2cf-116">Esto es necesario para coincidir con el nivel de aislamiento del cliente.</span><span class="sxs-lookup"><span data-stu-id="7d2cf-116">This is required to match the client's isolation level.</span></span>

  - <span data-ttu-id="7d2cf-117">La propiedad `ReleaseServiceInstanceOnTransactionComplete` especifica si se recicla la instancia del servicio cuando se completa una transacción.</span><span class="sxs-lookup"><span data-stu-id="7d2cf-117">The `ReleaseServiceInstanceOnTransactionComplete` property specifies whether the service instance is recycled when a transaction completes.</span></span> <span data-ttu-id="7d2cf-118">Si se establece en `false`, el servicio mantiene la misma instancia del servicio en las solicitudes de operación.</span><span class="sxs-lookup"><span data-stu-id="7d2cf-118">By setting it to `false`, the service maintains the same service instance across the operation requests.</span></span> <span data-ttu-id="7d2cf-119">Esto es necesario para mantener el total en ejecución.</span><span class="sxs-lookup"><span data-stu-id="7d2cf-119">This is required to maintain the running total.</span></span> <span data-ttu-id="7d2cf-120">Si se establece en `true`, se genera una instancia nueva después de cada acción completada.</span><span class="sxs-lookup"><span data-stu-id="7d2cf-120">If set to `true`, a new instance is generated after each completed action.</span></span>

  - <span data-ttu-id="7d2cf-121">La propiedad `TransactionAutoCompleteOnSessionClose` especifica si se completan las transacciones pendientes cuando la sesión se cierra.</span><span class="sxs-lookup"><span data-stu-id="7d2cf-121">The `TransactionAutoCompleteOnSessionClose` property specifies whether outstanding transactions are completed when the session closes.</span></span> <span data-ttu-id="7d2cf-122">Si se establece en `false`, las operaciones individuales son necesarias para establecer el <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete?displayProperty=nameWithType> propiedad `true` o exigir explícitamente una llamada a la <xref:System.ServiceModel.OperationContext.SetTransactionComplete?displayProperty=nameWithType> método para realizar transacciones.</span><span class="sxs-lookup"><span data-stu-id="7d2cf-122">By setting it to `false`, the individual operations are required to either set the <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete?displayProperty=nameWithType> property to `true` or to explicitly require a call to the <xref:System.ServiceModel.OperationContext.SetTransactionComplete?displayProperty=nameWithType> method to complete transactions.</span></span> <span data-ttu-id="7d2cf-123">Este ejemplo muestra ambos enfoques.</span><span class="sxs-lookup"><span data-stu-id="7d2cf-123">This sample demonstrates both approaches.</span></span>

- <span data-ttu-id="7d2cf-124">En `ServiceContractAttribute`:</span><span class="sxs-lookup"><span data-stu-id="7d2cf-124">On the `ServiceContractAttribute`:</span></span>

  - <span data-ttu-id="7d2cf-125">La propiedad `SessionMode` especifica si el servicio pone en correlación las solicitudes adecuadas en una sesión lógica.</span><span class="sxs-lookup"><span data-stu-id="7d2cf-125">The `SessionMode` property specifies whether the service correlates the appropriate requests into a logical session.</span></span> <span data-ttu-id="7d2cf-126">Dado que este servicio incluye las operaciones en las que la propiedad OperationBehaviorAttribute TransactionAutoComplete está establecida en `false` (multiplicar y dividir), debe especificarse `SessionMode.Required`.</span><span class="sxs-lookup"><span data-stu-id="7d2cf-126">Because this service includes operations where the OperationBehaviorAttribute TransactionAutoComplete property is set to `false` (Multiply and Divide), `SessionMode.Required` must be specified.</span></span> <span data-ttu-id="7d2cf-127">Por ejemplo, la operación de multiplicación no completa su transacción sino que confía en una llamada posterior para que se complete la operación de división usando el método `SetTransactionComplete`; el servicio debe poder determinar que estas operaciones se están produciendo dentro de la misma sesión.</span><span class="sxs-lookup"><span data-stu-id="7d2cf-127">For example, the Multiply operation does not complete its transaction and instead relies upon a later call to Divide to complete using the `SetTransactionComplete` method; the service must be able to determine that these operations are occurring within the same session.</span></span>

- <span data-ttu-id="7d2cf-128">En `OperationBehaviorAttribute`:</span><span class="sxs-lookup"><span data-stu-id="7d2cf-128">On the `OperationBehaviorAttribute`:</span></span>

  - <span data-ttu-id="7d2cf-129">La propiedad `TransactionScopeRequired` especifica si las acciones de la operación se deberían ejecutar dentro del ámbito de una transacción.</span><span class="sxs-lookup"><span data-stu-id="7d2cf-129">The `TransactionScopeRequired` property specifies whether the operation's actions should be executed within a transaction scope.</span></span> <span data-ttu-id="7d2cf-130">Se establece en `true` para todas las operaciones de este ejemplo y, dado que el cliente fluye su transacción a todas las operaciones, las acciones se producen dentro del ámbito de la transacción de ese cliente.</span><span class="sxs-lookup"><span data-stu-id="7d2cf-130">This is set to `true` for all operations in this sample and, because the client flows its transaction to all operations, the actions occur within the scope of that client transaction.</span></span>

  - <span data-ttu-id="7d2cf-131">La propiedad `TransactionAutoComplete` especifica si se completa automáticamente la transacción en la que se ejecuta el método si no se producen excepciones no controladas.</span><span class="sxs-lookup"><span data-stu-id="7d2cf-131">The `TransactionAutoComplete` property specifies whether the transaction in which the method executes is automatically completed if no unhandled exceptions occur.</span></span> <span data-ttu-id="7d2cf-132">Tal y como se ha descrito previamente, se establece en `true` para las operaciones de suma y resta, y en `false` para las de multiplicación y división.</span><span class="sxs-lookup"><span data-stu-id="7d2cf-132">As previously described, this is set to `true` for the Add and Subtract operations but `false` for the Multiply and Divide operations.</span></span> <span data-ttu-id="7d2cf-133">Las operaciones de suma y resta completan sus acciones automáticamente, la de división completa sus acciones mediante una llamada explícita al método `SetTransactionComplete` y la de multiplicación no completa sus acciones, sino que en realidad confía y necesita una llamada posterior, por ejemplo a la operación de dividir, para completar las acciones.</span><span class="sxs-lookup"><span data-stu-id="7d2cf-133">The Add and Subtract operations complete their actions automatically, the Divide completes its actions through an explicit call to the `SetTransactionComplete` method, and the Multiply does not complete its actions but instead relies upon and requires a later call, such as to Divide, to complete the actions.</span></span>

<span data-ttu-id="7d2cf-134">La implementación del servicio con atributos es como sigue:</span><span class="sxs-lookup"><span data-stu-id="7d2cf-134">The attributed service implementation is as follows:</span></span>

```csharp
[ServiceBehavior(
    TransactionIsolationLevel = System.Transactions.IsolationLevel.Serializable,
    TransactionTimeout = "00:00:30",
    ReleaseServiceInstanceOnTransactionComplete = false,
    TransactionAutoCompleteOnSessionClose = false)]
public class CalculatorService : ICalculator
{
    double runningTotal;

    public CalculatorService()
    {
        Console.WriteLine("Creating new service instance...");
    }

    [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]
    public double Add(double n)
    {
        RecordToLog(String.Format(CultureInfo.CurrentCulture, "Adding {0} to {1}", n, runningTotal));
        runningTotal = runningTotal + n;
        return runningTotal;
    }

    [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]
    public double Subtract(double n)
    {
        RecordToLog(String.Format(CultureInfo.CurrentCulture, "Subtracting {0} from {1}", n, runningTotal));
        runningTotal = runningTotal - n;
        return runningTotal;
    }

    [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = false)]
    public double Multiply(double n)
    {
        RecordToLog(String.Format(CultureInfo.CurrentCulture, "Multiplying {0} by {1}", runningTotal, n));
        runningTotal = runningTotal * n;
        return runningTotal;
    }

    [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = false)]
    public double Divide(double n)
    {
        RecordToLog(String.Format(CultureInfo.CurrentCulture, "Dividing {0} by {1}", runningTotal, n));
        runningTotal = runningTotal / n;
        OperationContext.Current.SetTransactionComplete();
        return runningTotal;
    }

    // Logging method omitted for brevity
}
```

<span data-ttu-id="7d2cf-135">Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente.</span><span class="sxs-lookup"><span data-stu-id="7d2cf-135">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="7d2cf-136">Presione ENTRAR en la ventana de cliente para cerrar el cliente.</span><span class="sxs-lookup"><span data-stu-id="7d2cf-136">Press ENTER in the client window to shut down the client.</span></span>

```console
Starting transaction
Performing calculations...
  Adding 100, running total=100
  Subtracting 45, running total=55
  Multiplying by 9, running total=495
  Dividing by 15, running total=33
  Completing transaction
Transaction committed
Press <ENTER> to terminate client.
```

<span data-ttu-id="7d2cf-137">El registro de las solicitudes de operación de servicio se muestra en la ventana de la consola del servicio.</span><span class="sxs-lookup"><span data-stu-id="7d2cf-137">The logging of the service operation requests are displayed in the service's console window.</span></span> <span data-ttu-id="7d2cf-138">Presione ENTRAR en la ventana de cliente para cerrar el cliente.</span><span class="sxs-lookup"><span data-stu-id="7d2cf-138">Press ENTER in the client window to shut down the client.</span></span>

```console
Press <ENTER> to terminate service.
Creating new service instance...
  Writing row 1 to database: Adding 100 to 0
  Writing row 2 to database: Subtracting 45 from 100
  Writing row 3 to database: Multiplying 55 by 9
  Writing row 4 to database: Dividing 495 by 15
```

<span data-ttu-id="7d2cf-139">Tenga en cuenta que además de mantener el total en ejecución de los cálculos, el servicio informa sobre la creación de instancias (una instancia en este ejemplo) y registra las solicitudes de operación en una base de datos.</span><span class="sxs-lookup"><span data-stu-id="7d2cf-139">Note that in addition to keeping the running total of the calculations, the service reports the creation of instances (one instance for this sample) and logs the operation requests to a database.</span></span> <span data-ttu-id="7d2cf-140">Como todas las solicitudes fluyen en la transacción del cliente, cualquier error para completar esa transacción da como resultado que se reviertan todas las operaciones de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="7d2cf-140">Because all of the requests flow the client's transaction, any failure to complete that transaction results in all of the database operations being rolled back.</span></span> <span data-ttu-id="7d2cf-141">Esto se puede demostrar de varias maneras:</span><span class="sxs-lookup"><span data-stu-id="7d2cf-141">This can be demonstrated in a number of ways:</span></span>

- <span data-ttu-id="7d2cf-142">Marcar como comentario la llamada del cliente en `tx.Complete`() y volver a ejecutar. Esto ocasiona que el cliente salga del ámbito de la transacción sin completar su transacción.</span><span class="sxs-lookup"><span data-stu-id="7d2cf-142">Comment out the client's call to `tx.Complete`() and rerun - this results in the client exiting the transaction scope without completing its transaction.</span></span>

- <span data-ttu-id="7d2cf-143">Marcar como comentario la llamada a la operación de servicio de dividir. Así se impide que la acción iniciada por la operación de multiplicación se complete y, por tanto, la transacción del cliente tampoco podrá completarse.</span><span class="sxs-lookup"><span data-stu-id="7d2cf-143">Comment out the call to the Divide service operation - this results prevent the action initiated by the Multiply operation from completing and thus the client's transaction ultimately also fails to complete.</span></span>

- <span data-ttu-id="7d2cf-144">Iniciar una excepción no controlada en cualquier parte del ámbito de la transacción del cliente. Del mismo modo, esto impide que el cliente complete su transacción.</span><span class="sxs-lookup"><span data-stu-id="7d2cf-144">Throw an unhandled exception anywhere in the client's transaction scope - this similarly prevents the client from completing its transaction.</span></span>

<span data-ttu-id="7d2cf-145">El resultado en cualquiera de estos casos es que no se confirma ninguna de las operaciones realizadas dentro del ámbito y no se incrementa el recuento de filas conservadas en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="7d2cf-145">The result of any of these is that none of the operations performed within that scope are committed and the count of rows persisted to the database do not increment.</span></span>

> [!NOTE]
> <span data-ttu-id="7d2cf-146">Como parte del proceso de compilación, el archivo de base de datos se copia en la carpeta de la bandeja.</span><span class="sxs-lookup"><span data-stu-id="7d2cf-146">As part of the build process the database file is copied to the bin folder.</span></span> <span data-ttu-id="7d2cf-147">Debe examinar esa copia del archivo de base de datos para observar las filas que se conservan en el registro en lugar del archivo que está incluido en el proyecto de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="7d2cf-147">You must look at that copy of the database file to observe the rows that are persisted to the log rather than the file that is included in the Visual Studio project.</span></span>

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="7d2cf-148">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="7d2cf-148">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="7d2cf-149">Asegúrese de que ha instalado SQL Server 2005 Express Edition o SQL Server 2005.</span><span class="sxs-lookup"><span data-stu-id="7d2cf-149">Ensure that you have installed SQL Server 2005 Express Edition or SQL Server 2005.</span></span> <span data-ttu-id="7d2cf-150">En el archivo App.config del servicio, puede establecerse la base de datos`connectionString` o las interacciones de la base de datos pueden deshabilitarse estableciendo el valor `usingSql` de appSettings en `false`.</span><span class="sxs-lookup"><span data-stu-id="7d2cf-150">In the service's App.config file, the database `connectionString` may be set or the database interactions may be disabled by setting the appSettings `usingSql` value to `false`.</span></span>

2. <span data-ttu-id="7d2cf-151">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="7d2cf-151">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>

3. <span data-ttu-id="7d2cf-152">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecutando los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="7d2cf-152">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>

<span data-ttu-id="7d2cf-153">Si ejecuta el ejemplo entre máquinas, debe configurar el Microsoft distribuidas (Coordinador de transacciones) para habilitar el flujo de transacciones de red y usar la herramienta WsatConfig.exe para habilitar las transacciones de red de Windows Communication Foundation (WCF) soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="7d2cf-153">If you run the sample across machines, you must configure the Microsoft Distributed Transaction Coordinator (MSDTC) to enable network transaction flow and use the WsatConfig.exe tool to enable Windows Communication Foundation (WCF) transactions network support.</span></span>

### <a name="to-configure-the-microsoft-distributed-transaction-coordinator-msdtc-to-support-running-the-sample-across-machines"></a><span data-ttu-id="7d2cf-154">Para configurar MSDTC de forma que admita la ejecución del ejemplo en varios equipos</span><span class="sxs-lookup"><span data-stu-id="7d2cf-154">To configure the Microsoft Distributed Transaction Coordinator (MSDTC) to support running the sample across machines</span></span>

1. <span data-ttu-id="7d2cf-155">En el equipo de servicio, configure MSDTC para permitir las transacciones de red entrantes.</span><span class="sxs-lookup"><span data-stu-id="7d2cf-155">On the service machine, configure MSDTC to allow incoming network transactions.</span></span>

    1. <span data-ttu-id="7d2cf-156">Desde el **iniciar** menú, vaya a **Panel de Control**, a continuación, **herramientas administrativas**y, a continuación, **servicios de componentes**.</span><span class="sxs-lookup"><span data-stu-id="7d2cf-156">From the **Start** menu, navigate to **Control Panel**, then **Administrative Tools**, and then **Component Services**.</span></span>

    2. <span data-ttu-id="7d2cf-157">Haga clic en **Mi PC** y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="7d2cf-157">Right-click **My Computer** and select **Properties**.</span></span>

    3. <span data-ttu-id="7d2cf-158">En el **MSDTC** , haga clic **configuración de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="7d2cf-158">On the **MSDTC** tab, click **Security Configuration**.</span></span>

    4. <span data-ttu-id="7d2cf-159">Comprobar **acceso DTC de red** y **Permitir entrantes**.</span><span class="sxs-lookup"><span data-stu-id="7d2cf-159">Check **Network DTC Access** and **Allow Inbound**.</span></span>

    5. <span data-ttu-id="7d2cf-160">Haga clic en **Sí** para reiniciar el servicio MS DTC y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7d2cf-160">Click **Yes** to restart the MS DTC service and then click **OK**.</span></span>

    6. <span data-ttu-id="7d2cf-161">Haga clic en **Aceptar** para cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="7d2cf-161">Click **OK** to close the dialog box.</span></span>

2. <span data-ttu-id="7d2cf-162">En el equipo de servicio y el equipo cliente, configure el Firewall de Windows para incluir Microsoft DTC (MSDTC, Coordinador de transacciones distribuidas) en la lista de aplicaciones exceptuadas:</span><span class="sxs-lookup"><span data-stu-id="7d2cf-162">On the service machine and the client machine, configure the Windows Firewall to include the Microsoft Distributed Transaction Coordinator (MSDTC) to the list of excepted applications:</span></span>

    1. <span data-ttu-id="7d2cf-163">Ejecute la aplicación Firewall de Windows desde el Panel de control.</span><span class="sxs-lookup"><span data-stu-id="7d2cf-163">Run the Windows Firewall application from Control Panel.</span></span>

    2. <span data-ttu-id="7d2cf-164">Desde el **excepciones** , haga clic **Agregar programa**.</span><span class="sxs-lookup"><span data-stu-id="7d2cf-164">From the **Exceptions** tab, click **Add Program**.</span></span>

    3. <span data-ttu-id="7d2cf-165">Desplácese a la carpeta C:\WINDOWS\System32.</span><span class="sxs-lookup"><span data-stu-id="7d2cf-165">Browse to the folder C:\WINDOWS\System32.</span></span>

    4. <span data-ttu-id="7d2cf-166">Seleccione Msdtc.exe y haga clic en **abierto**.</span><span class="sxs-lookup"><span data-stu-id="7d2cf-166">Select Msdtc.exe and click **Open**.</span></span>

    5. <span data-ttu-id="7d2cf-167">Haga clic en **Aceptar** para cerrar el **Agregar programa** cuadro de diálogo y haga clic en **Aceptar** otra vez para cerrar el applet del Firewall de Windows.</span><span class="sxs-lookup"><span data-stu-id="7d2cf-167">Click **OK** to close the **Add Program** dialog box, and click **OK** again to close the Windows Firewall applet.</span></span>

3. <span data-ttu-id="7d2cf-168">En el equipo cliente, configure MSDTC para permitir las transacciones de red salientes:</span><span class="sxs-lookup"><span data-stu-id="7d2cf-168">On the client machine, configure MSDTC to allow outgoing network transactions:</span></span>

    1. <span data-ttu-id="7d2cf-169">Desde el **iniciar** menú, vaya a **Panel de Control**, a continuación, **herramientas administrativas**y, a continuación, **servicios de componentes**.</span><span class="sxs-lookup"><span data-stu-id="7d2cf-169">From the **Start** menu, navigate to **Control Panel**, then **Administrative Tools**, and then **Component Services**.</span></span>

    2. <span data-ttu-id="7d2cf-170">Haga clic en **Mi PC** y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="7d2cf-170">Right-click **My Computer** and select **Properties**.</span></span>

    3. <span data-ttu-id="7d2cf-171">En el **MSDTC** , haga clic **configuración de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="7d2cf-171">On the **MSDTC** tab, click **Security Configuration**.</span></span>

    4. <span data-ttu-id="7d2cf-172">Comprobar **acceso DTC de red** y **Permitir salientes**.</span><span class="sxs-lookup"><span data-stu-id="7d2cf-172">Check **Network DTC Access** and **Allow Outbound**.</span></span>

    5. <span data-ttu-id="7d2cf-173">Haga clic en **Sí** para reiniciar el servicio MS DTC y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7d2cf-173">Click **Yes** to restart the MS DTC service and then click **OK**.</span></span>

    6. <span data-ttu-id="7d2cf-174">Haga clic en **Aceptar** para cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="7d2cf-174">Click **OK** to close the dialog box.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7d2cf-175">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="7d2cf-175">The samples may already be installed on your machine.</span></span> <span data-ttu-id="7d2cf-176">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="7d2cf-176">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="7d2cf-177">Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="7d2cf-177">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="7d2cf-178">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="7d2cf-178">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Behaviors\Transactions`
