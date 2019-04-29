---
title: Procedimiento para intercambiar mensajes dentro de una sesión confiable
ms.date: 03/30/2017
ms.assetid: 87cd0e75-dd2c-44c1-8da0-7b494bbdeaea
ms.openlocfilehash: aad4eae870e3ba603c56a28a620fe8bc0e31ceb6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61778370"
---
# <a name="how-to-exchange-messages-within-a-reliable-session"></a><span data-ttu-id="1bb83-102">Procedimiento para intercambiar mensajes dentro de una sesión confiable</span><span class="sxs-lookup"><span data-stu-id="1bb83-102">How to: Exchange Messages Within a Reliable Session</span></span>

<span data-ttu-id="1bb83-103">En este tema se describen los pasos necesarios para habilitar una sesión confiable utilizando uno de los enlaces proporcionados por el sistema que admiten este tipo de sesión, pero no de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="1bb83-103">This topic outlines the steps required to enable a reliable session using one of the system-provided bindings that support such a session, but not by default.</span></span> <span data-ttu-id="1bb83-104">Habilitar una sesión confiable de manera imperativa mediante código o mediante declaración en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="1bb83-104">You enable a reliable session imperatively using code or declaratively in your configuration file.</span></span> <span data-ttu-id="1bb83-105">Este procedimiento utiliza los archivos de configuración de cliente y servicio para habilitar la sesión confiable y para estipular que los mensajes lleguen en el mismo orden en que se enviaron.</span><span class="sxs-lookup"><span data-stu-id="1bb83-105">This procedure uses the client and service configuration files to enable the reliable session and to stipulate that the messages arrive in the same order in which they were sent.</span></span>

<span data-ttu-id="1bb83-106">La parte clave de este procedimiento es que el elemento de configuración de punto de conexión contienen un `bindingConfiguration` atributo que hace referencia a una configuración de enlace denominada `Binding1`.</span><span class="sxs-lookup"><span data-stu-id="1bb83-106">The key part of this procedure is that the endpoint configuration element contain a `bindingConfiguration` attribute that references a binding configuration named `Binding1`.</span></span> <span data-ttu-id="1bb83-107">El [  **\<enlace >** ](../../../../docs/framework/misc/binding.md) elemento de configuración hace referencia a este nombre para habilitar sesiones confiables estableciendo el `enabled` atributo de la [  **\<reliableSession >** ](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731302(v=vs.100)) elemento `true`.</span><span class="sxs-lookup"><span data-stu-id="1bb83-107">The [**\<binding>**](../../../../docs/framework/misc/binding.md) configuration element references this name to enable reliable sessions by setting the `enabled` attribute of the [**\<reliableSession>**](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731302(v=vs.100)) element to `true`.</span></span> <span data-ttu-id="1bb83-108">Especifica las garantías de entrega ordenada de la sesión confiable estableciendo el atributo `ordered` en `true`.</span><span class="sxs-lookup"><span data-stu-id="1bb83-108">You specify the ordered delivery assurances for the reliable session by setting the `ordered` attribute to `true`.</span></span>

<span data-ttu-id="1bb83-109">Para la copia de origen de este ejemplo, vea [sesión confiable WS](../../../../docs/framework/wcf/samples/ws-reliable-session.md).</span><span class="sxs-lookup"><span data-stu-id="1bb83-109">For the source copy of this example, see [WS Reliable Session](../../../../docs/framework/wcf/samples/ws-reliable-session.md).</span></span>

### <a name="configure-the-service-with-a-wshttpbinding-to-use-a-reliable-session"></a><span data-ttu-id="1bb83-110">Configurar el servicio con WSHttpBinding para utilizar una sesión confiable</span><span class="sxs-lookup"><span data-stu-id="1bb83-110">Configure the service with a WSHttpBinding to use a reliable session</span></span>

1. <span data-ttu-id="1bb83-111">Defina un contrato de servicios para el tipo de servicio.</span><span class="sxs-lookup"><span data-stu-id="1bb83-111">Define a service contract for the type of service.</span></span>

   [!code-csharp[c_HowTo_UseReliableSession#1121](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/service.cs#1121)]

1. <span data-ttu-id="1bb83-112">Implemente el contrato de servicios en una clase de servicio.</span><span class="sxs-lookup"><span data-stu-id="1bb83-112">Implement the service contract in a service class.</span></span> <span data-ttu-id="1bb83-113">Tenga en cuenta que no se especifica la información de dirección o enlace dentro de la implementación del servicio.</span><span class="sxs-lookup"><span data-stu-id="1bb83-113">Note that the address or binding information isn't specified inside the implementation of the service.</span></span> <span data-ttu-id="1bb83-114">No es necesario escribir código para recuperar la información de dirección o enlace desde el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="1bb83-114">You aren't required to write code to retrieve the address or binding information from the configuration file.</span></span>

   [!code-csharp[c_HowTo_UseReliableSession#1122](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/service.cs#1122)]

1. <span data-ttu-id="1bb83-115">Crear un *Web.config* archivo para configurar un punto de conexión para el `CalculatorService` que usa el <xref:System.ServiceModel.WSHttpBinding> con sesión confiable habilitada y entrega ordenada de mensajes necesarios.</span><span class="sxs-lookup"><span data-stu-id="1bb83-115">Create a *Web.config* file to configure an endpoint for the `CalculatorService` that uses the <xref:System.ServiceModel.WSHttpBinding> with reliable session enabled and ordered delivery of messages required.</span></span>

   [!code-xml[c_HowTo_UseReliableSession#2111](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/common/web.config#2111)]

1. <span data-ttu-id="1bb83-116">Crear un *Service.svc* archivo que contiene la línea:</span><span class="sxs-lookup"><span data-stu-id="1bb83-116">Create a *Service.svc* file that contains the line:</span></span>

   ```
   <%@ServiceHost language=c# Service="CalculatorService" %>
   ```

1. <span data-ttu-id="1bb83-117">Colocar el *Service.svc* archivo en el directorio virtual de Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="1bb83-117">Place the *Service.svc* file in your Internet Information Services (IIS) virtual directory.</span></span>

### <a name="configure-the-client-with-a-wshttpbinding-to-use-a-reliable-session"></a><span data-ttu-id="1bb83-118">Configurar al cliente con un WSHttpBinding para utilizar una sesión confiable</span><span class="sxs-lookup"><span data-stu-id="1bb83-118">Configure the client with a WSHttpBinding to use a reliable session</span></span>

1. <span data-ttu-id="1bb83-119">Use la [ServiceModel Metadata Utility Tool (*Svcutil.exe*)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) desde la línea de comandos para generar código a partir de los metadatos del servicio:</span><span class="sxs-lookup"><span data-stu-id="1bb83-119">Use the [ServiceModel Metadata Utility Tool (*Svcutil.exe*)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) from the command line to generate code from service metadata:</span></span>

   ```console
   Svcutil.exe <service's Metadata Exchange (MEX) address or HTTP GET address>
   ```

1. <span data-ttu-id="1bb83-120">El cliente generado contiene la `ICalculator` interfaz que define el contrato de servicio que debe cumplir la implementación del cliente.</span><span class="sxs-lookup"><span data-stu-id="1bb83-120">The generated client contains the `ICalculator` interface that defines the service contract that the client implementation must satisfy.</span></span>

   [!code-csharp[C_HowTo_UseReliableSession#1221](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/client.cs#1221)]

1. <span data-ttu-id="1bb83-121">La aplicación de cliente generada también contiene la implementación de `ClientCalculator`.</span><span class="sxs-lookup"><span data-stu-id="1bb83-121">The generated client application also contains the implementation of the `ClientCalculator`.</span></span> <span data-ttu-id="1bb83-122">Tenga en cuenta que la información de dirección y el enlace no se especifica en cualquier lugar dentro de la implementación del servicio.</span><span class="sxs-lookup"><span data-stu-id="1bb83-122">Note that the address and binding information isn't specified anywhere inside the implementation of the service.</span></span> <span data-ttu-id="1bb83-123">No es necesario escribir código para recuperar la información de dirección o enlace desde el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="1bb83-123">You aren't required to write code to retrieve the address or binding information from the configuration file.</span></span>

   [!code-csharp[C_HowTo_UseReliableSession#1222](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/client.cs#1222)]

1. <span data-ttu-id="1bb83-124">*Svcutil.exe* también genera la configuración para el cliente que usa el <xref:System.ServiceModel.WSHttpBinding> clase.</span><span class="sxs-lookup"><span data-stu-id="1bb83-124">*Svcutil.exe* also generates the configuration for the client that uses the <xref:System.ServiceModel.WSHttpBinding> class.</span></span> <span data-ttu-id="1bb83-125">Nombre del archivo de configuración *App.config* cuando se usa Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="1bb83-125">Name the configuration file *App.config* when using Visual Studio.</span></span>

   [!code-xml[C_HowTo_UseReliableSession#2211](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/common/app.config#2211)]

1. <span data-ttu-id="1bb83-126">Cree una instancia de la `ClientCalculator` en una aplicación y llamar a las operaciones de servicio.</span><span class="sxs-lookup"><span data-stu-id="1bb83-126">Create an instance of the `ClientCalculator` in an application and call the service operations.</span></span>

   [!code-csharp[C_HowTo_UseReliableSession#1223](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/client.cs#1223)]

1. <span data-ttu-id="1bb83-127">Compile y ejecute el cliente.</span><span class="sxs-lookup"><span data-stu-id="1bb83-127">Compile and run the client.</span></span>

## <a name="example"></a><span data-ttu-id="1bb83-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1bb83-128">Example</span></span>

<span data-ttu-id="1bb83-129">Algunos de los enlaces proporcionados por el sistema admiten de forma predeterminada las sesiones confiables.</span><span class="sxs-lookup"><span data-stu-id="1bb83-129">Several of the system-provided bindings support reliable sessions by default.</span></span> <span data-ttu-id="1bb83-130">Se incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="1bb83-130">These include:</span></span>

- <xref:System.ServiceModel.WSDualHttpBinding>

- <xref:System.ServiceModel.NetNamedPipeBinding>

- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>

<span data-ttu-id="1bb83-131">Para obtener un ejemplo de cómo crear un enlace personalizado que admite sesiones confiables, vea [Cómo: Creación de un enlace personalizado de sesión confiable con HTTPS](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md).</span><span class="sxs-lookup"><span data-stu-id="1bb83-131">For an example of how to create a custom binding that supports reliable sessions, see [How to: Create a Custom Reliable Session Binding with HTTPS](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1bb83-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="1bb83-132">See also</span></span>

- [<span data-ttu-id="1bb83-133">Sesiones de confianza</span><span class="sxs-lookup"><span data-stu-id="1bb83-133">Reliable Sessions</span></span>](../../../../docs/framework/wcf/feature-details/reliable-sessions.md)
