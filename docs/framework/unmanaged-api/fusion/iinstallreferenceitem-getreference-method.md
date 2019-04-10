---
title: IInstallReferenceItem::GetReference (Método)
ms.date: 03/30/2017
api_name:
- IInstallReferenceItem.GetReference
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IInstallReferenceItem::GetReference
helpviewer_keywords:
- IInstallReferenceItem::GetReference method [.NET Framework fusion]
- GetReference method [.NET Framework fusion]
ms.assetid: 8960332f-c98a-405a-ba92-7003de0c1187
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cd0a554535122b81f5812102c7951f56b294796a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59213368"
---
# <a name="iinstallreferenceitemgetreference-method"></a><span data-ttu-id="56e72-102">IInstallReferenceItem::GetReference (Método)</span><span class="sxs-lookup"><span data-stu-id="56e72-102">IInstallReferenceItem::GetReference Method</span></span>
<span data-ttu-id="56e72-103">Obtiene un puntero a la [FUSION_INSTALL_REFERENCE](../../../../docs/framework/unmanaged-api/fusion/fusion-install-reference-structure.md) estructura representada por este [IInstallReferenceItem](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md) objeto.</span><span class="sxs-lookup"><span data-stu-id="56e72-103">Gets a pointer to the [FUSION_INSTALL_REFERENCE](../../../../docs/framework/unmanaged-api/fusion/fusion-install-reference-structure.md) structure represented by this [IInstallReferenceItem](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56e72-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="56e72-104">Syntax</span></span>  
  
```  
HRESULT GetReference (  
    [out] LPFUSION_INSTALL_REFERENCE *ppRefData,  
    [in]  DWORD dwFlags,  
    [in]  LPVOID pvReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="56e72-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="56e72-105">Parameters</span></span>  
 `ppRefData`  
 <span data-ttu-id="56e72-106">[out] El valor devuelto `FUSION_INSTALL_REFERENCE` puntero.</span><span class="sxs-lookup"><span data-stu-id="56e72-106">[out] The returned `FUSION_INSTALL_REFERENCE` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="56e72-107">[in] Reservado para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="56e72-107">[in] Reserved for future extensibility.</span></span> `dwFlags` <span data-ttu-id="56e72-108">debe ser 0 (cero).</span><span class="sxs-lookup"><span data-stu-id="56e72-108">must be 0 (zero).</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="56e72-109">[in] Reservado para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="56e72-109">[in] Reserved for future extensibility.</span></span> `pvReserved` <span data-ttu-id="56e72-110">debe ser una referencia nula.</span><span class="sxs-lookup"><span data-stu-id="56e72-110">must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="56e72-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="56e72-111">Requirements</span></span>  
 <span data-ttu-id="56e72-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="56e72-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="56e72-113">**Encabezado**: Fusion.h</span><span class="sxs-lookup"><span data-stu-id="56e72-113">**Header:** Fusion.h</span></span>  
  
 **<span data-ttu-id="56e72-114">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="56e72-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="56e72-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="56e72-115">See also</span></span>

- [<span data-ttu-id="56e72-116">IInstallReferenceItem (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="56e72-116">IInstallReferenceItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md)
- [<span data-ttu-id="56e72-117">FUSION_INSTALL_REFERENCE (Estructura)</span><span class="sxs-lookup"><span data-stu-id="56e72-117">FUSION_INSTALL_REFERENCE Structure</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-install-reference-structure.md)
