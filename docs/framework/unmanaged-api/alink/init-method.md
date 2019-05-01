---
title: Init (Método)
ms.date: 03/30/2017
api_name:
- IALink.Init
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- Init
helpviewer_keywords:
- Init method
ms.assetid: e48b5c64-049f-4f93-ad87-d07ae9cd5845
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 60602462376543fe934bb3c58bc4988fa8ab34bf
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61949115"
---
# <a name="init-method"></a><span data-ttu-id="95814-102">Init (Método)</span><span class="sxs-lookup"><span data-stu-id="95814-102">Init Method</span></span>
<span data-ttu-id="95814-103">Prepara los objetos que implementan la [IALink (interfaz)](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md) para su uso.</span><span class="sxs-lookup"><span data-stu-id="95814-103">Prepares objects implementing the [IALink Interface](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md) for use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95814-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="95814-104">Syntax</span></span>  
  
```  
HRESULT Init(  
    IMetaDataDispenserEx* pDispenser,  
    IMetaDataError* pErrorHandler  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="95814-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="95814-105">Parameters</span></span>  
 `pDispenser`  
 <span data-ttu-id="95814-106">[IMetaDataDispenserEx (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md) puntero en el dispensador de metadatos.</span><span class="sxs-lookup"><span data-stu-id="95814-106">[IMetaDataDispenserEx Interface](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md) pointer to the metadata dispenser.</span></span>  
  
 `pErrorHandler`  
 <span data-ttu-id="95814-107">[IMetaDataError (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md) puntero a una interfaz de control de errores opcional.</span><span class="sxs-lookup"><span data-stu-id="95814-107">[IMetaDataError Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md) pointer to an optional error handling interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="95814-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="95814-108">Return Value</span></span>  
 <span data-ttu-id="95814-109">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="95814-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95814-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="95814-110">Requirements</span></span>  
 <span data-ttu-id="95814-111">Requiere alink.h</span><span class="sxs-lookup"><span data-stu-id="95814-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95814-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="95814-112">See also</span></span>

- [<span data-ttu-id="95814-113">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="95814-113">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="95814-114">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="95814-114">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="95814-115">API de ALink</span><span class="sxs-lookup"><span data-stu-id="95814-115">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
