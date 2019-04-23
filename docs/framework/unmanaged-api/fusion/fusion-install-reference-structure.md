---
title: FUSION_INSTALL_REFERENCE (Estructura)
ms.date: 03/30/2017
api_name:
- FUSION_INSTALL_REFERENCE
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- FUSION_INSTALL_REFERENCE
helpviewer_keywords:
- FUSION_INSTALL_REFERENCE structure [.NET Framework fusion]
ms.assetid: ae181ec8-36bf-4ed1-9a02-ca27d417c80b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 611b4a543a1de7c6163ec45ff7f17d07726569ba
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59110370"
---
# <a name="fusioninstallreference-structure"></a><span data-ttu-id="4c6c5-102">FUSION_INSTALL_REFERENCE (Estructura)</span><span class="sxs-lookup"><span data-stu-id="4c6c5-102">FUSION_INSTALL_REFERENCE Structure</span></span>
<span data-ttu-id="4c6c5-103">Representa una referencia a la que hace que una aplicación a un ensamblado que ha instalado la aplicación en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="4c6c5-103">Represents a reference that an application makes to an assembly that the application has installed in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c6c5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4c6c5-104">Syntax</span></span>  
  
```  
typedef struct _FUSION_INSTALL_REFERENCE_ {  
    DWORD    cbSize,  
    DWORD    dwFlags,  
    GUID     guidScheme,  
    LPCWSTR  szIdentifier,  
    LPCWSTR  szNonCanonicalData  
} FUSION_INSTALL_REFERENCE, *LPFUSION_INSTALL_REFERENCE;  
```  
  
## <a name="members"></a><span data-ttu-id="4c6c5-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="4c6c5-105">Members</span></span>  
  
|<span data-ttu-id="4c6c5-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="4c6c5-106">Member</span></span>|<span data-ttu-id="4c6c5-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="4c6c5-107">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="4c6c5-108">El tamaño de la estructura en bytes.</span><span class="sxs-lookup"><span data-stu-id="4c6c5-108">The size of the structure in bytes.</span></span>|  
|`dwFlags`|<span data-ttu-id="4c6c5-109">Reservado para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="4c6c5-109">Reserved for future extensibility.</span></span> <span data-ttu-id="4c6c5-110">Este valor debe ser 0 (cero).</span><span class="sxs-lookup"><span data-stu-id="4c6c5-110">This value must be 0 (zero).</span></span>|  
|`guidScheme`|<span data-ttu-id="4c6c5-111">La entidad que agrega la referencia.</span><span class="sxs-lookup"><span data-stu-id="4c6c5-111">The entity that adds the reference.</span></span> <span data-ttu-id="4c6c5-112">Este campo puede tener uno de los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="4c6c5-112">This field can have one of the following values:</span></span><br /><br /> <span data-ttu-id="4c6c5-113">-FUSION_REFCOUNT_MSI_GUID: El ensamblado se hace referencia a una aplicación que se instaló mediante el instalador de Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="4c6c5-113">-   FUSION_REFCOUNT_MSI_GUID: The assembly is referenced by an application that was installed using the Microsoft Windows Installer.</span></span> <span data-ttu-id="4c6c5-114">El `szIdentifier` campo se establece en `MSI`y el `szNonCanonicalData` campo se establece en `Windows Installer`.</span><span class="sxs-lookup"><span data-stu-id="4c6c5-114">The `szIdentifier` field is set to `MSI`, and the `szNonCanonicalData` field is set to `Windows Installer`.</span></span> <span data-ttu-id="4c6c5-115">Este esquema se utiliza para los ensamblados en paralelo de Windows.</span><span class="sxs-lookup"><span data-stu-id="4c6c5-115">This scheme is used for Windows side-by-side assemblies.</span></span><br /><span data-ttu-id="4c6c5-116">-   FUSION_REFCOUNT_UNINSTALL_SUBKEY_GUID: El ensamblado se hace referencia a una aplicación que aparece en el **agregar o quitar programas** interfaz.</span><span class="sxs-lookup"><span data-stu-id="4c6c5-116">-   FUSION_REFCOUNT_UNINSTALL_SUBKEY_GUID: The assembly is referenced by an application that appears in the **Add/Remove Programs** interface.</span></span> <span data-ttu-id="4c6c5-117">El `szIdentifier` campo proporciona el token que registra la aplicación con el **agregar o quitar programas** interfaz.</span><span class="sxs-lookup"><span data-stu-id="4c6c5-117">The `szIdentifier` field provides the token that registers the application with the **Add/Remove Programs** interface.</span></span><br /><span data-ttu-id="4c6c5-118">-FUSION_REFCOUNT_FILEPATH_GUID: Una aplicación que se representa mediante un archivo en el sistema de archivos al que hace referencia el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="4c6c5-118">-   FUSION_REFCOUNT_FILEPATH_GUID: The assembly is referenced by an application that is represented by a file in the file system.</span></span> <span data-ttu-id="4c6c5-119">El `szIdentifier` campo proporciona la ruta de acceso a este archivo.</span><span class="sxs-lookup"><span data-stu-id="4c6c5-119">The `szIdentifier` field provides the path to this file.</span></span><br /><span data-ttu-id="4c6c5-120">-   FUSION_REFCOUNT_OPAQUE_STRING_GUID: Se hace referencia al ensamblado por una aplicación que se representa sólo mediante una cadena opaca.</span><span class="sxs-lookup"><span data-stu-id="4c6c5-120">-   FUSION_REFCOUNT_OPAQUE_STRING_GUID: The assembly is referenced by an application that is represented only by an opaque string.</span></span> <span data-ttu-id="4c6c5-121">El `szIdentifier` campo proporciona esta cadena opaca.</span><span class="sxs-lookup"><span data-stu-id="4c6c5-121">The `szIdentifier` field provides this opaque string.</span></span> <span data-ttu-id="4c6c5-122">La caché global de ensamblados no comprueba la existencia de referencias opacas cuando se quita este valor.</span><span class="sxs-lookup"><span data-stu-id="4c6c5-122">The global assembly cache does not check for the existence of opaque references when you remove this value.</span></span><br /><span data-ttu-id="4c6c5-123">-FUSION_REFCOUNT_OSINSTALL_GUID: Este valor está reservado.</span><span class="sxs-lookup"><span data-stu-id="4c6c5-123">-   FUSION_REFCOUNT_OSINSTALL_GUID: This value is reserved.</span></span>|  
|`szIdentifier`|<span data-ttu-id="4c6c5-124">Una cadena única que identifica la aplicación que instala al ensamblado en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="4c6c5-124">A unique string that identifies the application that installed the assembly in the global assembly cache.</span></span> <span data-ttu-id="4c6c5-125">Su valor depende del valor de la `guidScheme` campo.</span><span class="sxs-lookup"><span data-stu-id="4c6c5-125">Its value depends upon the value of the `guidScheme` field.</span></span>|  
|`szNonCanonicalData`|<span data-ttu-id="4c6c5-126">Una cadena que solo entiende la entidad que agrega la referencia.</span><span class="sxs-lookup"><span data-stu-id="4c6c5-126">A string that is understood only by the entity that adds the reference.</span></span> <span data-ttu-id="4c6c5-127">La caché global de ensamblados almacena esta cadena, pero no lo usa.</span><span class="sxs-lookup"><span data-stu-id="4c6c5-127">The global assembly cache stores this string, but does not use it.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4c6c5-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4c6c5-128">Requirements</span></span>  
 <span data-ttu-id="4c6c5-129">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4c6c5-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4c6c5-130">**Encabezado**: Fusion.h</span><span class="sxs-lookup"><span data-stu-id="4c6c5-130">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="4c6c5-131">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4c6c5-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c6c5-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="4c6c5-132">See also</span></span>

- [<span data-ttu-id="4c6c5-133">Estructuras de fusión</span><span class="sxs-lookup"><span data-stu-id="4c6c5-133">Fusion Structures</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)
- [<span data-ttu-id="4c6c5-134">Caché global de ensamblados</span><span class="sxs-lookup"><span data-stu-id="4c6c5-134">Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/gac.md)
