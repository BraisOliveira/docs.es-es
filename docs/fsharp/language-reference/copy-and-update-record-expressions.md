---
title: Expresiones de registro de copia y actualización
description: Obtenga información sobre cómo escribir un "copiar y actualizar registro expression" que copia un registro, actualizaciones especifica los campos y devuelve el registro actualizado.
author: ChrSteinert
ms.date: 06/04/2016
ms.openlocfilehash: 7657b0295c9437890baea258295f9e9ab10073dd
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65645581"
---
# <a name="copy-and-update-record-expressions"></a><span data-ttu-id="5ff66-103">Expresiones de registro de copia y actualización</span><span class="sxs-lookup"><span data-stu-id="5ff66-103">Copy and Update Record Expressions</span></span>

<span data-ttu-id="5ff66-104">Un *copiar y actualizar la expresión de registro* es una expresión que se copia un registro existente, actualiza los campos especificados y devuelve el registro actualizado.</span><span class="sxs-lookup"><span data-stu-id="5ff66-104">A *copy and update record expression* is an expression that copies an existing record, updates specified fields, and returns the updated record.</span></span>

## <a name="syntax"></a><span data-ttu-id="5ff66-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5ff66-105">Syntax</span></span>

```fsharp
{ record-name with
    updated-member-definitions }
```

## <a name="remarks"></a><span data-ttu-id="5ff66-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5ff66-106">Remarks</span></span>

<span data-ttu-id="5ff66-107">Los registros son inmutables de manera predeterminada, por lo que no es posible ninguna actualización para un registro existente.</span><span class="sxs-lookup"><span data-stu-id="5ff66-107">Records are immutable by default, so that there is no update to an existing record possible.</span></span> <span data-ttu-id="5ff66-108">Para crear un registro actualizado de todos los campos de un registro deberá especificarse de nuevo.</span><span class="sxs-lookup"><span data-stu-id="5ff66-108">To create an updated record all the fields of a record would have to be specified again.</span></span> <span data-ttu-id="5ff66-109">Para simplificar esta tarea un *copiar y actualizar la expresión de registro* se puede usar.</span><span class="sxs-lookup"><span data-stu-id="5ff66-109">To simplify this task a *copy and update record expression* can be used.</span></span> <span data-ttu-id="5ff66-110">Esta expresión toma un registro existente, se crea uno nuevo del mismo tipo mediante el uso de los campos especificados de la expresión y el especificado por la expresión de campo que falta.</span><span class="sxs-lookup"><span data-stu-id="5ff66-110">This expression takes an existing record, creates a new one of the same type by using specified fields from the expression and the missing field specified by the expression.</span></span>
<span data-ttu-id="5ff66-111">Esto puede ser útil cuando tiene que copiar un registro existente y posiblemente cambiar algunos de los valores de campo.</span><span class="sxs-lookup"><span data-stu-id="5ff66-111">This can be useful when you have to copy an existing record, and possibly change some of the field values.</span></span>

<span data-ttu-id="5ff66-112">Tomemos como ejemplo un registro recién creado.</span><span class="sxs-lookup"><span data-stu-id="5ff66-112">Take for instance a newly created record.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

<span data-ttu-id="5ff66-113">Si desea actualizar solo en el campo de ese registro se podría utilizar el *copiar y actualizar la expresión de registro* similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="5ff66-113">If you were to update only on field of that record you could use the *copy and update record expression* like the following:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

## <a name="see-also"></a><span data-ttu-id="5ff66-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="5ff66-114">See also</span></span>

- [<span data-ttu-id="5ff66-115">Registros</span><span class="sxs-lookup"><span data-stu-id="5ff66-115">Records</span></span>](records.md)
- [<span data-ttu-id="5ff66-116">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="5ff66-116">F# Language Reference</span></span>](index.md)
