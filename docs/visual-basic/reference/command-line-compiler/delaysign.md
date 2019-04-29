---
title: -delaysign
ms.date: 03/10/2018
helpviewer_keywords:
- delaysign compiler option [Visual Basic]
- -delaysign compiler option [Visual Basic]
- -delaysign compiler option [Visual Basic]
ms.assetid: c76e61a4-1884-4252-9fb2-377f99caa690
ms.openlocfilehash: 770dcad385c522a548a0c6fd3b6ef02dfbac82f5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61649717"
---
# <a name="-delaysign"></a><span data-ttu-id="cfe32-102">-delaysign</span><span class="sxs-lookup"><span data-stu-id="cfe32-102">-delaysign</span></span>
<span data-ttu-id="cfe32-103">Especifica si el ensamblado estará firmado total o parcialmente.</span><span class="sxs-lookup"><span data-stu-id="cfe32-103">Specifies whether the assembly will be fully or partially signed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cfe32-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cfe32-104">Syntax</span></span>  
  
```  
-delaysign[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="cfe32-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="cfe32-105">Arguments</span></span>  
 <span data-ttu-id="cfe32-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="cfe32-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="cfe32-107">Opcional.</span><span class="sxs-lookup"><span data-stu-id="cfe32-107">Optional.</span></span> <span data-ttu-id="cfe32-108">Use `-delaysign-` para firmar completamente un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="cfe32-108">Use `-delaysign-` if you want a fully signed assembly.</span></span> <span data-ttu-id="cfe32-109">Use `-delaysign+` si desea colocar la clave pública en el ensamblado y reservar espacio para el hash firmado.</span><span class="sxs-lookup"><span data-stu-id="cfe32-109">Use `-delaysign+` if you want to place the public key in the assembly and reserve space for the signed hash.</span></span> <span data-ttu-id="cfe32-110">De manera predeterminada, es `-delaysign-`.</span><span class="sxs-lookup"><span data-stu-id="cfe32-110">The default is `-delaysign-`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cfe32-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cfe32-111">Remarks</span></span>  
 <span data-ttu-id="cfe32-112">El `-delaysign` opción no tiene ningún efecto a menos que se usa con [- keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md) o [- keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md).</span><span class="sxs-lookup"><span data-stu-id="cfe32-112">The `-delaysign` option has no effect unless used with [-keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md) or [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md).</span></span>  
  
 <span data-ttu-id="cfe32-113">Cuando se solicita un ensamblado totalmente firmado, el compilador genera un valor hash para el archivo que contiene el manifiesto (metadatos del ensamblado) y firma dicho valor mediante la clave privada.</span><span class="sxs-lookup"><span data-stu-id="cfe32-113">When you request a fully signed assembly, the compiler hashes the file that contains the manifest (assembly metadata) and signs that hash with the private key.</span></span> <span data-ttu-id="cfe32-114">La firma digital resultante se almacena en el archivo que contiene el manifiesto.</span><span class="sxs-lookup"><span data-stu-id="cfe32-114">The resulting digital signature is stored in the file that contains the manifest.</span></span> <span data-ttu-id="cfe32-115">Cuando se retrasa la firma de un ensamblado, el compilador no de proceso y se almacena la firma, pero reserva espacio en el archivo para que la firma se puede agregar más adelante.</span><span class="sxs-lookup"><span data-stu-id="cfe32-115">When an assembly is delay signed, the compiler does not compute and store the signature but reserves space in the file so the signature can be added later.</span></span>  
  
 <span data-ttu-id="cfe32-116">Por ejemplo, mediante el uso de `-delaysign+`, un desarrollador de una organización puede distribuir las versiones de prueba sin signo de un ensamblado que se pueden registrar con la caché global de ensamblados y usar los evaluadores.</span><span class="sxs-lookup"><span data-stu-id="cfe32-116">For example, by using `-delaysign+`, a developer in an organization can distribute unsigned test versions of an assembly that testers can register with the global assembly cache and use.</span></span> <span data-ttu-id="cfe32-117">Cuando se completa el trabajo en el ensamblado, la persona responsable de la clave privada de la organización puede firmar completamente el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="cfe32-117">When work on the assembly is completed, the person responsible for the organization's private key can fully sign the assembly.</span></span> <span data-ttu-id="cfe32-118">Esta división de funciones protege la clave privada de la organización de la divulgación, permitiendo que todos los desarrolladores pueden trabajar en los ensamblados.</span><span class="sxs-lookup"><span data-stu-id="cfe32-118">This compartmentalization protects the organization's private key from disclosure, while allowing all developers to work on the assemblies.</span></span>  
  
 <span data-ttu-id="cfe32-119">Consulte [crear y utilizar ensamblados](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) para obtener más información sobre cómo firmar un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="cfe32-119">See [Creating and Using Strong-Named Assemblies](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) for more information on signing an assembly.</span></span>  
  
### <a name="to-set--delaysign-in-the-visual-studio-integrated-development-environment"></a><span data-ttu-id="cfe32-120">Para establecer delaysign - en el entorno de desarrollo integrado de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="cfe32-120">To set -delaysign in the Visual Studio integrated development environment</span></span>  
  
1. <span data-ttu-id="cfe32-121">Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="cfe32-121">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="cfe32-122">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="cfe32-122">On the **Project** menu, click **Properties**.</span></span>   
  
2. <span data-ttu-id="cfe32-123">Haga clic en la pestaña **Firma**.</span><span class="sxs-lookup"><span data-stu-id="cfe32-123">Click the **Signing** tab.</span></span>  
  
3. <span data-ttu-id="cfe32-124">Establezca el valor el **Retrasar firma solo** cuadro.</span><span class="sxs-lookup"><span data-stu-id="cfe32-124">Set the value in the **Delay sign only** box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfe32-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="cfe32-125">See also</span></span>

- [<span data-ttu-id="cfe32-126">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cfe32-126">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="cfe32-127">-keyfile</span><span class="sxs-lookup"><span data-stu-id="cfe32-127">-keyfile</span></span>](../../../visual-basic/reference/command-line-compiler/keyfile.md)
- [<span data-ttu-id="cfe32-128">-keycontainer</span><span class="sxs-lookup"><span data-stu-id="cfe32-128">-keycontainer</span></span>](../../../visual-basic/reference/command-line-compiler/keycontainer.md)
- [<span data-ttu-id="cfe32-129">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="cfe32-129">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
