---
title: SetAssemblyFile2 (Método)
ms.date: 03/30/2017
api_name:
- IALink2.SetAssemblyFile2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetAssemblyFile2
helpviewer_keywords:
- SetAssemblyFile2 method
ms.assetid: eedb9125-1ef1-4000-abfc-7de86e5a1f17
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 59bfc6785d3ad195e219afc323b7fdb513d8fefc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59092570"
---
# <a name="setassemblyfile2-method"></a><span data-ttu-id="98be4-102">SetAssemblyFile2 (Método)</span><span class="sxs-lookup"><span data-stu-id="98be4-102">SetAssemblyFile2 Method</span></span>
<span data-ttu-id="98be4-103">Establece el nombre y las opciones para un nuevo ensamblado.</span><span class="sxs-lookup"><span data-stu-id="98be4-103">Sets the name of and options for a new assembly.</span></span> <span data-ttu-id="98be4-104">No llame a este método cuando se crean los módulos no enlazados.</span><span class="sxs-lookup"><span data-stu-id="98be4-104">Do not call this method when you produce unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98be4-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="98be4-105">Syntax</span></span>  
  
```  
HRESULT SetAssemblyFile2(  
    LPCWSTR pszFilename,  
    IMetaDataEmit2* pEmitter,  
    AssemblyFlags   afFlags,  
    mdAssembly* pAssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="98be4-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="98be4-106">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="98be4-107">Nombre del archivo de manifiesto.</span><span class="sxs-lookup"><span data-stu-id="98be4-107">Name of manifest file.</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="98be4-108">[IMetaDataEmit2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md) interfaz para este archivo.</span><span class="sxs-lookup"><span data-stu-id="98be4-108">[IMetaDataEmit2 Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md) interface for this file.</span></span>  
  
 `afFlags`  
 <span data-ttu-id="98be4-109">Opciones representados por [AssemblyFlags (enumeración)](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="98be4-109">Options represented by [AssemblyFlags Enumeration](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md).</span></span>  
  
 `pAssemblyID`  
 <span data-ttu-id="98be4-110">Recibe el identificador único para el ensamblado que se está construyendo.</span><span class="sxs-lookup"><span data-stu-id="98be4-110">Receives unique ID for the assembly being constructed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="98be4-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="98be4-111">Return Value</span></span>  
 <span data-ttu-id="98be4-112">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="98be4-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98be4-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="98be4-113">Requirements</span></span>  
 <span data-ttu-id="98be4-114">Requiere alink.h.</span><span class="sxs-lookup"><span data-stu-id="98be4-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98be4-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="98be4-115">See also</span></span>

- [<span data-ttu-id="98be4-116">IALink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="98be4-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="98be4-117">IALink (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="98be4-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="98be4-118">API de ALink</span><span class="sxs-lookup"><span data-stu-id="98be4-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
