---
title: <binaryMessageEncoding>
ms.date: 03/30/2017
ms.assetid: e4ae3cd4-6b67-4ce1-af4b-9400e0a38dba
ms.openlocfilehash: afe0479d9cbf6d754b309c18e23d3a479870177c
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2019
ms.locfileid: "73739073"
---
# <a name="binarymessageencoding"></a><span data-ttu-id="e7448-101">\<binaryMessageEncoding ></span><span class="sxs-lookup"><span data-stu-id="e7448-101">\<binaryMessageEncoding></span></span>
<span data-ttu-id="e7448-102">Define un codificador del mensaje binario que codifica los mensajes de la Windows Communication Foundation (WCF) en binario en la conexión.</span><span class="sxs-lookup"><span data-stu-id="e7448-102">Defines a binary message encoder that encodes Windows Communication Foundation (WCF) messages in binary on the wire.</span></span>  
  
<span data-ttu-id="e7448-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e7448-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e7448-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="e7448-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="e7448-105">&nbsp;&nbsp;&nbsp;&nbsp;\<[**enlaces**](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="e7448-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="e7448-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**customBinding**](custombinding.md) ></span><span class="sxs-lookup"><span data-stu-id="e7448-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="e7448-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**enlace** ></span><span class="sxs-lookup"><span data-stu-id="e7448-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="e7448-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<binaryMessageEncoding >**</span><span class="sxs-lookup"><span data-stu-id="e7448-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binaryMessageEncoding>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7448-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e7448-109">Syntax</span></span>  
  
```xml  
<binaryMessageEncoding maxReadPoolSize="Integer"
                       maxSessionSize="Integer"
                       maxWritePoolSize="Integer"
                       messageVersion="Soap11Addressing10/Soap12Addressing10" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e7448-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e7448-110">Attributes and Elements</span></span>  
 <span data-ttu-id="e7448-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e7448-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e7448-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="e7448-112">Attributes</span></span>  
  
|<span data-ttu-id="e7448-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="e7448-113">Attribute</span></span>|<span data-ttu-id="e7448-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="e7448-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e7448-115">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="e7448-115">maxReadPoolSize</span></span>|<span data-ttu-id="e7448-116">Entero que define cuántos mensajes pueden leerse simultáneamente sin asignar nuevos lectores.</span><span class="sxs-lookup"><span data-stu-id="e7448-116">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="e7448-117">Los tamaños de grupo más grandes hacen que el sistema sea más tolerante a picos de actividad a costa de un espacio de trabajo mayor.</span><span class="sxs-lookup"><span data-stu-id="e7448-117">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="e7448-118">El valor predeterminado es 64.</span><span class="sxs-lookup"><span data-stu-id="e7448-118">The default is 64.</span></span>|  
|<span data-ttu-id="e7448-119">maxSessionSize</span><span class="sxs-lookup"><span data-stu-id="e7448-119">maxSessionSize</span></span>|<span data-ttu-id="e7448-120">Un entero positivo que establece el tamaño, en bytes, del búfer utilizado para codificar.</span><span class="sxs-lookup"><span data-stu-id="e7448-120">A positive integer that sets the size, in bytes, of the buffer used for encoding.</span></span> <span data-ttu-id="e7448-121">Un búfer mayor aumenta la velocidad de codificación a costa del tamaño del espacio de trabajo.</span><span class="sxs-lookup"><span data-stu-id="e7448-121">A larger buffer increases encoding speed at the expense of the size of the working set.</span></span> <span data-ttu-id="e7448-122">El valor predeterminado es 2048.</span><span class="sxs-lookup"><span data-stu-id="e7448-122">The default is 2048.</span></span>|  
|<span data-ttu-id="e7448-123">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="e7448-123">maxWritePoolSize</span></span>|<span data-ttu-id="e7448-124">Entero que define cuántos mensajes pueden enviarse simultáneamente sin asignar nuevos escritores.</span><span class="sxs-lookup"><span data-stu-id="e7448-124">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="e7448-125">Los tamaños de grupo más grandes hacen que el sistema sea más tolerante a picos de actividad a costa de un espacio de trabajo mayor.</span><span class="sxs-lookup"><span data-stu-id="e7448-125">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="e7448-126">El valor predeterminado es 16.</span><span class="sxs-lookup"><span data-stu-id="e7448-126">The default is 16.</span></span>|  
|<span data-ttu-id="e7448-127">messageVersion</span><span class="sxs-lookup"><span data-stu-id="e7448-127">messageVersion</span></span>|<span data-ttu-id="e7448-128">Especifica las versiones del mensaje SOAP y de WS-Addressing que se usan o se esperan.</span><span class="sxs-lookup"><span data-stu-id="e7448-128">Specifies the SOAP message and WS-Addressing versions that are used or expected.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e7448-129">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e7448-129">Child Elements</span></span>  
  
|<span data-ttu-id="e7448-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="e7448-130">Element</span></span>|<span data-ttu-id="e7448-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="e7448-131">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e7448-132">[\<readerQuotas >](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="e7448-132">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="e7448-133">Define las restricciones en la complejidad de los mensajes SOAP que pueden ser procesados por los puntos de conexión configurados con este enlace.</span><span class="sxs-lookup"><span data-stu-id="e7448-133">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="e7448-134">Este elemento es del tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="e7448-134">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e7448-135">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e7448-135">Parent Elements</span></span>  
  
|<span data-ttu-id="e7448-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="e7448-136">Element</span></span>|<span data-ttu-id="e7448-137">Descripción</span><span class="sxs-lookup"><span data-stu-id="e7448-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e7448-138">\<> de enlace</span><span class="sxs-lookup"><span data-stu-id="e7448-138">\<binding></span></span>](bindings.md)|<span data-ttu-id="e7448-139">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="e7448-139">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e7448-140">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e7448-140">Remarks</span></span>  
 <span data-ttu-id="e7448-141">La codificación es el proceso de transformación de un mensaje en una secuencia de bytes.</span><span class="sxs-lookup"><span data-stu-id="e7448-141">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="e7448-142">La descodificación es el proceso inverso.</span><span class="sxs-lookup"><span data-stu-id="e7448-142">Decoding is the reverse process.</span></span> <span data-ttu-id="e7448-143">Windows Communication Foundation (WCF) incluye tres tipos de codificación para los mensajes SOAP: Texto, Binario y Mecanismo de optimización de transmisión del mensaje (MTOM).</span><span class="sxs-lookup"><span data-stu-id="e7448-143">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="e7448-144">El elemento `binaryMessageEncoding` especifica el formato binario de .NET para XML y tiene las opciones para especificar la codificación de caracteres, así como la versión de SOAP y WS-Addressing que se va a utilizar.</span><span class="sxs-lookup"><span data-stu-id="e7448-144">The `binaryMessageEncoding` element specifies the .NET Binary Format for XML and has options to specify the character encoding and the SOAP and WS-Addressing version to be used.</span></span> <span data-ttu-id="e7448-145">El codificador del mensaje binario codifica los mensajes de Windows Communication Foundation (WCF) en binario en la conexión.</span><span class="sxs-lookup"><span data-stu-id="e7448-145">The binary message encoder encodes Windows Communication Foundation (WCF) messages in binary on the wire.</span></span> <span data-ttu-id="e7448-146">Aunque esta codificación realiza transmisiones muy rápidas de mensajes, la interoperabilidad basada en estándares WS-\* se pierde.</span><span class="sxs-lookup"><span data-stu-id="e7448-146">While this encoding results in very fast transmission of messages, interoperability based on the WS-\* standards is lost.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e7448-147">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e7448-147">Example</span></span>  
  
```xml  
<binaryMessageEncoding maxReadPoolSize="211"
                       maxWritePoolSize="2132"
                       maxSessionSize="3141" />
```  
  
## <a name="see-also"></a><span data-ttu-id="e7448-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="e7448-148">See also</span></span>

- <xref:System.ServiceModel.Configuration.BinaryMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>
- [<span data-ttu-id="e7448-149">Codificación de mensajes</span><span class="sxs-lookup"><span data-stu-id="e7448-149">Message Encoding</span></span>](message-encoding.md)
- [<span data-ttu-id="e7448-150">Elección de un codificador de mensajes</span><span class="sxs-lookup"><span data-stu-id="e7448-150">Choosing a Message Encoder</span></span>](../../../wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="e7448-151">Enlaces</span><span class="sxs-lookup"><span data-stu-id="e7448-151">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="e7448-152">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="e7448-152">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="e7448-153">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="e7448-153">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="e7448-154">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="e7448-154">\<customBinding></span></span>](custombinding.md)
