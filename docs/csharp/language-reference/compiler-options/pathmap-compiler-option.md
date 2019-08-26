---
title: -pathmap (opciones del compilador de C#)
ms.date: 05/16/2018
f1_keywords:
- /pathmap
helpviewer_keywords:
- -pathmap compiler option [C#]
- pathmap compiler option [C#]
- /pathmap compiler option [C#]
ms.openlocfilehash: 48e96d2ec2ccbea83d573c0eb3630b1591c407a9
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/19/2019
ms.locfileid: "69606627"
---
# <a name="-pathmap-c-compiler-options"></a><span data-ttu-id="4afcf-102">-pathmap (opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="4afcf-102">-pathmap (C# Compiler Options)</span></span>

<span data-ttu-id="4afcf-103">La opción **-pathmap** del compilador especifica cómo asignar rutas físicas a los nombres de rutas de acceso de origen generados por el compilador.</span><span class="sxs-lookup"><span data-stu-id="4afcf-103">The **-pathmap** compiler option specifies how to map physical paths to source path names output by the compiler.</span></span>

## <a name="syntax"></a><span data-ttu-id="4afcf-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4afcf-104">Syntax</span></span>

```console
-pathmap:path1=sourcePath1,path2=sourcePath2
```

## <a name="arguments"></a><span data-ttu-id="4afcf-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="4afcf-105">Arguments</span></span>

 <span data-ttu-id="4afcf-106">`path1` La ruta de acceso completa a los archivos de origen en el entorno actual</span><span class="sxs-lookup"><span data-stu-id="4afcf-106">`path1` The full path to the source files in the current environment</span></span>

 <span data-ttu-id="4afcf-107">`sourcePath1` La ruta de acceso de origen sustituida por `path1` en cualquier archivo de salida</span><span class="sxs-lookup"><span data-stu-id="4afcf-107">`sourcePath1` The source path substituted for `path1` in any output files.</span></span>

<span data-ttu-id="4afcf-108">Para especificar varias rutas de acceso de origen asignadas, sepárelas con una coma.</span><span class="sxs-lookup"><span data-stu-id="4afcf-108">To specify multiple mapped source paths, separate each with a comma.</span></span>

## <a name="remarks"></a><span data-ttu-id="4afcf-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4afcf-109">Remarks</span></span>

<span data-ttu-id="4afcf-110">El compilador escribe la ruta de acceso de origen en la salida por las razones siguientes:</span><span class="sxs-lookup"><span data-stu-id="4afcf-110">The compiler writes the source path into its output for the following reasons:</span></span>

1. <span data-ttu-id="4afcf-111">La ruta de acceso de origen se sustituye por un argumento cuando se aplica <xref:System.Runtime.CompilerServices.CallerFilePathAttribute> a un parámetro opcional.</span><span class="sxs-lookup"><span data-stu-id="4afcf-111">The source path is substituted for an argument when the <xref:System.Runtime.CompilerServices.CallerFilePathAttribute> is applied to an optional parameter.</span></span>
1. <span data-ttu-id="4afcf-112">La ruta de acceso de origen se inserta en un archivo PDB.</span><span class="sxs-lookup"><span data-stu-id="4afcf-112">The source path is embedded in a PDB file.</span></span>
1. <span data-ttu-id="4afcf-113">La ruta de acceso del archivo PDB se inserta en un archivo PE (ejecutable portable).</span><span class="sxs-lookup"><span data-stu-id="4afcf-113">The path of the PDB file is embedded into a PE (portable executable) file.</span></span>

<span data-ttu-id="4afcf-114">Esta opción asigna cada ruta de acceso física en la máquina donde el compilador se ejecuta a una ruta de acceso correspondiente que debe escribirse en los archivos de salida.</span><span class="sxs-lookup"><span data-stu-id="4afcf-114">This option maps each physical path on the machine where the compiler runs to a corresponding path that should be written in the output files.</span></span>

## <a name="example"></a><span data-ttu-id="4afcf-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4afcf-115">Example</span></span>

<span data-ttu-id="4afcf-116">Compile `t.cs` en el directorio **C:\\work\\test** y asigne ese directorio a **\publish** en la salida:</span><span class="sxs-lookup"><span data-stu-id="4afcf-116">Compile `t.cs` in the directory **C:\\work\\tests** and map that directory to **\publish** in the output:</span></span>

```console
csc -pathmap:C:\work\tests=\publish t.cs
```

## <a name="see-also"></a><span data-ttu-id="4afcf-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="4afcf-117">See also</span></span>

- [<span data-ttu-id="4afcf-118">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="4afcf-118">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="4afcf-119">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="4afcf-119">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
