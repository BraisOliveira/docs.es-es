---
title: -filealign
ms.date: 03/10/2018
helpviewer_keywords:
- sections compiler option [Visual Basic]
- alignment compiler option [Visual Basic]
- -filealign compiler option [Visual Basic]
- section alignment
- /filealign compiler option [Visual Basic]
- filealign compiler option [Visual Basic]
ms.assetid: cc61ec3d-ad38-4b28-9659-099d73cad099
ms.openlocfilehash: 9a844515a4596064937762ac05b850463f1b5e14
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62051707"
---
# <a name="-filealign"></a><span data-ttu-id="b70e4-102">-filealign</span><span class="sxs-lookup"><span data-stu-id="b70e4-102">-filealign</span></span>
<span data-ttu-id="b70e4-103">Especifica dónde se alinean las secciones del archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="b70e4-103">Specifies where to align the sections of the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b70e4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b70e4-104">Syntax</span></span>  
  
```  
-filealign:number  
```  
  
## <a name="arguments"></a><span data-ttu-id="b70e4-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="b70e4-105">Arguments</span></span>  
 `number`  
 <span data-ttu-id="b70e4-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="b70e4-106">Required.</span></span> <span data-ttu-id="b70e4-107">Un valor que especifica la alineación de las secciones del archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="b70e4-107">A value that specifies the alignment of sections in the output file.</span></span> <span data-ttu-id="b70e4-108">Los valores válidos son 512, 1024, 2048, 4096 y 8192.</span><span class="sxs-lookup"><span data-stu-id="b70e4-108">Valid values are 512, 1024, 2048, 4096, and 8192.</span></span> <span data-ttu-id="b70e4-109">Estos valores están en bytes.</span><span class="sxs-lookup"><span data-stu-id="b70e4-109">These values are in bytes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b70e4-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b70e4-110">Remarks</span></span>  
 <span data-ttu-id="b70e4-111">Puede usar el `-filealign` opción para especificar la alineación de las secciones en el archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="b70e4-111">You can use the `-filealign` option to specify the alignment of sections in your output file.</span></span> <span data-ttu-id="b70e4-112">Las secciones son bloques de memoria contigua en un archivo ejecutable Portable (PE) que contiene el código o datos.</span><span class="sxs-lookup"><span data-stu-id="b70e4-112">Sections are blocks of contiguous memory in a Portable Executable (PE) file that contains either code or data.</span></span> <span data-ttu-id="b70e4-113">El `-filealign` opción le permite compilar la aplicación con una alineación no estándar; la mayoría de los desarrolladores no es necesario usar esta opción.</span><span class="sxs-lookup"><span data-stu-id="b70e4-113">The `-filealign` option lets you compile your application with a nonstandard alignment; most developers do not need to use this option.</span></span>  
  
 <span data-ttu-id="b70e4-114">Cada sección se alinea en un límite que es un múltiplo de la `-filealign` valor.</span><span class="sxs-lookup"><span data-stu-id="b70e4-114">Each section is aligned on a boundary that is a multiple of the `-filealign` value.</span></span> <span data-ttu-id="b70e4-115">No hay ningún valor predeterminado fijo.</span><span class="sxs-lookup"><span data-stu-id="b70e4-115">There is no fixed default.</span></span> <span data-ttu-id="b70e4-116">Si `-filealign` no se especifica, el compilador elige un valor predeterminado en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="b70e4-116">If `-filealign` is not specified, the compiler picks a default at compile time.</span></span>  
  
 <span data-ttu-id="b70e4-117">Al especificar el tamaño de la sección, puede cambiar el tamaño del archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="b70e4-117">By specifying the section size, you can change the size of the output file.</span></span> <span data-ttu-id="b70e4-118">Modificar el tamaño de la sección puede ser útil para los programas que se ejecutan en dispositivos más pequeños.</span><span class="sxs-lookup"><span data-stu-id="b70e4-118">Modifying section size may be useful for programs that will run on smaller devices.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b70e4-119">El `-filealign` opción no está disponible en el entorno de desarrollo de Visual Studio; está disponible solo cuando se compila desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="b70e4-119">The `-filealign` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b70e4-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="b70e4-120">See also</span></span>

- [<span data-ttu-id="b70e4-121">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b70e4-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
