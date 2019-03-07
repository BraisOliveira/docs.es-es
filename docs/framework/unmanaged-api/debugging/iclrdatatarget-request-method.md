---
title: ICLRDataTarget::Request (Método)
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.Request
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::Request
helpviewer_keywords:
- ICLRDataTarget::Request method [.NET Framework debugging]
- Request method [.NET Framework debugging]
ms.assetid: 4723bd1c-eddb-4ed2-897a-010024a47e01
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bafc8be92da72cbb98f7cd47ec6632a3fbb76656
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487224"
---
# <a name="iclrdatatargetrequest-method"></a><span data-ttu-id="c2a52-102">ICLRDataTarget::Request (Método)</span><span class="sxs-lookup"><span data-stu-id="c2a52-102">ICLRDataTarget::Request Method</span></span>
<span data-ttu-id="c2a52-103">Llamado por los servicios de acceso a datos de common language runtime (CLR) para solicitar una operación, como se define en la implementación.</span><span class="sxs-lookup"><span data-stu-id="c2a52-103">Called by the common language runtime (CLR) data access services to request an operation, as defined by the implementation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2a52-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c2a52-104">Syntax</span></span>  
  
```  
HRESULT Request (  
    [in] ULONG32            reqCode,  
    [in] ULONG32            inBufferSize,  
    [in, size_is(inBufferSize)]   
        BYTE                *inBuffer,  
    [in] ULONG32            outBufferSize,  
    [out, size_is(outBufferSize)]   
        BYTE                *outBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c2a52-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c2a52-105">Parameters</span></span>  
 `reqCode`  
 <span data-ttu-id="c2a52-106">[in] Definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="c2a52-106">[in] User-defined.</span></span>  
  
 `inBufferSize`  
 <span data-ttu-id="c2a52-107">[in] El tamaño del búfer de entrada, que se usa para la solicitud entrante.</span><span class="sxs-lookup"><span data-stu-id="c2a52-107">[in] The size of the input buffer, which is used for the incoming request.</span></span>  
  
 `inBuffer`  
 <span data-ttu-id="c2a52-108">[in] Un búfer que contiene la solicitud.</span><span class="sxs-lookup"><span data-stu-id="c2a52-108">[in] A buffer containing the request.</span></span>  
  
 `outBufferSize`  
 <span data-ttu-id="c2a52-109">[in] El tamaño del búfer de salida, que se usa para la respuesta.</span><span class="sxs-lookup"><span data-stu-id="c2a52-109">[in] The size of the output buffer, which is used for the response.</span></span>  
  
 `outBuffer`  
 <span data-ttu-id="c2a52-110">[out] Un búfer que contiene la respuesta.</span><span class="sxs-lookup"><span data-stu-id="c2a52-110">[out] A Buffer containing the response.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c2a52-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c2a52-111">Remarks</span></span>  
 <span data-ttu-id="c2a52-112">El `Request` método facilita la adición de operaciones personalizadas no especificadas.</span><span class="sxs-lookup"><span data-stu-id="c2a52-112">The `Request` method facilitates the addition of unspecified custom operations.</span></span> <span data-ttu-id="c2a52-113">Es decir, este método proporciona extensibilidad sin necesidad de revisión de la definición de interfaz.</span><span class="sxs-lookup"><span data-stu-id="c2a52-113">That is, this method provides extensibility without requiring revision of the interface definition.</span></span>  
  
 <span data-ttu-id="c2a52-114">Este método lo implementa el escritor de la aplicación de depuración.</span><span class="sxs-lookup"><span data-stu-id="c2a52-114">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2a52-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c2a52-115">Requirements</span></span>  
 <span data-ttu-id="c2a52-116">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c2a52-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2a52-117">**Encabezado**: ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="c2a52-117">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="c2a52-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c2a52-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c2a52-119">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2a52-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2a52-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="c2a52-120">See also</span></span>
- [<span data-ttu-id="c2a52-121">ICLRDataTarget (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c2a52-121">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
