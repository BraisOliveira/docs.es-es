---
title: ICLRDataTarget::GetThreadContext (Método)
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetThreadContext
helpviewer_keywords:
- ICLRDataTarget::GetThreadContext method [.NET Framework debugging]
- GetThreadContext method, ICLRDataTarget interface [.NET Framework debugging]
ms.assetid: b9d8c3b5-3a2e-4225-95d4-dd052c4532c3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 88d563918709a6cf31d9c14a52bbd461ae004420
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61698309"
---
# <a name="iclrdatatargetgetthreadcontext-method"></a><span data-ttu-id="3706f-102">ICLRDataTarget::GetThreadContext (Método)</span><span class="sxs-lookup"><span data-stu-id="3706f-102">ICLRDataTarget::GetThreadContext Method</span></span>
<span data-ttu-id="3706f-103">Obtiene el contexto de ejecución actual para el subproceso especificado en el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="3706f-103">Gets the current execution context for the given thread in the target process.</span></span> <span data-ttu-id="3706f-104">Los servicios de acceso de datos de common language runtime llama a este método.</span><span class="sxs-lookup"><span data-stu-id="3706f-104">This method is called by the common language runtime data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3706f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3706f-105">Syntax</span></span>  
  
```  
HRESULT GetThreadContext (  
    [in] ULONG32            threadID,  
    [in] ULONG32            contextFlags,  
    [in] ULONG32            contextSize,  
    [out, size_is(contextSize)]   
        BYTE                *context  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3706f-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3706f-106">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="3706f-107">[in] El identificador del sistema operativo de un subproceso del proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="3706f-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `contextFlags`  
 <span data-ttu-id="3706f-108">[in] Marcadores que especifican qué partes del contexto se devuelven.</span><span class="sxs-lookup"><span data-stu-id="3706f-108">[in] Flags that specify which parts of the context to return.</span></span> <span data-ttu-id="3706f-109">La implementación devolverá al menos estas partes del contexto.</span><span class="sxs-lookup"><span data-stu-id="3706f-109">The implementation will return at least these parts of the context.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="3706f-110">[in] El tamaño del contexto.</span><span class="sxs-lookup"><span data-stu-id="3706f-110">[in] The size of the context.</span></span>  
  
 `context`  
 <span data-ttu-id="3706f-111">[out] Puntero a un búfer en el que se va a colocar el contexto.</span><span class="sxs-lookup"><span data-stu-id="3706f-111">[out] Pointer to a buffer in which to place the context.</span></span>  
  
 <span data-ttu-id="3706f-112">Los datos en el `context` búfer debe tener el formato de Win32 `CONTEXT` estructura.</span><span class="sxs-lookup"><span data-stu-id="3706f-112">The data in the `context` buffer must be in the format of the Win32 `CONTEXT` structure.</span></span> <span data-ttu-id="3706f-113">El contexto especifica los datos de registro específicas del procesador, por lo que la definición de Win32 `CONTEXT` estructura depende de la arquitectura del procesador.</span><span class="sxs-lookup"><span data-stu-id="3706f-113">The context specifies processor-specific register data, so the definition of the Win32 `CONTEXT` structure depends on the processor's architecture.</span></span> <span data-ttu-id="3706f-114">Consulte el archivo de encabezado WinNT.h para la definición de Win32 `CONTEXT` estructura.</span><span class="sxs-lookup"><span data-stu-id="3706f-114">Refer to the WinNT.h header file for the definition of the Win32 `CONTEXT` structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3706f-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3706f-115">Remarks</span></span>  
 <span data-ttu-id="3706f-116">Este método lo implementa el escritor de la aplicación de depuración.</span><span class="sxs-lookup"><span data-stu-id="3706f-116">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3706f-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3706f-117">Requirements</span></span>  
 <span data-ttu-id="3706f-118">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3706f-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3706f-119">**Encabezado**: ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="3706f-119">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="3706f-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3706f-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3706f-121">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3706f-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3706f-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="3706f-122">See also</span></span>

- [<span data-ttu-id="3706f-123">ICLRDataTarget (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3706f-123">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
