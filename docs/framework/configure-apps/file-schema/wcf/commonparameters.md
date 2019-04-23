---
title: <commonParameters>
ms.date: 03/30/2017
ms.assetid: ffc20832-34d6-4622-8174-81924fd53514
ms.openlocfilehash: b9ab4e8ca5a71d54a80d17322b61c83d41af2b40
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59088358"
---
# <a name="commonparameters"></a><span data-ttu-id="12aa4-101">\<commonParameters></span><span class="sxs-lookup"><span data-stu-id="12aa4-101">\<commonParameters></span></span>
<span data-ttu-id="12aa4-102">Representa una colección de parámetros que se utilizan globalmente en varios servicios.</span><span class="sxs-lookup"><span data-stu-id="12aa4-102">Represents a collection of parameters that are used globally across multiple services.</span></span> <span data-ttu-id="12aa4-103">Esta colección incluirá, normalmente, la cadena de conexión de la base de datos que podrían compartir los servicios duraderos.</span><span class="sxs-lookup"><span data-stu-id="12aa4-103">This collection will typically include the database connection string that might be shared by durable services.</span></span>  
  
 <span data-ttu-id="12aa4-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="12aa4-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="12aa4-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="12aa4-105">\<behaviors></span></span>  
<span data-ttu-id="12aa4-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="12aa4-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="12aa4-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="12aa4-107">\<behavior></span></span>  
<span data-ttu-id="12aa4-108">\<workflowRuntime></span><span class="sxs-lookup"><span data-stu-id="12aa4-108">\<workflowRuntime></span></span>  
<span data-ttu-id="12aa4-109">\<commonParameters></span><span class="sxs-lookup"><span data-stu-id="12aa4-109">\<commonParameters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12aa4-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="12aa4-110">Syntax</span></span>  
  
```xml  
<workflowRuntime>
  <commonParameters>
    <add name="String"
         value="String" />
  </commonParameters>
</workflowRuntime>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="12aa4-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="12aa4-111">Attributes and Elements</span></span>  
 <span data-ttu-id="12aa4-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="12aa4-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="12aa4-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="12aa4-113">Attributes</span></span>  
 <span data-ttu-id="12aa4-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="12aa4-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="12aa4-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="12aa4-115">Child Elements</span></span>  
  
|<span data-ttu-id="12aa4-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="12aa4-116">Element</span></span>|<span data-ttu-id="12aa4-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="12aa4-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="12aa4-118">\<add></span><span class="sxs-lookup"><span data-stu-id="12aa4-118">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-commonparameters.md)|<span data-ttu-id="12aa4-119">Agrega un par de nombre y valor de parámetros comunes utilizados por los servicios para la colección.</span><span class="sxs-lookup"><span data-stu-id="12aa4-119">Adds a name-value pair of common parameters used by services to the collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="12aa4-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="12aa4-120">Parent Elements</span></span>  
  
|<span data-ttu-id="12aa4-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="12aa4-121">Element</span></span>|<span data-ttu-id="12aa4-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="12aa4-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="12aa4-123">\<workflowRuntime></span><span class="sxs-lookup"><span data-stu-id="12aa4-123">\<workflowRuntime></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/workflowruntime.md)|<span data-ttu-id="12aa4-124">Especifica la configuración de una instancia de <xref:System.Workflow.Runtime.WorkflowRuntime> para hospedar servicios de Windows Communication Foundation (WCF) basados en flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="12aa4-124">Specifies settings for an instance of <xref:System.Workflow.Runtime.WorkflowRuntime> for hosting workflow-based Windows Communication Foundation (WCF) services.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="12aa4-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="12aa4-125">Remarks</span></span>  
 <span data-ttu-id="12aa4-126">El elemento `<commonParameters>` define cualquier parámetro que se usa globalmente en varios servicios, por ejemplo `ConnectionString` al usar <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>.</span><span class="sxs-lookup"><span data-stu-id="12aa4-126">The `<commonParameters>` element defines any parameters that are used globally across multiple services, for example `ConnectionString` when using the <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="12aa4-127">El servicio de seguimiento de SQL no utiliza de forma consistente el valor `ConnectionString` si se especifica en la sección `<commonParameters>`.</span><span class="sxs-lookup"><span data-stu-id="12aa4-127">SQL Tracking service does not consistently use the `ConnectionString` value if it is specified in the `<commonParameters>` section.</span></span> <span data-ttu-id="12aa4-128">Es posible que se produzca un error en alguna de sus operaciones, como al recuperar la propiedad `StateMachineWorkflowInstance.StateHistory`.</span><span class="sxs-lookup"><span data-stu-id="12aa4-128">Some of its operations such as retrieving the `StateMachineWorkflowInstance.StateHistory` property may fail.</span></span> <span data-ttu-id="12aa4-129">Para solucionar este problema, especifique el atributo `ConnectionString` en la sección de configuración del proveedor de seguimiento, tal y como se indica en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="12aa4-129">To workaround this, specify the `ConnectionString` attribute in the configuration section for tracking provider, as indicated in the following example.</span></span>  
  
 `<add`  
  
 `type="System.Workflow.Runtime.Tracking.SqlTrackingService, System.Workflow.Runtime, Version=3.0.00000.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"`  
  
 `ConnectionString="Data Source=localhost;Initial Catalog=Partner20WFTP;Integrated Security=True;" />`  
  
 <span data-ttu-id="12aa4-130">Puede habilitar los servicios que confirman los lotes de trabajo en los almacenes de persistencia, como <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> y <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>, para reintentar su transacción utilizando el parámetro `EnableRetries` como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="12aa4-130">For services that commit work batches to persistence stores, such as <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> and <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>, you can enable them to retry their transaction by using the `EnableRetries` parameter as shown in the following example:</span></span>  
  
```xml  
<workflowRuntime name="SampleApplication"
                 unloadOnIdle="false">
  <commonParameters>
    <add name="ConnectionString"
         value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;" />
    <add name="EnableRetries"
         value="True" />
  </commonParameters>
  <services>
    <add type="System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService, System.Workflow.Runtime,
               Version=3.0.00000.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"
         enableRetries="False" />
  </services>
</workflowRuntime>
```  
  
 <span data-ttu-id="12aa4-131">Tenga en cuenta que el `EnableRetries` parámetro puede establecerse en un nivel global (como se muestra en el *CommonParameters* sección) o para servicios individuales que admiten `EnableRetries` (como se muestra en el *servicios*sección).</span><span class="sxs-lookup"><span data-stu-id="12aa4-131">Notice that the `EnableRetries` parameter can be set either at a global level (as shown in the *CommonParameters* section) or for individual services that support `EnableRetries` (as shown in the *Services* section).</span></span>  
  
 <span data-ttu-id="12aa4-132">El siguiente código de ejemplo muestra cómo cambiar los parámetros comunes mediante programación.</span><span class="sxs-lookup"><span data-stu-id="12aa4-132">The following sample code shows how to change the common parameters programmatically.</span></span>  
  
```  
Configuration config=WebConfigurationManager.OpenWebConfiguration("/Workflow", "Default Web Site", null, "localhost");  
WorkflowRuntimeSection wfruntime=config.GetSection("WorkflowRuntime") as WorkflowRuntimeSection;  
NameValueConfigurationCollection commonParameters=wfruntime.CommonParameters;  
commonParameters["ConnectionString"].Value="another connection string";  
config.Save();  
```  
  
 <span data-ttu-id="12aa4-133">Para obtener más información sobre el uso de un archivo de configuración para controlar el comportamiento de un <xref:System.Workflow.Runtime.WorkflowRuntime> objeto de una aplicación de host de Windows Workflow Foundation, vea [archivos de configuración de flujo de trabajo](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="12aa4-133">For more information about using a configuration file to control the behavior of a <xref:System.Workflow.Runtime.WorkflowRuntime> object of a Windows Workflow Foundation host application, see [Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="12aa4-134">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="12aa4-134">Example</span></span>  
  
```xml  
<commonParameters>
   <add name="ConnectionString"
        value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;" />
   <add name="EnableRetries"
        value="true" />
</commonParameters>
```  
  
## <a name="see-also"></a><span data-ttu-id="12aa4-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="12aa4-135">See also</span></span>

- <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>
- <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>
- <xref:System.Workflow.Runtime.WorkflowRuntime>
- <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService>
- <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>
- <span data-ttu-id="12aa4-136">[Archivos de configuración de flujo de trabajo](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="12aa4-136">[Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span></span>
- [<span data-ttu-id="12aa4-137">\<add></span><span class="sxs-lookup"><span data-stu-id="12aa4-137">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-commonparameters.md)
