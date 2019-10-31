---
title: ICorDebugMetaDataLocator::GetMetaData (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugMetaDataLocator.GetMetaData
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMetaDataLocator::GetMetaData
helpviewer_keywords:
- ICorDebugMetaDataLocator::GetMetaData method [.NET Framework debugging]
- GetMetaData method, ICorDebugMetaDataLocator interface [.NET Framework debugging]
ms.assetid: f9b0ff22-54db-45eb-9cc3-508000a3141d
topic_type:
- apiref
ms.openlocfilehash: 6e4f11de423d1ab6b66aca40e671607a383a4413
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136627"
---
# <a name="icordebugmetadatalocatorgetmetadata-method"></a><span data-ttu-id="9ce2f-102">ICorDebugMetaDataLocator::GetMetaData (Método)</span><span class="sxs-lookup"><span data-stu-id="9ce2f-102">ICorDebugMetaDataLocator::GetMetaData Method</span></span>
<span data-ttu-id="9ce2f-103">Pide al depurador que devuelva la ruta de acceso completa a un módulo cuyos metadatos se necesitan para completar una operación solicitada por el depurador.</span><span class="sxs-lookup"><span data-stu-id="9ce2f-103">Asks the debugger to return the full path to a module whose metadata is needed to complete an operation the debugger requested.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ce2f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9ce2f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMetaData(  
      [in] LPCWSTR wszImagePath,  
      [in] DWORD   dwImageTimeStamp,  
      [in] DWORD   dwImageSize,  
      [in] ULONG32 cchPathBuffer,  
      [out] ULONG32 * pcchPathBuffer,  
      [out, size_is(cchPathBuffer), length_is(*pcchPathBuffer)]  
               WCHAR wszPathBuffer[]  
      );  
```  
  
## <a name="parameters"></a><span data-ttu-id="9ce2f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9ce2f-105">Parameters</span></span>  
 `wszImagePath`  
 <span data-ttu-id="9ce2f-106">[in] Cadena terminada en NULL que representa la ruta de acceso completa al archivo.</span><span class="sxs-lookup"><span data-stu-id="9ce2f-106">[in] A null-terminated string that represents the full path to the file.</span></span> <span data-ttu-id="9ce2f-107">Si la ruta de acceso completa no está disponible, el nombre y la extensión del archivo (*filename*. *extensión*).</span><span class="sxs-lookup"><span data-stu-id="9ce2f-107">If the full path is not available, the name and extension of the file (*filename*.*extension*).</span></span>  
  
 `dwImageTimeStamp`  
 <span data-ttu-id="9ce2f-108">[in] Marca de tiempo de los encabezados del archivo PE de la imagen.</span><span class="sxs-lookup"><span data-stu-id="9ce2f-108">[in] The time stamp from the image's PE file headers.</span></span> <span data-ttu-id="9ce2f-109">Este parámetro puede usarse potencialmente para una búsqueda del servidor de símbolos ([SymSrv](/windows/desktop/debug/using-symsrv)).</span><span class="sxs-lookup"><span data-stu-id="9ce2f-109">This parameter can potentially be used for a symbol server ([SymSrv](/windows/desktop/debug/using-symsrv)) lookup.</span></span>  
  
 `dwImageSize`  
 <span data-ttu-id="9ce2f-110">[in] Tamaño de la imagen en los encabezados de archivo PE.</span><span class="sxs-lookup"><span data-stu-id="9ce2f-110">[in] The image size from PE file headers.</span></span> <span data-ttu-id="9ce2f-111">Este parámetro podría usarse para una búsqueda de SymSrv.</span><span class="sxs-lookup"><span data-stu-id="9ce2f-111">This parameter can potentially be used for a SymSrv lookup.</span></span>  
  
 `cchPathBuffer`  
 <span data-ttu-id="9ce2f-112">[in] Número de caracteres de `wszPathBuffer`.</span><span class="sxs-lookup"><span data-stu-id="9ce2f-112">[in] The character count in `wszPathBuffer`.</span></span>  
  
 `pcchPathBuffer`  
 <span data-ttu-id="9ce2f-113">[out] Número de `WCHAR` escritos en `wszPathBuffer`.</span><span class="sxs-lookup"><span data-stu-id="9ce2f-113">[out] The count of `WCHAR`s written to `wszPathBuffer`.</span></span>  
  
 <span data-ttu-id="9ce2f-114">Si el método devuelve E_NOT_SUFFICIENT_BUFFER, contiene el número de `WCHAR` necesarios para almacenar la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="9ce2f-114">If the method returns E_NOT_SUFFICIENT_BUFFER, contains the count of `WCHAR`s needed to store the path.</span></span>  
  
 `wszPathBuffer`  
 <span data-ttu-id="9ce2f-115">[out] Puntero a un búfer en el que el depurador copiará la ruta de acceso completa del archivo que contiene los metadatos solicitados.</span><span class="sxs-lookup"><span data-stu-id="9ce2f-115">[out] Pointer to a buffer into which the debugger will copy the full path of the file that contains the requested metadata.</span></span>  
  
 <span data-ttu-id="9ce2f-116">La marca de `ofReadOnly` de la enumeración [CorOpenFlags (](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) se usa para solicitar acceso de solo lectura a los metadatos de este archivo.</span><span class="sxs-lookup"><span data-stu-id="9ce2f-116">The `ofReadOnly` flag from the [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) enumeration is used to request read-only access to the metadata in this file.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9ce2f-117">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9ce2f-117">Return Value</span></span>  
 <span data-ttu-id="9ce2f-118">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="9ce2f-118">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span> <span data-ttu-id="9ce2f-119">Cualquier otro HRESULT de error indica que el archivo no se puede recuperar.</span><span class="sxs-lookup"><span data-stu-id="9ce2f-119">All other failure HRESULTs indicate that the file is not retrievable.</span></span>  
  
|<span data-ttu-id="9ce2f-120">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9ce2f-120">HRESULT</span></span>|<span data-ttu-id="9ce2f-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="9ce2f-121">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9ce2f-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="9ce2f-122">S_OK</span></span>|<span data-ttu-id="9ce2f-123">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="9ce2f-123">The method completed successfully.</span></span> <span data-ttu-id="9ce2f-124">`wszPathBuffer` contiene la ruta de acceso completa al archivo y termina en NULL.</span><span class="sxs-lookup"><span data-stu-id="9ce2f-124">`wszPathBuffer` contains the full path to the file and is null-terminated.</span></span>|  
|<span data-ttu-id="9ce2f-125">E_NOT_SUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="9ce2f-125">E_NOT_SUFFICIENT_BUFFER</span></span>|<span data-ttu-id="9ce2f-126">El tamaño actual de `wszPathBuffer` no es suficiente para contener la ruta de acceso completa.</span><span class="sxs-lookup"><span data-stu-id="9ce2f-126">The current size of `wszPathBuffer` is not sufficient to hold the full path.</span></span> <span data-ttu-id="9ce2f-127">En este caso, `pcchPathBuffer` contiene el número necesario de `WCHAR`, incluido el carácter NULL final, y se llama a `GetMetaData` una segunda vez con el tamaño de búfer solicitado.</span><span class="sxs-lookup"><span data-stu-id="9ce2f-127">In this case, `pcchPathBuffer` contains the needed count of `WCHAR`s, including the terminating null character, and `GetMetaData` is called a second time with the requested buffer size.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9ce2f-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9ce2f-128">Remarks</span></span>  
 <span data-ttu-id="9ce2f-129">Si `wszImagePath` contiene una ruta de acceso completa para un módulo de un volcado de memoria, especifica la ruta de acceso del equipo desde el que se recopiló el volcado de memoria.</span><span class="sxs-lookup"><span data-stu-id="9ce2f-129">If `wszImagePath` contains a full path for a module from a dump, it specifies the path from the computer where the dump was collected.</span></span> <span data-ttu-id="9ce2f-130">Puede que el archivo no exista en esta ubicación o que en ella haya almacenado un archivo incorrecto con el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="9ce2f-130">The file may not exist at this location, or an incorrect file with the same name may be stored on the path.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ce2f-131">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9ce2f-131">Requirements</span></span>  
 <span data-ttu-id="9ce2f-132">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9ce2f-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ce2f-133">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9ce2f-133">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9ce2f-134">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9ce2f-134">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9ce2f-135">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ce2f-135">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ce2f-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="9ce2f-136">See also</span></span>

- [<span data-ttu-id="9ce2f-137">ICorDebugThread4 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9ce2f-137">ICorDebugThread4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-interface.md)
- [<span data-ttu-id="9ce2f-138">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="9ce2f-138">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="9ce2f-139">Depuración</span><span class="sxs-lookup"><span data-stu-id="9ce2f-139">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
