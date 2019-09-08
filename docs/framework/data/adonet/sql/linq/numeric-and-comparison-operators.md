---
title: Operadores numéricos y de comparación
ms.date: 03/30/2017
ms.assetid: 25b4a26a-06f2-4f80-87a9-76705ed46197
ms.openlocfilehash: 7e7af725864aa191f092055fa32b403093321aa5
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781287"
---
# <a name="numeric-and-comparison-operators"></a><span data-ttu-id="4bd37-102">Operadores numéricos y de comparación</span><span class="sxs-lookup"><span data-stu-id="4bd37-102">Numeric and Comparison Operators</span></span>

<span data-ttu-id="4bd37-103">Los operadores aritméticos y de comparación funcionan como cabía esperar en Common Language Runtime (CLR), con las siguientes excepciones:</span><span class="sxs-lookup"><span data-stu-id="4bd37-103">Arithmetic and comparison operators work as expected in the common language runtime (CLR) except as follows:</span></span>

- <span data-ttu-id="4bd37-104">SQL no admite al operador de módulo en números de punto flotante.</span><span class="sxs-lookup"><span data-stu-id="4bd37-104">SQL does not support the modulus operator on floating-point numbers.</span></span>

- <span data-ttu-id="4bd37-105">SQL no admite la aritmética no comprobada.</span><span class="sxs-lookup"><span data-stu-id="4bd37-105">SQL does not support unchecked arithmetic.</span></span>

- <span data-ttu-id="4bd37-106">Los operadores de incremento y decremento producen efectos no deseados cuando se utilizan en expresiones que no se pueden replicar en SQL y son, por tanto, incompatibles.</span><span class="sxs-lookup"><span data-stu-id="4bd37-106">Increment and decrement operators cause side-effects when you use them in expressions that cannot be replicated in SQL and are, therefore, not supported.</span></span>

## <a name="supported-operators"></a><span data-ttu-id="4bd37-107">Operadores compatibles</span><span class="sxs-lookup"><span data-stu-id="4bd37-107">Supported Operators</span></span>

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="4bd37-108">admite los operadores siguientes.</span><span class="sxs-lookup"><span data-stu-id="4bd37-108">supports the following operators.</span></span>

- <span data-ttu-id="4bd37-109">Operadores aritméticos básicos:</span><span class="sxs-lookup"><span data-stu-id="4bd37-109">Basic arithmetic operators:</span></span>

  - `+`

  - <span data-ttu-id="4bd37-110">`-` (resta)</span><span class="sxs-lookup"><span data-stu-id="4bd37-110">`-` (subtraction)</span></span>

  - `*`

  - `/`

  - <span data-ttu-id="4bd37-111">División de enteros en Visual Basic (`\`)</span><span class="sxs-lookup"><span data-stu-id="4bd37-111">Visual Basic integer division (`\`)</span></span>

  - <span data-ttu-id="4bd37-112">`%` (Visual Basic `Mod`)</span><span class="sxs-lookup"><span data-stu-id="4bd37-112">`%` (Visual Basic `Mod`)</span></span>

  - `<<`

  - `>>`

  - <span data-ttu-id="4bd37-113">`-` (negación unaria)</span><span class="sxs-lookup"><span data-stu-id="4bd37-113">`-` (unary negation)</span></span>

- <span data-ttu-id="4bd37-114">Operadores de comparación básicos:</span><span class="sxs-lookup"><span data-stu-id="4bd37-114">Basic comparison operators:</span></span>

  - <span data-ttu-id="4bd37-115">`=` en Visual Basic y `==` en C#</span><span class="sxs-lookup"><span data-stu-id="4bd37-115">Visual Basic `=` and C# `==`</span></span>

  - <span data-ttu-id="4bd37-116">`<>` en Visual Basic y `!=` en C#</span><span class="sxs-lookup"><span data-stu-id="4bd37-116">Visual Basic `<>` and C# `!=`</span></span>

  - <span data-ttu-id="4bd37-117">`Is/IsNot` en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4bd37-117">Visual Basic `Is/IsNot`</span></span>

  - `<`

  - `<=`

  - `>`

  - `>=`

## <a name="see-also"></a><span data-ttu-id="4bd37-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="4bd37-118">See also</span></span>

- [<span data-ttu-id="4bd37-119">Tipos de datos y funciones</span><span class="sxs-lookup"><span data-stu-id="4bd37-119">Data Types and Functions</span></span>](data-types-and-functions.md)
- [<span data-ttu-id="4bd37-120">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="4bd37-120">C# Operators</span></span>](../../../../../csharp/language-reference/operators/index.md)
- [<span data-ttu-id="4bd37-121">Operadores</span><span class="sxs-lookup"><span data-stu-id="4bd37-121">Operators</span></span>](../../../../../visual-basic/language-reference/operators/index.md)
