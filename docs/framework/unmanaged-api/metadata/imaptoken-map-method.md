---
title: IMapToken::Map (Método)
ms.date: 03/30/2017
api_name:
- IMapToken.Map
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMapToken::Map
helpviewer_keywords:
- IMapToken::Map method [.NET Framework metadata]
- Map method [.NET Framework metadata]
ms.assetid: b9b4bf2f-1098-43d6-9619-a99b4bda1940
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a85dc586b0c08fabdd34c018e82314c9003eeded
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59171020"
---
# <a name="imaptokenmap-method"></a><span data-ttu-id="047b4-102">IMapToken::Map (Método)</span><span class="sxs-lookup"><span data-stu-id="047b4-102">IMapToken::Map Method</span></span>
<span data-ttu-id="047b4-103">Asigna una relación entre los ensamblados utilizando firmas de metadatos.</span><span class="sxs-lookup"><span data-stu-id="047b4-103">Maps a relationship between the assemblies using metadata signatures.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="047b4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="047b4-104">Syntax</span></span>  
  
```  
HRESULT Map (  
    [in]  mdToken tkImp,   
    [in]  mdToken tkEmit  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="047b4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="047b4-105">Parameters</span></span>  
 `tkImp`  
 <span data-ttu-id="047b4-106">[in] El token de metadatos que representa el objeto de código importados.</span><span class="sxs-lookup"><span data-stu-id="047b4-106">[in] The metadata token that represents the imported code object.</span></span>  
  
 `tkEmit`  
 <span data-ttu-id="047b4-107">[in] El token de metadatos que representa el objeto de código emitido.</span><span class="sxs-lookup"><span data-stu-id="047b4-107">[in] The metadata token that represents the emitted code object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="047b4-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="047b4-108">Remarks</span></span>  
 <span data-ttu-id="047b4-109">Cuando el token volver a asignar se produce durante una combinación, el token original se limita el ámbito de metadatos importados (origen) y el nuevo token se enfoca en el ámbito de metadatos emitido (destino).</span><span class="sxs-lookup"><span data-stu-id="047b4-109">When the token re-map occurs during a merge, the original token is scoped in the imported (source) metadata scope and the new token is scoped in the emitted (target) metadata scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="047b4-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="047b4-110">Requirements</span></span>  
 <span data-ttu-id="047b4-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="047b4-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="047b4-112">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="047b4-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="047b4-113">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="047b4-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="047b4-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="047b4-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="047b4-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="047b4-115">See also</span></span>

- [<span data-ttu-id="047b4-116">IMapToken (interfaz)</span><span class="sxs-lookup"><span data-stu-id="047b4-116">IMapToken Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md)
