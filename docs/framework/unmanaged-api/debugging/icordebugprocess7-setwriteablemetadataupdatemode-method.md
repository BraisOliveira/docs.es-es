---
title: ICorDebugProcess7::SetWriteableMetadataUpdateMode (Método)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugProcess7.SetWriteableMetadataUpdateMode
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 8589bba7-7304-45ba-9e31-7bf43dfd5c19
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 70d8f5bf23b5cdf0714bfbb8c8571f9412ad7115
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487294"
---
# <a name="icordebugprocess7setwriteablemetadataupdatemode-method"></a><span data-ttu-id="1b622-102">ICorDebugProcess7::SetWriteableMetadataUpdateMode (Método)</span><span class="sxs-lookup"><span data-stu-id="1b622-102">ICorDebugProcess7::SetWriteableMetadataUpdateMode Method</span></span>
<span data-ttu-id="1b622-103">[Compatible con .NET Framework 4.5.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="1b622-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="1b622-104">Configura cómo el depurador controla las actualizaciones en memoria de los metadatos dentro del proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="1b622-104">Configures how the debugger handles in-memory updates to metadata within the target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b622-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1b622-105">Syntax</span></span>  
  
```cpp
HRESULT SetWriteableMetadataUpdateMode(  
   WriteableMetadataUpdateMode flags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1b622-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1b622-106">Parameters</span></span>  
 `flags`  
 <span data-ttu-id="1b622-107">Un [WriteableMetadataUpdateMode](../../../../docs/framework/unmanaged-api/debugging/writeablemetadataupdatemode-enumeration.md) valor de enumeración que especifica si las actualizaciones en memoria de metadatos en el proceso de destino son visibles (`WriteableMetadataUpdateMode::AlwaysShowUpdates`) o no es visible (`WriteableMetadataUpdateMode::LegacyCompatPolicy`) al depurador.</span><span class="sxs-lookup"><span data-stu-id="1b622-107">A [WriteableMetadataUpdateMode](../../../../docs/framework/unmanaged-api/debugging/writeablemetadataupdatemode-enumeration.md) enumeration value that specifies whether in-memory updates to metadata in the target process are visible (`WriteableMetadataUpdateMode::AlwaysShowUpdates`) or not visible (`WriteableMetadataUpdateMode::LegacyCompatPolicy`) to the debugger.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1b622-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1b622-108">Remarks</span></span>  
 <span data-ttu-id="1b622-109">Actualiza los metadatos del proceso de destino que proceden de Editar y Continuar, de un generador de perfiles o de <xref:System.Reflection.Emit?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1b622-109">Updates to the metadata of the target process can come from Edit and Continue, a profiler, or <xref:System.Reflection.Emit?displayProperty=nameWithType>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b622-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1b622-110">Requirements</span></span>  
 <span data-ttu-id="1b622-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1b622-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b622-112">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1b622-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1b622-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1b622-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1b622-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b622-114">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b622-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="1b622-115">See also</span></span>
- [<span data-ttu-id="1b622-116">ICorDebugProcess7 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1b622-116">ICorDebugProcess7 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess7-interface.md)
- [<span data-ttu-id="1b622-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="1b622-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
