---
title: Utilizar DataContractSerializer y DataContractResolver para proporcionar la funcionalidad de NetDataContractSerializer
ms.date: 03/30/2017
ms.assetid: 1376658f-f695-45f7-a7e0-94664e9619ff
ms.openlocfilehash: 0378f8d6e21f44eb1f39e9ebf51ef0dfaf8d8e8a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61990410"
---
# <a name="using-datacontractserializer-and-datacontractresolver-to-provide-the-functionality-of-netdatacontractserializer"></a><span data-ttu-id="5428a-102">Utilizar DataContractSerializer y DataContractResolver para proporcionar la funcionalidad de NetDataContractSerializer</span><span class="sxs-lookup"><span data-stu-id="5428a-102">Using DataContractSerializer and DataContractResolver to Provide the Functionality of NetDataContractSerializer</span></span>
<span data-ttu-id="5428a-103">En este ejemplo se muestra el modo en que el uso de un <xref:System.Runtime.Serialization.DataContractSerializer> con un <xref:System.Runtime.Serialization.DataContractResolver> adecuado proporciona la misma funcionalidad que <xref:System.Runtime.Serialization.NetDataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="5428a-103">This sample demonstrates how the use of <xref:System.Runtime.Serialization.DataContractSerializer> with an appropriate <xref:System.Runtime.Serialization.DataContractResolver> provides the same functionality as <xref:System.Runtime.Serialization.NetDataContractSerializer>.</span></span> <span data-ttu-id="5428a-104">En este ejemplo se muestra cómo crear el <xref:System.Runtime.Serialization.DataContractResolver> adecuado y cómo agregarlo a <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="5428a-104">This sample shows how to create the appropriate <xref:System.Runtime.Serialization.DataContractResolver> and how to add it to the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>

## <a name="sample-details"></a><span data-ttu-id="5428a-105">Detalles del ejemplo</span><span class="sxs-lookup"><span data-stu-id="5428a-105">Sample details</span></span>
 <span data-ttu-id="5428a-106"><xref:System.Runtime.Serialization.NetDataContractSerializer> difiere de <xref:System.Runtime.Serialization.DataContractSerializer> en un aspecto importante: <xref:System.Runtime.Serialization.NetDataContractSerializer> incluye información de tipos CLR en el XML serializado, mientras que <xref:System.Runtime.Serialization.DataContractSerializer> no.</span><span class="sxs-lookup"><span data-stu-id="5428a-106"><xref:System.Runtime.Serialization.NetDataContractSerializer> differs from <xref:System.Runtime.Serialization.DataContractSerializer> in one important way: <xref:System.Runtime.Serialization.NetDataContractSerializer> includes CLR type information in the serialized XML, whereas <xref:System.Runtime.Serialization.DataContractSerializer> does not.</span></span> <span data-ttu-id="5428a-107">Por lo tanto, solo se puede utilizar <xref:System.Runtime.Serialization.NetDataContractSerializer> si ambos extremos, los de la serialización y los de la deserialización, comparten los mismos tipos de CLR.</span><span class="sxs-lookup"><span data-stu-id="5428a-107">Therefore, <xref:System.Runtime.Serialization.NetDataContractSerializer> can be used only if both the serializing and deserializing ends share the same CLR types.</span></span> <span data-ttu-id="5428a-108">Sin embargo, se recomienda utilizar <xref:System.Runtime.Serialization.DataContractSerializer> porque su rendimiento es mejor que el de <xref:System.Runtime.Serialization.NetDataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="5428a-108">However, it is recommended to use <xref:System.Runtime.Serialization.DataContractSerializer> because its performance is better than <xref:System.Runtime.Serialization.NetDataContractSerializer>.</span></span> <span data-ttu-id="5428a-109">Puede cambiar la información que se serializa en <xref:System.Runtime.Serialization.DataContractSerializer> agregando un <xref:System.Runtime.Serialization.DataContractResolver> a él.</span><span class="sxs-lookup"><span data-stu-id="5428a-109">You can change the information that is serialized in <xref:System.Runtime.Serialization.DataContractSerializer> by adding a <xref:System.Runtime.Serialization.DataContractResolver> to it.</span></span>

 <span data-ttu-id="5428a-110">Este ejemplo consta de dos proyectos.</span><span class="sxs-lookup"><span data-stu-id="5428a-110">This sample consists of two projects.</span></span> <span data-ttu-id="5428a-111">El primer proyecto utiliza <xref:System.Runtime.Serialization.NetDataContractSerializer> para serializar un objeto.</span><span class="sxs-lookup"><span data-stu-id="5428a-111">The first project uses <xref:System.Runtime.Serialization.NetDataContractSerializer> to serialize an object.</span></span> <span data-ttu-id="5428a-112">El segundo proyecto utiliza <xref:System.Runtime.Serialization.DataContractSerializer> con <xref:System.Runtime.Serialization.DataContractResolver> para proporcionar la misma funcionalidad que el primer proyecto.</span><span class="sxs-lookup"><span data-stu-id="5428a-112">The second project uses <xref:System.Runtime.Serialization.DataContractSerializer> with a <xref:System.Runtime.Serialization.DataContractResolver> to provide the same functionality as the first project.</span></span>

 <span data-ttu-id="5428a-113">El siguiente ejemplo de código muestra la implementación de un <xref:System.Runtime.Serialization.DataContractResolver> personalizado denominado `MyDataContractResolver` que se agrega a <xref:System.Runtime.Serialization.DataContractSerializer> en el proyecto DCSwithDCR.</span><span class="sxs-lookup"><span data-stu-id="5428a-113">The following code example shows the implementation of a custom <xref:System.Runtime.Serialization.DataContractResolver> named `MyDataContractResolver` that is added to the <xref:System.Runtime.Serialization.DataContractSerializer> in the DCSwithDCR project.</span></span>

```csharp
class MyDataContractResolver : DataContractResolver
{
    private XmlDictionary dictionary = new XmlDictionary();

    public MyDataContractResolver()
    {
    }

    // Used at deserialization
    // Allows users to map xsi:type name to any Type
    public override Type ResolveName(string typeName, string typeNamespace, DataContractResolver knownTypeResolver)
    {
        Type type = knownTypeResolver.ResolveName(typeName, typeNamespace, null);
        if (type == null)
        {
            type = Type.GetType(typeName + ", " + typeNamespace);
        }
        return type;
    }

    // Used at serialization
    // Maps any Type to a new xsi:type representation
    public override void ResolveType(Type dataContractType, DataContractResolver knownTypeResolver, out XmlDictionaryString typeName, out XmlDictionaryString typeNamespace)
    {
        knownTypeResolver.ResolveType(dataContractType, null, out typeName, out typeNamespace);
        if (typeName == null || typeNamespace == null)
        {
            XmlDictionary dictionary = new XmlDictionary();
            typeName = dictionary.Add(dataContractType.FullName);
            typeNamespace = dictionary.Add(dataContractType.Assembly.FullName);
        }
    }
}
```

#### <a name="to-use-this-sample"></a><span data-ttu-id="5428a-114">Para utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="5428a-114">To use this sample</span></span>

1. <span data-ttu-id="5428a-115">Con Visual Studio 2012, abra el archivo de Cdrsample.sln.</span><span class="sxs-lookup"><span data-stu-id="5428a-115">Using Visual Studio 2012, open the DCRSample.sln solution file.</span></span>

2. <span data-ttu-id="5428a-116">Haga clic en el archivo de solución y elija **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="5428a-116">Right-click the solution file and choose **Properties**.</span></span>

3. <span data-ttu-id="5428a-117">En el **páginas de propiedades de la solución** cuadro de diálogo, en **propiedades comunes**, **proyecto de inicio**, seleccione **varios proyectos de inicio:**.</span><span class="sxs-lookup"><span data-stu-id="5428a-117">In the **Solution Property Pages** dialog, under **Common Properties**, **Startup Project**, select **Multiple startup projects:**.</span></span>

4. <span data-ttu-id="5428a-118">Junto a la **DCSwithDCR** proyecto, seleccione **iniciar** desde el **acción** lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="5428a-118">Next to the **DCSwithDCR** project, select **Start** from the **Action** dropdown.</span></span>

5. <span data-ttu-id="5428a-119">Junto a la **NetDCS** proyecto, seleccione **iniciar** desde el **acción** lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="5428a-119">Next to the **NetDCS** project, select **Start** from the **Action** dropdown.</span></span>

6. <span data-ttu-id="5428a-120">Haga clic en **Aceptar** para cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="5428a-120">Click **OK** to close the dialog.</span></span>

7. <span data-ttu-id="5428a-121">Para compilar la solución, presione Ctrl+MAYÚS+B.</span><span class="sxs-lookup"><span data-stu-id="5428a-121">To build the solution, press CTRL+SHIFT+B.</span></span>

8. <span data-ttu-id="5428a-122">Para ejecutar la solución, presione CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="5428a-122">To run the solution, press CTRL+F5.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="5428a-123">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="5428a-123">The samples may already be installed on your machine.</span></span> <span data-ttu-id="5428a-124">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="5428a-124">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="5428a-125">Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="5428a-125">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="5428a-126">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="5428a-126">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Data\NetDcSasDcSwithDCR`  
