---
title: COR_PRF_ASSEMBLY_REFERENCE_INFO (Estructura)
ms.date: 03/30/2017
dev_langs:
- cpp
ms.assetid: c8c1d916-8d1a-4f82-8128-9fd3732383fc
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 99fa1cc05ee583cf1bd59235fcd9821d1c92d21f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59101437"
---
# <a name="corprfassemblyreferenceinfo-structure"></a><span data-ttu-id="d8e98-102">COR_PRF_ASSEMBLY_REFERENCE_INFO (Estructura)</span><span class="sxs-lookup"><span data-stu-id="d8e98-102">COR_PRF_ASSEMBLY_REFERENCE_INFO Structure</span></span>
<span data-ttu-id="d8e98-103">[Compatible con .NET Framework 4.5.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="d8e98-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="d8e98-104">Proporciona a Common Language Runtime información sobre una referencia de ensamblado que debe tener en cuenta a la hora de realizar un rastreo de cierre de referencias de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d8e98-104">Provides the common language runtime with information about an assembly reference that it should consider when performing an assembly reference closure walk.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8e98-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d8e98-105">Syntax</span></span>  
  
```cpp  
typedef struct _COR_PRF_ASSEMBLY_REFERENCE_INFO {  
    void* pbPublicKeyOrToken;  
    ULONG cbPublicKeyOrToken;  
    LPCWSTR szName;  
    ASSEMBLYMETADATA* pMetaData;  
    void* pbHashValue;  
    ULONG cbHashValue;  
    DWORD dwAssemblyRefFlags;  
} COR_PRF_EX_CLAUSE_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="d8e98-106">Miembros</span><span class="sxs-lookup"><span data-stu-id="d8e98-106">Members</span></span>  
  
|<span data-ttu-id="d8e98-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="d8e98-107">Member</span></span>|<span data-ttu-id="d8e98-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="d8e98-108">Description</span></span>|  
|------------|-----------------|  
|`pbPublicKeyOrToken`|<span data-ttu-id="d8e98-109">Puntero a la clave pública o token del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d8e98-109">A pointer to the public key or token of the assembly.</span></span>|  
|`cbPublicKeyOrToken`|<span data-ttu-id="d8e98-110">Número de bytes en la clave pública o token.</span><span class="sxs-lookup"><span data-stu-id="d8e98-110">The number of bytes in the public key or token.</span></span>|  
|`szName`|<span data-ttu-id="d8e98-111">Nombre del ensamblado al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="d8e98-111">The name of the assembly that is referenced.</span></span>|  
|`pMetaData`|<span data-ttu-id="d8e98-112">Puntero a los metadatos del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d8e98-112">A pointer to the assembly's metadata.</span></span>|  
|`pbHashValue`|<span data-ttu-id="d8e98-113">Puntero a un objeto binario grande (BLOB) de hash.</span><span class="sxs-lookup"><span data-stu-id="d8e98-113">A pointer to a hash binary large object (BLOB).</span></span>|  
|`cbHashValue`|<span data-ttu-id="d8e98-114">Número de bytes en el BLOB de hash.</span><span class="sxs-lookup"><span data-stu-id="d8e98-114">The number of bytes in the hash BLOB.</span></span>|  
|`dwAssemblyRefFlags`|<span data-ttu-id="d8e98-115">Marcas del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d8e98-115">The assembly's flags.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d8e98-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d8e98-116">Remarks</span></span>  
 <span data-ttu-id="d8e98-117">El generador de perfiles rellena la estructura `COR_PRF_EX_CLAUSE_INFO` cuando declara referencias de ensamblado adicionales que Common Language Runtime debe tener en cuenta al realizar un rastreo de cierre de referencias de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d8e98-117">The `COR_PRF_EX_CLAUSE_INFO` structure is populated by the profiler when it declares additional assembly references that the common language runtime should consider when performing an assembly reference closure walk.</span></span>  
  
 <span data-ttu-id="d8e98-118">Si se registra el generador de perfiles para el [icorprofilercallback6:: Getassemblyreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) el método de devolución de llamada, el tiempo de ejecución pasa la ruta de acceso y el nombre del ensamblado que se va a cargar, junto con un puntero a un [ ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) objeto de interfaz a ese método.</span><span class="sxs-lookup"><span data-stu-id="d8e98-118">If the profiler registers for the [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback method, the runtime passes the path and name of the assembly to be loaded, along with a pointer to an [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) interface object to that method.</span></span> <span data-ttu-id="d8e98-119">El generador de perfiles, a continuación, puede llamar a la [Icorprofilerassemblyreferenceprovider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) método con un `COR_PRF_ASSEMBLY_REFERENCE_INFO` objeto para cada ensamblado de destino tiene previsto hacer referencia desde el ensamblado especificado en el [ Icorprofilercallback6:: Getassemblyreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="d8e98-119">The profiler can then call the [ICorProfilerAssemblyReferenceProvider::AddAssemblyReference](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) method with a `COR_PRF_ASSEMBLY_REFERENCE_INFO` object for each target assembly it plans to reference from the assembly specified in the [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8e98-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d8e98-120">Requirements</span></span>  
 <span data-ttu-id="d8e98-121">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d8e98-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8e98-122">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d8e98-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d8e98-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d8e98-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d8e98-124">**Versiones de .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8e98-124">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8e98-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="d8e98-125">See also</span></span>

- [<span data-ttu-id="d8e98-126">Estructuras para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="d8e98-126">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
- [<span data-ttu-id="d8e98-127">GetAssemblyReferences (método)</span><span class="sxs-lookup"><span data-stu-id="d8e98-127">GetAssemblyReferences Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md)
- [<span data-ttu-id="d8e98-128">Método AddAssemblyReference</span><span class="sxs-lookup"><span data-stu-id="d8e98-128">AddAssemblyReference Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md)
