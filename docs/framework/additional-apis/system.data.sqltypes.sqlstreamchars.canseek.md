---
title: Propiedad SqlStreamChars.CanSeek (System.Data.SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/19/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.CanSeek
- System.Data.SqlTypes.SqlStreamChars.get_CanSeek
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: b85e21c6bc89d2a00ff8d302f67a3d074d5e7b8f
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65634382"
---
# <a name="sqlstreamcharscanseek-property"></a><span data-ttu-id="cc24c-102">Propiedad SqlStreamChars.CanSeek</span><span class="sxs-lookup"><span data-stu-id="cc24c-102">SqlStreamChars.CanSeek Property</span></span>

<span data-ttu-id="cc24c-103">Cuando se invalida en una clase derivada, obtiene un valor que indica si la secuencia actual admite la operación de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="cc24c-103">When overridden in a derived class, gets a value that indicates whether the current steam supports the seek operation.</span></span> <span data-ttu-id="cc24c-104">El ensamblado que contiene esta propiedad tiene una relación de confianza con SQLAccess.dll.</span><span class="sxs-lookup"><span data-stu-id="cc24c-104">The assembly that contains this property has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="cc24c-105">Está pensado para su uso con SQL Server.</span><span class="sxs-lookup"><span data-stu-id="cc24c-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="cc24c-106">Para otras bases de datos, utilice el mecanismo de hospedaje proporcionado por esa base de datos.</span><span class="sxs-lookup"><span data-stu-id="cc24c-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public abstract bool CanSeek { get; }
```

## <a name="property-value"></a><span data-ttu-id="cc24c-107">Valor de propiedad</span><span class="sxs-lookup"><span data-stu-id="cc24c-107">Property value</span></span>

<xref:System.Boolean>\
<span data-ttu-id="cc24c-108">`true` Si la secuencia actual admite la operación de búsqueda; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="cc24c-108">`true` if the current steam supports the seek operation; otherwise, `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="cc24c-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cc24c-109">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="cc24c-110">El `SqlStreamChars.CanSeek` propiedad es privada y no está pensada para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="cc24c-110">The `SqlStreamChars.CanSeek` property is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="cc24c-111">Microsoft no admite el uso de este campo en una aplicación de producción bajo ninguna circunstancia.</span><span class="sxs-lookup"><span data-stu-id="cc24c-111">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="cc24c-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cc24c-112">Requirements</span></span>

<span data-ttu-id="cc24c-113">**Espacio de nombres:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="cc24c-113">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="cc24c-114">**Ensamblado:** System.Data (en System.Data.dll)</span><span class="sxs-lookup"><span data-stu-id="cc24c-114">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="cc24c-115">**Versiones de .NET framework:** Disponible desde la versión 2.0.</span><span class="sxs-lookup"><span data-stu-id="cc24c-115">**.NET Framework versions:** Available since 2.0.</span></span>
