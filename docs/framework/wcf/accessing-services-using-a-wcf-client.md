---
title: Acceso a los servicios mediante un cliente WCF
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- clients [WCF], consuming services
ms.assetid: d780af9f-73c5-42db-9e52-077a5e4de7fe
ms.openlocfilehash: 462d9a3923009f0124c2b90b6fa86dfa9869a3c5
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2019
ms.locfileid: "72316531"
---
# <a name="accessing-services-using-a-wcf-client"></a><span data-ttu-id="39440-102">Acceso a los servicios mediante un cliente WCF</span><span class="sxs-lookup"><span data-stu-id="39440-102">Accessing Services Using a WCF Client</span></span>

<span data-ttu-id="39440-103">Después de crear un servicio, el siguiente paso es crear un proxy de cliente de WCF.</span><span class="sxs-lookup"><span data-stu-id="39440-103">After you create a service, the next step is to create a WCF client proxy.</span></span> <span data-ttu-id="39440-104">Una aplicación cliente utiliza el proxy de cliente de WCF para comunicarse con el servicio.</span><span class="sxs-lookup"><span data-stu-id="39440-104">A client application uses the WCF client proxy to communicate with the service.</span></span> <span data-ttu-id="39440-105">Las aplicaciones cliente suelen importar los metadatos de un servicio para generar el código de cliente de WCF que se puede usar para invocar el servicio.</span><span class="sxs-lookup"><span data-stu-id="39440-105">Client applications usually import a service's metadata to generate WCF client code that can be used to invoke the service.</span></span>

 <span data-ttu-id="39440-106">Los pasos básicos para crear un cliente WCF son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="39440-106">The basic steps for creating a WCF client include the following:</span></span>

1. <span data-ttu-id="39440-107">Compilar el código del servicio.</span><span class="sxs-lookup"><span data-stu-id="39440-107">Compile the service code.</span></span>

2. <span data-ttu-id="39440-108">Genere el proxy de cliente de WCF.</span><span class="sxs-lookup"><span data-stu-id="39440-108">Generate the WCF client proxy.</span></span>

3. <span data-ttu-id="39440-109">Cree una instancia del proxy de cliente de WCF.</span><span class="sxs-lookup"><span data-stu-id="39440-109">Instantiate the WCF client proxy.</span></span>

<span data-ttu-id="39440-110">El proxy de cliente de WCF se puede generar manualmente mediante la herramienta de utilidad de metadatos del modelo de servicio (SvcUtil. exe) para obtener más información, vea la [herramienta de utilidad de metadatos de ServiceModel (SvcUtil. exe)](servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="39440-110">The WCF client proxy can be generated manually by using the Service Model Metadata Utility Tool (SvcUtil.exe) for more information see, [ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span> <span data-ttu-id="39440-111">También se puede generar el proxy de cliente de WCF en Visual Studio mediante la característica **Agregar referencia de servicio** .</span><span class="sxs-lookup"><span data-stu-id="39440-111">The WCF client proxy can also be generated within Visual Studio using the **Add Service Reference**  feature.</span></span> <span data-ttu-id="39440-112">Para generar el proxy de cliente de WCF usando cualquier método, el servicio debe estar en ejecución.</span><span class="sxs-lookup"><span data-stu-id="39440-112">To generate the WCF client proxy using either method the service must be running.</span></span> <span data-ttu-id="39440-113">Si el servicio se autohospeda, debe ejecutar el host.</span><span class="sxs-lookup"><span data-stu-id="39440-113">If the service is self-hosted you must run the host.</span></span> <span data-ttu-id="39440-114">Si el servicio se hospeda en IIS/WAS no necesita hacer nada más.</span><span class="sxs-lookup"><span data-stu-id="39440-114">If the service is hosted in IIS/WAS you do not need to do anything else.</span></span>

## <a name="servicemodel-metadata-utility-tool"></a><span data-ttu-id="39440-115">Herramienta de utilidad de metadatos ServiceModel</span><span class="sxs-lookup"><span data-stu-id="39440-115">ServiceModel Metadata Utility Tool</span></span>
 <span data-ttu-id="39440-116">La [herramienta de utilidad de metadatos de ServiceModel (SvcUtil. exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) es una herramienta de línea de comandos para generar código a partir de metadatos.</span><span class="sxs-lookup"><span data-stu-id="39440-116">The [ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) is a command-line tool for generating code from metadata.</span></span> <span data-ttu-id="39440-117">A continuación se muestra un ejemplo del uso de un comando básico Svcutil.exe.</span><span class="sxs-lookup"><span data-stu-id="39440-117">The following use is an example of a basic Svcutil.exe command.</span></span>

```console
Svcutil.exe <service's Metadata Exchange (MEX) address or HTTP GET address>
```

 <span data-ttu-id="39440-118">Como alternativa, puede usar Svcutil.exe con archivos de Lenguaje de descripción de servicios Web (WSDL) y de lenguaje de definición de esquemas XML (XSD) en el sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="39440-118">Alternatively, you can use Svcutil.exe with Web Services Description Language (WSDL) and XML Schema definition language (XSD) files on the file system.</span></span>

```console
Svcutil.exe <list of WSDL and XSD files on file system>
```

 <span data-ttu-id="39440-119">El resultado es un archivo de código que contiene el código de cliente de WCF que la aplicación cliente puede usar para invocar el servicio.</span><span class="sxs-lookup"><span data-stu-id="39440-119">The result is a code file that contains WCF client code that the client application can use to invoke the service.</span></span>

 <span data-ttu-id="39440-120">También puede usar la herramienta para generar archivos de configuración.</span><span class="sxs-lookup"><span data-stu-id="39440-120">You can also use the tool to generate configuration files.</span></span>

```console
Svcutil.exe <file1 [,file2]>
```

 <span data-ttu-id="39440-121">Si se proporciona solo uno nombre de archivo, ése será el nombre del archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="39440-121">If only one file name is given, that is the name of the output file.</span></span> <span data-ttu-id="39440-122">Si se proporcionan dos nombres de archivo, entonces el primer archivo es un archivo de configuración de entrada cuyo contenido está combinado con la configuración generada y que se escribe en el segundo archivo.</span><span class="sxs-lookup"><span data-stu-id="39440-122">If two file names are given, then the first file is an input configuration file whose contents are merged with the generated configuration and written out into the second file.</span></span> <span data-ttu-id="39440-123">Para obtener más información acerca de la configuración, consulte [configuración de enlaces para servicios](configuring-bindings-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="39440-123">For more information about configuration, see [Configuring Bindings for Services](configuring-bindings-for-wcf-services.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="39440-124">Las solicitudes de metadatos que no son seguras plantean ciertos riesgos, al igual que cualquier solicitud de una red no segura: si no está seguro de que el punto de conexión con el que se está comunicando es el que dice ser, es posible que la información que recupere sean metadatos de un servicio malintencionado.</span><span class="sxs-lookup"><span data-stu-id="39440-124">Unsecured metadata requests pose certain risks in the same way that any unsecured network request does: If you are not certain that the endpoint you are communicating with is who it says it is, the information you retrieve might be metadata from a malicious service.</span></span>

## <a name="add-service-reference-in-visual-studio"></a><span data-ttu-id="39440-125">Agregar referencia de servicio en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="39440-125">Add Service Reference in Visual Studio</span></span>

 <span data-ttu-id="39440-126">Con el servicio en ejecución, haga clic con el botón secundario en el proyecto que contendrá el proxy de cliente de WCF y seleccione **Agregar\*\*\*\*referencia de servicio**de  > .</span><span class="sxs-lookup"><span data-stu-id="39440-126">With the service running, right click the project that will contain the WCF client proxy and select **Add** > **Service Reference**.</span></span> <span data-ttu-id="39440-127">En el **cuadro de diálogo Agregar referencia de servicio**, escriba la dirección URL del servicio al que desea llamar y haga clic en el botón **ir** .</span><span class="sxs-lookup"><span data-stu-id="39440-127">In the **Add Service Reference Dialog**, type in the URL to the service you want to call and click the **Go** button.</span></span> <span data-ttu-id="39440-128">El cuadro de diálogo mostrará una lista de servicios disponibles en la dirección especificada.</span><span class="sxs-lookup"><span data-stu-id="39440-128">The dialog will display a list of services available at the address you specify.</span></span> <span data-ttu-id="39440-129">Haga doble clic en el servicio para ver los contratos y las operaciones disponibles, especifique un espacio de nombres para el código generado y haga clic en el botón **Aceptar** .</span><span class="sxs-lookup"><span data-stu-id="39440-129">Double click the service to see the contracts and operations available, specify a namespace for the generated code, and click the **OK** button.</span></span>

## <a name="example"></a><span data-ttu-id="39440-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="39440-130">Example</span></span>
 <span data-ttu-id="39440-131">El ejemplo de código siguiente muestra un contrato de servicio creado para un servicio.</span><span class="sxs-lookup"><span data-stu-id="39440-131">The following code example shows a service contract created for a service.</span></span>

```csharp
// Define a service contract.
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]
public interface ICalculator
{
    [OperationContract]
    double Add(double n1, double n2);
    // Other methods are not shown here.
}
```

```vb
' Define a service contract.
<ServiceContract(Namespace:="http://Microsoft.ServiceModel.Samples")> _
Public Interface ICalculator
    <OperationContract()>  _
    Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double
    ' Other methods are not shown here.
End Interface
```

 <span data-ttu-id="39440-132">La herramienta de utilidad de metadatos de ServiceModel y **Agregar referencia de servicio** en Visual Studio generan la siguiente clase de cliente WCF.</span><span class="sxs-lookup"><span data-stu-id="39440-132">The ServiceModel Metadata utility tool and **Add Service Reference** in Visual Studio generates the following WCF client class.</span></span> <span data-ttu-id="39440-133">La clase adquiere de la clase <xref:System.ServiceModel.ClientBase%601> genérica e implementa la interfaz `ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="39440-133">The class inherits from the generic <xref:System.ServiceModel.ClientBase%601> class and implements the `ICalculator` interface.</span></span> <span data-ttu-id="39440-134">La herramienta también genera la interfaz (no se muestra aquí) `ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="39440-134">The tool also generates the `ICalculator` interface (not shown here).</span></span>

```csharp
public partial class CalculatorClient : System.ServiceModel.ClientBase<ICalculator>, ICalculator
{
    public CalculatorClient()
    {}

    public CalculatorClient(string endpointConfigurationName) :
            base(endpointConfigurationName)
    {}

    public CalculatorClient(string endpointConfigurationName, string remoteAddress) :
            base(endpointConfigurationName, remoteAddress)
    {}

    public CalculatorClient(string endpointConfigurationName,
        System.ServiceModel.EndpointAddress remoteAddress) :
            base(endpointConfigurationName, remoteAddress)
    {}

    public CalculatorClient(System.ServiceModel.Channels.Binding binding,
        System.ServiceModel.EndpointAddress remoteAddress) :
            base(binding, remoteAddress)
    {}

    public double Add(double n1, double n2)
    {
        return base.Channel.Add(n1, n2);
    }
}
```

```vb
Partial Public Class CalculatorClient
    Inherits System.ServiceModel.ClientBase(Of ICalculator)
    Implements ICalculator

    Public Sub New()
        MyBase.New
    End Sub

    Public Sub New(ByVal endpointConfigurationName As String)
        MyBase.New(endpointConfigurationName)
    End Sub

    Public Sub New(ByVal endpointConfigurationName As String, ByVal remoteAddress As String)
        MyBase.New(endpointConfigurationName, remoteAddress)
    End Sub

    Public Sub New(ByVal endpointConfigurationName As String,
        ByVal remoteAddress As System.ServiceModel.EndpointAddress)
        MyBase.New(endpointConfigurationName, remoteAddress)
    End Sub

    Public Sub New(ByVal binding As System.ServiceModel.Channels.Binding,
        ByVal remoteAddress As System.ServiceModel.EndpointAddress)
        MyBase.New(binding, remoteAddress)
    End Sub

    Public Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double
        Implements ICalculator.Add
        Return MyBase.Channel.Add(n1, n2)
    End Function
End Class
```

## <a name="using-the-wcf-client"></a><span data-ttu-id="39440-135">Uso del cliente WCF</span><span class="sxs-lookup"><span data-stu-id="39440-135">Using the WCF Client</span></span>
 <span data-ttu-id="39440-136">Para usar el cliente de WCF, cree una instancia del cliente de WCF y, a continuación, llame a sus métodos, tal y como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="39440-136">To use the WCF client, create an instance of the WCF client, and then call its methods, as shown in the following code.</span></span>

```csharp
// Create a client object with the given client endpoint configuration.
CalculatorClient calcClient = new CalculatorClient("CalculatorEndpoint"));
// Call the Add service operation.
double value1 = 100.00D;
double value2 = 15.99D;
double result = calcClient.Add(value1, value2);
Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);
```

```vb
' Create a client object with the given client endpoint configuration.
Dim calcClient As CalculatorClient = _
New CalculatorClient("CalculatorEndpoint")

' Call the Add service operation.
Dim value1 As Double = 100.00D
Dim value2 As Double = 15.99D
Dim result As Double = calcClient.Add(value1, value2)
Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result)
```

## <a name="debugging-exceptions-thrown-by-a-client"></a><span data-ttu-id="39440-137">Depuración de las excepciones iniciadas por un cliente</span><span class="sxs-lookup"><span data-stu-id="39440-137">Debugging Exceptions Thrown by a Client</span></span>

<span data-ttu-id="39440-138">Muchas de las excepciones producidas por un cliente de WCF se producen debido a una excepción en el servicio.</span><span class="sxs-lookup"><span data-stu-id="39440-138">Many exceptions thrown by a WCF client are caused by an exception on the service.</span></span> <span data-ttu-id="39440-139">Estos son algunos ejemplos:</span><span class="sxs-lookup"><span data-stu-id="39440-139">Some examples of this are:</span></span>

- <span data-ttu-id="39440-140"><xref:System.Net.Sockets.SocketException>: el host remoto forzó el cierre de la conexión existente.</span><span class="sxs-lookup"><span data-stu-id="39440-140"><xref:System.Net.Sockets.SocketException>: An existing connection was forcibly closed by the remote host.</span></span>

- <span data-ttu-id="39440-141"><xref:System.ServiceModel.CommunicationException>: la conexión ha terminado de forma inesperada.</span><span class="sxs-lookup"><span data-stu-id="39440-141"><xref:System.ServiceModel.CommunicationException>: The underlying connection was closed unexpectedly.</span></span>

- <span data-ttu-id="39440-142"><xref:System.ServiceModel.CommunicationObjectAbortedException>: se anuló la conexión de socket.</span><span class="sxs-lookup"><span data-stu-id="39440-142"><xref:System.ServiceModel.CommunicationObjectAbortedException>: The socket connection was aborted.</span></span> <span data-ttu-id="39440-143">La causa puede ser un error en el procesamiento del mensaje, que se superó el tiempo de espera de recepción en el host remoto, o bien un problema de recursos de red subyacente.</span><span class="sxs-lookup"><span data-stu-id="39440-143">This could be caused by an error processing your message, a receive time-out being exceeded by the remote host, or an underlying network resource issue.</span></span>

<span data-ttu-id="39440-144">Cuando se producen estos tipos de excepciones, la mejor manera de resolver el problema es activar el seguimiento en el lado del servicio y determinar qué excepción se produjo allí.</span><span class="sxs-lookup"><span data-stu-id="39440-144">When these types of exceptions occur, the best way to solve the problem is to turn on tracing on the service side and determine what exception occurred there.</span></span> <span data-ttu-id="39440-145">Para obtener más información sobre el seguimiento, vea [seguimiento](./diagnostics/tracing/index.md) y [uso del seguimiento para solucionar problemas de la aplicación](./diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md).</span><span class="sxs-lookup"><span data-stu-id="39440-145">For more information about tracing, see [Tracing](./diagnostics/tracing/index.md) and [Using Tracing to Troubleshoot Your Application](./diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="39440-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="39440-146">See also</span></span>

- [<span data-ttu-id="39440-147">Cómo crear un cliente</span><span class="sxs-lookup"><span data-stu-id="39440-147">How to: Create a Client</span></span>](how-to-create-a-wcf-client.md)
- [<span data-ttu-id="39440-148">Acceso a los servicios con un contrato dúplex</span><span class="sxs-lookup"><span data-stu-id="39440-148">How to: Access Services with a Duplex Contract</span></span>](./feature-details/how-to-access-services-with-a-duplex-contract.md)
- [<span data-ttu-id="39440-149">Llamada a operaciones de servicio de forma asincrónica</span><span class="sxs-lookup"><span data-stu-id="39440-149">How to: Call Service Operations Asynchronously</span></span>](./feature-details/how-to-call-wcf-service-operations-asynchronously.md)
- [<span data-ttu-id="39440-150">Acceso a los servicios con contratos unidireccionales y de solicitud-respuesta</span><span class="sxs-lookup"><span data-stu-id="39440-150">How to: Access Services with One-Way and Request-Reply Contracts</span></span>](./feature-details/how-to-access-wcf-services-with-one-way-and-request-reply-contracts.md)
- [<span data-ttu-id="39440-151">Acceso a un servicio WSE 3.0</span><span class="sxs-lookup"><span data-stu-id="39440-151">How to: Access a WSE 3.0 Service</span></span>](./feature-details/how-to-access-a-wse-3-0-service-with-a-wcf-client.md)
- [<span data-ttu-id="39440-152">Información sobre códigos de cliente generado</span><span class="sxs-lookup"><span data-stu-id="39440-152">Understanding Generated Client Code</span></span>](./feature-details/understanding-generated-client-code.md)
- [<span data-ttu-id="39440-153">Mejora del tiempo de inicio de las aplicaciones cliente WCF mediante XmlSerializer</span><span class="sxs-lookup"><span data-stu-id="39440-153">How to: Improve the Startup Time of WCF Client Applications using the XmlSerializer</span></span>](./feature-details/startup-time-of-wcf-client-applications-using-the-xmlserializer.md)
- [<span data-ttu-id="39440-154">Especificación del comportamiento de tiempo de ejecución del cliente</span><span class="sxs-lookup"><span data-stu-id="39440-154">Specifying Client Run-Time Behavior</span></span>](specifying-client-run-time-behavior.md)
- [<span data-ttu-id="39440-155">Configuración de los comportamientos del cliente</span><span class="sxs-lookup"><span data-stu-id="39440-155">Configuring Client Behaviors</span></span>](configuring-client-behaviors.md)
