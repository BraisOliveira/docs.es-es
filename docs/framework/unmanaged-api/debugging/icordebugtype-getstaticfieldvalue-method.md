---
title: ICorDebugType::GetStaticFieldValue (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetStaticFieldValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetStaticFieldValue
helpviewer_keywords:
- GetStaticFieldValue method, ICorDebugType interface [.NET Framework debugging]
- ICorDebugType::GetStaticFieldValue method [.NET Framework debugging]
ms.assetid: 62eb5d55-53ee-4fb3-8d47-7b6c96808f9e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1054c7c977a487bb5a4bbf464322a65bcc039608
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67755735"
---
# <a name="icordebugtypegetstaticfieldvalue-method"></a><span data-ttu-id="df072-102">ICorDebugType::GetStaticFieldValue (Método)</span><span class="sxs-lookup"><span data-stu-id="df072-102">ICorDebugType::GetStaticFieldValue Method</span></span>
<span data-ttu-id="df072-103">Obtiene un puntero de interfaz a un objeto ICorDebugValue que contiene el valor del campo estático al que hace referencia el campo especificado de token en el marco de pila especificado.</span><span class="sxs-lookup"><span data-stu-id="df072-103">Gets an interface pointer to an ICorDebugValue object that contains the value of the static field referenced by the specified field token in the specified stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df072-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="df072-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStaticFieldValue (  
    [in]  mdFieldDef        fieldDef,  
    [in]  ICorDebugFrame    *pFrame,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="df072-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="df072-105">Parameters</span></span>  
 `fieldDef`  
 <span data-ttu-id="df072-106">[in] Un `mdFieldDef` símbolo (token) que especifica el campo estático.</span><span class="sxs-lookup"><span data-stu-id="df072-106">[in] An `mdFieldDef` token that specifies the static field.</span></span>  
  
 `pFrame`  
 <span data-ttu-id="df072-107">[in] Un puntero a un ICorDebugFrame que representa el marco de pila.</span><span class="sxs-lookup"><span data-stu-id="df072-107">[in] A pointer to an ICorDebugFrame that represents the stack frame.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="df072-108">[out] Un puntero a la dirección de un `ICorDebugValue` que contiene el valor del campo estático.</span><span class="sxs-lookup"><span data-stu-id="df072-108">[out] A pointer to the address of an `ICorDebugValue` that contains the value of the static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="df072-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="df072-109">Remarks</span></span>  
 <span data-ttu-id="df072-110">El `GetStaticFieldValue` método se puede usar sólo si el tipo es ELEMENT_TYPE_CLASS o ELEMENT_TYPE_VALUETYPE, tal y como indica la [ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="df072-110">The `GetStaticFieldValue` method may be used only if the type is ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE, as indicated by the [ICorDebugType::GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) method.</span></span>  
  
 <span data-ttu-id="df072-111">Para tipos no genéricos, la operación se realiza por `GetStaticFieldValue` es idéntico a llamar a [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getstaticfieldvalue-method.md) en el objeto ICorDebugClass devuelto por [ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md).</span><span class="sxs-lookup"><span data-stu-id="df072-111">For non-generic types, the operation performed by `GetStaticFieldValue` is identical to calling [ICorDebugClass::GetStaticFieldValue](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getstaticfieldvalue-method.md) on the ICorDebugClass object that is returned by [ICorDebugType::GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md).</span></span>  
  
 <span data-ttu-id="df072-112">Para tipos genéricos, un valor de campo estático será relativa a una instancia determinada.</span><span class="sxs-lookup"><span data-stu-id="df072-112">For generic types, a static field value will be relative to a particular instantiation.</span></span> <span data-ttu-id="df072-113">También, si el campo estático, posiblemente, podría ser relativo a un subproceso, un contexto o un dominio de aplicación, a continuación, el marco de pila ayudará al depurador determinar el valor adecuado.</span><span class="sxs-lookup"><span data-stu-id="df072-113">Also, if the static field could possibly be relative to a thread, a context, or an application domain, then the stack frame will help the debugger determine the proper value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="df072-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="df072-114">Remarks</span></span>  
 <span data-ttu-id="df072-115">`GetStaticFieldValue` puede usarse solo cuando una llamada a `ICorDebugType::GetType` devuelve un valor de ELEMENT_TYPE_CLASS o ELEMENT_TYPE_VALUETYPE.</span><span class="sxs-lookup"><span data-stu-id="df072-115">`GetStaticFieldValue` can be used only when a call to `ICorDebugType::GetType` returns a value of ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df072-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="df072-116">Requirements</span></span>  
 <span data-ttu-id="df072-117">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="df072-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df072-118">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="df072-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="df072-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="df072-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="df072-120">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df072-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
