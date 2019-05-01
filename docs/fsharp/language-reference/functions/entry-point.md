---
title: Punto de entrada
description: Aprenda a configurar el punto de entrada un F# programa que se compila como un archivo ejecutable, dónde formalmente comienza la ejecución.
ms.date: 05/16/2016
ms.openlocfilehash: 915ab17b9a4fc7fd4d0ae344cb273b1d348a02f1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61996832"
---
# <a name="entry-point"></a><span data-ttu-id="f10f0-103">Punto de entrada</span><span class="sxs-lookup"><span data-stu-id="f10f0-103">Entry Point</span></span>

<span data-ttu-id="f10f0-104">En este tema se describe el método que use para establecer el punto de entrada en un F# programa.</span><span class="sxs-lookup"><span data-stu-id="f10f0-104">This topic describes the method that you use to set the entry point to an F# program.</span></span>

## <a name="syntax"></a><span data-ttu-id="f10f0-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f10f0-105">Syntax</span></span>

```fsharp
[<EntryPoint>]
let-function-binding
```

## <a name="remarks"></a><span data-ttu-id="f10f0-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f10f0-106">Remarks</span></span>

<span data-ttu-id="f10f0-107">En la sintaxis anterior, *enlace de función permiten* es la definición de una función en un `let` enlace.</span><span class="sxs-lookup"><span data-stu-id="f10f0-107">In the previous syntax, *let-function-binding* is the definition of a function in a `let` binding.</span></span>

<span data-ttu-id="f10f0-108">El punto de entrada a un programa que se compila como un archivo ejecutable es dónde formalmente comienza la ejecución.</span><span class="sxs-lookup"><span data-stu-id="f10f0-108">The entry point to a program that is compiled as an executable file is where execution formally starts.</span></span> <span data-ttu-id="f10f0-109">Especifique el punto de entrada a un F# aplicación aplicando la `EntryPoint` atributo para el programa `main` función.</span><span class="sxs-lookup"><span data-stu-id="f10f0-109">You specify the entry point to an F# application by applying the `EntryPoint` attribute to the program's `main` function.</span></span> <span data-ttu-id="f10f0-110">Esta función (creada mediante un `let` enlace) debe ser la última función en el último archivo compilado.</span><span class="sxs-lookup"><span data-stu-id="f10f0-110">This function (created by using a `let` binding) must be the last function in the last compiled file.</span></span> <span data-ttu-id="f10f0-111">El último archivo compilado es el último archivo del proyecto o el último archivo que se pasa a la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="f10f0-111">The last compiled file is the last file in the project or the last file that is passed to the command line.</span></span>

<span data-ttu-id="f10f0-112">La función de punto de entrada tiene el tipo `string array -> int`.</span><span class="sxs-lookup"><span data-stu-id="f10f0-112">The entry point function has type `string array -> int`.</span></span> <span data-ttu-id="f10f0-113">Los argumentos proporcionados en la línea de comandos se pasan a la `main` función en la matriz de cadenas.</span><span class="sxs-lookup"><span data-stu-id="f10f0-113">The arguments provided on the command line are passed to the `main` function in the array of strings.</span></span> <span data-ttu-id="f10f0-114">El primer elemento de la matriz es el primer argumento; el nombre del archivo ejecutable no se incluye en la matriz, como en otros lenguajes.</span><span class="sxs-lookup"><span data-stu-id="f10f0-114">The first element of the array is the first argument; the name of the executable file is not included in the array, as it is in some other languages.</span></span> <span data-ttu-id="f10f0-115">El valor devuelto se utiliza como el código de salida para el proceso.</span><span class="sxs-lookup"><span data-stu-id="f10f0-115">The return value is used as the exit code for the process.</span></span> <span data-ttu-id="f10f0-116">Cero indica normalmente correctamente; valores distintos de cero indican un error.</span><span class="sxs-lookup"><span data-stu-id="f10f0-116">Zero usually indicates success; nonzero values indicate an error.</span></span> <span data-ttu-id="f10f0-117">No hay ninguna convención para el significado específico de los códigos de retorno distinto de cero; los significados de los códigos de retorno son específicos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f10f0-117">There is no convention for the specific meaning of nonzero return codes; the meanings of the return codes are application-specific.</span></span>

<span data-ttu-id="f10f0-118">El ejemplo siguiente muestra un sencillo `main` función.</span><span class="sxs-lookup"><span data-stu-id="f10f0-118">The following example illustrates a simple `main` function.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/entry-point/snippet501.fs)]

<span data-ttu-id="f10f0-119">Cuando se ejecuta este código con la línea de comandos `EntryPoint.exe 1 2 3`, el resultado es como sigue.</span><span class="sxs-lookup"><span data-stu-id="f10f0-119">When this code is executed with the command line `EntryPoint.exe 1 2 3`, the output is as follows.</span></span>

```console
Arguments passed to function : [|"1"; "2"; "3"|]
```

## <a name="implicit-entry-point"></a><span data-ttu-id="f10f0-120">Punto de entrada implícito</span><span class="sxs-lookup"><span data-stu-id="f10f0-120">Implicit Entry Point</span></span>

<span data-ttu-id="f10f0-121">Cuando un programa no tiene ningún **EntryPoint** atributo que indica el punto de entrada, los enlaces de nivel superior en el último archivo para compilarse de forma explícita se utilizan como punto de entrada.</span><span class="sxs-lookup"><span data-stu-id="f10f0-121">When a program has no **EntryPoint** attribute that explicitly indicates the entry point, the top level bindings in the last file to be compiled are used as the entry point.</span></span>

## <a name="see-also"></a><span data-ttu-id="f10f0-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="f10f0-122">See also</span></span>

- [<span data-ttu-id="f10f0-123">Funciones</span><span class="sxs-lookup"><span data-stu-id="f10f0-123">Functions</span></span>](index.md)
- [<span data-ttu-id="f10f0-124">Enlaces let</span><span class="sxs-lookup"><span data-stu-id="f10f0-124">let Bindings</span></span>](let-bindings.md)