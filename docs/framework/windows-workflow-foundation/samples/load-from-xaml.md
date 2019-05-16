---
title: Cargar de XAML
ms.date: 03/30/2017
ms.assetid: 1f103ef6-7bed-4f16-ae52-9e665c5a43d7
ms.openlocfilehash: e0cac1b6dfb9568ba08079cf5194b3432eea856f
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65637714"
---
# <a name="load-from-xaml"></a><span data-ttu-id="26d66-102">Cargar de XAML</span><span class="sxs-lookup"><span data-stu-id="26d66-102">Load From XAML</span></span>
<span data-ttu-id="26d66-103">En este ejemplo se muestra cómo cargar dinámicamente un flujo de trabajo de XAML sin tener que ejecutar la herramienta XamlBuildTask.</span><span class="sxs-lookup"><span data-stu-id="26d66-103">This sample demonstrates how to dynamically load a XAML workflow without having to run the XamlBuildTask tool.</span></span> <span data-ttu-id="26d66-104">En su lugar, el ejemplo llama al método <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A>.</span><span class="sxs-lookup"><span data-stu-id="26d66-104">Instead, the sample calls the <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A> method.</span></span> <span data-ttu-id="26d66-105">El ejemplo es una aplicación de cliente de Windows Presentation Foundation (WPF) que carga flujos de trabajo XAML mediante el <xref:System.Activities.XamlIntegration.ActivityXamlServices> de clases y los ejecuta.</span><span class="sxs-lookup"><span data-stu-id="26d66-105">The sample is a Windows Presentation Foundation (WPF) client application that loads XAML workflows using the <xref:System.Activities.XamlIntegration.ActivityXamlServices> class and executes them.</span></span> <span data-ttu-id="26d66-106">Una vez cargados utilizando la clase <xref:System.Activities.XamlIntegration.ActivityXamlServices>, se devuelve una actividad <xref:System.Activities.DynamicActivity%601> que se puede ejecutar.</span><span class="sxs-lookup"><span data-stu-id="26d66-106">After they have been loaded using the <xref:System.Activities.XamlIntegration.ActivityXamlServices> class, a <xref:System.Activities.DynamicActivity%601> is returned that can be executed.</span></span>

#### <a name="to-use-this-sample"></a><span data-ttu-id="26d66-107">Para utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="26d66-107">To use this sample</span></span>

1. <span data-ttu-id="26d66-108">Con Visual Studio 2010, abra el archivo de solución LoadFromXAML.sln.</span><span class="sxs-lookup"><span data-stu-id="26d66-108">Using Visual Studio 2010, open the LoadFromXAML.sln solution file.</span></span>

2. <span data-ttu-id="26d66-109">Para compilar la solución, presione Ctrl+MAYÚS+B.</span><span class="sxs-lookup"><span data-stu-id="26d66-109">To build the solution, press CTRL+SHIFT+B.</span></span>

3. <span data-ttu-id="26d66-110">Para ejecutar la solución, presione CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="26d66-110">To run the solution, press CTRL+F5.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="26d66-111">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="26d66-111">The samples may already be installed on your machine.</span></span> <span data-ttu-id="26d66-112">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="26d66-112">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="26d66-113">Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="26d66-113">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="26d66-114">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="26d66-114">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\DynamicActivity\LoadFromXAML`
