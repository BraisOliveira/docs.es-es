---
title: Ejemplo de Version Tolerant Serialization Technology
ms.date: 03/30/2017
ms.assetid: 2a183664-bfbf-4ff0-96f6-c836284ea916
ms.openlocfilehash: d7dfcf7548571d29032495ca8be96db70f2336fc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59308372"
---
# <a name="version-tolerant-serialization-technology-sample"></a><span data-ttu-id="fc95d-102">Ejemplo de Version Tolerant Serialization Technology</span><span class="sxs-lookup"><span data-stu-id="fc95d-102">Version Tolerant Serialization Technology Sample</span></span>
[<span data-ttu-id="fc95d-103">Descargar ejemplo</span><span class="sxs-lookup"><span data-stu-id="fc95d-103">Download Sample</span></span>](https://download.microsoft.com/download/4/7/B/47B2164C-E780-4B10-8DE4-2CB5B886E0A6/Technologies/Serialization/Runtime%20Serialization/VTS.zip.exe)  
  
 <span data-ttu-id="fc95d-104">Este ejemplo muestra las características de tolerancia a versiones de .NET Serialization.</span><span class="sxs-lookup"><span data-stu-id="fc95d-104">This sample demonstrates the version tolerance features of .NET Serialization.</span></span> <span data-ttu-id="fc95d-105">En el ejemplo se generan aplicaciones que utilizan versiones diferentes de una clase <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> para serializar y deserializar datos.</span><span class="sxs-lookup"><span data-stu-id="fc95d-105">The sample builds applications that use different versions of a <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> to serialize and deserialize data.</span></span> <span data-ttu-id="fc95d-106">A pesar de la presencia de versiones de tipo diferentes, las aplicaciones se comunican de forma transparente.</span><span class="sxs-lookup"><span data-stu-id="fc95d-106">Despite the presence of different type versions, the applications communicate seamlessly.</span></span> <span data-ttu-id="fc95d-107">Para obtener más información, vea [Version Tolerant Serialization](../../../docs/standard/serialization/version-tolerant-serialization.md) (Serialización tolerante a versiones).</span><span class="sxs-lookup"><span data-stu-id="fc95d-107">For more information, see [Version Tolerant Serialization](../../../docs/standard/serialization/version-tolerant-serialization.md).</span></span>  
  
### <a name="to-build-the-sample-using-the-command-prompt"></a><span data-ttu-id="fc95d-108">Para generar el ejemplo desde el símbolo del sistema</span><span class="sxs-lookup"><span data-stu-id="fc95d-108">To build the sample using the command prompt</span></span>  
  
1. <span data-ttu-id="fc95d-109">Abra una ventana del símbolo del sistema y navegue hasta uno de los subdirectorios específicos del lenguaje (en V1 Application o V2 Application) del ejemplo.</span><span class="sxs-lookup"><span data-stu-id="fc95d-109">Open a Command Prompt window and navigate to one of the language-specific subdirectories (under V1 Application or V2 Application) for the sample.</span></span>  
  
2. <span data-ttu-id="fc95d-110">Escriba **msbuild.exe \<ver> application.sln** en la línea de comandos (donde \<ver> es v1 o v2).</span><span class="sxs-lookup"><span data-stu-id="fc95d-110">Type **msbuild.exe \<ver> application.sln** at the command line (where \<ver> is either v1 or v2).</span></span>  
  
### <a name="to-build-the-sample-using-visual-studio"></a><span data-ttu-id="fc95d-111">Para compilar el ejemplo con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="fc95d-111">To build the sample using Visual Studio</span></span>  
  
1. <span data-ttu-id="fc95d-112">Abra [!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)] y navegue hasta uno de los subdirectorios específicos del lenguaje del ejemplo.</span><span class="sxs-lookup"><span data-stu-id="fc95d-112">Open [!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)] and navigate to one of the language-specific subdirectories for the sample.</span></span>  
  
2. <span data-ttu-id="fc95d-113">Navegue hasta el subdirectorio V1 Application del directorio que seleccionó en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="fc95d-113">Navigate to the V1 Application subdirectory of the directory you selected in the previous step.</span></span>  
  
3. <span data-ttu-id="fc95d-114">Haga doble clic en el icono V1 Application.sln para abrir el archivo en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="fc95d-114">Double-click the icon for V1 Application.sln to open the file in Visual Studio.</span></span>  
  
4. <span data-ttu-id="fc95d-115">En el menú **Compilar** , haga clic en **Compilar solución**.</span><span class="sxs-lookup"><span data-stu-id="fc95d-115">On the **Build** menu, click **Build Solution**.</span></span>  
  
5. <span data-ttu-id="fc95d-116">Navegue hasta el subdirectorio V2 Application y repita los dos pasos anteriores para generar la aplicación V2 Application.</span><span class="sxs-lookup"><span data-stu-id="fc95d-116">Navigate to the V2 Application subdirectory and repeat the two previous steps to build the V2 Application.</span></span>  
  
 <span data-ttu-id="fc95d-117">Las aplicaciones se generarán en los subdirectorios predeterminados \bin o \bin\Debug de sus directorios de proyecto respectivos.</span><span class="sxs-lookup"><span data-stu-id="fc95d-117">The applications will be built in the default \bin or \bin\Debug subdirectories of their respective project directories.</span></span>  
  
### <a name="to-run-the-sample"></a><span data-ttu-id="fc95d-118">Para ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="fc95d-118">To run the sample</span></span>  
  
1. <span data-ttu-id="fc95d-119">En la ventana del símbolo del sistema, navegue hasta el subdirectorio específico del lenguaje que seleccionó cuando generó las aplicaciones de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="fc95d-119">In the Command Prompt window, navigate to the language-specific subdirectory that you selected when you built the sample applications.</span></span>  
  
2. <span data-ttu-id="fc95d-120">Escriba **runme.cmd** en la línea de comandos para ejecutar ambas aplicaciones a la vez.</span><span class="sxs-lookup"><span data-stu-id="fc95d-120">Type **runme.cmd** at the command line to run both applications at once.</span></span>  
  
 <span data-ttu-id="fc95d-121">Otra opción es navegar a los directorios que contienen las nuevas aplicaciones ejecutables y ejecutarlas secuencialmente.</span><span class="sxs-lookup"><span data-stu-id="fc95d-121">Alternatively, navigate to the directories that contain the new executables and run them sequentially.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fc95d-122">En el ejemplo se generan aplicaciones de consola.</span><span class="sxs-lookup"><span data-stu-id="fc95d-122">The sample builds console applications.</span></span> <span data-ttu-id="fc95d-123">Para ver el resultado, debe iniciarlas y ejecutarlas en una ventana del símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="fc95d-123">You must launch and run them in a Command Prompt window to view their output.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc95d-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="fc95d-124">See also</span></span>

- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>
- <xref:System.IO.FileStream>
