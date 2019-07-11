---
title: SetAssemblyFile (Método)
ms.date: 03/30/2017
api_name:
- IALink.SetAssemblyFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetAssemblyFile
helpviewer_keywords:
- SetAssemblyFile method
ms.assetid: 3a912787-f139-43ca-a841-8bbda3107ecf
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b7be346f1c92c877932957787b0747515c144752
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741534"
---
# <a name="setassemblyfile-method"></a><span data-ttu-id="efaa1-102">SetAssemblyFile (Método)</span><span class="sxs-lookup"><span data-stu-id="efaa1-102">SetAssemblyFile Method</span></span>
<span data-ttu-id="efaa1-103">Asigna el nombre del ensamblado que se crea.</span><span class="sxs-lookup"><span data-stu-id="efaa1-103">Assigns the name of the assembly to be built.</span></span> <span data-ttu-id="efaa1-104">No para su uso cuando se producen los módulos no enlazados.</span><span class="sxs-lookup"><span data-stu-id="efaa1-104">Not for use when producing unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="efaa1-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="efaa1-105">Syntax</span></span>  
  
```cpp  
HRESULT SetAssemblyFile(  
    LPCWSTR pszFilename,  
    IMetaDataEmit* pEmitter,  
    AssemblyFlags afFlags,  
    mdAssembly* pAssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="efaa1-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="efaa1-106">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="efaa1-107">Nombre completo del archivo de manifiesto.</span><span class="sxs-lookup"><span data-stu-id="efaa1-107">Fully qualified name of the manifest file.</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="efaa1-108">Puntero a [IMetaDataEmit (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="efaa1-108">Pointer to [IMetaDataEmit Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interface.</span></span>  
  
 `afFlags`  
 <span data-ttu-id="efaa1-109">Marcadores definidos en [AssemblyFlags (enumeración)](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="efaa1-109">Flags as defined in [AssemblyFlags Enumeration](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md).</span></span>  
  
 `pAssemblyID`  
 <span data-ttu-id="efaa1-110">Puntero al identificador del ensamblado resultante.</span><span class="sxs-lookup"><span data-stu-id="efaa1-110">Pointer to ID of resulting assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="efaa1-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="efaa1-111">Return Value</span></span>  
 <span data-ttu-id="efaa1-112">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="efaa1-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="efaa1-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="efaa1-113">Requirements</span></span>  
 <span data-ttu-id="efaa1-114">Requiere alink.h.</span><span class="sxs-lookup"><span data-stu-id="efaa1-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efaa1-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="efaa1-115">See also</span></span>

- [<span data-ttu-id="efaa1-116">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="efaa1-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="efaa1-117">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="efaa1-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="efaa1-118">API de ALink</span><span class="sxs-lookup"><span data-stu-id="efaa1-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
