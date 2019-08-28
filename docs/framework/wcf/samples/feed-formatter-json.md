---
title: Formateador de suministro (JSON)
ms.date: 03/30/2017
ms.assetid: f9c0b295-55e7-48ea-b308-ba51c7d31143
ms.openlocfilehash: 028d2f9abd7e23f18eb90e5ecae8c57da3a871d1
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2019
ms.locfileid: "70039643"
---
# <a name="feed-formatter-json"></a><span data-ttu-id="b499c-102">Formateador de suministro (JSON)</span><span class="sxs-lookup"><span data-stu-id="b499c-102">Feed Formatter (JSON)</span></span>
<span data-ttu-id="b499c-103">Este ejemplo muestra cómo serializar una instancia de una clase <xref:System.ServiceModel.Syndication.SyndicationFeed> en el formato de la Notación de objeto JavaScript (JSON) utilizando un <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter> personalizado y <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span><span class="sxs-lookup"><span data-stu-id="b499c-103">This sample shows how to serialize an instance of a <xref:System.ServiceModel.Syndication.SyndicationFeed> class in JavaScript Object Notation (JSON) format by using a custom <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter> and the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span></span>  
  
## <a name="architecture-of-the-sample"></a><span data-ttu-id="b499c-104">Arquitectura del ejemplo</span><span class="sxs-lookup"><span data-stu-id="b499c-104">Architecture of the Sample</span></span>  
 <span data-ttu-id="b499c-105">El ejemplo implementa una clase denominada `JsonFeedFormatter` que se hereda desde <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter>.</span><span class="sxs-lookup"><span data-stu-id="b499c-105">The sample implements a class named `JsonFeedFormatter` that inherits from <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter>.</span></span> <span data-ttu-id="b499c-106">La clase `JsonFeedFormatter` confía en que <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> lea y escriba los datos en formato de JSON.</span><span class="sxs-lookup"><span data-stu-id="b499c-106">The `JsonFeedFormatter` class relies on the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> to read and write the data in JSON format.</span></span> <span data-ttu-id="b499c-107">Internamente, el formateador utiliza un conjunto personalizado de tipos de contrato de datos denominado `JsonSyndicationFeed` y `JsonSyndicationItem` para controlar el formato de los datos de JSON generado por el serializador.</span><span class="sxs-lookup"><span data-stu-id="b499c-107">Internally, the formatter uses a custom set of data contract types named `JsonSyndicationFeed` and `JsonSyndicationItem` to control the format of the JSON data produced by the serializer.</span></span> <span data-ttu-id="b499c-108">Estos detalles de implementación se ocultan del usuario final, permitiendo realizar las llamadas contra los <xref:System.ServiceModel.Syndication.SyndicationFeed> estándar y las clases <xref:System.ServiceModel.Syndication.SyndicationItem>.</span><span class="sxs-lookup"><span data-stu-id="b499c-108">These implementation details are hidden from the end user, allowing calls to be made against the standard <xref:System.ServiceModel.Syndication.SyndicationFeed> and <xref:System.ServiceModel.Syndication.SyndicationItem> classes.</span></span>  
  
## <a name="writing-json-feeds"></a><span data-ttu-id="b499c-109">Escribir las fuentes de JSON</span><span class="sxs-lookup"><span data-stu-id="b499c-109">Writing JSON feeds</span></span>  
 <span data-ttu-id="b499c-110">Escribir una fuente de JSON se puede lograr utilizando `JsonFeedFormatter` (se implementa en este ejemplo) con <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> como se muestra en el código muestra siguiente.</span><span class="sxs-lookup"><span data-stu-id="b499c-110">Writing a JSON feed can be accomplished by using the `JsonFeedFormatter` (implemented in this sample) with the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> as shown in the following sample code.</span></span>  
  
```  
//Basic feed with sample data  
SyndicationFeed feed = new SyndicationFeed("Custom JSON feed", "A Syndication extensibility sample", null);  
feed.LastUpdatedTime = DateTime.Now;  
feed.Items = from s in new string[] { "hello", "world" }  
select new SyndicationItem()  
{  
    Summary = SyndicationContent.CreatePlaintextContent(s)  
};  
  
//Write the feed out to a MemoryStream in JSON format  
DataContractJsonSerializer writeSerializer = new DataContractJsonSerializer(typeof(JsonFeedFormatter));  
writeSerializer.WriteObject(stream, new JsonFeedFormatter(feed));  
```  
  
## <a name="reading-a-json-feed"></a><span data-ttu-id="b499c-111">Leer una fuente de JSON</span><span class="sxs-lookup"><span data-stu-id="b499c-111">Reading a JSON feed</span></span>  
 <span data-ttu-id="b499c-112">Obtener una <xref:System.ServiceModel.Syndication.SyndicationFeed> de una secuencia de datos dados formateados por JSON se puede lograr con `JsonFeedFormatter` como presentación en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="b499c-112">Obtaining a <xref:System.ServiceModel.Syndication.SyndicationFeed> from a stream of JSON-formatted data can be accomplished with the `JsonFeedFormatter` as show in the following code.</span></span>  
  
 `//Read in the feed using the DataContractJsonSerializer`  
  
 `DataContractJsonSerializer readSerializer = new DataContractJsonSerializer(typeof(JsonFeedFormatter));`  
  
 `JsonFeedFormatter formatter = readSerializer.ReadObject(stream) as JsonFeedFormatter;`  
  
 `SyndicationFeed feedRead = formatter.Feed;`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="b499c-113">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="b499c-113">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="b499c-114">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="b499c-114">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="b499c-115">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="b499c-115">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="b499c-116">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="b499c-116">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="b499c-117">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="b499c-117">The samples may already be installed on your computer.</span></span> <span data-ttu-id="b499c-118">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="b499c-118">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="b499c-119">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) [!INCLUDE[wf1](../../../../includes/wf1-md.md)] y ejemplos.</span><span class="sxs-lookup"><span data-stu-id="b499c-119">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="b499c-120">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="b499c-120">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Syndication\JsonFeeds`  
