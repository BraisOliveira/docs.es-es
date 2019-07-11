---
title: METAHOST_POLICY_FLAGS (Enumeración)
ms.date: 03/30/2017
api_name:
- METAHOST_POLICY_FLAGS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- METAHOST_POLICY_FLAGS
helpviewer_keywords:
- METAHOST_POLICY_FLAGS enumeration [.NET Framework hosting]
ms.assetid: 3bb4b526-0118-42e2-ba59-c95648528ce9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1d35bd5f8aaa2dc0df0044671414a5a936fed24d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781057"
---
# <a name="metahostpolicyflags-enumeration"></a><span data-ttu-id="6a690-102">METAHOST_POLICY_FLAGS (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="6a690-102">METAHOST_POLICY_FLAGS Enumeration</span></span>
<span data-ttu-id="6a690-103">Proporciona directivas de enlace que son comunes a la mayoría de los hosts en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="6a690-103">Provides binding policies that are common to most runtime hosts.</span></span> <span data-ttu-id="6a690-104">Esta enumeración se utiliza en el [ICLRMetaHostPolicy:: GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="6a690-104">This enumeration is used by the [ICLRMetaHostPolicy::GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a690-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6a690-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    METAHOST_POLICY_HIGHCOMPAT              = 0x00,  
    METAHOST_POLICY_APPLY_UPGRADE_POLICY    = 0x08,  
    METAHOST_POLICY_EMULATE_EXE_LAUNCH      = 0x10,  
    METAHOST_POLICY_SHOW_ERROR_DIALOG       = 0x20,  
    METAHOST_POLICY_USE_PROCESS_IMAGE_PATH  = 0x40,  
    METAHOST_POLICY_ENSURE_SKU_SUPPORTED    = 0x80,  
    METAHOST_POLICY_IGNORE_ERROR_MODE       = 0x1000  
  
} METAHOST_POLICY_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="6a690-106">Miembros</span><span class="sxs-lookup"><span data-stu-id="6a690-106">Members</span></span>  
  
|<span data-ttu-id="6a690-107">Member</span><span class="sxs-lookup"><span data-stu-id="6a690-107">Member</span></span>|<span data-ttu-id="6a690-108">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="6a690-108">Description</span></span>|  
|------------|-----------------|  
|`METAHOST_POLICY_HIGHCOMPAT`|<span data-ttu-id="6a690-109">Define la directiva de compatibilidad de alta, que no tiene en cuenta cualquier common language runtime (CLR) que se carga en el proceso actual.</span><span class="sxs-lookup"><span data-stu-id="6a690-109">Defines the high-compatibility policy, which does not consider any common language runtime (CLR) that is loaded into the current process.</span></span> <span data-ttu-id="6a690-110">En su lugar, considera que sólo el CLR instalados y las preferencias del componente, según se deriva el propio archivo de ensamblado, la versión integrada contra declarada o el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="6a690-110">Instead, it considers only the installed CLRs and the preferences of the component, as derived from the assembly file itself, the declared built-against version, or the configuration file.</span></span>|  
|`METAHOST_POLICY_APPLY_UPGRADE_POLICY`|<span data-ttu-id="6a690-111">Aplica la directiva de actualización para el resultado del enlace de versión cuando no se encuentra una coincidencia exacta, según el contenido de HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\. NETFramework\Policy\Upgrades.</span><span class="sxs-lookup"><span data-stu-id="6a690-111">Applies upgrade policy to the version bind result when an exact match is not found, based on the contents of HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework\Policy\Upgrades.</span></span> <span data-ttu-id="6a690-112">Esto tiene el mismo efecto que [RUNTIME_INFO_UPGRADE_VERSION](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="6a690-112">This has the same effect as [RUNTIME_INFO_UPGRADE_VERSION](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md).</span></span>|  
|`METAHOST_POLICY_EMULATE_EXE_LAUNCH`|<span data-ttu-id="6a690-113">Enlace de resultados se devuelven como si la imagen proporcionada a la llamada se lanzaron en un nuevo proceso.</span><span class="sxs-lookup"><span data-stu-id="6a690-113">Binding results are returned as if the image provided to the call were launched in a new process.</span></span> <span data-ttu-id="6a690-114">Actualmente, `GetRequestedRuntime` omite el conjunto de tiempos de ejecución que se puede cargar y se enlaza con el conjunto de runtimes instalados.</span><span class="sxs-lookup"><span data-stu-id="6a690-114">Currently, `GetRequestedRuntime` ignores the set of loadable runtimes and binds against the set of installed runtimes.</span></span> <span data-ttu-id="6a690-115">Esta marca permite a un host determinar qué tiempo de ejecución de un archivo EXE se enlazará a cuando se inicia.</span><span class="sxs-lookup"><span data-stu-id="6a690-115">This flag allows a host to determine which runtime an EXE will bind to when it is launched.</span></span>|  
|`METAHOST_POLICY_SHOW_ERROR_DIALOG`|<span data-ttu-id="6a690-116">Se muestra un cuadro de diálogo de error si `GetRequestedRuntime` no encuentra un tiempo de ejecución es compatible con los parámetros de entrada.</span><span class="sxs-lookup"><span data-stu-id="6a690-116">An error dialog box is displayed if `GetRequestedRuntime` is unable to find a runtime that is compatible with the input parameters.</span></span> <span data-ttu-id="6a690-117">A partir de .NET Framework 4.5, este cuadro de diálogo de error puede adoptar la forma de un cuadro de diálogo características de Windows que le pregunta si desea que el usuario habilitar la característica correspondiente.</span><span class="sxs-lookup"><span data-stu-id="6a690-117">Beginning with the .NET Framework 4.5, this error dialog box can take the form of a Windows feature dialog box that asks whether the user would like to enable the appropriate feature.</span></span>|  
|`METAHOST_POLICY_USE_PROCESS_IMAGE_PATH`|<span data-ttu-id="6a690-118">`GetRequestedRuntime` usa la imagen de proceso (y cualquier archivo de configuración correspondiente) como entrada adicional para el proceso de enlace.</span><span class="sxs-lookup"><span data-stu-id="6a690-118">`GetRequestedRuntime` uses the process image (and any corresponding configuration file) as additional input to the binding process.</span></span> <span data-ttu-id="6a690-119">De forma predeterminada, `GetRequestedRuntime` no recurre a la ruta de acceso de la imagen de proceso (normalmente, el EXE que se usó para iniciar el proceso) al determinar el tiempo de ejecución para enlazar a.</span><span class="sxs-lookup"><span data-stu-id="6a690-119">By default, `GetRequestedRuntime` does not fall back to the process image path (typically, the EXE that was used to launch the process) when determining the runtime to bind to.</span></span>|  
|`METAHOST_POLICY_ENSURE_SKU_SUPPORTED`|<span data-ttu-id="6a690-120">`GetRequestedRuntime` debe comprobar si la SKU adecuada instalada cuando no hay información disponible en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="6a690-120">`GetRequestedRuntime` must check whether the appropriate SKU is installed when no information is available in the configuration file.</span></span> <span data-ttu-id="6a690-121">Esto permite que las aplicaciones que no tienen archivos de configuración para generar un error en la SKU más pequeñas que la instalación predeterminada de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6a690-121">This allows applications that do not have configuration files to fail gracefully on smaller SKUs than the default installation of the .NET Framework.</span></span> <span data-ttu-id="6a690-122">De forma predeterminada, `GetRequestedRuntime` no comprueba si está instalada la SKU adecuada a menos que se especifica el atributo SKU en el archivo de configuración `<supportedRuntime />` elemento.</span><span class="sxs-lookup"><span data-stu-id="6a690-122">By default, `GetRequestedRuntime` does not check whether the appropriate SKU is installed unless the SKU attribute is specified in the configuration file `<supportedRuntime />` element.</span></span>|  
|`METAHOST_POLICY_IGNORE_ERROR_MODE`|<span data-ttu-id="6a690-123">`GetRequestedRuntime` debe ignorar SEM_FAILCRITICALERRORS (que se establece mediante una llamada a la [SetErrorMode](https://go.microsoft.com/fwlink/p/?LinkId=255242) función) y mostrar el cuadro de diálogo de error.</span><span class="sxs-lookup"><span data-stu-id="6a690-123">`GetRequestedRuntime` should ignore SEM_FAILCRITICALERRORS (which is set by calling the [SetErrorMode](https://go.microsoft.com/fwlink/p/?LinkId=255242) function), and show the error dialog box.</span></span> <span data-ttu-id="6a690-124">De forma predeterminada, SEM_FAILCRITICALERRORS suprime el cuadro de diálogo de error.</span><span class="sxs-lookup"><span data-stu-id="6a690-124">By default, SEM_FAILCRITICALERRORS suppresses the error dialog box.</span></span> <span data-ttu-id="6a690-125">Puede haber heredado desde otro proceso y el error silencioso puede no ser deseable en su escenario.</span><span class="sxs-lookup"><span data-stu-id="6a690-125">It may have been inherited from another process, and the silent error may be undesirable in your scenario.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6a690-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6a690-126">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a690-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6a690-127">Requirements</span></span>  
 <span data-ttu-id="6a690-128">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6a690-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a690-129">**Encabezado**: Metahost.h</span><span class="sxs-lookup"><span data-stu-id="6a690-129">**Header:** Metahost.h</span></span>  
  
 <span data-ttu-id="6a690-130">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6a690-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6a690-131">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6a690-131">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a690-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="6a690-132">See also</span></span>

- [<span data-ttu-id="6a690-133">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="6a690-133">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
- [<span data-ttu-id="6a690-134">GetRequestedRuntime (método)</span><span class="sxs-lookup"><span data-stu-id="6a690-134">GetRequestedRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)
