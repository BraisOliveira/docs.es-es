---
title: Propiedad SqlStreamChars. IsNull (System. Data. SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/19/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.IsNull
- System.Data.SqlTypes.SqlStreamChars.get_IsNull
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: d80f653724b3ef0a1cadb69a5f72b1d9455597d6
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395731"
---
# <a name="sqlstreamcharsisnull-property"></a><span data-ttu-id="36149-102">SqlStreamChars. IsNull (propiedad)</span><span class="sxs-lookup"><span data-stu-id="36149-102">SqlStreamChars.IsNull Property</span></span>

<span data-ttu-id="36149-103">Cuando se reemplaza en una clase derivada, obtiene un valor que indica si la secuencia es `null`.</span><span class="sxs-lookup"><span data-stu-id="36149-103">When overridden in a derived class, gets a value that indicates whether the stream is `null`.</span></span> <span data-ttu-id="36149-104">El ensamblado que contiene esta propiedad tiene una relación de confianza con SQLAccess. dll.</span><span class="sxs-lookup"><span data-stu-id="36149-104">The assembly that contains this property has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="36149-105">Está pensado para su uso por SQL Server.</span><span class="sxs-lookup"><span data-stu-id="36149-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="36149-106">En el caso de otras bases de datos, use el mecanismo de hospedaje proporcionado por esa base de datos.</span><span class="sxs-lookup"><span data-stu-id="36149-106">For other databases, use the hosting mechanism provided by that database.</span></span>

## <a name="syntax"></a><span data-ttu-id="36149-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="36149-107">Syntax</span></span>

```csharp
public abstract bool IsNull { get; }
```

## <a name="property-value"></a><span data-ttu-id="36149-108">Valor de propiedad</span><span class="sxs-lookup"><span data-stu-id="36149-108">Property value</span></span>

<xref:System.Boolean>\
<span data-ttu-id="36149-109">`true` si la secuencia es `null`; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="36149-109">`true` if the stream is `null`; otherwise, `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="36149-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="36149-110">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="36149-111">La propiedad `SqlStreamChars.IsNull` es privada y no está diseñada para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="36149-111">The `SqlStreamChars.IsNull` property is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="36149-112">Microsoft no admite el uso de esta propiedad en una aplicación de producción bajo ninguna circunstancia.</span><span class="sxs-lookup"><span data-stu-id="36149-112">Microsoft does not support the use of this property in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="36149-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="36149-113">Requirements</span></span>

<span data-ttu-id="36149-114">**Espacio de nombres:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="36149-114">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="36149-115">**Ensamblado:** System. Data (en System. Data. dll)</span><span class="sxs-lookup"><span data-stu-id="36149-115">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="36149-116">**.NET Framework versiones:** Disponible desde 2,0.</span><span class="sxs-lookup"><span data-stu-id="36149-116">**.NET Framework versions:** Available since 2.0.</span></span>
