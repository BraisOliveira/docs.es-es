---
title: Serializar flujos de trabajo y actividades a y de XAML
ms.date: 03/30/2017
ms.assetid: 37685b32-24e3-4d72-88d8-45d5fcc49ec2
ms.openlocfilehash: 70ee2e8e0c457e9db2853935ef95b86c7f903fc3
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57715846"
---
# <a name="serializing-workflows-and-activities-to-and-from-xaml"></a><span data-ttu-id="ab1c1-102">Serializar flujos de trabajo y actividades a y de XAML</span><span class="sxs-lookup"><span data-stu-id="ab1c1-102">Serializing Workflows and Activities to and from XAML</span></span>
<span data-ttu-id="ab1c1-103">Además de compilarse en tipos incluidos en ensamblados, las definiciones de flujo de trabajo también se pueden serializar en XAML.</span><span class="sxs-lookup"><span data-stu-id="ab1c1-103">In addition to being compiled into types that are contained in assemblies, workflow definitions can also be serialized to XAML.</span></span> <span data-ttu-id="ab1c1-104">Estas definiciones serializadas se pueden recargar para edición o inspección, pasar a un sistema de compilación para compilación, o bien cargar e invocar.</span><span class="sxs-lookup"><span data-stu-id="ab1c1-104">These serialized definitions can be reloaded for editing or inspection, passed to a build system for compilation, or loaded and invoked.</span></span> <span data-ttu-id="ab1c1-105">En este tema se proporciona información general sobre la serialización de definiciones de flujo de trabajo y el trabajo con definiciones de flujo de trabajo de XAML.</span><span class="sxs-lookup"><span data-stu-id="ab1c1-105">This topic provides an overview of serializing workflow definitions and working with XAML workflow definitions.</span></span>  
  
## <a name="working-with-xaml-workflow-definitions"></a><span data-ttu-id="ab1c1-106">Trabajar con definiciones de flujo de trabajo de XAML</span><span class="sxs-lookup"><span data-stu-id="ab1c1-106">Working with XAML Workflow Definitions</span></span>  
 <span data-ttu-id="ab1c1-107">Para crear una definición de flujo de trabajo para la serialización, se utiliza la clase <xref:System.Activities.ActivityBuilder>.</span><span class="sxs-lookup"><span data-stu-id="ab1c1-107">To create a workflow definition for serialization, the <xref:System.Activities.ActivityBuilder> class is used.</span></span> <span data-ttu-id="ab1c1-108">La creación de una clase <xref:System.Activities.ActivityBuilder> es muy similar a la creación de una clase <xref:System.Activities.DynamicActivity>.</span><span class="sxs-lookup"><span data-stu-id="ab1c1-108">Creating an <xref:System.Activities.ActivityBuilder> is very similar to creating a <xref:System.Activities.DynamicActivity>.</span></span> <span data-ttu-id="ab1c1-109">Se especifican los argumento deseados y se configuran las actividades que constituyen el comportamiento.</span><span class="sxs-lookup"><span data-stu-id="ab1c1-109">Any desired arguments are specified, and the activities that constitute the behavior are configured.</span></span> <span data-ttu-id="ab1c1-110">En el siguiente ejemplo, se crea una actividad `Add` que toma dos argumentos de entrada, los suma y devuelve el resultado.</span><span class="sxs-lookup"><span data-stu-id="ab1c1-110">In the following example, an `Add` activity is created that takes two input arguments, adds them together, and returns the result.</span></span> <span data-ttu-id="ab1c1-111">Dado que esta actividad devuelve un resultado, se utiliza la clase <xref:System.Activities.ActivityBuilder%601> la genérica.</span><span class="sxs-lookup"><span data-stu-id="ab1c1-111">Because this activity returns a result, the generic <xref:System.Activities.ActivityBuilder%601> class is used.</span></span>  
  
 [!code-csharp[CFX_WorkflowApplicationExample#41](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#41)]  
  
 <span data-ttu-id="ab1c1-112">Cada una de las instancias de <xref:System.Activities.DynamicActivityProperty> representa uno de los argumentos de entrada al flujo de trabajo y la propiedad <xref:System.Activities.ActivityBuilder.Implementation%2A> contiene las actividades que constituyen la lógica del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ab1c1-112">Each of the <xref:System.Activities.DynamicActivityProperty> instances represents one of the input arguments to the workflow, and the <xref:System.Activities.ActivityBuilder.Implementation%2A> contains the activities that make up the logic of the workflow.</span></span> <span data-ttu-id="ab1c1-113">Observe que las expresiones de valor de r de este ejemplo son expresiones de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="ab1c1-113">Note that the r-value expressions in this example are Visual Basic expressions.</span></span> <span data-ttu-id="ab1c1-114">Las expresiones lambda no son serializables en XAML a menos que se use <xref:System.Activities.Expressions.ExpressionServices.Convert%2A>.</span><span class="sxs-lookup"><span data-stu-id="ab1c1-114">Lambda expressions are not serializable to XAML unless <xref:System.Activities.Expressions.ExpressionServices.Convert%2A> is used.</span></span> <span data-ttu-id="ab1c1-115">Si los flujos de trabajo serializados están pensados para abrirse o editarse en el diseñador de flujo de trabajo, se deben usar expresiones de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="ab1c1-115">If the serialized workflows are intended to be opened or edited in the workflow designer then Visual Basic expressions should be used.</span></span> <span data-ttu-id="ab1c1-116">Para obtener más información, consulte [creación de flujos de trabajo, actividades y expresiones mediante código imperativo](authoring-workflows-activities-and-expressions-using-imperative-code.md).</span><span class="sxs-lookup"><span data-stu-id="ab1c1-116">For more information, see [Authoring Workflows, Activities, and Expressions Using Imperative Code](authoring-workflows-activities-and-expressions-using-imperative-code.md).</span></span>  
  
 <span data-ttu-id="ab1c1-117">Para serializar la definición de flujo de trabajo representada por la instancia de <xref:System.Activities.ActivityBuilder> en XAML, use <xref:System.Activities.XamlIntegration.ActivityXamlServices> para crear <xref:System.Xaml.XamlWriter> y use después <xref:System.Xaml.XamlServices> para serializar la definición de flujo de trabajo mediante <xref:System.Xaml.XamlWriter>.</span><span class="sxs-lookup"><span data-stu-id="ab1c1-117">To serialize the workflow definition represented by the <xref:System.Activities.ActivityBuilder> instance to XAML, use <xref:System.Activities.XamlIntegration.ActivityXamlServices> to create a <xref:System.Xaml.XamlWriter>, and then use <xref:System.Xaml.XamlServices> to serialize the workflow definition by using the <xref:System.Xaml.XamlWriter>.</span></span> <span data-ttu-id="ab1c1-118"><xref:System.Activities.XamlIntegration.ActivityXamlServices> tiene métodos para asignar instancias de <xref:System.Activities.ActivityBuilder> en XAML y viceversa, y cargar flujos de trabajo de XAML y devolver <xref:System.Activities.DynamicActivity> que se pueda invocar.</span><span class="sxs-lookup"><span data-stu-id="ab1c1-118"><xref:System.Activities.XamlIntegration.ActivityXamlServices> has methods to map <xref:System.Activities.ActivityBuilder> instances to and from XAML, and to load XAML workflows and return a <xref:System.Activities.DynamicActivity> that can be invoked.</span></span> <span data-ttu-id="ab1c1-119">En el siguiente ejemplo, la instancia de <xref:System.Activities.ActivityBuilder> del ejemplo anterior se serializa en una cadena y también se guarda en un archivo.</span><span class="sxs-lookup"><span data-stu-id="ab1c1-119">In the following example, the <xref:System.Activities.ActivityBuilder> instance from the previous example is serialized to a string, and also saved to a file.</span></span>  
  
```csharp  
// Serialize the workflow to XAML and store it in a string.  
StringBuilder sb = new StringBuilder();  
StringWriter tw = new StringWriter(sb);  
XamlWriter xw = ActivityXamlServices.CreateBuilderWriter(new XamlXmlWriter(tw, new XamlSchemaContext()));  
XamlServices.Save(xw , ab);  
string serializedAB = sb.ToString();  
  
// Display the XAML to the console.  
Console.WriteLine(serializedAB);  
  
// Serialize the workflow to XAML and save it to a file.  
StreamWriter sw = File.CreateText(@"C:\Workflows\add.xaml");  
XamlWriter xw2 = ActivityXamlServices.CreateBuilderWriter(new XamlXmlWriter(sw, new XamlSchemaContext()));  
XamlServices.Save(xw2, ab);  
sw.Close();  
```  
  
 <span data-ttu-id="ab1c1-120">En el siguiente ejemplo se representa el flujo de trabajo serializado.</span><span class="sxs-lookup"><span data-stu-id="ab1c1-120">The following example represents the serialized workflow.</span></span>  
  
```xaml  
<Activity   
  x:TypeArguments="x:Int32"   
  x:Class="Add"   
  xmlns="http://schemas.microsoft.com/netfx/2009/xaml/activities"   
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">  
  <x:Members>  
    <x:Property Name="Operand1" Type="InArgument(x:Int32)" />  
    <x:Property Name="Operand2" Type="InArgument(x:Int32)" />  
  </x:Members>  
  <Sequence>  
    <WriteLine Text="[Operand1.ToString() + " + " + Operand2.ToString()]" />  
    <Assign x:TypeArguments="x:Int32" Value="[Operand1 + Operand2]">  
      <Assign.To>  
        <OutArgument x:TypeArguments="x:Int32">  
          <ArgumentReference x:TypeArguments="x:Int32" ArgumentName="Result" />  
          </OutArgument>  
      </Assign.To>  
    </Assign>  
  </Sequence>  
</Activity>  
```  
  
 <span data-ttu-id="ab1c1-121">Para cargar un flujo de trabajo serializado, el <xref:System.Activities.XamlIntegration.ActivityXamlServices> <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A> se usa el método.</span><span class="sxs-lookup"><span data-stu-id="ab1c1-121">To load a serialized workflow, the <xref:System.Activities.XamlIntegration.ActivityXamlServices> <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A> method is used.</span></span> <span data-ttu-id="ab1c1-122">Este método toma la definición de flujo de trabajo serializada y devuelve una clase <xref:System.Activities.DynamicActivity> que representa la definición de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ab1c1-122">This takes the serialized workflow definition and returns a <xref:System.Activities.DynamicActivity> that represents the workflow definition.</span></span> <span data-ttu-id="ab1c1-123">Observe que el XAML no se deserializa hasta que se llama al método <xref:System.Activities.Activity.CacheMetadata%2A> en el cuerpo de la clase <xref:System.Activities.DynamicActivity> durante el proceso de validación.</span><span class="sxs-lookup"><span data-stu-id="ab1c1-123">Note that the XAML is not deserialized until <xref:System.Activities.Activity.CacheMetadata%2A> is called on the body of the <xref:System.Activities.DynamicActivity> during the validation process.</span></span> <span data-ttu-id="ab1c1-124">Si no se llama a la validación explícitamente, se realiza cuando se invoca el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ab1c1-124">If validation is not explicitly called then it is performed when the workflow is invoked.</span></span> <span data-ttu-id="ab1c1-125">Si la definición de flujo de trabajo de XAML no es válida, se produce una excepción <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="ab1c1-125">If the XAML workflow definition is invalid, then an <xref:System.ArgumentException> exception is thrown.</span></span> <span data-ttu-id="ab1c1-126">Las excepciones que se producen desde el método <xref:System.Activities.Activity.CacheMetadata%2A> escapan de la llamada al método <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> y deben ser administradas por el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="ab1c1-126">Any exceptions thrown from <xref:System.Activities.Activity.CacheMetadata%2A> escape from the call to <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> and must be handled by the caller.</span></span> <span data-ttu-id="ab1c1-127">En el siguiente ejemplo, el flujo de trabajo serializado del ejemplo anterior se carga y se invoca utilizando <xref:System.Activities.WorkflowInvoker>.</span><span class="sxs-lookup"><span data-stu-id="ab1c1-127">In the following example, the serialized workflow from the previous example is loaded and invoked by using <xref:System.Activities.WorkflowInvoker>.</span></span>  
  
 [!code-csharp[CFX_WorkflowApplicationExample#43](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#43)]  
  
 <span data-ttu-id="ab1c1-128">Cuando se invoca este flujo de trabajo, en la consola se muestra el siguiente resultado.</span><span class="sxs-lookup"><span data-stu-id="ab1c1-128">When this workflow is invoked, the following output is displayed to the console.</span></span>  
  
 <span data-ttu-id="ab1c1-129">**25 + 15**</span><span class="sxs-lookup"><span data-stu-id="ab1c1-129">**25 + 15**</span></span>  
<span data-ttu-id="ab1c1-130">**40**</span><span class="sxs-lookup"><span data-stu-id="ab1c1-130">**40**</span></span>    
> [!NOTE]
>  <span data-ttu-id="ab1c1-131">Para obtener más información sobre cómo invocar flujos de trabajo con argumentos de entrada y salidos, vea [usar WorkflowInvoker y WorkflowApplication](using-workflowinvoker-and-workflowapplication.md) y <xref:System.Activities.WorkflowInvoker.Invoke%2A>.</span><span class="sxs-lookup"><span data-stu-id="ab1c1-131">For more information about invoking workflows with input and output arguments, see [Using WorkflowInvoker and WorkflowApplication](using-workflowinvoker-and-workflowapplication.md) and <xref:System.Activities.WorkflowInvoker.Invoke%2A>.</span></span>  
  
 <span data-ttu-id="ab1c1-132">Si el flujo de trabajo serializado contiene C# expresiones, una <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings> instancia con su <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A> propiedad establecida en `true` deben pasarse como parámetro a <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A?displayProperty=nameWithType>en caso contrario, un <xref:System.NotSupportedException> se iniciará con un mensaje similar a lo siguiente: `Expression Activity type 'CSharpValue`1' requiere compilación para ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="ab1c1-132">If the serialized workflow contains C# expressions, then an <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings> instance with its <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A> property set to `true` must be passed as a parameter to <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A?displayProperty=nameWithType>, otherwise a <xref:System.NotSupportedException> will be thrown with a message similar to the following: `Expression Activity type 'CSharpValue`1' requires compilation in order to run.</span></span>  <span data-ttu-id="ab1c1-133">Asegúrese de que se ha compilado el flujo de trabajo. "</span><span class="sxs-lookup"><span data-stu-id="ab1c1-133">Please ensure that the workflow has been compiled.\`</span></span>  
  
```csharp  
ActivityXamlServicesSettings settings = new ActivityXamlServicesSettings  
{  
    CompileExpressions = true  
};  
  
DynamicActivity<int> wf = ActivityXamlServices.Load(new StringReader(serializedAB), settings) as DynamicActivity<int>;  
```  
  
 <span data-ttu-id="ab1c1-134">Para obtener más información, consulte [ C# expresiones](csharp-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="ab1c1-134">For more information, see [C# Expressions](csharp-expressions.md).</span></span>  
  
 <span data-ttu-id="ab1c1-135">También se puede cargar una definición de flujo de trabajo serializado en un <xref:System.Activities.ActivityBuilder> instancia utilizando el <xref:System.Activities.XamlIntegration.ActivityXamlServices> <xref:System.Activities.XamlIntegration.ActivityXamlServices.CreateBuilderReader%2A> método.</span><span class="sxs-lookup"><span data-stu-id="ab1c1-135">A serialized workflow definition can also be loaded into an <xref:System.Activities.ActivityBuilder> instance by using the <xref:System.Activities.XamlIntegration.ActivityXamlServices> <xref:System.Activities.XamlIntegration.ActivityXamlServices.CreateBuilderReader%2A> method.</span></span> <span data-ttu-id="ab1c1-136">Una vez cargado un flujo de trabajo serializado en una instancia de <xref:System.Activities.ActivityBuilder>, se puede inspeccionar y modificar.</span><span class="sxs-lookup"><span data-stu-id="ab1c1-136">After a serialized workflow is loaded into an <xref:System.Activities.ActivityBuilder> instance it can be inspected and modified.</span></span> <span data-ttu-id="ab1c1-137">Esto resulta útil para los autores de diseñadores de flujo de trabajo personalizados y proporciona un mecanismo para guardar y recargar las definiciones de flujo de trabajo durante el proceso del diseño.</span><span class="sxs-lookup"><span data-stu-id="ab1c1-137">This is useful for custom workflow designer authors and provides a mechanism for saving and reloading workflow definitions during the design process.</span></span> <span data-ttu-id="ab1c1-138">En el siguiente ejemplo, se carga la definición de flujo de trabajo serializada del ejemplo anterior y se inspeccionan sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="ab1c1-138">In the following example, the serialized workflow definition from the previous example is loaded and its properties are inspected.</span></span>  
  
 [!code-csharp[CFX_WorkflowApplicationExample#44](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#44)]
