---
title: -keycontainer
ms.date: 03/10/2018
helpviewer_keywords:
- -keycontainer compiler option [Visual Basic]
- keycontainer compiler option [Visual Basic]
- /keycontainer compiler option [Visual Basic]
ms.assetid: 6a9bc861-1752-4db1-9f64-b5252f0482cc
ms.openlocfilehash: 5892baaa2732d95cfe698147e06b914af968adc5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69929424"
---
# <a name="-keycontainer"></a><span data-ttu-id="f62f0-102">-keycontainer</span><span class="sxs-lookup"><span data-stu-id="f62f0-102">-keycontainer</span></span>
<span data-ttu-id="f62f0-103">Especifica un nombre de contenedor de claves para un par de claves que asigna un nombre seguro al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="f62f0-103">Specifies a key container name for a key pair to give an assembly a strong name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f62f0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f62f0-104">Syntax</span></span>  
  
```  
-keycontainer:container  
```  
  
## <a name="arguments"></a><span data-ttu-id="f62f0-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="f62f0-105">Arguments</span></span>  
  
|<span data-ttu-id="f62f0-106">Término</span><span class="sxs-lookup"><span data-stu-id="f62f0-106">Term</span></span>|<span data-ttu-id="f62f0-107">Definición</span><span class="sxs-lookup"><span data-stu-id="f62f0-107">Definition</span></span>|  
|---|---|  
|`container`|<span data-ttu-id="f62f0-108">Necesario.</span><span class="sxs-lookup"><span data-stu-id="f62f0-108">Required.</span></span> <span data-ttu-id="f62f0-109">Archivo contenedor que contiene la clave.</span><span class="sxs-lookup"><span data-stu-id="f62f0-109">Container file that contains the key.</span></span> <span data-ttu-id="f62f0-110">Escriba el nombre de archivo entre comillas ("") si el nombre contiene un espacio.</span><span class="sxs-lookup"><span data-stu-id="f62f0-110">Enclose the file name in quotation marks ("") if the name contains a space.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f62f0-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f62f0-111">Remarks</span></span>  
 <span data-ttu-id="f62f0-112">El compilador crea el componente compartible insertando una clave pública en el manifiesto del ensamblado y firma el ensamblado final con la clave privada.</span><span class="sxs-lookup"><span data-stu-id="f62f0-112">The compiler creates the sharable component by inserting a public key into the assembly manifest and by signing the final assembly with the private key.</span></span> <span data-ttu-id="f62f0-113">Para generar un archivo de claves, escriba `sn -k file` en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="f62f0-113">To generate a key file, type `sn -k file` at the command line.</span></span> <span data-ttu-id="f62f0-114">La `-i` opción instala el par de claves en un contenedor.</span><span class="sxs-lookup"><span data-stu-id="f62f0-114">The `-i` option installs the key pair into a container.</span></span> <span data-ttu-id="f62f0-115">Para obtener más información, consulte [SN. exe (herramienta de nombre seguro)](../../../framework/tools/sn-exe-strong-name-tool.md)).</span><span class="sxs-lookup"><span data-stu-id="f62f0-115">For more information, see [Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md)).</span></span>  
  
 <span data-ttu-id="f62f0-116">Si compila con `-target:module`, el nombre del archivo de clave se mantiene en el módulo y se incorpora en el ensamblado que se crea al compilar un ensamblado con [-AddModule](../../../visual-basic/reference/command-line-compiler/addmodule.md).</span><span class="sxs-lookup"><span data-stu-id="f62f0-116">If you compile with `-target:module`, the name of the key file is held in the module and incorporated into the assembly that is created when you compile an assembly with [-addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md).</span></span>  
  
 <span data-ttu-id="f62f0-117">También se puede especificar esta opción como un atributo personalizado (<xref:System.Reflection.AssemblyKeyNameAttribute>) en el código fuente de cualquier módulo del Lenguaje Intermedio de Microsoft (MSIL).</span><span class="sxs-lookup"><span data-stu-id="f62f0-117">You can also specify this option as a custom attribute (<xref:System.Reflection.AssemblyKeyNameAttribute>) in the source code for any Microsoft intermediate language (MSIL) module.</span></span>  
  
 <span data-ttu-id="f62f0-118">También se puede pasar la información de cifrado al compilador con [-keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md).</span><span class="sxs-lookup"><span data-stu-id="f62f0-118">You can also pass your encryption information to the compiler with [-keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md).</span></span> <span data-ttu-id="f62f0-119">Use [-delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md) para firmar el ensamblado de forma parcial.</span><span class="sxs-lookup"><span data-stu-id="f62f0-119">Use [-delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md) if you want a partially signed assembly.</span></span>  
  
 <span data-ttu-id="f62f0-120">Vea [crear y utilizar ensamblados con nombre seguro](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) para obtener más información sobre la firma de un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="f62f0-120">See [Creating and Using Strong-Named Assemblies](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) for more information on signing an assembly.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f62f0-121">La `-keycontainer` opción no está disponible en el entorno de desarrollo de Visual Studio; solo está disponible al compilar desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="f62f0-121">The `-keycontainer` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f62f0-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f62f0-122">Example</span></span>  
 <span data-ttu-id="f62f0-123">En el código siguiente se compila el archivo `Input.vb` de código fuente y se especifica un contenedor de claves.</span><span class="sxs-lookup"><span data-stu-id="f62f0-123">The following code compiles source file `Input.vb` and specifies a key container.</span></span>  
  
```  
vbc -keycontainer:key1 input.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="f62f0-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="f62f0-124">See also</span></span>

- [<span data-ttu-id="f62f0-125">Ensamblados de .NET</span><span class="sxs-lookup"><span data-stu-id="f62f0-125">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
- [<span data-ttu-id="f62f0-126">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f62f0-126">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="f62f0-127">-keyfile</span><span class="sxs-lookup"><span data-stu-id="f62f0-127">-keyfile</span></span>](../../../visual-basic/reference/command-line-compiler/keyfile.md)
- [<span data-ttu-id="f62f0-128">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="f62f0-128">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
