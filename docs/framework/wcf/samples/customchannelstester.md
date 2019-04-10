---
title: CustomChannelsTester
ms.date: 03/30/2017
ms.assetid: ee1fa307-98b1-4647-8860-2e9217ba6082
ms.openlocfilehash: 7402ac9ccc0e5e1777fa77f339d7605e1d306e13
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59312675"
---
# <a name="customchannelstester"></a><span data-ttu-id="67211-102">CustomChannelsTester</span><span class="sxs-lookup"><span data-stu-id="67211-102">CustomChannelsTester</span></span>
<span data-ttu-id="67211-103">El `CustomChannelsTester` es una herramienta que se utiliza para probar las implementaciones del canal personalizadas contra un conjunto de contratos de servicios predefinidos.</span><span class="sxs-lookup"><span data-stu-id="67211-103">The `CustomChannelsTester` is a tool that you can use to test your custom channel implementations against a set of predefined service contracts.</span></span> <span data-ttu-id="67211-104">Puede seleccionar el conjunto de contratos de servicios y pasarlo a la herramienta utilizando un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="67211-104">You can select the set of service contracts and pass it to the tool using an XML file.</span></span> <span data-ttu-id="67211-105">La herramienta genera a continuación el servicio y el cliente que ejerce sus implementaciones del canal personalizadas durante el intercambio de mensajes.</span><span class="sxs-lookup"><span data-stu-id="67211-105">The tool then generates the service and client that exercises your custom channel implementations during message exchange.</span></span>  
  
### <a name="to-build-the-tool"></a><span data-ttu-id="67211-106">Para compilar la herramienta</span><span class="sxs-lookup"><span data-stu-id="67211-106">To build the tool</span></span>  
  
1. <span data-ttu-id="67211-107">Para compilar la solución, siga las instrucciones de [compilar los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="67211-107">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
2. <span data-ttu-id="67211-108">Al compilar la solución, se generan tres archivos: CustomChannelsTester.exe, TestSpec.xml y SampleRun.cmd. CustomChannelsTester.exe, TestSpec.xml y SampleRun.cmd.</span><span class="sxs-lookup"><span data-stu-id="67211-108">Building the solution generates three files: CustomChannelsTester.exe, TestSpec.xml and SampleRun.cmd.</span></span> <span data-ttu-id="67211-109">Samplerun.cmd del archivo tiene una línea de comandos de ejemplo que muestra cómo usar esta herramienta para probar la [transporte: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) ejemplo.</span><span class="sxs-lookup"><span data-stu-id="67211-109">The file SampleRun.cmd has a sample command line that shows how to use this tool to test the [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) sample.</span></span>  
  
### <a name="to-run-the-tool"></a><span data-ttu-id="67211-110">Para ejecutar la herramienta</span><span class="sxs-lookup"><span data-stu-id="67211-110">To run the tool</span></span>  
  
-   <span data-ttu-id="67211-111">Escriba el siguiente comando en el símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="67211-111">At the command prompt type the following command:</span></span>  
  
    ```  
    CustomChannelsTester.exe /binding:YourCustomBindngName /dll:TheAssemblyWhereThisTypeisDefined /testspec:XmlFileNameWhichContainsTestOptions  
    ```  
  
     <span data-ttu-id="67211-112">Se requiere utilizar la opción `/binding`.</span><span class="sxs-lookup"><span data-stu-id="67211-112">Using the `/binding` option is required.</span></span>  
  
     `/dll` <span data-ttu-id="67211-113">es necesario si "enlace" no es un enlace proporcionado por el sistema proporcionado por Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="67211-113">is required if "binding" is not a system-provided binding provided by Windows Communication Foundation (WCF).</span></span>  
  
     `/testspec` <span data-ttu-id="67211-114">es opcional.</span><span class="sxs-lookup"><span data-stu-id="67211-114">is optional.</span></span>  
  
     <span data-ttu-id="67211-115">Esto crea el servidor y los clientes basados en las características técnicas de pruebas y el enlace.</span><span class="sxs-lookup"><span data-stu-id="67211-115">This creates server and clients based on the test specifications and the binding.</span></span>  
  
     <span data-ttu-id="67211-116">Ejecuta el cliente y el servidor y devuelve los resultados.</span><span class="sxs-lookup"><span data-stu-id="67211-116">Executes the client and server and returns the results.</span></span>  
  
     <span data-ttu-id="67211-117">A continuación, se muestra el ejemplo XML para la descripción de las características técnicas de pruebas (testspec.xml):</span><span class="sxs-lookup"><span data-stu-id="67211-117">The following is the sample XML for the description of the test specifications (testspec.xml):</span></span>  
  
    ```xml  
    <TestSpec xmlns="http://WCF/TestSpec" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata"   
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" >  
    <ServiceContract>  
    <!-- Test a contract which has oneway / twoway operations. If you set ExpandAll = true, both types of contracts are tested -->    <IsOneWay ExpandAll="true">true</IsOneWay>  
    <!-- Test a contract with Asynchronous / Synchronous Operations-->  
        <IsAsync>false</IsAsync>   
    <!-- Test a sessionful / sessionless contract-->      
        <IsSession ExpandAll="true">true</IsSession>  
    <!-- If the Service Contract includes a CallBack Contract-->      
        <IsCallBack ExpandAll="true">true</IsCallBack>  
    </ServiceContract>  
    <TestDetails>  
    <!-- Name of the machine that runs the server - required if you want to run the test crossmachine-->  
        <ServerName>ReplaceThisWithTheServerMachineName</ServerName>  
    <!-- Port Number - Optional-->  
        <Port>8000</Port>  
    <!--URI for the callBack address for the CLient. The client will receive the messages from the server on this address in case of a CallBack Contract-->  
        <ClientCallBackAddress/>      
    <!-- Duration (in sec) after the server has started, it times out - optional(default = 300sec) -->  
        <ServerTimeout>300</ServerTimeout>  
    <!-- Duration (in sec) before the Client initializes -optional(default = 60sec) -->  
        <ClientTimeout>60</ClientTimeout>  
    <!-- Number of clients for each service - optional(default = 1) -->  
        <NumberOfClients>1</NumberOfClients>  
    <!-- Number of messages each client sends to the service - optional(default = 1) -->  
        <MessagesPerClient>1</MessagesPerClient>  
    </TestDetails>  
    </TestSpec>  
    ```  
