---
title: CreateInstallReferenceEnum (Función)
ms.date: 03/30/2017
api_name:
- CreateInstallReferenceEnum
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- CreateInstallReference
helpviewer_keywords:
- CreateInstallReference function [.NET Framework fusion]
ms.assetid: 80dbbbf8-54fc-4894-b74a-0179d3201083
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d7820b33dcfacae5ede5235607e40d95940fc474
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59092830"
---
# <a name="createinstallreferenceenum-function"></a><span data-ttu-id="4912c-102">CreateInstallReferenceEnum (Función)</span><span class="sxs-lookup"><span data-stu-id="4912c-102">CreateInstallReferenceEnum Function</span></span>
<span data-ttu-id="4912c-103">Obtiene un puntero a un [IInstallReferenceEnum](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md) instancia que representa una lista de referencias de la aplicación para el ensamblado especificado.</span><span class="sxs-lookup"><span data-stu-id="4912c-103">Gets a pointer to an [IInstallReferenceEnum](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md) instance that represents a list of an application's references to the specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4912c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4912c-104">Syntax</span></span>  
  
```  
HRESULT CreateInstallReferenceEnum (  
    [out] IInstallReferenceEnum **ppRefEnum,  
    [in]  IAssemblyName         *pName,  
    [in]  DWORD                 dwFlags,  
    [in]  LPVOID                pvReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="4912c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4912c-105">Parameters</span></span>  
 `ppRefEnum`  
 <span data-ttu-id="4912c-106">[out] El valor devuelto `IInstallReferenceEnum` puntero.</span><span class="sxs-lookup"><span data-stu-id="4912c-106">[out] The returned `IInstallReferenceEnum` pointer.</span></span>  
  
 `pName`  
 <span data-ttu-id="4912c-107">[in] El [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) que identifica el ensamblado que se va a enumerar las referencias.</span><span class="sxs-lookup"><span data-stu-id="4912c-107">[in] The [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) that identifies the assembly for which to enumerate references.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="4912c-108">[in] Marcas que influyen en el comportamiento del enumerador.</span><span class="sxs-lookup"><span data-stu-id="4912c-108">[in] Flags that influence the enumerator's behavior.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="4912c-109">[in] Reservado para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="4912c-109">[in] Reserved for future extensibility.</span></span> `pvReserved` <span data-ttu-id="4912c-110">debe ser una referencia nula.</span><span class="sxs-lookup"><span data-stu-id="4912c-110">must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4912c-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4912c-111">Requirements</span></span>  
 <span data-ttu-id="4912c-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4912c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4912c-113">**Encabezado**: Fusion.h</span><span class="sxs-lookup"><span data-stu-id="4912c-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="4912c-114">**Biblioteca:** El archivo Fusion.dll y Mscorwks.dll.</span><span class="sxs-lookup"><span data-stu-id="4912c-114">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="4912c-115">Use el archivo Fusion.dll en lugar de Mscorwks.dll para asegurarse de que tener como destino la versión correcta de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4912c-115">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 **<span data-ttu-id="4912c-116">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="4912c-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4912c-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="4912c-117">See also</span></span>

- [<span data-ttu-id="4912c-118">IInstallReferenceEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4912c-118">IInstallReferenceEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md)
- [<span data-ttu-id="4912c-119">IAssemblyName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4912c-119">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
- [<span data-ttu-id="4912c-120">Funciones estáticas globales de la fusión</span><span class="sxs-lookup"><span data-stu-id="4912c-120">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
