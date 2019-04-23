---
title: Procedimiento para generar ensamblados de interoperabilidad a partir de bibliotecas de tipos
ms.date: 03/30/2017
helpviewer_keywords:
- importing type library
- interop assemblies, generating
- Type Library Importer
- type libraries
- COM interop, importing type library
ms.assetid: 4afd40c3-68f2-41c5-8ec1-4951bc148b9c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3a3ee82a9091f0caeee010ec79632ce703efb589
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59338844"
---
# <a name="how-to-generate-interop-assemblies-from-type-libraries"></a><span data-ttu-id="270da-102">Procedimiento para generar ensamblados de interoperabilidad a partir de bibliotecas de tipos</span><span class="sxs-lookup"><span data-stu-id="270da-102">How to: Generate Interop Assemblies from Type Libraries</span></span>
<span data-ttu-id="270da-103">El [importador de la biblioteca de tipos (Tlbimp.exe)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md) es una herramienta de línea de comandos que convierte las coclases e interfaces contenidas en una biblioteca de tipos COM en metadatos.</span><span class="sxs-lookup"><span data-stu-id="270da-103">The [Type Library Importer (Tlbimp.exe)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md) is a command-line tool that converts the coclasses and interfaces contained in a COM type library to metadata.</span></span> <span data-ttu-id="270da-104">Esta herramienta crea automáticamente un ensamblado de interoperabilidad y un espacio de nombres para la información de tipos.</span><span class="sxs-lookup"><span data-stu-id="270da-104">This tool creates an interop assembly and namespace for the type information automatically.</span></span> <span data-ttu-id="270da-105">Una vez que los metadatos de una clase están disponibles, los clientes administrados pueden crear instancias del tipo COM y llamar a sus métodos, como si se tratara de una instancia de .NET.</span><span class="sxs-lookup"><span data-stu-id="270da-105">After the metadata of a class is available, managed clients can create instances of the COM type and call its methods, just as if it were a .NET instance.</span></span> <span data-ttu-id="270da-106">Tlbimp.exe convierte una biblioteca de tipos completa en metadatos de una vez y no se puede generar información de tipos para un subconjunto de los tipos definidos en una biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="270da-106">Tlbimp.exe converts an entire type library to metadata at once and cannot generate type information for a subset of the types defined in a type library.</span></span>  
  
### <a name="to-generate-an-interop-assembly-from-a-type-library"></a><span data-ttu-id="270da-107">Para generar un ensamblado de interoperabilidad a partir de una biblioteca de tipos</span><span class="sxs-lookup"><span data-stu-id="270da-107">To generate an interop assembly from a type library</span></span>  
  
1. <span data-ttu-id="270da-108">Use el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="270da-108">Use the following command:</span></span>  
  
     <span data-ttu-id="270da-109">**tlbimp** \<*archivo-de-biblioteca-de-tipos*></span><span class="sxs-lookup"><span data-stu-id="270da-109">**tlbimp** \<*type-library-file*></span></span>  
  
     <span data-ttu-id="270da-110">Agregar el modificador **/out:** genera un ensamblado de interoperabilidad con un nombre modificado, como LOANLib.dll.</span><span class="sxs-lookup"><span data-stu-id="270da-110">Adding the **/out:** switch produces an interop assembly with an altered name, such as LOANLib.dll.</span></span> <span data-ttu-id="270da-111">Modificar el nombre de ensamblado de interoperabilidad puede ayudar a distinguirlo del archivo DLL original de COM e impedir problemas que pueden producirse al tener nombres duplicados.</span><span class="sxs-lookup"><span data-stu-id="270da-111">Altering the interop assembly name can help distinguish it from the original COM DLL and prevent problems that can occur from having duplicate names.</span></span>  
  
## <a name="example"></a><span data-ttu-id="270da-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="270da-112">Example</span></span>  
 <span data-ttu-id="270da-113">El comando siguiente genera el ensamblado Loanlib.dll en el espacio de nombres `Loanlib`.</span><span class="sxs-lookup"><span data-stu-id="270da-113">The following command produces the Loanlib.dll assembly in the `Loanlib` namespace.</span></span>  
  
```  
tlbimp Loanlib.tlb  
```  
  
 <span data-ttu-id="270da-114">El comando siguiente genera un ensamblado de interoperabilidad con un nombre modificado (LOANLib.dll).</span><span class="sxs-lookup"><span data-stu-id="270da-114">The following command produces an interop assembly with an altered name (LOANLib.dll).</span></span>  
  
```  
tlbimp LoanLib.tlb /out: LOANLib.dll  
```  
  
## <a name="see-also"></a><span data-ttu-id="270da-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="270da-115">See also</span></span>

- [<span data-ttu-id="270da-116">Importar una biblioteca de tipos como un ensamblado</span><span class="sxs-lookup"><span data-stu-id="270da-116">Importing a Type Library as an Assembly</span></span>](../../../docs/framework/interop/importing-a-type-library-as-an-assembly.md)
- [<span data-ttu-id="270da-117">Exponer componentes COM en .NET Framework</span><span class="sxs-lookup"><span data-stu-id="270da-117">Exposing COM Components to the .NET Framework</span></span>](../../../docs/framework/interop/exposing-com-components.md)
