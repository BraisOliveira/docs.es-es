---
title: CLRDataCreateInstance (Función)
ms.date: 03/30/2017
api_name:
- CLRDataCreateInstance
api_location:
- mscordbi.dll
- mscordacwks.dll
api_type:
- COM
f1_keywords:
- CLRDataCreateInstance
helpviewer_keywords:
- CLRDataCreateInstance function [.NET Framework debugging]
ms.assetid: 440bad90-5a88-45e7-9157-4596801d8d19
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 73a4a8a2fc737bbf4b49ca859f0549ca7efd54a2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59089775"
---
# <a name="clrdatacreateinstance-function"></a><span data-ttu-id="3b1b1-102">CLRDataCreateInstance (Función)</span><span class="sxs-lookup"><span data-stu-id="3b1b1-102">CLRDataCreateInstance Function</span></span>
<span data-ttu-id="3b1b1-103">Crea un objeto de interfaz para el elemento de destino especificado.</span><span class="sxs-lookup"><span data-stu-id="3b1b1-103">Creates an interface object for the specified target item.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b1b1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3b1b1-104">Syntax</span></span>  
  
```  
HRESULT CLRDataCreateInstance (  
    [in]  REFIID           iid,   
    [in]  ICLRDataTarget  *target,   
    [out] void           **iface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3b1b1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3b1b1-105">Parameters</span></span>  
 `iid`  
 <span data-ttu-id="3b1b1-106">[in] El identificador de la interfaz de creación de instancias.</span><span class="sxs-lookup"><span data-stu-id="3b1b1-106">[in] The identifier of the interface to be instantiated.</span></span>  
  
 `target`  
 <span data-ttu-id="3b1b1-107">[in] Un puntero a un usuario implementa [ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md) objeto que representa el elemento de destino para el que se va a crear el objeto de interfaz.</span><span class="sxs-lookup"><span data-stu-id="3b1b1-107">[in] A pointer to a user-implemented [ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md) object that represents the target item for which to create the interface object.</span></span>  
  
 `iface`  
 <span data-ttu-id="3b1b1-108">[out] Un puntero a la dirección del objeto de interfaz devuelto.</span><span class="sxs-lookup"><span data-stu-id="3b1b1-108">[out] A pointer to the address of the returned interface object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3b1b1-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3b1b1-109">Remarks</span></span>  
 <span data-ttu-id="3b1b1-110">La `ICLRDataTarget` objeto es implementado por el sistema de escritura de la aplicación de depuración.</span><span class="sxs-lookup"><span data-stu-id="3b1b1-110">The `ICLRDataTarget` object is implemented by the writer of the debugging application.</span></span> <span data-ttu-id="3b1b1-111">La implementación depende del tipo de elemento de destino que se va a representar.</span><span class="sxs-lookup"><span data-stu-id="3b1b1-111">The implementation depends on the type of target item being represented.</span></span> <span data-ttu-id="3b1b1-112">El elemento de destino puede ser un proceso, volcado de memoria, equipo remoto y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="3b1b1-112">The target item may be a process, memory dump, remote machine, and so on.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b1b1-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3b1b1-113">Requirements</span></span>  
 <span data-ttu-id="3b1b1-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3b1b1-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b1b1-115">**Encabezado**: ClrData.idl</span><span class="sxs-lookup"><span data-stu-id="3b1b1-115">**Header:** ClrData.idl</span></span>  
  
 <span data-ttu-id="3b1b1-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3b1b1-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3b1b1-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b1b1-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b1b1-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="3b1b1-118">See also</span></span>

- [<span data-ttu-id="3b1b1-119">Funciones estáticas globales de depuración</span><span class="sxs-lookup"><span data-stu-id="3b1b1-119">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
