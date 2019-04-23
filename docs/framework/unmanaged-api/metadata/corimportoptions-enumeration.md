---
title: CorImportOptions (Enumeración)
ms.date: 03/30/2017
api_name:
- CorImportOptions
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorImportOptions
helpviewer_keywords:
- CorImportOptions enumeration [.NET Framework metadata]
ms.assetid: 4e5d03cb-97c9-4ff4-8dbd-17d94ee374d3
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a2f71a277484adbbfe3628222c635528cdab03e6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59156135"
---
# <a name="corimportoptions-enumeration"></a><span data-ttu-id="9b77e-102">CorImportOptions (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="9b77e-102">CorImportOptions Enumeration</span></span>
<span data-ttu-id="9b77e-103">Contiene valores de marca que controlan el comportamiento durante la importación de un ensamblado fuera del ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="9b77e-103">Contains flag values that control the behavior during importation of an assembly outside the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b77e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9b77e-104">Syntax</span></span>  
  
```  
typedef enum CorImportOptions {  
  
    MDImportOptionDefault                = 0x00000000,  
    MDImportOptionAll                    = 0xFFFFFFFF,  
    MDImportOptionAllTypeDefs            = 0x00000001,  
    MDImportOptionAllMethodDefs          = 0x00000002,  
    MDImportOptionAllFieldDefs           = 0x00000004,  
    MDImportOptionAllProperties          = 0x00000008,  
    MDImportOptionAllEvents              = 0x00000010,  
    MDImportOptionAllCustomAttributes    = 0x00000020,  
    MDImportOptionAllExportedTypes       = 0x00000040  
  
} CorImportOptions;  
```  
  
## <a name="members"></a><span data-ttu-id="9b77e-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="9b77e-105">Members</span></span>  
  
|<span data-ttu-id="9b77e-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="9b77e-106">Member</span></span>|<span data-ttu-id="9b77e-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="9b77e-107">Description</span></span>|  
|------------|-----------------|  
|`MDImportOptionDefault`|<span data-ttu-id="9b77e-108">Indica el comportamiento predeterminado, que se usa para omitir los registros eliminados.</span><span class="sxs-lookup"><span data-stu-id="9b77e-108">Indicates the default behavior, which is to skip deleted records.</span></span>|  
|`MDImportOptionAll`|<span data-ttu-id="9b77e-109">Indica que se deben enumerar todos los metadatos.</span><span class="sxs-lookup"><span data-stu-id="9b77e-109">Indicates that all metadata should be enumerated.</span></span>|  
|`MDImportOptionAllTypeDefs`|<span data-ttu-id="9b77e-110">Indica que se deben enumerar todas las definiciones de tipos, incluidos los eliminados.</span><span class="sxs-lookup"><span data-stu-id="9b77e-110">Indicates that all TypeDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllMethodDefs`|<span data-ttu-id="9b77e-111">Indica que se deben enumerar todos los MethodDefs, incluyendo los eliminados.</span><span class="sxs-lookup"><span data-stu-id="9b77e-111">Indicates that all MethodDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllFieldDefs`|<span data-ttu-id="9b77e-112">Indica que se deben enumerar todos los FieldDefs, incluyendo los eliminados.</span><span class="sxs-lookup"><span data-stu-id="9b77e-112">Indicates that all FieldDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllProperties`|<span data-ttu-id="9b77e-113">Indica que se deben enumerar todos los PropertyDefs, incluyendo los eliminados.</span><span class="sxs-lookup"><span data-stu-id="9b77e-113">Indicates that all PropertyDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllEvents`|<span data-ttu-id="9b77e-114">Indica que se deben enumerar todos los EventDefs, incluyendo los eliminados.</span><span class="sxs-lookup"><span data-stu-id="9b77e-114">Indicates that all EventDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllCustomAttributes`|<span data-ttu-id="9b77e-115">Indica que se deben enumerar todos los atributos personalizados, incluyendo los eliminados.</span><span class="sxs-lookup"><span data-stu-id="9b77e-115">Indicates that all custom attributes, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllExportedTypes`|<span data-ttu-id="9b77e-116">Indica que se deben enumerar todos los tipos exportados, incluidos los eliminados.</span><span class="sxs-lookup"><span data-stu-id="9b77e-116">Indicates that all exported types, including deleted ones, should be enumerated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9b77e-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9b77e-117">Requirements</span></span>  
 <span data-ttu-id="9b77e-118">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9b77e-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b77e-119">**Encabezado**: CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="9b77e-119">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="9b77e-120">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b77e-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b77e-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="9b77e-121">See also</span></span>

- [<span data-ttu-id="9b77e-122">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="9b77e-122">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
