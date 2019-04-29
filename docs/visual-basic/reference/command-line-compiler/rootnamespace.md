---
title: -rootnamespace
ms.date: 03/13/2018
f1_keywords:
- /rootnamespace
- rootnamespace
helpviewer_keywords:
- /rootnamespace compiler option [Visual Basic]
- -rootnamespace compiler option [Visual Basic]
- rootnamespace compiler option [Visual Basic]
ms.assetid: e9245edf-6bef-420d-a7c7-324117752783
ms.openlocfilehash: ff4b1729f1b9fb1d698b4b5b1e3711ce3d27b4db
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61639040"
---
# <a name="-rootnamespace"></a><span data-ttu-id="7fd39-102">-rootnamespace</span><span class="sxs-lookup"><span data-stu-id="7fd39-102">-rootnamespace</span></span>
<span data-ttu-id="7fd39-103">Especifica un espacio de nombres para todas las declaraciones de tipos.</span><span class="sxs-lookup"><span data-stu-id="7fd39-103">Specifies a namespace for all type declarations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7fd39-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7fd39-104">Syntax</span></span>  
  
```  
-rootnamespace:namespace  
```  
  
## <a name="arguments"></a><span data-ttu-id="7fd39-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="7fd39-105">Arguments</span></span>  
  
|<span data-ttu-id="7fd39-106">Término</span><span class="sxs-lookup"><span data-stu-id="7fd39-106">Term</span></span>|<span data-ttu-id="7fd39-107">Definición</span><span class="sxs-lookup"><span data-stu-id="7fd39-107">Definition</span></span>|  
|---|---|  
|`namespace`|<span data-ttu-id="7fd39-108">El nombre del espacio de nombres en el que se va a incluir todas las declaraciones de tipo para el proyecto actual.</span><span class="sxs-lookup"><span data-stu-id="7fd39-108">The name of the namespace in which to enclose all type declarations for the current project.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7fd39-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7fd39-109">Remarks</span></span>  
 <span data-ttu-id="7fd39-110">Si usa el archivo ejecutable de Visual Studio (Devenv.exe) para compilar un proyecto creado en el entorno de desarrollo integrado de Visual Studio, use `-rootnamespace` para especificar el valor de la <xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="7fd39-110">If you use the Visual Studio executable file (Devenv.exe) to compile a project created in the Visual Studio integrated development environment, use `-rootnamespace` to specify the value of the <xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A> property.</span></span> <span data-ttu-id="7fd39-111">Consulte [modificadores de línea de comandos para Devenv](/visualstudio/ide/reference/devenv-command-line-switches) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="7fd39-111">See [Devenv Command Line Switches](/visualstudio/ide/reference/devenv-command-line-switches) for more information.</span></span>  
  
 <span data-ttu-id="7fd39-112">Utilizar el Desensamblador de MSIL de common language runtime (`Ildasm.exe`) para ver los nombres de espacio de nombres en el archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="7fd39-112">Use the common language runtime MSIL Disassembler (`Ildasm.exe`) to view the namespace names in your output file.</span></span>  
  
|<span data-ttu-id="7fd39-113">Para establecer - rootnamespace en el entorno de desarrollo integrado de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7fd39-113">To set -rootnamespace in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="7fd39-114">1.  Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="7fd39-114">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="7fd39-115">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="7fd39-115">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="7fd39-116">2.  Haga clic en la pestaña **Aplicación** .</span><span class="sxs-lookup"><span data-stu-id="7fd39-116">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="7fd39-117">3.  Modifique el valor en el **raíz Namespace** cuadro.</span><span class="sxs-lookup"><span data-stu-id="7fd39-117">3.  Modify the value in the **Root Namespace** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="7fd39-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7fd39-118">Example</span></span>  
 <span data-ttu-id="7fd39-119">El siguiente código compila `In.vb` y engloba todas las declaraciones de tipo en el espacio de nombres `mynamespace`.</span><span class="sxs-lookup"><span data-stu-id="7fd39-119">The following code compiles `In.vb` and encloses all type declarations in the namespace `mynamespace`.</span></span>  
  
```console
vbc -rootnamespace:mynamespace in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="7fd39-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="7fd39-120">See also</span></span>

- [<span data-ttu-id="7fd39-121">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7fd39-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="7fd39-122">Ildasm.exe (Desensamblador de IL)</span><span class="sxs-lookup"><span data-stu-id="7fd39-122">Ildasm.exe (IL Disassembler)</span></span>](../../../framework/tools/ildasm-exe-il-disassembler.md)
- [<span data-ttu-id="7fd39-123">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="7fd39-123">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
