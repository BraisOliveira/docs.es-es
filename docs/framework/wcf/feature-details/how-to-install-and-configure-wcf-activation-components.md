---
title: Procedimiento para instalar y configurar los componentes de activación de WFC
ms.date: 03/30/2017
helpviewer_keywords:
- HTTP activation [WCF]
ms.assetid: 33a7054a-73ec-464d-83e5-b203aeded658
ms.openlocfilehash: 953df285d1a439cd8a1a95358915a7a50e98552a
ms.sourcegitcommit: ffd7dd79468a81bbb0d6449f6d65513e050c04c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2019
ms.locfileid: "65960110"
---
# <a name="how-to-install-and-configure-wcf-activation-components"></a><span data-ttu-id="034bb-102">Procedimiento para instalar y configurar los componentes de activación de WFC</span><span class="sxs-lookup"><span data-stu-id="034bb-102">How to: Install and Configure WCF Activation Components</span></span>
<span data-ttu-id="034bb-103">En este tema se describe los pasos necesarios para configurar Windows Process Activation Service (también conocido como WAS) en [!INCLUDE[wv](../../../../includes/wv-md.md)] para hospedar servicios de Windows Communication Foundation (WCF) protocolos de red de servicios que no se comunican a través de HTTP.</span><span class="sxs-lookup"><span data-stu-id="034bb-103">This topic describes the steps required to set up Windows Process Activation Service (also known as WAS) on [!INCLUDE[wv](../../../../includes/wv-md.md)] to host Windows Communication Foundation (WCF) services that do not communicate over HTTP network protocols.</span></span> <span data-ttu-id="034bb-104">Las siguientes secciones describen los pasos para realizar esta configuración:</span><span class="sxs-lookup"><span data-stu-id="034bb-104">The following sections outline the steps for this configuration:</span></span>  
  
- <span data-ttu-id="034bb-105">Instale (o confirme la instalación de) los componentes de activación de WCF.</span><span class="sxs-lookup"><span data-stu-id="034bb-105">Install (or confirm the installation of) the WCF activation components.</span></span>  
  
- <span data-ttu-id="034bb-106">Configure WAS para que admita un protocolo que no sea HTTP.</span><span class="sxs-lookup"><span data-stu-id="034bb-106">Configure WAS to support a non-HTTP protocol.</span></span> <span data-ttu-id="034bb-107">El procedimiento siguiente configura [!INCLUDE[wv](../../../../includes/wv-md.md)] para la activación del TCP.</span><span class="sxs-lookup"><span data-stu-id="034bb-107">The following procedure configures [!INCLUDE[wv](../../../../includes/wv-md.md)] for TCP activation.</span></span>  
  
 <span data-ttu-id="034bb-108">Después de instalar y configurar WAS, vea [Cómo: Hospedar un servicio WCF en WAS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-was.md) para conocer los procedimientos crear un servicio WCF que expone un punto de conexión que no sea HTTP que emplee WAS.</span><span class="sxs-lookup"><span data-stu-id="034bb-108">After installing and configuring WAS, see [How to: Host a WCF Service in WAS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-was.md) for the procedures to create a WCF service that exposes an non-HTTP endpoint that employs WAS.</span></span>  
  
### <a name="to-install-the-wcf-non-http-activation-components"></a><span data-ttu-id="034bb-109">Instalación de los componentes de activación que no son HTTP de WCF</span><span class="sxs-lookup"><span data-stu-id="034bb-109">To install the WCF non-HTTP activation components</span></span>  
  
1. <span data-ttu-id="034bb-110">Haga clic en el **iniciar** botón y, a continuación, haga clic en **Panel de Control**.</span><span class="sxs-lookup"><span data-stu-id="034bb-110">Click the **Start** button, and then click **Control Panel**.</span></span>  
  
2. <span data-ttu-id="034bb-111">Haga clic en **programas**y, a continuación, haga clic en **programas y características**.</span><span class="sxs-lookup"><span data-stu-id="034bb-111">Click **Programs**, and then click **Programs and Features**.</span></span>  
  
3. <span data-ttu-id="034bb-112">En el **tareas** menú, haga clic en **o desactivar las características de Windows Active**.</span><span class="sxs-lookup"><span data-stu-id="034bb-112">On the **Tasks** menu, click **Turn Windows features on or off**.</span></span>  
  
4. <span data-ttu-id="034bb-113">Busque el nodo de WinFX, seleccione y, a continuación, expándala.</span><span class="sxs-lookup"><span data-stu-id="034bb-113">Find the WinFX node, select and then expand it.</span></span>  
  
5. <span data-ttu-id="034bb-114">Seleccione el **componentes de activación no Http de WCF** cuadro y guardar la configuración.</span><span class="sxs-lookup"><span data-stu-id="034bb-114">Select the **WCF Non-Http Activation Components** box and save the setting.</span></span>  
  
### <a name="to-configure-the-was-to-support-tcp-activation"></a><span data-ttu-id="034bb-115">Configuración de WAS para admitir la activación TCP</span><span class="sxs-lookup"><span data-stu-id="034bb-115">To configure the WAS to support TCP activation</span></span>  
  
1. <span data-ttu-id="034bb-116">Para admitir la activación del net.tcp, el sitio web predeterminado debe enlazarse primero a un puerto net.tcp.</span><span class="sxs-lookup"><span data-stu-id="034bb-116">To support net.tcp activation, the default Web site must first be bound to a net.tcp port.</span></span> <span data-ttu-id="034bb-117">Puede hacer esto utilizando Appcmd.exe, que está instalado con el conjunto de herramientas de administración [!INCLUDE[iisver](../../../../includes/iisver-md.md)].</span><span class="sxs-lookup"><span data-stu-id="034bb-117">You can do this by using Appcmd.exe, which is installed with the [!INCLUDE[iisver](../../../../includes/iisver-md.md)] management toolset.</span></span> <span data-ttu-id="034bb-118">En una ventana de símbolo de sistema para administradores, ejecute el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="034bb-118">In an administrator-level Command Prompt window, run the following command.</span></span>  
  
    ```  
    %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site" -+bindings.[protocol='net.tcp',bindingInformation='808:*']  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="034bb-119">Este comando es una sola línea de texto.</span><span class="sxs-lookup"><span data-stu-id="034bb-119">This command is a single line of text.</span></span> <span data-ttu-id="034bb-120">Este comando agrega un enlace del sitio net.tcp al sitio web predeterminado que realiza escuchas en el puerto TCP 808 con cualquier nombre de host.</span><span class="sxs-lookup"><span data-stu-id="034bb-120">This command adds a net.tcp site binding to the default Web site listening on TCP port 808 with any host name.</span></span>  
  
2. <span data-ttu-id="034bb-121">Aunque todas las aplicaciones dentro de un sitio comparten un enlace net. tcp común, cada aplicación puede habilitar la compatibilidad net. tcp individualmente.</span><span class="sxs-lookup"><span data-stu-id="034bb-121">Although all applications within a site share a common net.tcp binding, each application can enable net.tcp support individually.</span></span> <span data-ttu-id="034bb-122">Para habilitar net.tcp para la aplicación, ejecute el siguiente comando desde un símbolo del sistema del nivel del administrador:</span><span class="sxs-lookup"><span data-stu-id="034bb-122">To enable net.tcp for the application, run the following command from an administrator-level command prompt.</span></span>  
  
    ```  
    %windir%\system32\inetsrv\appcmd.exe set app   
    "Default Web Site/<WCF Application>" /enabledProtocols:http,net.tcp  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="034bb-123">Este comando es una sola línea de texto.</span><span class="sxs-lookup"><span data-stu-id="034bb-123">This command is a single line of text.</span></span> <span data-ttu-id="034bb-124">Este comando habilita la /\<*aplicación WCF*> aplicación para tener acceso utilizando tanto `http://localhost/<WCF Application>` y `net.tcp://localhost/<WCF Application>`.</span><span class="sxs-lookup"><span data-stu-id="034bb-124">This command enables the /\<*WCF Application*> application to be accessed using both `http://localhost/<WCF Application>` and `net.tcp://localhost/<WCF Application>`.</span></span>
  
     <span data-ttu-id="034bb-125">Elimine el enlace del sitio de net.tcp que ha agregado para este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="034bb-125">Remove the net.tcp site binding you added for this sample.</span></span>  
  
     <span data-ttu-id="034bb-126">Para su comodidad, los dos pasos siguientes se implementan en un archivo de información llamado RemoveNetTcpSiteBinding.cmd localizado en el directorio de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="034bb-126">As a convenience, the following two steps are implemented in a batch file called RemoveNetTcpSiteBinding.cmd located in the sample directory.</span></span>  
  
    1. <span data-ttu-id="034bb-127">Quite el net.tcp de la lista de protocolos habilitados ejecutando el comando siguiente en una ventana de símbolo del sistema del nivel del administrador:</span><span class="sxs-lookup"><span data-stu-id="034bb-127">Remove net.tcp from the list of enabled protocols by running the following command in an administrator-level Command Prompt window.</span></span>  
  
        ```  
        %windir%\system32\inetsrv\appcmd.exe set app   
        "Default Web Site/servicemodelsamples<WCF Application>" " /enabledProtocols:http  
        ```  
  
        > [!NOTE]
        >  <span data-ttu-id="034bb-128">Este comando es una sola línea de texto.</span><span class="sxs-lookup"><span data-stu-id="034bb-128">This command is a single line of text.</span></span>  
  
    2. <span data-ttu-id="034bb-129">Quite el enlace del sitio net.tcp ejecutando el siguiente comando desde una ventana de símbolo del sistema elevado:</span><span class="sxs-lookup"><span data-stu-id="034bb-129">Remove the net.tcp site binding by running the following command in an elevated Command Prompt window:</span></span>  
  
        ```  
        %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site"   
        --bindings.[protocol='net.tcp',bindingInformation='808:*']  
        ```  
  
        > [!NOTE]
        >  <span data-ttu-id="034bb-130">Este comando es una sola línea de texto.</span><span class="sxs-lookup"><span data-stu-id="034bb-130">This command is a single line of text.</span></span>  
  
### <a name="to-remove-nettcp-from-the-list-of-enabled-protocols"></a><span data-ttu-id="034bb-131">Quitar el net.tcp de la lista de protocolos habilitados</span><span class="sxs-lookup"><span data-stu-id="034bb-131">To remove net.tcp from the list of enabled protocols</span></span>  
  
1. <span data-ttu-id="034bb-132">Para quitar el net.tcp de la lista de protocolos habilitados, ejecute el siguiente comando en una ventana de símbolo del sistema del nivel del administrador:</span><span class="sxs-lookup"><span data-stu-id="034bb-132">To remove net.tcp from the list of enabled protocols, run the following command in an administrator-level Command Prompt window.</span></span>  
  
    ```  
    %windir%\system32\inetsrv\appcmd.exe set app "Default Web Site/servicemodelsamples<WCF Application>" " /enabledProtocols:http  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="034bb-133">Este comando es una sola línea de texto.</span><span class="sxs-lookup"><span data-stu-id="034bb-133">This command is a single line of text.</span></span>  
  
### <a name="to-remove-the-nettcp-site-binding"></a><span data-ttu-id="034bb-134">Quitar el enlace de sitio de net.tcp</span><span class="sxs-lookup"><span data-stu-id="034bb-134">To remove the net.tcp site binding</span></span>  
  
1. <span data-ttu-id="034bb-135">Para quitar el enlace del sitio net.tcp ejecute el siguiente comando desde una ventana de símbolo del sistema en el nivel de administrador:</span><span class="sxs-lookup"><span data-stu-id="034bb-135">To remove the net.tcp site binding run the following command in an administrator-level Command Prompt window.</span></span>  
  
    ```  
    %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site"   
    -bindings.[protocol='net.tcp',bindingInformation='808:*']  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="034bb-136">Este comando es una sola línea de texto.</span><span class="sxs-lookup"><span data-stu-id="034bb-136">This command is a single line of text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="034bb-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="034bb-137">See also</span></span>

- [<span data-ttu-id="034bb-138">Activación TCP</span><span class="sxs-lookup"><span data-stu-id="034bb-138">TCP Activation</span></span>](../../../../docs/framework/wcf/samples/tcp-activation.md)
- [<span data-ttu-id="034bb-139">Activación MSMQ</span><span class="sxs-lookup"><span data-stu-id="034bb-139">MSMQ Activation</span></span>](../../../../docs/framework/wcf/samples/msmq-activation.md)
- [<span data-ttu-id="034bb-140">Activación NamedPipe</span><span class="sxs-lookup"><span data-stu-id="034bb-140">NamedPipe Activation</span></span>](../../../../docs/framework/wcf/samples/namedpipe-activation.md)
- [<span data-ttu-id="034bb-141">Características de hospedaje de Windows Server AppFabric</span><span class="sxs-lookup"><span data-stu-id="034bb-141">Windows Server App Fabric Hosting Features</span></span>](https://go.microsoft.com/fwlink/?LinkId=201276)
