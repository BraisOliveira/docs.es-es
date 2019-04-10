---
title: ISymUnmanagedScope (Interfaz)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope
helpviewer_keywords:
- ISymUnmanagedScope interface [.NET Framework debugging]
ms.assetid: 3db7a220-cfe9-4810-8ca8-a094bb8e0f5b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 809368ea19528a7ce00d4fcada06ef5724eb79a6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59228164"
---
# <a name="isymunmanagedscope-interface"></a><span data-ttu-id="70db3-102">ISymUnmanagedScope (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="70db3-102">ISymUnmanagedScope Interface</span></span>
<span data-ttu-id="70db3-103">Representa un ámbito léxico dentro de un método.</span><span class="sxs-lookup"><span data-stu-id="70db3-103">Represents a lexical scope within a method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="70db3-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="70db3-104">Methods</span></span>  
  
|<span data-ttu-id="70db3-105">Método</span><span class="sxs-lookup"><span data-stu-id="70db3-105">Method</span></span>|<span data-ttu-id="70db3-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="70db3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="70db3-107">Método GetChildren</span><span class="sxs-lookup"><span data-stu-id="70db3-107">GetChildren Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getchildren-method.md)|<span data-ttu-id="70db3-108">Obtiene a los elementos secundarios de este ámbito.</span><span class="sxs-lookup"><span data-stu-id="70db3-108">Gets the children of this scope.</span></span>|  
|[<span data-ttu-id="70db3-109">Método GetEndOffset</span><span class="sxs-lookup"><span data-stu-id="70db3-109">GetEndOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getendoffset-method.md)|<span data-ttu-id="70db3-110">Obtiene el desplazamiento final de este ámbito.</span><span class="sxs-lookup"><span data-stu-id="70db3-110">Gets the end offset for this scope.</span></span>|  
|[<span data-ttu-id="70db3-111">Método GetLocalCount</span><span class="sxs-lookup"><span data-stu-id="70db3-111">GetLocalCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getlocalcount-method.md)|<span data-ttu-id="70db3-112">Obtiene un recuento de las variables locales definidas en este ámbito.</span><span class="sxs-lookup"><span data-stu-id="70db3-112">Gets a count of the local variables defined within this scope.</span></span>|  
|[<span data-ttu-id="70db3-113">Método GetLocals</span><span class="sxs-lookup"><span data-stu-id="70db3-113">GetLocals Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getlocals-method.md)|<span data-ttu-id="70db3-114">Obtiene las variables locales definidas en este ámbito.</span><span class="sxs-lookup"><span data-stu-id="70db3-114">Gets the local variables defined within this scope.</span></span>|  
|[<span data-ttu-id="70db3-115">Método GetMethod</span><span class="sxs-lookup"><span data-stu-id="70db3-115">GetMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getmethod-method.md)|<span data-ttu-id="70db3-116">Obtiene el método que contiene este ámbito.</span><span class="sxs-lookup"><span data-stu-id="70db3-116">Gets the method that contains this scope.</span></span>|  
|[<span data-ttu-id="70db3-117">Método GetNamespaces</span><span class="sxs-lookup"><span data-stu-id="70db3-117">GetNamespaces Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getnamespaces-method.md)|<span data-ttu-id="70db3-118">Obtiene los espacios de nombres que se utilizan dentro de este ámbito.</span><span class="sxs-lookup"><span data-stu-id="70db3-118">Gets the namespaces that are being used within this scope.</span></span>|  
|[<span data-ttu-id="70db3-119">Método GetParent</span><span class="sxs-lookup"><span data-stu-id="70db3-119">GetParent Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getparent-method.md)|<span data-ttu-id="70db3-120">Obtiene el ámbito primario de este ámbito.</span><span class="sxs-lookup"><span data-stu-id="70db3-120">Gets the parent scope of this scope.</span></span>|  
|[<span data-ttu-id="70db3-121">Método GetStartOffset</span><span class="sxs-lookup"><span data-stu-id="70db3-121">GetStartOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getstartoffset-method.md)|<span data-ttu-id="70db3-122">Obtiene el desplazamiento inicial de este ámbito.</span><span class="sxs-lookup"><span data-stu-id="70db3-122">Gets the start offset for this scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="70db3-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="70db3-123">Requirements</span></span>  
 <span data-ttu-id="70db3-124">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="70db3-124">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70db3-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="70db3-125">See also</span></span>

- [<span data-ttu-id="70db3-126">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="70db3-126">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="70db3-127">ISymUnmanagedScope2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="70db3-127">ISymUnmanagedScope2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)
