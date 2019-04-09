---
title: ICorDebugCode::GetEnCRemapSequencePoints (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetEnCRemapSequencePoints
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetEnCRemapSequencePoints
helpviewer_keywords:
- GetEnCRemapSequencePoints method [.NET Framework debugging]
- ICorDebugCode::GetEnCRemapSequencePoints method [.NET Framework debugging]
ms.assetid: 8463a98a-de4a-418e-beb0-9611885ae6b0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 785defaa69609fc30852be9996531e6063586ceb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59092388"
---
# <a name="icordebugcodegetencremapsequencepoints-method"></a><span data-ttu-id="9d53b-102">ICorDebugCode::GetEnCRemapSequencePoints (Método)</span><span class="sxs-lookup"><span data-stu-id="9d53b-102">ICorDebugCode::GetEnCRemapSequencePoints Method</span></span>
<span data-ttu-id="9d53b-103">Este método no se implementa en la versión actual de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9d53b-103">This method is not implemented in the current version of the .NET Framework.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d53b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9d53b-104">Syntax</span></span>  
  
```  
HRESULT GetEnCRemapSequencePoints(  
    [in] ULONG32 cMap,  
    [out] ULONG32 *pcMap,  
    [out, size_is(cMap), length_is(*pcMap)]  
        ULONG32 offsets[]  
);  
```  
  
## <a name="see-also"></a><span data-ttu-id="9d53b-105">Vea también</span><span class="sxs-lookup"><span data-stu-id="9d53b-105">See also</span></span>
