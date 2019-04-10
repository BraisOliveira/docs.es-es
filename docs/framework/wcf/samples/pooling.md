---
title: Agrupación
ms.date: 03/30/2017
ms.assetid: 688dfb30-b79a-4cad-a687-8302f8a9ad6a
ms.openlocfilehash: f4df661ad5d831158da55fe3890805ccc5cd695f
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59307215"
---
# <a name="pooling"></a><span data-ttu-id="15d3c-102">Agrupación</span><span class="sxs-lookup"><span data-stu-id="15d3c-102">Pooling</span></span>
<span data-ttu-id="15d3c-103">Este ejemplo muestra cómo ampliar Windows Communication Foundation (WCF) para admitir la agrupación de objetos.</span><span class="sxs-lookup"><span data-stu-id="15d3c-103">This sample demonstrates how to extend Windows Communication Foundation (WCF) to support object pooling.</span></span> <span data-ttu-id="15d3c-104">El ejemplo muestra cómo crear un atributo que es sintáctica y semánticamente similar a la funcionalidad del atributo `ObjectPoolingAttribute` de Enterprise Services.</span><span class="sxs-lookup"><span data-stu-id="15d3c-104">The sample demonstrates how to create an attribute that is syntactically and semantically similar to the `ObjectPoolingAttribute` attribute functionality of Enterprise Services.</span></span> <span data-ttu-id="15d3c-105">La agrupación de objetos puede aumentar de manera considerable el rendimiento de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="15d3c-105">Object pooling can provide a dramatic boost to an application's performance.</span></span> <span data-ttu-id="15d3c-106">Sin embargo, puede tener el efecto contrario si no se utiliza correctamente.</span><span class="sxs-lookup"><span data-stu-id="15d3c-106">However, it can have the opposite effect if it is not used properly.</span></span> <span data-ttu-id="15d3c-107">La agrupación de objetos ayuda a reducir la sobrecarga que supone volver a crear objetos usados con frecuencia que requieren inicialización extensa.</span><span class="sxs-lookup"><span data-stu-id="15d3c-107">Object pooling helps reduce the overhead of recreating frequently used objects that require extensive initialization.</span></span> <span data-ttu-id="15d3c-108">Sin embargo, si una llamada a un método en un objeto agrupado necesita una cantidad considerable de tiempo para completarse, la agrupación de objetos pone en la cola solicitudes adicionales en cuanto se alcance el tamaño máximo del grupo.</span><span class="sxs-lookup"><span data-stu-id="15d3c-108">However, if a call to a method on a pooled object takes a considerable amount of time to complete, object pooling queues additional requests as soon as the maximum pool size is reached.</span></span> <span data-ttu-id="15d3c-109">Así, puede ser que no se preste servicio a algunas solicitudes de creación de objetos produciendo una excepción de tiempo de espera agotado.</span><span class="sxs-lookup"><span data-stu-id="15d3c-109">Thus it may fail to serve some object creation requests by throwing a timeout exception.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="15d3c-110">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="15d3c-110">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="15d3c-111">El primer paso para crear una extensión de WCF es decidir el punto de extensibilidad para usar.</span><span class="sxs-lookup"><span data-stu-id="15d3c-111">The first step in creating a WCF extension is to decide the extensibility point to use.</span></span>  
  
 <span data-ttu-id="15d3c-112">En WCF el término *distribuidor* hace referencia a un componente de tiempo de ejecución responsable de convertir los mensajes entrantes en invocaciones de método en el servicio del usuario y para convertir los valores devueltos de ese método en un mensaje saliente.</span><span class="sxs-lookup"><span data-stu-id="15d3c-112">In WCF the term *dispatcher* refers to a run-time component responsible for converting incoming messages into method invocations on the user’s service and for converting return values from that method to an outgoing message.</span></span> <span data-ttu-id="15d3c-113">Un servicio WCF crea un distribuidor para cada punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="15d3c-113">A WCF service creates a dispatcher for each endpoint.</span></span> <span data-ttu-id="15d3c-114">Un cliente WCF debe utilizar un distribuidor si el contrato asociado a ese cliente es un contrato dúplex.</span><span class="sxs-lookup"><span data-stu-id="15d3c-114">A WCF client must use a dispatcher if the contract associated with that client is a duplex contract.</span></span>  
  
 <span data-ttu-id="15d3c-115">Los distribuidores de extremos y canales proporcionan extensibilidad para canales y contratos exponiendo varias propiedades que controlan el comportamiento del distribuidor.</span><span class="sxs-lookup"><span data-stu-id="15d3c-115">The channel and endpoint dispatchers offer channel-and contract-wide extensibility by exposing various properties that control the behavior of the dispatcher.</span></span> <span data-ttu-id="15d3c-116">La propiedad <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.DispatchRuntime%2A> también le permite inspeccionar, modificar o personalizar el proceso de distribución.</span><span class="sxs-lookup"><span data-stu-id="15d3c-116">The <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.DispatchRuntime%2A> property also enables you to inspect, modify, or customize the dispatching process.</span></span> <span data-ttu-id="15d3c-117">Este ejemplo se centra en la propiedad <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceProvider%2A> que señala al objeto que proporciona las instancias de la clase de servicio.</span><span class="sxs-lookup"><span data-stu-id="15d3c-117">This sample focuses on the <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceProvider%2A> property that points to the object that provides the instances of the service class.</span></span>  
  
## <a name="the-iinstanceprovider"></a><span data-ttu-id="15d3c-118">IInstanceProvider</span><span class="sxs-lookup"><span data-stu-id="15d3c-118">The IInstanceProvider</span></span>  
 <span data-ttu-id="15d3c-119">En WCF, el distribuidor crea instancias de la clase de servicio con un <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceProvider%2A>, que implementa el <xref:System.ServiceModel.Dispatcher.IInstanceProvider> interfaz.</span><span class="sxs-lookup"><span data-stu-id="15d3c-119">In WCF, the dispatcher creates instances of the service class using a <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceProvider%2A>, which implements the <xref:System.ServiceModel.Dispatcher.IInstanceProvider> interface.</span></span> <span data-ttu-id="15d3c-120">Esta interfaz tiene tres métodos:</span><span class="sxs-lookup"><span data-stu-id="15d3c-120">This interface has three methods:</span></span>  
  
-   <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%28System.ServiceModel.InstanceContext%2CSystem.ServiceModel.Channels.Message%29><span data-ttu-id="15d3c-121">: Cuando un mensaje llega el distribuidor llama el <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%28System.ServiceModel.InstanceContext%2CSystem.ServiceModel.Channels.Message%29> método para crear una instancia de la clase de servicio para procesar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="15d3c-121">: When a message arrives the Dispatcher calls the <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%28System.ServiceModel.InstanceContext%2CSystem.ServiceModel.Channels.Message%29> method to create an instance of the service class to process the message.</span></span> <span data-ttu-id="15d3c-122">La propiedad <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> determina la frecuencia de las llamadas a este método.</span><span class="sxs-lookup"><span data-stu-id="15d3c-122">The frequency of the calls to this method is determined by the <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> property.</span></span> <span data-ttu-id="15d3c-123">Por ejemplo, si la propiedad <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> está establecida en <xref:System.ServiceModel.InstanceContextMode.PerCall>, se crea una nueva instancia de la clase de servicio para procesar cada mensaje que llegue, por lo que se llama a <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%28System.ServiceModel.InstanceContext%2CSystem.ServiceModel.Channels.Message%29> siempre que llegue un mensaje.</span><span class="sxs-lookup"><span data-stu-id="15d3c-123">For example, if the <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> property is set to <xref:System.ServiceModel.InstanceContextMode.PerCall> a new instance of service class is created to process each message that arrives, so <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%28System.ServiceModel.InstanceContext%2CSystem.ServiceModel.Channels.Message%29> is called whenever a message arrives.</span></span>  
  
-   <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%28System.ServiceModel.InstanceContext%29><span data-ttu-id="15d3c-124">: Esto es idéntico al método anterior, salvo que se invoca cuando no hay ningún argumento de mensaje.</span><span class="sxs-lookup"><span data-stu-id="15d3c-124">: This is identical to the previous method, except this is invoked when there is no Message argument.</span></span>  
  
-   <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%28System.ServiceModel.InstanceContext%2CSystem.Object%29><span data-ttu-id="15d3c-125">: Cuando haya transcurrido la duración de una instancia de servicio, el distribuidor llama el <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%28System.ServiceModel.InstanceContext%2CSystem.Object%29> método.</span><span class="sxs-lookup"><span data-stu-id="15d3c-125">: When a service instance's lifetime has elapsed, the Dispatcher calls the <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%28System.ServiceModel.InstanceContext%2CSystem.Object%29> method.</span></span> <span data-ttu-id="15d3c-126">Tal y como ocurre en el método <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%28System.ServiceModel.InstanceContext%2CSystem.ServiceModel.Channels.Message%29>, la frecuencia de las llamadas a este método está determinada por la propiedad <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A>.</span><span class="sxs-lookup"><span data-stu-id="15d3c-126">Just like for the <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%28System.ServiceModel.InstanceContext%2CSystem.ServiceModel.Channels.Message%29> method, the frequency of the calls to this method is determined by the <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> property.</span></span>  
  
## <a name="the-object-pool"></a><span data-ttu-id="15d3c-127">Agrupación de objetos</span><span class="sxs-lookup"><span data-stu-id="15d3c-127">The Object Pool</span></span>  
 <span data-ttu-id="15d3c-128">Una implementación <xref:System.ServiceModel.Dispatcher.IInstanceProvider> personalizada proporciona la semántica de la agrupación de objetos necesaria para un servicio.</span><span class="sxs-lookup"><span data-stu-id="15d3c-128">A custom <xref:System.ServiceModel.Dispatcher.IInstanceProvider> implementation provides the required object pooling semantics for a service.</span></span> <span data-ttu-id="15d3c-129">Por consiguiente, este ejemplo tiene un tipo `ObjectPoolingInstanceProvider` que proporciona implementación personalizada de <xref:System.ServiceModel.Dispatcher.IInstanceProvider> para la agrupación.</span><span class="sxs-lookup"><span data-stu-id="15d3c-129">Therefore, this sample has an `ObjectPoolingInstanceProvider` type that provides custom implementation of <xref:System.ServiceModel.Dispatcher.IInstanceProvider> for pooling.</span></span> <span data-ttu-id="15d3c-130">Cuando `Dispatcher` llama al método <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%28System.ServiceModel.InstanceContext%2CSystem.ServiceModel.Channels.Message%29>, en lugar de crear una nueva instancia, la implementación personalizada busca un objeto existente en un grupo en memoria.</span><span class="sxs-lookup"><span data-stu-id="15d3c-130">When the `Dispatcher` calls the <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%28System.ServiceModel.InstanceContext%2CSystem.ServiceModel.Channels.Message%29> method, instead of creating a new instance, the custom implementation looks for an existing object in an in-memory pool.</span></span> <span data-ttu-id="15d3c-131">Si hay uno disponible, se devuelve.</span><span class="sxs-lookup"><span data-stu-id="15d3c-131">If one is available, it is returned.</span></span> <span data-ttu-id="15d3c-132">De lo contrario, se crea un nuevo objeto.</span><span class="sxs-lookup"><span data-stu-id="15d3c-132">Otherwise, a new object is created.</span></span> <span data-ttu-id="15d3c-133">Se muestra la implementación para `GetInstance` en el código de ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="15d3c-133">The implementation for `GetInstance` is shown in the following sample code.</span></span>  
  
```  
object IInstanceProvider.GetInstance(InstanceContext instanceContext, Message message)  
{  
    object obj = null;  
  
    lock (poolLock)  
    {  
        if (pool.Count > 0)  
        {  
            obj = pool.Pop();  
        }  
        else  
        {  
            obj = CreateNewPoolObject();  
        }  
        activeObjectsCount++;  
    }  
  
    WritePoolMessage(ResourceHelper.GetString("MsgNewObject"));  
  
    idleTimer.Stop();  
  
    return obj;            
}  
```  
  
 <span data-ttu-id="15d3c-134">La implementación `ReleaseInstance` personalizada agrega la instancia liberada de nuevo al grupo y disminuye el valor de `ActiveObjectsCount`.</span><span class="sxs-lookup"><span data-stu-id="15d3c-134">The custom `ReleaseInstance` implementation adds the released instance back to the pool and decrements the `ActiveObjectsCount` value.</span></span> <span data-ttu-id="15d3c-135">`Dispatcher` puede llamar a estos métodos desde subprocesos diferentes, por lo que se necesita tener acceso sincronizado a los miembros del nivel de clase en la clase `ObjectPoolingInstanceProvider`.</span><span class="sxs-lookup"><span data-stu-id="15d3c-135">The `Dispatcher` can call these methods from different threads, and therefore synchronized access to the class level members in the `ObjectPoolingInstanceProvider` class is required.</span></span>  
  
```  
void IInstanceProvider.ReleaseInstance(InstanceContext instanceContext, object instance)  
{  
    lock (poolLock)  
    {  
        pool.Push(instance);  
        activeObjectsCount--;  
  
        WritePoolMessage(  
        ResourceHelper.GetString("MsgObjectPooled"));  
  
        // When the service goes completely idle (no requests   
        // are being processed), the idle timer is started  
        if (activeObjectsCount == 0)  
            idleTimer.Start();                       
    }  
}  
```  
  
 <span data-ttu-id="15d3c-136">El `ReleaseInstance` método proporciona una característica de "inicialización de limpieza".</span><span class="sxs-lookup"><span data-stu-id="15d3c-136">The `ReleaseInstance` method provides a "clean up initialization" feature.</span></span> <span data-ttu-id="15d3c-137">Normalmente el grupo mantiene un número mínimo de objetos para la duración del grupo.</span><span class="sxs-lookup"><span data-stu-id="15d3c-137">Normally the pool maintains a minimum number of objects for the lifetime of the pool.</span></span> <span data-ttu-id="15d3c-138">Sin embargo, puede haber períodos de uso excesivo que requieren la creación de objetos adicionales en el grupo para alcanzar el límite máximo especificado en la configuración.</span><span class="sxs-lookup"><span data-stu-id="15d3c-138">However, there can be periods of excessive usage that require creating additional objects in the pool to reach the maximum limit specified in the configuration.</span></span> <span data-ttu-id="15d3c-139">Finalmente, cuando el grupo se vuelve menos activo, esos objetos adicionales pueden suponer una sobrecarga adicional.</span><span class="sxs-lookup"><span data-stu-id="15d3c-139">Eventually, when the pool becomes less active, those surplus objects can become an extra overhead.</span></span> <span data-ttu-id="15d3c-140">Por consiguiente, cuando `activeObjectsCount` llega a cero, se inicia un temporizador inactivo que activa y realiza un ciclo de limpieza.</span><span class="sxs-lookup"><span data-stu-id="15d3c-140">Therefore, when the `activeObjectsCount` reaches zero, an idle timer is started that triggers and performs a clean-up cycle.</span></span>  
  
## <a name="adding-the-behavior"></a><span data-ttu-id="15d3c-141">Adición del comportamiento</span><span class="sxs-lookup"><span data-stu-id="15d3c-141">Adding the Behavior</span></span>  
 <span data-ttu-id="15d3c-142">Las extensiones de nivel de distribuidor se enlazan utilizando los comportamientos siguientes:</span><span class="sxs-lookup"><span data-stu-id="15d3c-142">Dispatcher-layer extensions are hooked up using the following behaviors:</span></span>  
  
-   <span data-ttu-id="15d3c-143">Comportamientos de servicio.</span><span class="sxs-lookup"><span data-stu-id="15d3c-143">Service Behaviors.</span></span> <span data-ttu-id="15d3c-144">Permiten la personalización de todo el tiempo de ejecución del servicio.</span><span class="sxs-lookup"><span data-stu-id="15d3c-144">These allow for the customization of the entire service runtime.</span></span>  
  
-   <span data-ttu-id="15d3c-145">Comportamientos del extremo.</span><span class="sxs-lookup"><span data-stu-id="15d3c-145">Endpoint Behaviors.</span></span> <span data-ttu-id="15d3c-146">Permiten la personalización de los puntos de conexión del servicio, específicamente un distribuidor de canales y de puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="15d3c-146">These allow for the customization of service endpoints, specifically a Channel and Endpoint Dispatcher.</span></span>  
  
-   <span data-ttu-id="15d3c-147">Comportamientos de contrato.</span><span class="sxs-lookup"><span data-stu-id="15d3c-147">Contract Behaviors.</span></span> <span data-ttu-id="15d3c-148">Éstos permiten la personalización de las clases <xref:System.ServiceModel.Dispatcher.ClientRuntime> y <xref:System.ServiceModel.Dispatcher.DispatchRuntime> en el cliente y el servicio respectivamente.</span><span class="sxs-lookup"><span data-stu-id="15d3c-148">These allow for the customization of both <xref:System.ServiceModel.Dispatcher.ClientRuntime> and <xref:System.ServiceModel.Dispatcher.DispatchRuntime> classes on the client and the service respectively.</span></span>  
  
 <span data-ttu-id="15d3c-149">Se debe crear un comportamiento de servicio para una extensión de agrupación de objetos.</span><span class="sxs-lookup"><span data-stu-id="15d3c-149">For the purpose of an object pooling extension a service behavior must be created.</span></span> <span data-ttu-id="15d3c-150">Los comportamientos de servicio se crean implementando la interfaz <xref:System.ServiceModel.Description.IServiceBehavior>.</span><span class="sxs-lookup"><span data-stu-id="15d3c-150">Service behaviors are created by implementing the <xref:System.ServiceModel.Description.IServiceBehavior> interface.</span></span> <span data-ttu-id="15d3c-151">Hay varias maneras de hacer que el modelo de servicio sea consciente de los comportamientos personalizados:</span><span class="sxs-lookup"><span data-stu-id="15d3c-151">There are several ways to make the service model aware of the custom behaviors:</span></span>  
  
-   <span data-ttu-id="15d3c-152">Utilizar un atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="15d3c-152">Using a custom attribute.</span></span>  
  
-   <span data-ttu-id="15d3c-153">Agregarlo de manera imperativa a la colección de comportamientos de la descripción del servicio.</span><span class="sxs-lookup"><span data-stu-id="15d3c-153">Imperatively adding it to the service description’s behaviors collection.</span></span>  
  
-   <span data-ttu-id="15d3c-154">Extender el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="15d3c-154">Extending the configuration file.</span></span>  
  
 <span data-ttu-id="15d3c-155">Este ejemplo utiliza un atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="15d3c-155">This sample uses a custom attribute.</span></span> <span data-ttu-id="15d3c-156">Cuando se construye <xref:System.ServiceModel.ServiceHost>, examina los atributos utilizados en la definición de tipo del servicio y agrega los comportamientos disponibles a la colección de comportamientos de la descripción del servicio.</span><span class="sxs-lookup"><span data-stu-id="15d3c-156">When the <xref:System.ServiceModel.ServiceHost> is constructed it examines the attributes used in the service’s type definition and adds the available behaviors to the service description’s behaviors collection.</span></span>  
  
 <span data-ttu-id="15d3c-157">La interfaz <xref:System.ServiceModel.Description.IServiceBehavior> tiene tres métodos: <xref:System.ServiceModel.Description.IServiceBehavior.Validate%2A>, <xref:System.ServiceModel.Description.IServiceBehavior.AddBindingParameters%2A> y <xref:System.ServiceModel.Description.IServiceBehavior.ApplyDispatchBehavior%2A>.</span><span class="sxs-lookup"><span data-stu-id="15d3c-157">The interface <xref:System.ServiceModel.Description.IServiceBehavior> has three methods in it -- <xref:System.ServiceModel.Description.IServiceBehavior.Validate%2A>, <xref:System.ServiceModel.Description.IServiceBehavior.AddBindingParameters%2A>, and <xref:System.ServiceModel.Description.IServiceBehavior.ApplyDispatchBehavior%2A>.</span></span> <span data-ttu-id="15d3c-158">Se usa el método <xref:System.ServiceModel.Description.IServiceBehavior.Validate%2A> para garantizar que se pueda aplicar el comportamiento al servicio.</span><span class="sxs-lookup"><span data-stu-id="15d3c-158">The <xref:System.ServiceModel.Description.IServiceBehavior.Validate%2A> method is used to ensure that the behavior can be applied to the service.</span></span> <span data-ttu-id="15d3c-159">En este ejemplo, la implementación asegura que el servicio no se ha configurado con <xref:System.ServiceModel.InstanceContextMode.Single>.</span><span class="sxs-lookup"><span data-stu-id="15d3c-159">In this sample, the implementation ensures that the service is not configured with <xref:System.ServiceModel.InstanceContextMode.Single>.</span></span> <span data-ttu-id="15d3c-160">Se usa el método <xref:System.ServiceModel.Description.IServiceBehavior.AddBindingParameters%2A> para configurar los enlaces del servicio.</span><span class="sxs-lookup"><span data-stu-id="15d3c-160">The <xref:System.ServiceModel.Description.IServiceBehavior.AddBindingParameters%2A> method is used to configure the service's bindings.</span></span> <span data-ttu-id="15d3c-161">No es necesario en este escenario.</span><span class="sxs-lookup"><span data-stu-id="15d3c-161">It is not required in this scenario.</span></span> <span data-ttu-id="15d3c-162"><xref:System.ServiceModel.Description.IServiceBehavior.ApplyDispatchBehavior%2A> se utiliza para configurar los distribuidores del servicio.</span><span class="sxs-lookup"><span data-stu-id="15d3c-162">The <xref:System.ServiceModel.Description.IServiceBehavior.ApplyDispatchBehavior%2A> is used to configure the service's dispatchers.</span></span> <span data-ttu-id="15d3c-163">WCF llama a este método cuando el <xref:System.ServiceModel.ServiceHost> se está inicializando.</span><span class="sxs-lookup"><span data-stu-id="15d3c-163">This method is called by WCF when the <xref:System.ServiceModel.ServiceHost> is being initialized.</span></span> <span data-ttu-id="15d3c-164">Los parámetros siguientes se pasan a este método:</span><span class="sxs-lookup"><span data-stu-id="15d3c-164">The following parameters are passed into this method:</span></span>  
  
-   `Description`<span data-ttu-id="15d3c-165">: Este argumento proporciona la descripción del servicio para el servicio completo.</span><span class="sxs-lookup"><span data-stu-id="15d3c-165">: This argument provides the service description for the entire service.</span></span> <span data-ttu-id="15d3c-166">Esto se puede utilizar para inspeccionar los datos de la descripción sobre los extremos, contratos, enlaces y otros datos del servicio.</span><span class="sxs-lookup"><span data-stu-id="15d3c-166">This can be used to inspect description data about the service’s endpoints, contracts, bindings, and other data.</span></span>  
  
-   `ServiceHostBase`<span data-ttu-id="15d3c-167">: Este argumento proporciona el <xref:System.ServiceModel.ServiceHostBase> que se está inicializando actualmente.</span><span class="sxs-lookup"><span data-stu-id="15d3c-167">: This argument provides the <xref:System.ServiceModel.ServiceHostBase> that is currently being initialized.</span></span>  
  
 <span data-ttu-id="15d3c-168">En la implementación personalizada <xref:System.ServiceModel.Description.IServiceBehavior>, se crea una nueva instancia de `ObjectPoolingInstanceProvider` y se asigna a la propiedad <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceProvider%2A> en cada <xref:System.ServiceModel.Dispatcher.DispatchRuntime> en ServiceHostBase.</span><span class="sxs-lookup"><span data-stu-id="15d3c-168">In the custom <xref:System.ServiceModel.Description.IServiceBehavior> implementation a new instance of `ObjectPoolingInstanceProvider` is instantiated and assigned to the <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceProvider%2A> property in each <xref:System.ServiceModel.Dispatcher.DispatchRuntime> in the ServiceHostBase.</span></span>  
  
```  
void IServiceBehavior.ApplyDispatchBehavior(ServiceDescription description, ServiceHostBase serviceHostBase)  
{  
    // Create an instance of the ObjectPoolInstanceProvider.  
    ObjectPoolingInstanceProvider instanceProvider = new  
           ObjectPoolingInstanceProvider(description.ServiceType,   
                                                    minPoolSize);  
  
    // Forward the call if we created a ServiceThrottlingBehavior.  
    if (this.throttlingBehavior != null)  
    {  
        ((IServiceBehavior)this.throttlingBehavior).ApplyDispatchBehavior(description, serviceHostBase);  
    }  
  
    // In case there was already a ServiceThrottlingBehavior   
    // (this.throttlingBehavior==null), it should have initialized   
    // a single ServiceThrottle on all ChannelDispatchers.    
    // As we loop through the ChannelDispatchers, we verify that   
    // and modify the ServiceThrottle to guard MaxPoolSize.  
    ServiceThrottle throttle = null;  
  
    foreach (ChannelDispatcherBase cdb in   
            serviceHostBase.ChannelDispatchers)  
    {  
        ChannelDispatcher cd = cdb as ChannelDispatcher;  
        if (cd != null)  
        {  
            // Make sure there is exactly one throttle used by all   
            // endpoints. If there were others, we could not enforce   
            // MaxPoolSize.  
            if ((this.throttlingBehavior == null) &&   
                        (this.maxPoolSize != Int32.MaxValue))  
            {  
                if (throttle == null)  
                {  
                    throttle = cd.ServiceThrottle;  
                }  
                if (cd.ServiceThrottle == null)  
                {  
                    throw new   
InvalidOperationException(ResourceHelper.GetString("ExNullThrottle"));  
                }  
                if (throttle != cd.ServiceThrottle)  
                {  
                    throw new InvalidOperationException(ResourceHelper.GetString("ExDifferentThrottle"));  
                }  
             }  
  
             foreach (EndpointDispatcher ed in cd.Endpoints)  
             {  
                 // Assign it to DispatchBehavior in each endpoint.  
                 ed.DispatchRuntime.InstanceProvider =   
                                      instanceProvider;  
             }  
         }  
     }  
  
     // Set the MaxConcurrentInstances to limit the number of items   
     // that will ever be requested from the pool.  
     if ((throttle != null) && (throttle.MaxConcurrentInstances >   
                                      this.maxPoolSize))  
     {  
         throttle.MaxConcurrentInstances = this.maxPoolSize;  
     }  
}  
```  
  
 <span data-ttu-id="15d3c-169">Además de una implementación <xref:System.ServiceModel.Description.IServiceBehavior>, la clase <xref:System.EnterpriseServices.ObjectPoolingAttribute> cuenta con varios miembros para personalizar el grupo de objetos mediante los argumentos de atributo.</span><span class="sxs-lookup"><span data-stu-id="15d3c-169">In addition to an <xref:System.ServiceModel.Description.IServiceBehavior> implementation the <xref:System.EnterpriseServices.ObjectPoolingAttribute> class has several members to customize the object pool using the attribute arguments.</span></span> <span data-ttu-id="15d3c-170">Estos miembros incluyen <xref:System.EnterpriseServices.ObjectPoolingAttribute.MaxPoolSize%2A>, <xref:System.EnterpriseServices.ObjectPoolingAttribute.MinPoolSize%2A> y <xref:System.EnterpriseServices.ObjectPoolingAttribute.CreationTimeout%2A>, para que coincida con el conjunto de características de objetos proporcionado por .NET Enterprise Services.</span><span class="sxs-lookup"><span data-stu-id="15d3c-170">These members include <xref:System.EnterpriseServices.ObjectPoolingAttribute.MaxPoolSize%2A>, <xref:System.EnterpriseServices.ObjectPoolingAttribute.MinPoolSize%2A>, and <xref:System.EnterpriseServices.ObjectPoolingAttribute.CreationTimeout%2A>, to match the object pooling feature set provided by .NET Enterprise Services.</span></span>  
  
 <span data-ttu-id="15d3c-171">El comportamiento de agrupación de objetos ahora se pueden agregar a un servicio WCF anotando la implementación del servicio con el recién creado custom `ObjectPooling` atributo.</span><span class="sxs-lookup"><span data-stu-id="15d3c-171">The object pooling behavior can now be added to a WCF service by annotating the service implementation with the newly created custom `ObjectPooling` attribute.</span></span>  
  
```  
[ObjectPooling(MaxPoolSize=1024, MinPoolSize=10, CreationTimeout=30000)]      
public class PoolService : IPoolService  
{  
  // …  
}  
```  
  
## <a name="running-the-sample"></a><span data-ttu-id="15d3c-172">Ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="15d3c-172">Running the Sample</span></span>  
 <span data-ttu-id="15d3c-173">El ejemplo muestra la mejora en el rendimiento que puede obtenerse usando la agrupación de objetos en algunos escenarios.</span><span class="sxs-lookup"><span data-stu-id="15d3c-173">The sample demonstrates the performance benefits that can be gained by using object pooling in certain scenarios.</span></span>  
  
 <span data-ttu-id="15d3c-174">La aplicación de servicio implementa dos servicios: `WorkService` y `ObjectPooledWorkService`.</span><span class="sxs-lookup"><span data-stu-id="15d3c-174">The service application implements two services -- `WorkService` and `ObjectPooledWorkService`.</span></span> <span data-ttu-id="15d3c-175">Ambos servicios comparten la misma implementación: requieren una inicialización cara y después exponen un método `DoWork()` que es relativamente barato.</span><span class="sxs-lookup"><span data-stu-id="15d3c-175">Both services share the same implementation -- they both require expensive initialization and then expose a `DoWork()` method that is relatively cheap.</span></span> <span data-ttu-id="15d3c-176">La única diferencia es que `ObjectPooledWorkService` tiene la agrupación de objetos configurada:</span><span class="sxs-lookup"><span data-stu-id="15d3c-176">The only difference is that the `ObjectPooledWorkService` has object pooling configured:</span></span>  
  
```  
[ObjectPooling(MinPoolSize = 0, MaxPoolSize = 5)]  
public class ObjectPooledWorkService : IDoWork  
{  
    public ObjectPooledWorkService()  
    {  
        Thread.Sleep(5000);  
        ColorConsole.WriteLine(ConsoleColor.Blue, "ObjectPooledWorkService instance created.");  
    }  
  
    public void DoWork()  
    {  
        ColorConsole.WriteLine(ConsoleColor.Blue, "ObjectPooledWorkService.GetData() completed.");  
    }          
}  
```  
  
 <span data-ttu-id="15d3c-177">Al ejecutar el cliente, sincroniza llamando a `WorkService` cinco veces.</span><span class="sxs-lookup"><span data-stu-id="15d3c-177">When you run the client, it times calling the `WorkService` 5 times.</span></span> <span data-ttu-id="15d3c-178">Después, sincroniza llamando a `ObjectPooledWorkService` cinco veces.</span><span class="sxs-lookup"><span data-stu-id="15d3c-178">It then times calling the `ObjectPooledWorkService` 5 times.</span></span> <span data-ttu-id="15d3c-179">A continuación, se muestra la diferencia en cuanto a tiempo:</span><span class="sxs-lookup"><span data-stu-id="15d3c-179">The difference in time is then displayed:</span></span>  
  
```  
Press <ENTER> to start the client.  
  
Calling WorkService:  
1 - DoWork() Done  
2 - DoWork() Done  
3 - DoWork() Done  
4 - DoWork() Done  
5 - DoWork() Done  
Calling WorkService took: 26722 ms.  
Calling ObjectPooledWorkService:  
1 - DoWork() Done  
2 - DoWork() Done  
3 - DoWork() Done  
4 - DoWork() Done  
5 - DoWork() Done  
Calling ObjectPooledWorkService took: 5323 ms.  
Press <ENTER> to exit.  
```  
  
> [!NOTE]
>  <span data-ttu-id="15d3c-180">La primera vez que el cliente se ejecuta, parece que ambos servicios tardan la misma cantidad de tiempo.</span><span class="sxs-lookup"><span data-stu-id="15d3c-180">The first time the client is run both services appear to take about the same amount of time.</span></span> <span data-ttu-id="15d3c-181">Si vuelve a ejecutar el ejemplo, puede ver que `ObjectPooledWorkService` devuelve mucho más rápido porque ya existe una instancia de ese objeto en el grupo.</span><span class="sxs-lookup"><span data-stu-id="15d3c-181">If you re-run the sample, you can see that the `ObjectPooledWorkService` returns much quicker because an instance of that object already exists in the pool.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="15d3c-182">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="15d3c-182">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="15d3c-183">Asegúrese de que ha realizado la [procedimiento de instalación de un solo uso para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="15d3c-183">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="15d3c-184">Para compilar la solución, siga las instrucciones de [compilar los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="15d3c-184">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="15d3c-185">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecutando los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="15d3c-185">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="15d3c-186">Si usa Svcutil.exe para regenerar la configuración de este ejemplo, asegúrese de que modifica el nombre del extremo en la configuración del cliente para que coincida con el código de cliente.</span><span class="sxs-lookup"><span data-stu-id="15d3c-186">If you use Svcutil.exe to regenerate the configuration for this sample, be sure to modify the endpoint name in the client configuration to match the client code.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="15d3c-187">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="15d3c-187">The samples may already be installed on your machine.</span></span> <span data-ttu-id="15d3c-188">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="15d3c-188">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="15d3c-189">Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="15d3c-189">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="15d3c-190">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="15d3c-190">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Instancing\Pooling`  
