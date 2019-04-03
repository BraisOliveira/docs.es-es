---
title: -langversion (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- /langversion compiler option [Visual Basic]
- langversion compiler option [Visual Basic]
- -langversion compiler option [Visual Basic]
ms.assetid: 59b7b0c8-2dde-4e9b-94e7-0237f7e0bafb
ms.openlocfilehash: db2cb1eb107973e9ce60ecb0d669c677d4fa2c51
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58839731"
---
# <a name="-langversion-visual-basic"></a><span data-ttu-id="07fec-102">-langversion (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="07fec-102">-langversion (Visual Basic)</span></span>
<span data-ttu-id="07fec-103">Hace que el compilador acepta solo la sintaxis que se incluye en la versión de idioma de Visual Basic especificada.</span><span class="sxs-lookup"><span data-stu-id="07fec-103">Causes the compiler to accept only syntax that is included in the specified Visual Basic language version.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07fec-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="07fec-104">Syntax</span></span>  
  
```  
-langversion:version  
```  
  
## <a name="arguments"></a><span data-ttu-id="07fec-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="07fec-105">Arguments</span></span>  
 `version`  
 <span data-ttu-id="07fec-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="07fec-106">Required.</span></span> <span data-ttu-id="07fec-107">La versión de idioma que se usará durante la compilación.</span><span class="sxs-lookup"><span data-stu-id="07fec-107">The language version to be used during the compilation.</span></span> <span data-ttu-id="07fec-108">Valores aceptados son `9`, `10`, `11`, `12`, `14`, `15`, `15.3`, `15.5`, `default` y `latest`.</span><span class="sxs-lookup"><span data-stu-id="07fec-108">Accepted values are `9`, `10`, `11`, `12`, `14`, `15`, `15.3`, `15.5`, `default` and `latest`.</span></span>

 <span data-ttu-id="07fec-109">Cualquiera de los números enteros también pueden especificarse mediante `.0` como la versión secundaria, por ejemplo, `11.0`.</span><span class="sxs-lookup"><span data-stu-id="07fec-109">Any of the whole numbers may also be specified using `.0` as the minor version, for example, `11.0`.</span></span>

 <span data-ttu-id="07fec-110">Puede ver la lista de todos los valores posibles mediante la especificación de `-langversion:?` en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="07fec-110">You can see the list of all possible values by specifying `-langversion:?` on the command line.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="07fec-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="07fec-111">Remarks</span></span>  
 <span data-ttu-id="07fec-112">El `-langversion` opción especifica la sintaxis que el compilador acepta.</span><span class="sxs-lookup"><span data-stu-id="07fec-112">The `-langversion` option specifies what syntax the compiler accepts.</span></span> <span data-ttu-id="07fec-113">Por ejemplo, si especifica que la versión de lenguaje es 9.0, el compilador genera errores de sintaxis que es válida únicamente en la versión 10.0 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="07fec-113">For example, if you specify that the language version is 9.0, the compiler generates errors for syntax that is valid only in version 10.0 and later.</span></span>  
  
 <span data-ttu-id="07fec-114">Puede usar esta opción para desarrollar aplicaciones destinadas a versiones diferentes de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="07fec-114">You can use this option when you develop applications that target different versions of the .NET Framework.</span></span> <span data-ttu-id="07fec-115">Por ejemplo, si tiene como destino .NET Framework 3.5, podría usar esta opción para asegurarse de que no usan la sintaxis de la versión 10.0 del lenguaje.</span><span class="sxs-lookup"><span data-stu-id="07fec-115">For example, if you are targeting .NET Framework 3.5, you could use this option to ensure that you do not use syntax from language version 10.0.</span></span>  
  
 <span data-ttu-id="07fec-116">Puede establecer `-langversion` directamente utilizando la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="07fec-116">You can set `-langversion` directly only by using the command line.</span></span> <span data-ttu-id="07fec-117">Para obtener más información, consulte [Elegir una versión específica de .NET Framework](/visualstudio/ide/targeting-a-specific-dotnet-framework-version).</span><span class="sxs-lookup"><span data-stu-id="07fec-117">For more information, see [Targeting a Specific .NET Framework Version](/visualstudio/ide/targeting-a-specific-dotnet-framework-version).</span></span>  
  
## <a name="example"></a><span data-ttu-id="07fec-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="07fec-118">Example</span></span>  
 <span data-ttu-id="07fec-119">El siguiente código compila `sample.vb` para Visual Basic 9.0.</span><span class="sxs-lookup"><span data-stu-id="07fec-119">The following code compiles `sample.vb` for Visual Basic 9.0.</span></span>  
  
```console  
vbc -langversion:9.0 sample.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="07fec-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="07fec-120">See also</span></span>

- [<span data-ttu-id="07fec-121">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="07fec-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="07fec-122">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="07fec-122">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="07fec-123">Elegir una versión específica de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="07fec-123">Targeting a Specific .NET Framework Version</span></span>](/visualstudio/ide/targeting-a-specific-dotnet-framework-version)
