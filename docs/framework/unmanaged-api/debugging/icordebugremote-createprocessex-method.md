---
title: ICorDebugRemote::CreateProcessEx (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugRemote.CreateProcessEx
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugRemoteTarget::CreateProcessEx
helpviewer_keywords:
- CreateProcessEx method, ICorDebugRemote interface [.NET Framework debugging]
- ICorDebugRemote::CreateProcessEx method [.NET Framework debugging]
ms.assetid: 41af93c7-e448-4251-8d4d-413d38c635f2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a38812803127857281f9766fa3ed551971ec0330
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59093538"
---
# <a name="icordebugremotecreateprocessex-method"></a><span data-ttu-id="dbe62-102">ICorDebugRemote::CreateProcessEx (Método)</span><span class="sxs-lookup"><span data-stu-id="dbe62-102">ICorDebugRemote::CreateProcessEx Method</span></span>
<span data-ttu-id="dbe62-103">Inicia un proceso en un equipo remoto en el depurador.</span><span class="sxs-lookup"><span data-stu-id="dbe62-103">Launches a process on a remote machine under the debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dbe62-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dbe62-104">Syntax</span></span>  
  
```  
HRESULT CreateProcessEx (  
    [in]  ICorDebugRemoteTarget*      pRemoteTarget,  
    [in]  LPCWSTR                     lpApplicationName,  
    [in]  LPWSTR                      lpCommandLine,  
    [in]  LPSECURITY_ATTRIBUTES       lpProcessAttributes,  
    [in]  LPSECURITY_ATTRIBUTES       lpThreadAttributes,  
    [in]  BOOL                        bInheritHandles,  
    [in]  DWORD                       dwCreationFlags,  
    [in]  PVOID                       lpEnvironment,  
    [in]  LPCWSTR                     lpCurrentDirectory,  
    [in]  LPSTARTUPINFOW              lpStartupInfo,  
    [in]  LPPROCESS_INFORMATION       lpProcessInformation,  
    [in]  CorDebugCreateProcessFlags  debuggingFlags,  
    [out] ICorDebugProcess**          ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dbe62-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="dbe62-105">Parameters</span></span>  
 `pRemoteTarget`  
 <span data-ttu-id="dbe62-106">[in] Puntero a un [ICorDebugRemoteTarget (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md).</span><span class="sxs-lookup"><span data-stu-id="dbe62-106">[in] Pointer to an [ICorDebugRemoteTarget Interface](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md).</span></span> <span data-ttu-id="dbe62-107">Se usa para determinar el equipo remoto en el que se iniciará el proceso.</span><span class="sxs-lookup"><span data-stu-id="dbe62-107">Used to determine the remote machine on which the process will be launched.</span></span>  
  
 `lpApplicationName`  
 <span data-ttu-id="dbe62-108">[in] Puntero a una cadena terminada en null que especifica el módulo que va a ejecutar el proceso iniciado.</span><span class="sxs-lookup"><span data-stu-id="dbe62-108">[in] Pointer to a null-terminated string that specifies the module to be executed by the launched process.</span></span> <span data-ttu-id="dbe62-109">El módulo se ejecuta en el contexto de seguridad del proceso que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="dbe62-109">The module is executed in the security context of the calling process.</span></span>  
  
 `lpCommandLine`  
 <span data-ttu-id="dbe62-110">[in] Puntero a una cadena terminada en null que especifica la línea de comandos que va a ejecutar el proceso iniciado.</span><span class="sxs-lookup"><span data-stu-id="dbe62-110">[in] Pointer to a null-terminated string that specifies the command line to be executed by the launched process.</span></span>  
  
 `lpProcessAttributes`  
 <span data-ttu-id="dbe62-111">[in] No se utiliza para la depuración remota.</span><span class="sxs-lookup"><span data-stu-id="dbe62-111">[in] Unused for remote debugging.</span></span>  
  
 `lpThreadAttributes`  
 <span data-ttu-id="dbe62-112">[in] No se utiliza para la depuración remota.</span><span class="sxs-lookup"><span data-stu-id="dbe62-112">[in] Unused for remote debugging.</span></span>  
  
 `bInheritHandles`  
 <span data-ttu-id="dbe62-113">[in] No se utiliza para la depuración remota.</span><span class="sxs-lookup"><span data-stu-id="dbe62-113">[in] Unused for remote debugging.</span></span>  
  
 `dwCreationFlags`  
 <span data-ttu-id="dbe62-114">[in] No se utiliza para la depuración remota.</span><span class="sxs-lookup"><span data-stu-id="dbe62-114">[in] Unused for remote debugging.</span></span>  
  
 `lpEnvironment`  
 <span data-ttu-id="dbe62-115">[in] Puntero a un bloque de entorno para el nuevo proceso.</span><span class="sxs-lookup"><span data-stu-id="dbe62-115">[in] Pointer to an environment block for the new process.</span></span>  
  
 `lpCurrentDirectory`  
 <span data-ttu-id="dbe62-116">[in] Puntero a una cadena terminada en null que especifica la ruta de acceso completa al directorio actual para el proceso.</span><span class="sxs-lookup"><span data-stu-id="dbe62-116">[in] Pointer to a null-terminated string that specifies the full path to the current directory for the process.</span></span> <span data-ttu-id="dbe62-117">Si este parámetro es null, el nuevo proceso tendrá la misma unidad actual y el directorio que el proceso que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="dbe62-117">If this parameter is null, the new process will have the same current drive and directory as the calling process.</span></span>  
  
 `lpStartupInfo`  
 <span data-ttu-id="dbe62-118">[in] No se utiliza para la depuración remota.</span><span class="sxs-lookup"><span data-stu-id="dbe62-118">[in] Unused for remote debugging.</span></span>  
  
 `lpProcessInformation`  
 <span data-ttu-id="dbe62-119">[in] No se utiliza para la depuración remota.</span><span class="sxs-lookup"><span data-stu-id="dbe62-119">[in] Unused for remote debugging.</span></span>  
  
 `debuggingFlags`  
 <span data-ttu-id="dbe62-120">[in] No se utiliza para la depuración remota.</span><span class="sxs-lookup"><span data-stu-id="dbe62-120">[in] Unused for remote debugging.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="dbe62-121">[out] Un puntero a la dirección de un objeto "ICorDebugProcess (interfaz)" que representa el proceso.</span><span class="sxs-lookup"><span data-stu-id="dbe62-121">[out] A pointer to the address of a"ICorDebugProcess Interface" object that represents the process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dbe62-122">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="dbe62-122">Return Value</span></span>  
 <span data-ttu-id="dbe62-123">S_OK</span><span class="sxs-lookup"><span data-stu-id="dbe62-123">S_OK</span></span>  
 <span data-ttu-id="dbe62-124">Se inició correctamente el proceso en el equipo remoto y devuelve un "ICorDebugProcess (interfaz)" para la depuración.</span><span class="sxs-lookup"><span data-stu-id="dbe62-124">Successfully launched the process on the remote machine and returned an "ICorDebugProcess Interface" for debugging.</span></span>  
  
 <span data-ttu-id="dbe62-125">E_FAIL (u otros códigos devueltos de E_)</span><span class="sxs-lookup"><span data-stu-id="dbe62-125">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="dbe62-126">No se puede iniciar el proceso en el equipo remoto y devolver una "interfaz ICorDebugProcess" para la depuración.</span><span class="sxs-lookup"><span data-stu-id="dbe62-126">Unable to launch the process on the remote machine and return an "ICorDebugProcess Interface" for debugging.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dbe62-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="dbe62-127">Remarks</span></span>  
 <span data-ttu-id="dbe62-128">No se admite la depuración en modo mixto en Silverlight.</span><span class="sxs-lookup"><span data-stu-id="dbe62-128">Mixed-mode debugging is not supported in Silverlight.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dbe62-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dbe62-129">Requirements</span></span>  
 <span data-ttu-id="dbe62-130">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dbe62-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dbe62-131">**Encabezado**: CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="dbe62-131">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="dbe62-132">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dbe62-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dbe62-133">**Versiones de .NET framework:** 4.5, 4, 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="dbe62-133">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbe62-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="dbe62-134">See also</span></span>

- [<span data-ttu-id="dbe62-135">ICorDebugRemote (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="dbe62-135">ICorDebugRemote Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-interface.md)
- [<span data-ttu-id="dbe62-136">ICorDebug (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="dbe62-136">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)

- [<span data-ttu-id="dbe62-137">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="dbe62-137">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
