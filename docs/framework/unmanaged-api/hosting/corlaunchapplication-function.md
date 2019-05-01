---
title: CorLaunchApplication (Función)
ms.date: 03/30/2017
api_name:
- CorLaunchApplication
api_location:
- mscoree.dll
- clr.dll
api_type:
- COM
f1_keywords:
- CorLaunchApplication
helpviewer_keywords:
- CorLaunchApplication function [.NET Framework hosting]
ms.assetid: 71f362a9-8fe2-47ce-9302-05a645cf3d7d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4c997ab107ba3ceb7773bc9235b9c9dcd4d97df8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61985795"
---
# <a name="corlaunchapplication-function"></a><span data-ttu-id="7b1e7-102">CorLaunchApplication (Función)</span><span class="sxs-lookup"><span data-stu-id="7b1e7-102">CorLaunchApplication Function</span></span>
<span data-ttu-id="7b1e7-103">Inicia la aplicación en la ruta de acceso de red especificada, utilizando los manifiestos especificados y otros datos de aplicación.</span><span class="sxs-lookup"><span data-stu-id="7b1e7-103">Starts the application at the specified network path, using the specified manifests and other application data.</span></span>  
  
 <span data-ttu-id="7b1e7-104">Esta función está en desuso en [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7b1e7-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b1e7-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7b1e7-105">Syntax</span></span>  
  
```  
HRESULT CorLaunchApplication (  
    [in]  HOST_TYPE                dwClickOnceHost,  
    [in]  LPCWSTR                  pwzAppFullName,  
    [in]  DWORD                    dwManifestPaths,  
    [in]  LPCWSTR                 *ppwzManifestPaths,  
    [in]  DWORD                    dwActivationData,  
    [in]  LPCWSTR                 *ppwzActivationData,  
    [out] LPPROCESS_INFORMATION    lpProcessInformation  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7b1e7-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7b1e7-106">Parameters</span></span>  
 `dwClickOnceHost`  
 <span data-ttu-id="7b1e7-107">[in] Un valor de la [HOST_TYPE](../../../../docs/framework/unmanaged-api/hosting/host-type-enumeration.md) enumeración que especifica el tipo de host que está iniciando la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7b1e7-107">[in] A value of the [HOST_TYPE](../../../../docs/framework/unmanaged-api/hosting/host-type-enumeration.md) enumeration that specifies the type of host that is launching the application.</span></span>  
  
 `pwzAppFullName`  
 <span data-ttu-id="7b1e7-108">[in] El nombre completo de la aplicación que se va a iniciar.</span><span class="sxs-lookup"><span data-stu-id="7b1e7-108">[in] The full name of the application that is being launched.</span></span>  
  
 `dwManifestPaths`  
 <span data-ttu-id="7b1e7-109">[in] El número de rutas de acceso de manifiesto de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7b1e7-109">[in] The number of manifest paths for the application.</span></span>  
  
 `ppwzManifestPaths`  
 <span data-ttu-id="7b1e7-110">[in] Una matriz de cadenas, cada uno de los cuales especifica una ruta de acceso para un manifiesto de la aplicación que se va a iniciar.</span><span class="sxs-lookup"><span data-stu-id="7b1e7-110">[in] An array of strings, each of which specifies a path to a manifest for the application that is being launched.</span></span>  
  
 `dwActivationData`  
 <span data-ttu-id="7b1e7-111">[in] El número de elementos de datos de activación para la aplicación que se va a iniciar.</span><span class="sxs-lookup"><span data-stu-id="7b1e7-111">[in] The number of activation data items for the application that is being launched.</span></span>  
  
 `ppwzActivationData`  
 <span data-ttu-id="7b1e7-112">[in] Una matriz de cadenas, cada uno de los cuales es un elemento de datos de activación para la aplicación que se va a iniciar.</span><span class="sxs-lookup"><span data-stu-id="7b1e7-112">[in] An array of strings, each of which is an activation data item for the application that is being launched.</span></span>  
  
 `lpProcessInformation`  
 <span data-ttu-id="7b1e7-113">[out] Un puntero a información sobre el proceso en el que se ha cargado la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7b1e7-113">[out] A pointer to information about the process in which the application has been loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b1e7-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7b1e7-114">Requirements</span></span>  
 <span data-ttu-id="7b1e7-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7b1e7-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b1e7-116">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7b1e7-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7b1e7-117">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7b1e7-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7b1e7-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b1e7-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b1e7-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="7b1e7-119">See also</span></span>

- [<span data-ttu-id="7b1e7-120">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="7b1e7-120">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
