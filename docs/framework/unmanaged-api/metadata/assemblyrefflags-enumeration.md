---
title: AssemblyRefFlags (Enumeración)
ms.date: 03/30/2017
api_name:
- AssemblyRefFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- AssemblyRefFlags
helpviewer_keywords:
- AssemblyRefFlags enumeration [.NET Framework metadata]
ms.assetid: decd4f46-f3b2-466f-9501-e74f2b86b846
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bc98b2421d23ffd6dfb716a8cc782b46a9d59ce0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59128901"
---
# <a name="assemblyrefflags-enumeration"></a><span data-ttu-id="e8f6d-102">AssemblyRefFlags (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="e8f6d-102">AssemblyRefFlags Enumeration</span></span>
<span data-ttu-id="e8f6d-103">Contiene valores que describen las características de una referencia de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e8f6d-103">Contains values that describe features of an assembly reference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8f6d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e8f6d-104">Syntax</span></span>  
  
```  
typedef enum {  
    arfFullOriginator = 0x0001  
} AssemblyRefFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="e8f6d-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="e8f6d-105">Members</span></span>  
  
|<span data-ttu-id="e8f6d-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="e8f6d-106">Member</span></span>|<span data-ttu-id="e8f6d-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="e8f6d-107">Description</span></span>|  
|------------|-----------------|  
|`arfFullOriginator`|<span data-ttu-id="e8f6d-108">Especifica que la referencia de ensamblado contiene información sobre el publicador completa, sin valor de hash del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e8f6d-108">Specifies that the assembly reference contains full, unhashed information about the publisher of the assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e8f6d-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e8f6d-109">Requirements</span></span>  
 <span data-ttu-id="e8f6d-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e8f6d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8f6d-111">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="e8f6d-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e8f6d-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8f6d-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8f6d-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="e8f6d-113">See also</span></span>

- [<span data-ttu-id="e8f6d-114">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="e8f6d-114">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
- [<span data-ttu-id="e8f6d-115">IMetaDataAssemblyEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e8f6d-115">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [<span data-ttu-id="e8f6d-116">DefineAssemblyRef (método)</span><span class="sxs-lookup"><span data-stu-id="e8f6d-116">DefineAssemblyRef Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md)
