---
title: CREATE_ASM_NAME_OBJ_FLAGS (Enumeración)
ms.date: 03/30/2017
api_name:
- CREATE_ASM_NAME_OBJ_FLAGS
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- CREATE_ASM_NAME_OBJ_FLAGS
helpviewer_keywords:
- CREATE_ASM_NAME_OBJ_FLAGS enumeration [.NET Framework fusion]
ms.assetid: a5ed2fd0-c7d2-4603-aaca-5d0caad92675
topic_type:
- apiref
ms.openlocfilehash: f6abb59c3aaec40a4e7b228b8c69147a2d454431
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73108879"
---
# <a name="create_asm_name_obj_flags-enumeration"></a><span data-ttu-id="18bc7-102">CREATE_ASM_NAME_OBJ_FLAGS (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="18bc7-102">CREATE_ASM_NAME_OBJ_FLAGS Enumeration</span></span>
<span data-ttu-id="18bc7-103">Especifica los atributos de un objeto de [interfaz de IAssemblyName](iassemblyname-interface.md) cuando se construye mediante la función [createassemblynameobject (](createassemblynameobject-function.md) .</span><span class="sxs-lookup"><span data-stu-id="18bc7-103">Specifies the attributes of an [IAssemblyName Interface](iassemblyname-interface.md) object when it is constructed by the [CreateAssemblyNameObject](createassemblynameobject-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18bc7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="18bc7-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
  
    CANOF_PARSE_DISPLAY_NAME            = 0x1,  
    CANOF_SET_DEFAULT_VALUES            = 0x2,  
    CANOF_VERIFY_FRIEND_ASSEMBLYNAME    = 0x4,  
    CANOF_PARSE_FRIEND_DISPLAY_NAME     =   
        CANOF_PARSE_DISPLAY_NAME | CANOF_VERIFY_FRIEND_ASSEMBLYNAME  
  
} CREATE_ASM_NAME_OBJ_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="18bc7-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="18bc7-105">Members</span></span>  
  
|<span data-ttu-id="18bc7-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="18bc7-106">Member</span></span>|<span data-ttu-id="18bc7-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="18bc7-107">Description</span></span>|  
|------------|-----------------|  
|`CANOF_PARSE_DISPLAY_NAME`|<span data-ttu-id="18bc7-108">Indica que el parámetro pasado es una identidad textual.</span><span class="sxs-lookup"><span data-stu-id="18bc7-108">Indicates that the parameter passed is a textual identity.</span></span>|  
|`CANOF_SET_DEFAULT_VALUES`|<span data-ttu-id="18bc7-109">Establece algunos valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="18bc7-109">Sets a few default values.</span></span>|  
|`CANOF_VERIFY_FRIEND_ASSEMBLYNAME`|<span data-ttu-id="18bc7-110">Comprueba la regla de ensamblado de confianza (solo el nombre y la clave pública).</span><span class="sxs-lookup"><span data-stu-id="18bc7-110">Verifies the friend assembly rule (only name and public key).</span></span> <span data-ttu-id="18bc7-111">Este miembro es solo para uso interno.</span><span class="sxs-lookup"><span data-stu-id="18bc7-111">This member is for internal use only.</span></span>|  
|`CANOF_PARSE_FRIEND_DISPLAY_NAME`|<span data-ttu-id="18bc7-112">Combinación de las marcas `CANOF_PARSE_DISPLAY_NAME` y `CANOF_VERIFY_FRIEND_ASSEMBLYNAME`.</span><span class="sxs-lookup"><span data-stu-id="18bc7-112">A combination of the `CANOF_PARSE_DISPLAY_NAME` and `CANOF_VERIFY_FRIEND_ASSEMBLYNAME` flags.</span></span> <span data-ttu-id="18bc7-113">Este miembro es solo para uso interno.</span><span class="sxs-lookup"><span data-stu-id="18bc7-113">This member is for internal use only.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="18bc7-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="18bc7-114">Requirements</span></span>  
 <span data-ttu-id="18bc7-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="18bc7-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18bc7-116">**Encabezado:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="18bc7-116">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="18bc7-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="18bc7-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18bc7-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="18bc7-118">See also</span></span>

- [<span data-ttu-id="18bc7-119">IAssemblyName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="18bc7-119">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="18bc7-120">CreateAssemblyNameObject (Función)</span><span class="sxs-lookup"><span data-stu-id="18bc7-120">CreateAssemblyNameObject Function</span></span>](createassemblynameobject-function.md)
- [<span data-ttu-id="18bc7-121">Enumeraciones de fusión</span><span class="sxs-lookup"><span data-stu-id="18bc7-121">Fusion Enumerations</span></span>](fusion-enumerations.md)
