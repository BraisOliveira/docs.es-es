---
title: -win32icon
ms.date: 03/13/2018
helpviewer_keywords:
- win32icon compiler option [Visual Basic]
- -win32icon compiler option [Visual Basic]
- /win32icon compiler option [Visual Basic]
ms.assetid: aecaab01-9353-46c5-941c-6edabd4eff92
ms.openlocfilehash: e36e9187ab8c9c2b4950a66ff8ff3fc93adbd9c4
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58821483"
---
# <a name="-win32icon"></a><span data-ttu-id="82a16-102">-win32icon</span><span class="sxs-lookup"><span data-stu-id="82a16-102">-win32icon</span></span>
<span data-ttu-id="82a16-103">Inserta un archivo .ico en el archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="82a16-103">Inserts an .ico file in the output file.</span></span> <span data-ttu-id="82a16-104">Este archivo .ico representa el archivo de salida en **Explorador de archivos**.</span><span class="sxs-lookup"><span data-stu-id="82a16-104">This .ico file represents the output file in **File Explorer**.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82a16-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="82a16-105">Syntax</span></span>  
  
```  
-win32icon:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="82a16-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="82a16-106">Arguments</span></span>  
  
|<span data-ttu-id="82a16-107">Término</span><span class="sxs-lookup"><span data-stu-id="82a16-107">Term</span></span>|<span data-ttu-id="82a16-108">de esquema JSON</span><span class="sxs-lookup"><span data-stu-id="82a16-108">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="82a16-109">El archivo .ico para agregar al archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="82a16-109">The .ico file to add to your output file.</span></span> <span data-ttu-id="82a16-110">Ponga el nombre de archivo entre comillas ("") si contiene un espacio.</span><span class="sxs-lookup"><span data-stu-id="82a16-110">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="82a16-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="82a16-111">Remarks</span></span>  
 <span data-ttu-id="82a16-112">Puede crear un archivo .ico con el compilador de recursos de Microsoft Windows (RC).</span><span class="sxs-lookup"><span data-stu-id="82a16-112">You can create an .ico file with the Microsoft Windows Resource Compiler (RC).</span></span> <span data-ttu-id="82a16-113">El compilador de recursos se invoca cuando se compila un programa de Visual C++; se crea un archivo .ico en el archivo .rc.</span><span class="sxs-lookup"><span data-stu-id="82a16-113">The resource compiler is invoked when you compile a Visual C++ program; an .ico file is created from the .rc file.</span></span> <span data-ttu-id="82a16-114">El `-win32icon` y `-win32resource` opciones son mutuamente excluyentes.</span><span class="sxs-lookup"><span data-stu-id="82a16-114">The `-win32icon` and `-win32resource` options are mutually exclusive.</span></span>  
  
 <span data-ttu-id="82a16-115">Consulte [- linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) para hacer referencia a un [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] archivo de recursos, o [-resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) para adjuntar un [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] archivo de recursos.</span><span class="sxs-lookup"><span data-stu-id="82a16-115">See [-linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) to reference a [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] resource file, or [-resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) to attach a [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] resource file.</span></span> <span data-ttu-id="82a16-116">Consulte [-win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) para importar un archivo. res.</span><span class="sxs-lookup"><span data-stu-id="82a16-116">See [-win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) to import a .res file.</span></span>  
  
|<span data-ttu-id="82a16-117">Para establecer - win32icon en el IDE de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="82a16-117">To set -win32icon in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="82a16-118">1.  Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="82a16-118">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="82a16-119">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="82a16-119">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="82a16-120">2.  Haga clic en la pestaña **Aplicación** .</span><span class="sxs-lookup"><span data-stu-id="82a16-120">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="82a16-121">3.  Modifique el valor en el **icono** cuadro.</span><span class="sxs-lookup"><span data-stu-id="82a16-121">3.  Modify the value in the **Icon** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="82a16-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="82a16-122">Example</span></span>  
 <span data-ttu-id="82a16-123">El siguiente código compila `In.vb` y adjunta un archivo .ico, `Rf.ico`.</span><span class="sxs-lookup"><span data-stu-id="82a16-123">The following code compiles `In.vb` and attaches an .ico file, `Rf.ico`.</span></span>  
  
```console
vbc -win32icon:rf.ico in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="82a16-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="82a16-124">See also</span></span>

- [<span data-ttu-id="82a16-125">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="82a16-125">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="82a16-126">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="82a16-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
