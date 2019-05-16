---
title: Tipos básicos
description: Detectar los tipos básicos fundamentales que se usan en el F# lenguaje.
ms.date: 07/09/2018
ms.openlocfilehash: fb9f275490cb402ff36e959774cd65450de77115
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65645588"
---
# <a name="basic-types"></a><span data-ttu-id="fdef6-103">Tipos básicos</span><span class="sxs-lookup"><span data-stu-id="fdef6-103">Basic types</span></span>

<span data-ttu-id="fdef6-104">Este tema enumeran los tipos básicos que se definen en el F# lenguaje.</span><span class="sxs-lookup"><span data-stu-id="fdef6-104">This topic lists the basic types that are defined in the F# language.</span></span> <span data-ttu-id="fdef6-105">Estos tipos son las más importantes en F#, forman la base de casi todos F# programa.</span><span class="sxs-lookup"><span data-stu-id="fdef6-105">These types are the most fundamental in F#, forming the basis of nearly every F# program.</span></span> <span data-ttu-id="fdef6-106">Son un superconjunto de los tipos primitivos. NET.</span><span class="sxs-lookup"><span data-stu-id="fdef6-106">They are a superset of .NET primitive types.</span></span>

|<span data-ttu-id="fdef6-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="fdef6-107">Type</span></span>|<span data-ttu-id="fdef6-108">Tipo de .NET</span><span class="sxs-lookup"><span data-stu-id="fdef6-108">.NET type</span></span>|<span data-ttu-id="fdef6-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="fdef6-109">Description</span></span>|
|----|---------|-----------|
|`bool`|<xref:System.Boolean>|<span data-ttu-id="fdef6-110">Los valores posibles son `true` y `false`.</span><span class="sxs-lookup"><span data-stu-id="fdef6-110">Possible values are `true` and `false`.</span></span>|
|`byte`|<xref:System.Byte>|<span data-ttu-id="fdef6-111">Valores de 0 a 255.</span><span class="sxs-lookup"><span data-stu-id="fdef6-111">Values from 0 to 255.</span></span>|
|`sbyte`|<xref:System.SByte>|<span data-ttu-id="fdef6-112">Valores de -128 a 127.</span><span class="sxs-lookup"><span data-stu-id="fdef6-112">Values from -128 to 127.</span></span>|
|`int16`|<xref:System.Int16>|<span data-ttu-id="fdef6-113">Valores de -32768 a 32767.</span><span class="sxs-lookup"><span data-stu-id="fdef6-113">Values from -32768 to 32767.</span></span>|
|`uint16`|<xref:System.UInt16>|<span data-ttu-id="fdef6-114">Valores de 0 a 65535.</span><span class="sxs-lookup"><span data-stu-id="fdef6-114">Values from 0 to 65535.</span></span>|
|`int`|<xref:System.Int32>|<span data-ttu-id="fdef6-115">Valores entre -2.147.483.648 a 2.147.483.647.</span><span class="sxs-lookup"><span data-stu-id="fdef6-115">Values from -2,147,483,648 to 2,147,483,647.</span></span>|
|`uint32`|<xref:System.UInt32>|<span data-ttu-id="fdef6-116">Valores entre 0 y 4.294.967.295.</span><span class="sxs-lookup"><span data-stu-id="fdef6-116">Values from 0 to 4,294,967,295.</span></span>|
|`int64`|<xref:System.Int64>|<span data-ttu-id="fdef6-117">Valores comprendidos entre -9.223.372.036.854.775.808 a + 9.223.372.036.854.775.807.</span><span class="sxs-lookup"><span data-stu-id="fdef6-117">Values from -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807.</span></span>|
|`uint64`|<xref:System.UInt64>|<span data-ttu-id="fdef6-118">Valores de 0 a 18,446,744,073,709,551,615.</span><span class="sxs-lookup"><span data-stu-id="fdef6-118">Values from 0 to 18,446,744,073,709,551,615.</span></span>|
|`nativeint`|<xref:System.IntPtr>|<span data-ttu-id="fdef6-119">Un puntero nativo como un entero con signo.</span><span class="sxs-lookup"><span data-stu-id="fdef6-119">A native pointer as a signed integer.</span></span>|
|`unativeint`|<xref:System.UIntPtr>|<span data-ttu-id="fdef6-120">Un puntero nativo como un entero sin signo.</span><span class="sxs-lookup"><span data-stu-id="fdef6-120">A native pointer as an unsigned integer.</span></span>|
|`char`|<xref:System.Char>|<span data-ttu-id="fdef6-121">Valores de caracteres Unicode.</span><span class="sxs-lookup"><span data-stu-id="fdef6-121">Unicode character values.</span></span>|
|`string`|<xref:System.String>|<span data-ttu-id="fdef6-122">Texto Unicode.</span><span class="sxs-lookup"><span data-stu-id="fdef6-122">Unicode text.</span></span>|
|`decimal`|<xref:System.Decimal>|<span data-ttu-id="fdef6-123">Tipo de datos que tiene al menos 28 dígitos significativos de punto flotante.</span><span class="sxs-lookup"><span data-stu-id="fdef6-123">A floating point data type that has at least 28 significant digits.</span></span>|
|`unit`|<span data-ttu-id="fdef6-124">No aplicable</span><span class="sxs-lookup"><span data-stu-id="fdef6-124">not applicable</span></span>|<span data-ttu-id="fdef6-125">Indica la ausencia de un valor real.</span><span class="sxs-lookup"><span data-stu-id="fdef6-125">Indicates the absence of an actual value.</span></span> <span data-ttu-id="fdef6-126">El tipo tiene un único valor formal, que se indica `()`.</span><span class="sxs-lookup"><span data-stu-id="fdef6-126">The type has only one formal value, which is denoted `()`.</span></span> <span data-ttu-id="fdef6-127">El valor de unidad, `()`, a menudo se usa como marcador de posición donde se necesita un valor pero ningún valor real está disponible o que tenga sentido.</span><span class="sxs-lookup"><span data-stu-id="fdef6-127">The unit value, `()`, is often used as a placeholder where a value is needed but no real value is available or makes sense.</span></span>|
|`void`|<xref:System.Void>|<span data-ttu-id="fdef6-128">No indica que ningún tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="fdef6-128">Indicates no type or value.</span></span>|
|<span data-ttu-id="fdef6-129">`float32`, `single`</span><span class="sxs-lookup"><span data-stu-id="fdef6-129">`float32`, `single`</span></span>|<xref:System.Single>|<span data-ttu-id="fdef6-130">Tipo de punto flotante de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="fdef6-130">A 32-bit floating point type.</span></span>|
|<span data-ttu-id="fdef6-131">`float`, `double`</span><span class="sxs-lookup"><span data-stu-id="fdef6-131">`float`, `double`</span></span>|<xref:System.Double>|<span data-ttu-id="fdef6-132">Tipo de punto flotante de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="fdef6-132">A 64-bit floating point type.</span></span>|

> [!NOTE]
> <span data-ttu-id="fdef6-133">Puede realizar cálculos con números enteros demasiado grandes para el tipo de entero de 64 bits mediante el [bigint](https://msdn.microsoft.com/library/dc8be18d-4042-46c4-b136-2f21a84f6efa) tipo.</span><span class="sxs-lookup"><span data-stu-id="fdef6-133">You can perform computations with integers too big for the 64-bit integer type by using the [bigint](https://msdn.microsoft.com/library/dc8be18d-4042-46c4-b136-2f21a84f6efa) type.</span></span> <span data-ttu-id="fdef6-134">`bigint` no se considera un tipo básico; es la abreviatura de `System.Numerics.BigInteger`.</span><span class="sxs-lookup"><span data-stu-id="fdef6-134">`bigint` is not considered a basic type; it is an abbreviation for `System.Numerics.BigInteger`.</span></span>

## <a name="see-also"></a><span data-ttu-id="fdef6-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="fdef6-135">See also</span></span>

- [<span data-ttu-id="fdef6-136">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="fdef6-136">F# Language Reference</span></span>](index.md)
