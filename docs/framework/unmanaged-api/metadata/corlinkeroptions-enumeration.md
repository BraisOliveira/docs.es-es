---
title: CorLinkerOptions (Enumeración)
ms.date: 03/30/2017
api_name:
- CorLinkerOptions
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorLinkerOptions
helpviewer_keywords:
- CorLinkerOptions enumeration [.NET Framework metadata]
ms.assetid: a656aad6-cc7e-4994-8251-004a6a45e18f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: dc0554ed89d21607978d059b26c4ad69e59a2d4c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59166639"
---
# <a name="corlinkeroptions-enumeration"></a><span data-ttu-id="11638-102">CorLinkerOptions (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="11638-102">CorLinkerOptions Enumeration</span></span>
<span data-ttu-id="11638-103">Especifica marcas para seleccionar las opciones del vinculador de metadatos.</span><span class="sxs-lookup"><span data-stu-id="11638-103">Specifies flags to select options for the metadata linker.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11638-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="11638-104">Syntax</span></span>  
  
```  
typedef enum CorLinkerOptions {  
    MDAssembly          = 0x00000000,  
    MDNetModule         = 0x00000001,  
} CorLinkerOptions;  
```  
  
## <a name="members"></a><span data-ttu-id="11638-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="11638-105">Members</span></span>  
  
|<span data-ttu-id="11638-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="11638-106">Member</span></span>|<span data-ttu-id="11638-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="11638-107">Description</span></span>|  
|------------|-----------------|  
|`MDAssembly`|<span data-ttu-id="11638-108">No se conservan los tipos privados y funciones globales.</span><span class="sxs-lookup"><span data-stu-id="11638-108">The private types and global functions are not preserved.</span></span>|  
|`MDNetModule`|<span data-ttu-id="11638-109">Los tipos privados y funciones globales se conservan.</span><span class="sxs-lookup"><span data-stu-id="11638-109">The private types and global functions are preserved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="11638-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="11638-110">Requirements</span></span>  
 <span data-ttu-id="11638-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="11638-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11638-112">**Encabezado**: CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="11638-112">**Header:** CorHdr.h</span></span>  
  
 **<span data-ttu-id="11638-113">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="11638-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="11638-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="11638-114">See also</span></span>

- [<span data-ttu-id="11638-115">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="11638-115">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
