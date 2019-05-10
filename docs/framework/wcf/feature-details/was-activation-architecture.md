---
title: Arquitectura de activación de WAS
ms.date: 03/30/2017
ms.assetid: 58aeffb0-8f3f-4b40-80c8-15f3f1652fd3
ms.openlocfilehash: 063c5e43abf4ddda3edb1de1d9d983bfe8e05706
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64637393"
---
# <a name="was-activation-architecture"></a><span data-ttu-id="933e1-102">Arquitectura de activación de WAS</span><span class="sxs-lookup"><span data-stu-id="933e1-102">WAS Activation Architecture</span></span>
<span data-ttu-id="933e1-103">Este tema detalla y discute los componentes de Windows Process Activation Service (también conocido como WAS).</span><span class="sxs-lookup"><span data-stu-id="933e1-103">This topic itemizes and discusses the components of the Windows Process Activation Service (also known as WAS).</span></span>  
  
## <a name="activation-components"></a><span data-ttu-id="933e1-104">Componentes de activación</span><span class="sxs-lookup"><span data-stu-id="933e1-104">Activation Components</span></span>  
 <span data-ttu-id="933e1-105">WAS está compuesto por varios componentes arquitectónicos:</span><span class="sxs-lookup"><span data-stu-id="933e1-105">WAS consists of several architectural components:</span></span>  
  
- <span data-ttu-id="933e1-106">Adaptadores de escucha.</span><span class="sxs-lookup"><span data-stu-id="933e1-106">Listener adapters.</span></span> <span data-ttu-id="933e1-107">Servicios de Windows que reciben mensajes en protocolos de red concretos y se comunican con WAS para enrutar los mensajes entrantes hasta el proceso de trabajo correcto.</span><span class="sxs-lookup"><span data-stu-id="933e1-107">Windows services that receive messages on specific network protocols and communicate with WAS to route incoming messages to the correct worker process.</span></span>  
  
- <span data-ttu-id="933e1-108">WAS.</span><span class="sxs-lookup"><span data-stu-id="933e1-108">WAS.</span></span> <span data-ttu-id="933e1-109">El servicio de Windows que administra la creación y duración de procesos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="933e1-109">The Windows service that manages the creation and lifetime of worker processes.</span></span>  
  
- <span data-ttu-id="933e1-110">La aplicación ejecutable del proceso de trabajo genérica (w3wp.exe).</span><span class="sxs-lookup"><span data-stu-id="933e1-110">The generic worker process executable (w3wp.exe).</span></span>  
  
- <span data-ttu-id="933e1-111">Administrador de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="933e1-111">Application manager.</span></span> <span data-ttu-id="933e1-112">Administra la creación y duración de dominios de aplicación que hospedan aplicaciones dentro del proceso de trabajo.</span><span class="sxs-lookup"><span data-stu-id="933e1-112">Manages the creation and lifetime of application domains that host applications within the worker process.</span></span>  
  
- <span data-ttu-id="933e1-113">Controladores de protocolos.</span><span class="sxs-lookup"><span data-stu-id="933e1-113">Protocol handlers.</span></span> <span data-ttu-id="933e1-114">Componentes específicos de protocolos que se ejecutan en el proceso de trabajo y administran la comunicación entre el proceso de trabajo y los adaptadores de escucha individuales.</span><span class="sxs-lookup"><span data-stu-id="933e1-114">Protocol-specific components that run in the worker process and manage communication between the worker process and the individual listener adapters.</span></span> <span data-ttu-id="933e1-115">Existen dos tipos de controladores de protocolo: controladores de protocolo de proceso y controladores de protocolo del AppDomain.</span><span class="sxs-lookup"><span data-stu-id="933e1-115">Two types of protocol handlers exist: process protocol handlers and AppDomain protocol handlers.</span></span>  
  
 <span data-ttu-id="933e1-116">Cuando WAS activa una instancia del proceso de trabajo, carga los controladores de protocolo de proceso requeridos en el proceso de trabajo y utiliza el administrador de aplicaciones para crear un dominio de aplicación que hospede la aplicación.</span><span class="sxs-lookup"><span data-stu-id="933e1-116">When WAS activates a worker process instance, it loads the process protocol handlers required into the worker process and uses the application manager to create an application domain to host the application.</span></span> <span data-ttu-id="933e1-117">El dominio de la aplicación carga el código de la aplicación así como los controladores de protocolo del AppDomain que requieren los protocolos de red utilizados por la aplicación.</span><span class="sxs-lookup"><span data-stu-id="933e1-117">The application domain loads the application’s code as well as the AppDomain protocol handlers that the network protocols used by the application require.</span></span>  
  
 ![Captura de pantalla que muestra la arquitectura WAS.](./media/was-activation-architecture/windows-process-application-service-architecture.gif)  
  
### <a name="listener-adapters"></a><span data-ttu-id="933e1-119">Adaptadores de escucha</span><span class="sxs-lookup"><span data-stu-id="933e1-119">Listener Adapters</span></span>  
 <span data-ttu-id="933e1-120">Los adaptadores de escucha son servicios de Windows individuales que implementan la lógica de comunicación de red utilizada para recibir mensajes mediante el protocolo de red en el que realizan escuchas.</span><span class="sxs-lookup"><span data-stu-id="933e1-120">Listener adapters are individual Windows services that implement the network communication logic used to receive messages using the network protocol on which they listen.</span></span> <span data-ttu-id="933e1-121">En la tabla siguiente se enumera los adaptadores de escucha para los protocolos de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="933e1-121">The following table lists the listener adapters for Windows Communication Foundation (WCF) protocols.</span></span>  
  
|<span data-ttu-id="933e1-122">Nombre de servicio de adaptador de escucha</span><span class="sxs-lookup"><span data-stu-id="933e1-122">Listener adapter service name</span></span>|<span data-ttu-id="933e1-123">Protocolo</span><span class="sxs-lookup"><span data-stu-id="933e1-123">Protocol</span></span>|<span data-ttu-id="933e1-124">Notas</span><span class="sxs-lookup"><span data-stu-id="933e1-124">Notes</span></span>|  
|-----------------------------------|--------------|-----------|  
|<span data-ttu-id="933e1-125">W3SVC</span><span class="sxs-lookup"><span data-stu-id="933e1-125">W3SVC</span></span>|<span data-ttu-id="933e1-126">http</span><span class="sxs-lookup"><span data-stu-id="933e1-126">http</span></span>|<span data-ttu-id="933e1-127">Componente común que proporciona activación HTTP para IIS 7.0 y WCF.</span><span class="sxs-lookup"><span data-stu-id="933e1-127">Common component that provides HTTP activation for both IIS 7.0 and WCF.</span></span>|  
|<span data-ttu-id="933e1-128">NetTcpActivator</span><span class="sxs-lookup"><span data-stu-id="933e1-128">NetTcpActivator</span></span>|<span data-ttu-id="933e1-129">net.tcp</span><span class="sxs-lookup"><span data-stu-id="933e1-129">net.tcp</span></span>|<span data-ttu-id="933e1-130">Depende del servicio NetTcpPortSharing.</span><span class="sxs-lookup"><span data-stu-id="933e1-130">Depends on the NetTcpPortSharing service.</span></span>|  
|<span data-ttu-id="933e1-131">NetPipeActivator</span><span class="sxs-lookup"><span data-stu-id="933e1-131">NetPipeActivator</span></span>|<span data-ttu-id="933e1-132">net.pipe</span><span class="sxs-lookup"><span data-stu-id="933e1-132">net.pipe</span></span>||  
|<span data-ttu-id="933e1-133">NetMsmqActivator</span><span class="sxs-lookup"><span data-stu-id="933e1-133">NetMsmqActivator</span></span>|<span data-ttu-id="933e1-134">net.msmq</span><span class="sxs-lookup"><span data-stu-id="933e1-134">net.msmq</span></span>|<span data-ttu-id="933e1-135">Para su uso con aplicaciones basadas en WCF Message Queue Server.</span><span class="sxs-lookup"><span data-stu-id="933e1-135">For use with WCF-based Message Queuing applications.</span></span>|  
|<span data-ttu-id="933e1-136">NetMsmqActivator</span><span class="sxs-lookup"><span data-stu-id="933e1-136">NetMsmqActivator</span></span>|<span data-ttu-id="933e1-137">msmq.formatname</span><span class="sxs-lookup"><span data-stu-id="933e1-137">msmq.formatname</span></span>|<span data-ttu-id="933e1-138">Proporciona compatibilidad con versiones anteriores para aplicaciones existentes de Message Queuing.</span><span class="sxs-lookup"><span data-stu-id="933e1-138">Provides backwards compatibility with existing Message Queuing applications.</span></span>|  
  
 <span data-ttu-id="933e1-139">Los adaptadores de escucha para protocolos concretos se registran durante la instalación en el archivo applicationHost.config, tal y como se muestra en el siguiente XML de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="933e1-139">Listener adapters for specific protocols are registered during installation in the applicationHost.config file, as shown in the following XML example.</span></span>  
  
```xml  
<system.applicationHost>  
    <listenerAdapters>  
        <add name="http" />  
        <add name="net.tcp"   
          identity="S-1-5-80-3579033775-2824656752-1522793541-1960352512-462907086" />  
         <add name="net.pipe"   
           identity="S-1-5-80-2943419899-937267781-4189664001-1229628381-3982115073" />  
          <add name="net.msmq"   
            identity="S-1-5-80-89244771-1762554971-1007993102-348796144-2203111529" />  
           <add name="msmq.formatname"   
             identity="S-1-5-80-89244771-1762554971-1007993102-348796144-2203111529" />  
    </listenerAdapters>  
</system.applicationHost>  
```  
  
### <a name="protocol-handlers"></a><span data-ttu-id="933e1-140">Controladores de protocolo</span><span class="sxs-lookup"><span data-stu-id="933e1-140">Protocol Handlers</span></span>  
 <span data-ttu-id="933e1-141">Los controladores de protocolo de proceso y AppDomain se registran en el archivo Web.config de nivel de equipo.</span><span class="sxs-lookup"><span data-stu-id="933e1-141">Process and AppDomain protocol handlers for specific protocols are registered in the machine-level Web.config file.</span></span>  
  
```xml  
<system.web>  
   <protocols>  
      <add name="net.tcp"   
        processHandlerType=  
         "System.ServiceModel.WasHosting.TcpProcessProtocolHandler"  
        appDomainHandlerType=  
         "System.ServiceModel.WasHosting.TcpAppDomainProtocolHandler"  
        validate="false" />  
      <add name="net.pipe"   
        processHandlerType=  
         "System.ServiceModel.WasHosting.NamedPipeProcessProtocolHandler"  
          appDomainHandlerType=  
           "System.ServiceModel.WasHosting.NamedPipeAppDomainProtocolHandler"/>  
      <add name="net.msmq"  
        processHandlerType=  
         "System.ServiceModel.WasHosting.MsmqProcessProtocolHandler"  
        appDomainHandlerType=  
         "System.ServiceModel.WasHosting.MsmqAppDomainProtocolHandler"  
        validate="false" />  
   </protocols>  
</system.web>  
```  
  
## <a name="see-also"></a><span data-ttu-id="933e1-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="933e1-142">See also</span></span>

- [<span data-ttu-id="933e1-143">Configuración de WAS para su uso con WCF</span><span class="sxs-lookup"><span data-stu-id="933e1-143">Configuring WAS for Use with WCF</span></span>](../../../../docs/framework/wcf/feature-details/configuring-the-wpa--service-for-use-with-wcf.md)
- [<span data-ttu-id="933e1-144">Características de hospedaje de Windows Server AppFabric</span><span class="sxs-lookup"><span data-stu-id="933e1-144">Windows Server App Fabric Hosting Features</span></span>](https://go.microsoft.com/fwlink/?LinkId=201276)
