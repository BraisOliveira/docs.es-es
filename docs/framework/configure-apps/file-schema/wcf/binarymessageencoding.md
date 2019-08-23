---
title: <binaryMessageEncoding>
ms.date: 03/30/2017
ms.assetid: e4ae3cd4-6b67-4ce1-af4b-9400e0a38dba
ms.openlocfilehash: 9b6b74200c807e6523ed3f7250945040bd12658d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919793"
---
# <a name="binarymessageencoding"></a><span data-ttu-id="212ed-101">\<binaryMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="212ed-101">\<binaryMessageEncoding></span></span>
<span data-ttu-id="212ed-102">Define un codificador del mensaje binario que codifica los mensajes de la Windows Communication Foundation (WCF) en binario en la conexión.</span><span class="sxs-lookup"><span data-stu-id="212ed-102">Defines a binary message encoder that encodes Windows Communication Foundation (WCF) messages in binary on the wire.</span></span>  
  
 <span data-ttu-id="212ed-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="212ed-103">\<system.serviceModel></span></span>  
<span data-ttu-id="212ed-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="212ed-104">\<bindings></span></span>  
<span data-ttu-id="212ed-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="212ed-105">\<customBinding></span></span>  
<span data-ttu-id="212ed-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="212ed-106">\<binding></span></span>  
<span data-ttu-id="212ed-107">\<binaryMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="212ed-107">\<binaryMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="212ed-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="212ed-108">Syntax</span></span>  
  
```xml  
<binaryMessageEncoding maxReadPoolSize="Integer"
                       maxSessionSize="Integer"
                       maxWritePoolSize="Integer"
                       messageVersion="Soap11Addressing10/Soap12Addressing10" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="212ed-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="212ed-109">Attributes and Elements</span></span>  
 <span data-ttu-id="212ed-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="212ed-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="212ed-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="212ed-111">Attributes</span></span>  
  
|<span data-ttu-id="212ed-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="212ed-112">Attribute</span></span>|<span data-ttu-id="212ed-113">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="212ed-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="212ed-114">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="212ed-114">maxReadPoolSize</span></span>|<span data-ttu-id="212ed-115">Entero que define cuántos mensajes pueden leerse simultáneamente sin asignar nuevos lectores.</span><span class="sxs-lookup"><span data-stu-id="212ed-115">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="212ed-116">Los tamaños de grupo más grandes hacen que el sistema sea más tolerante a picos de actividad a costa de un espacio de trabajo mayor.</span><span class="sxs-lookup"><span data-stu-id="212ed-116">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="212ed-117">El valor predeterminado es 64.</span><span class="sxs-lookup"><span data-stu-id="212ed-117">The default is 64.</span></span>|  
|<span data-ttu-id="212ed-118">maxSessionSize</span><span class="sxs-lookup"><span data-stu-id="212ed-118">maxSessionSize</span></span>|<span data-ttu-id="212ed-119">Un entero positivo que establece el tamaño, en bytes, del búfer utilizado para codificar.</span><span class="sxs-lookup"><span data-stu-id="212ed-119">A positive integer that sets the size, in bytes, of the buffer used for encoding.</span></span> <span data-ttu-id="212ed-120">Un búfer mayor aumenta la velocidad de codificación a costa del tamaño del espacio de trabajo.</span><span class="sxs-lookup"><span data-stu-id="212ed-120">A larger buffer increases encoding speed at the expense of the size of the working set.</span></span> <span data-ttu-id="212ed-121">El valor predeterminado es 2048.</span><span class="sxs-lookup"><span data-stu-id="212ed-121">The default is 2048.</span></span>|  
|<span data-ttu-id="212ed-122">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="212ed-122">maxWritePoolSize</span></span>|<span data-ttu-id="212ed-123">Entero que define cuántos mensajes pueden enviarse simultáneamente sin asignar nuevos escritores.</span><span class="sxs-lookup"><span data-stu-id="212ed-123">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="212ed-124">Los tamaños de grupo más grandes hacen que el sistema sea más tolerante a picos de actividad a costa de un espacio de trabajo mayor.</span><span class="sxs-lookup"><span data-stu-id="212ed-124">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="212ed-125">El valor predeterminado es 16.</span><span class="sxs-lookup"><span data-stu-id="212ed-125">The default is 16.</span></span>|  
|<span data-ttu-id="212ed-126">messageVersion</span><span class="sxs-lookup"><span data-stu-id="212ed-126">messageVersion</span></span>|<span data-ttu-id="212ed-127">Especifica las versiones del mensaje SOAP y de WS-Addressing que se usan o se esperan.</span><span class="sxs-lookup"><span data-stu-id="212ed-127">Specifies the SOAP message and WS-Addressing versions that are used or expected.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="212ed-128">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="212ed-128">Child Elements</span></span>  
  
|<span data-ttu-id="212ed-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="212ed-129">Element</span></span>|<span data-ttu-id="212ed-130">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="212ed-130">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="212ed-131">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="212ed-131">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="212ed-132">Define las restricciones en la complejidad de los mensajes SOAP que pueden ser procesados por los puntos de conexión configurados con este enlace.</span><span class="sxs-lookup"><span data-stu-id="212ed-132">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="212ed-133">Este elemento es del tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span><span class="sxs-lookup"><span data-stu-id="212ed-133">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="212ed-134">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="212ed-134">Parent Elements</span></span>  
  
|<span data-ttu-id="212ed-135">Elemento</span><span class="sxs-lookup"><span data-stu-id="212ed-135">Element</span></span>|<span data-ttu-id="212ed-136">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="212ed-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="212ed-137">\<binding></span><span class="sxs-lookup"><span data-stu-id="212ed-137">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="212ed-138">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="212ed-138">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="212ed-139">Comentarios</span><span class="sxs-lookup"><span data-stu-id="212ed-139">Remarks</span></span>  
 <span data-ttu-id="212ed-140">La codificación es el proceso de transformación de un mensaje en una secuencia de bytes.</span><span class="sxs-lookup"><span data-stu-id="212ed-140">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="212ed-141">La descodificación es el proceso inverso.</span><span class="sxs-lookup"><span data-stu-id="212ed-141">Decoding is the reverse process.</span></span> <span data-ttu-id="212ed-142">Windows Communication Foundation (WCF) incluye tres tipos de codificación para los mensajes SOAP: Mecanismo de optimización de transmisión de mensajes, binarios y de texto (MTOM).</span><span class="sxs-lookup"><span data-stu-id="212ed-142">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="212ed-143">El elemento `binaryMessageEncoding` especifica el formato binario de .NET para XML y tiene las opciones para especificar la codificación de caracteres, así como la versión de SOAP y WS-Addressing que se va a utilizar.</span><span class="sxs-lookup"><span data-stu-id="212ed-143">The `binaryMessageEncoding` element specifies the .NET Binary Format for XML and has options to specify the character encoding and the SOAP and WS-Addressing version to be used.</span></span> <span data-ttu-id="212ed-144">El codificador del mensaje binario codifica los mensajes de Windows Communication Foundation (WCF) en binario en la conexión.</span><span class="sxs-lookup"><span data-stu-id="212ed-144">The binary message encoder encodes Windows Communication Foundation (WCF) messages in binary on the wire.</span></span> <span data-ttu-id="212ed-145">Aunque esta codificación realiza transmisiones muy rápidas de mensajes, la interoperabilidad basada en estándares WS-\* se pierde.</span><span class="sxs-lookup"><span data-stu-id="212ed-145">While this encoding results in very fast transmission of messages, interoperability based on the WS-\* standards is lost.</span></span>  
  
## <a name="example"></a><span data-ttu-id="212ed-146">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="212ed-146">Example</span></span>  
  
```xml  
<binaryMessageEncoding maxReadPoolSize="211"
                       maxWritePoolSize="2132"
                       maxSessionSize="3141" />
```  
  
## <a name="see-also"></a><span data-ttu-id="212ed-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="212ed-147">See also</span></span>

- <xref:System.ServiceModel.Configuration.BinaryMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>
- [<span data-ttu-id="212ed-148">Codificación de mensajes</span><span class="sxs-lookup"><span data-stu-id="212ed-148">Message Encoding</span></span>](message-encoding.md)
- [<span data-ttu-id="212ed-149">Elección de un codificador de mensajes</span><span class="sxs-lookup"><span data-stu-id="212ed-149">Choosing a Message Encoder</span></span>](../../../wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="212ed-150">Enlaces</span><span class="sxs-lookup"><span data-stu-id="212ed-150">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="212ed-151">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="212ed-151">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="212ed-152">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="212ed-152">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="212ed-153">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="212ed-153">\<customBinding></span></span>](custombinding.md)
