---
title: Ejemplo básico
ms.date: 03/30/2017
ms.assetid: c1910bc1-3d0a-4fa6-b12a-4ed6fe759620
ms.openlocfilehash: 015b3ccee939cb62411d5901c7e2e558da3cc237
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58814580"
---
# <a name="basic-sample"></a><span data-ttu-id="91a5a-102">Ejemplo básico</span><span class="sxs-lookup"><span data-stu-id="91a5a-102">Basic Sample</span></span>
<span data-ttu-id="91a5a-103">En este ejemplo se muestra cómo hacer que un servicio se pueda detectar y cómo buscar y llamar a un servicio detectable.</span><span class="sxs-lookup"><span data-stu-id="91a5a-103">This sample shows how to make a service discoverable and how to search for and call a discoverable service.</span></span> <span data-ttu-id="91a5a-104">Este ejemplo se compone de dos proyectos: servicio y cliente.</span><span class="sxs-lookup"><span data-stu-id="91a5a-104">This sample is composed of two projects: service and client.</span></span>

> [!NOTE]
>  <span data-ttu-id="91a5a-105">En él se implementa la detección en el código.</span><span class="sxs-lookup"><span data-stu-id="91a5a-105">This sample implements discovery in code.</span></span>  <span data-ttu-id="91a5a-106">Para obtener un ejemplo que implementa la detección de configuración, consulte [configuración](../../../../docs/framework/wcf/samples/configuration-sample.md).</span><span class="sxs-lookup"><span data-stu-id="91a5a-106">For a sample that implements discovery in configuration, see [Configuration](../../../../docs/framework/wcf/samples/configuration-sample.md).</span></span>  
  
## <a name="service"></a><span data-ttu-id="91a5a-107">web de Office</span><span class="sxs-lookup"><span data-stu-id="91a5a-107">Service</span></span>  
 <span data-ttu-id="91a5a-108">Se trata de la implementación de un servicio de calculadora sencillo.</span><span class="sxs-lookup"><span data-stu-id="91a5a-108">This is a simple calculator service implementation.</span></span> <span data-ttu-id="91a5a-109">El código relacionado con la detección se puede encontrar en `Main` donde un objeto <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> se agrega al host del servicio y un objeto <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> se agrega como se muestra en el siguiente código.</span><span class="sxs-lookup"><span data-stu-id="91a5a-109">The discovery related code can be found in `Main` where a <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> is added to the service host and a <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> is added as shown in the following code.</span></span>  
  
```csharp
using (ServiceHost serviceHost = new ServiceHost(typeof(CalculatorService), baseAddress))  
{  
    serviceHost.AddServiceEndpoint(typeof(ICalculatorService), new   
      WSHttpBinding(), String.Empty);  
  
    // Make the service discoverable over UDP multicast  
    serviceHost.Description.Behaviors.Add(new ServiceDiscoveryBehavior());                  
    serviceHost.AddServiceEndpoint(new UdpDiscoveryEndpoint());  
  
    serviceHost.Open();  
    // ...  
}  
```  
  
## <a name="client"></a><span data-ttu-id="91a5a-110">Cliente</span><span class="sxs-lookup"><span data-stu-id="91a5a-110">Client</span></span>  
 <span data-ttu-id="91a5a-111">El cliente usa un objeto <xref:System.ServiceModel.Discovery.DynamicEndpoint> para localizar el servicio.</span><span class="sxs-lookup"><span data-stu-id="91a5a-111">The client uses a <xref:System.ServiceModel.Discovery.DynamicEndpoint> to locate the service.</span></span> <span data-ttu-id="91a5a-112">El <xref:System.ServiceModel.Discovery.DynamicEndpoint>, un extremo estándar, resuelve el extremo del servicio cuando se abre el cliente.</span><span class="sxs-lookup"><span data-stu-id="91a5a-112">The <xref:System.ServiceModel.Discovery.DynamicEndpoint>, a standard endpoint, resolves the endpoint of the service when the client is opened.</span></span> <span data-ttu-id="91a5a-113">En este caso, el <xref:System.ServiceModel.Discovery.DynamicEndpoint> busca el servicio según el contrato de servicio.</span><span class="sxs-lookup"><span data-stu-id="91a5a-113">In this case, the <xref:System.ServiceModel.Discovery.DynamicEndpoint> looks for the service based on the service contract.</span></span> <span data-ttu-id="91a5a-114">El <xref:System.ServiceModel.Discovery.DynamicEndpoint> realiza la búsqueda a través de un <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="91a5a-114">The <xref:System.ServiceModel.Discovery.DynamicEndpoint> conducts the search over a <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> by default.</span></span> <span data-ttu-id="91a5a-115">Cuando localiza un punto de conexión de servicio, el cliente se conecta a ese servicio a través del enlace especificado.</span><span class="sxs-lookup"><span data-stu-id="91a5a-115">Once it locates a service endpoint, the client connects to that service over the specified binding.</span></span>  
  
```csharp  
public static void Main()  
{  
   DynamicEndpoint dynamicEndpoint = new DynamicEndpoint( ContractDescription.GetContract(typeof(ICalculatorService)), new WSHttpBinding());  
   // ...  
}              
```  
  
 <span data-ttu-id="91a5a-116">El cliente define un método denominado `InvokeCalculatorService` que utiliza la clase <xref:System.ServiceModel.Discovery.DiscoveryClient> para buscar servicios.</span><span class="sxs-lookup"><span data-stu-id="91a5a-116">The client defines a method called `InvokeCalculatorService` that uses the <xref:System.ServiceModel.Discovery.DiscoveryClient> class to search for services.</span></span> <span data-ttu-id="91a5a-117"><xref:System.ServiceModel.Discovery.DynamicEndpoint> hereda de <xref:System.ServiceModel.Description.ServiceEndpoint>, de modo que se pueda pasar al método `InvokeCalculatorService`.</span><span class="sxs-lookup"><span data-stu-id="91a5a-117">The <xref:System.ServiceModel.Discovery.DynamicEndpoint> inherits from <xref:System.ServiceModel.Description.ServiceEndpoint>, so it can be passed to the `InvokeCalculatorService` method.</span></span> <span data-ttu-id="91a5a-118">A continuación, el ejemplo utiliza <xref:System.ServiceModel.Discovery.DynamicEndpoint> para crear una instancia de `CalculatorServiceClient` y llama a diversas operaciones del servicio de calculadora.</span><span class="sxs-lookup"><span data-stu-id="91a5a-118">The example then uses the <xref:System.ServiceModel.Discovery.DynamicEndpoint> to create an instance of `CalculatorServiceClient` and calls the various operations of the calculator service.</span></span>  
  
```csharp  
static void InvokeCalculatorService(ServiceEndpoint serviceEndpoint)  
{  
   // Create a client  
   CalculatorServiceClient client = new CalculatorServiceClient(serviceEndpoint);  
  
   Console.WriteLine("Invoking CalculatorService");  
   Console.WriteLine();  
  
   double value1 = 100.00D;  
   double value2 = 15.99D;  
  
   // Call the Add service operation.  
   double result = client.Add(value1, value2);  
   Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);  
  
   // Call the Subtract service operation.  
   result = client.Subtract(value1, value2);  
   Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result);  
  
   // Call the Multiply service operation.  
   result = client.Multiply(value1, value2);  
   Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result);  
  
   // Call the Divide service operation.  
   result = client.Divide(value1, value2);  
   Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result);  
   Console.WriteLine();  
  
   //Closing the client gracefully closes the connection and cleans up resources  
   client.Close();  
}  
```  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="91a5a-119">Para utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="91a5a-119">To use this sample</span></span>  
  
1.  <span data-ttu-id="91a5a-120">Este ejemplo utiliza los extremos HTTP y para ejecutarlo, se deben agregar las ACL de dirección URL apropiadas.</span><span class="sxs-lookup"><span data-stu-id="91a5a-120">This sample uses HTTP endpoints and to run this sample, proper URL ACLs must be added.</span></span> <span data-ttu-id="91a5a-121">Para obtener más información, consulte [configurar HTTP y HTTPS](https://go.microsoft.com/fwlink/?LinkId=70353).</span><span class="sxs-lookup"><span data-stu-id="91a5a-121">For more information, see [Configuring HTTP and HTTPS](https://go.microsoft.com/fwlink/?LinkId=70353).</span></span> <span data-ttu-id="91a5a-122">Al ejecutar el siguiente comando con privilegios elevados, se deberían agregar las ACL adecuadas.</span><span class="sxs-lookup"><span data-stu-id="91a5a-122">Executing the following command at an elevated privilege should add the appropriate ACLs.</span></span> <span data-ttu-id="91a5a-123">Puede que desee sustituir su dominio y nombre de usuario para los siguientes argumentos si el comando no funciona como debería.</span><span class="sxs-lookup"><span data-stu-id="91a5a-123">You may want to substitute your Domain and Username for the following arguments if the command does not work as is.</span></span> `netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%`  
  
2.  <span data-ttu-id="91a5a-124">Con Visual Studio 2012, abra Basic.sln y compile el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="91a5a-124">Using Visual Studio 2012, open the Basic.sln and build the sample.</span></span>  
  
3.  <span data-ttu-id="91a5a-125">Ejecute la aplicación service.exe.</span><span class="sxs-lookup"><span data-stu-id="91a5a-125">Run the service.exe application.</span></span>  
  
4.  <span data-ttu-id="91a5a-126">Después de que se inicie el servicio, ejecute la aplicación client.exe.</span><span class="sxs-lookup"><span data-stu-id="91a5a-126">After the service has started, run the client.exe.</span></span>  
  
5.  <span data-ttu-id="91a5a-127">Observe que el cliente pudo encontrar el servicio sin conocer su dirección.</span><span class="sxs-lookup"><span data-stu-id="91a5a-127">Observe that the client was able to find the service without knowing its address.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="91a5a-128">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="91a5a-128">The samples may already be installed on your machine.</span></span> <span data-ttu-id="91a5a-129">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="91a5a-129">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="91a5a-130">Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="91a5a-130">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="91a5a-131">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="91a5a-131">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\Basic`  
  
