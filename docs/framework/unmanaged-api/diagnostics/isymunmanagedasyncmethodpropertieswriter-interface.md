---
title: ISymUnmanagedAsyncMethodPropertiesWriter (Interfaz)
ms.date: 03/30/2017
ms.assetid: caa71820-8058-4b6a-93a2-25ee757d92d3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 82fcddd7a3f89a92cc79285930b30342333fbec2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61940106"
---
# <a name="isymunmanagedasyncmethodpropertieswriter-interface"></a><span data-ttu-id="0f3ef-102">ISymUnmanagedAsyncMethodPropertiesWriter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0f3ef-102">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>
<span data-ttu-id="0f3ef-103">Permite definir la información de método asincrónico opcional para cada símbolo de método.</span><span class="sxs-lookup"><span data-stu-id="0f3ef-103">Allows you to define optional async method information for each method symbol.</span></span> <span data-ttu-id="0f3ef-104">Utilice siempre con un método abierto; es decir, entre las llamadas a la [OpenMethod (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md) y [CloseMethod (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md).</span><span class="sxs-lookup"><span data-stu-id="0f3ef-104">Always use with an opened method; that is, between calls to the [OpenMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md) and the [CloseMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f3ef-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0f3ef-105">Syntax</span></span>  
  
```idl  
[object,uuid(FC073774-1739-4232-BD56-A027294BEC15),pointer_default(unique)]interface ISymUnmanagedAsyncMethodPropertiesWriter : IUnknown  
```  
  
## <a name="methods"></a><span data-ttu-id="0f3ef-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="0f3ef-106">Methods</span></span>  
 <span data-ttu-id="0f3ef-107">Esta interfaz contiene los siguientes métodos:</span><span class="sxs-lookup"><span data-stu-id="0f3ef-107">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="0f3ef-108">Método</span><span class="sxs-lookup"><span data-stu-id="0f3ef-108">Method</span></span>|<span data-ttu-id="0f3ef-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="0f3ef-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0f3ef-110">DefineAsyncStepInfo (método)</span><span class="sxs-lookup"><span data-stu-id="0f3ef-110">DefineAsyncStepInfo Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md)|<span data-ttu-id="0f3ef-111">Definir un grupo de async await operaciones en el método actual.</span><span class="sxs-lookup"><span data-stu-id="0f3ef-111">Define a group of async await operations in the current method.</span></span><br /><br /> <span data-ttu-id="0f3ef-112">Cada desplazamiento yield coincide con la instrucción de devolución de una instrucción await, que identifica un rendimiento potencial.</span><span class="sxs-lookup"><span data-stu-id="0f3ef-112">Each yield offset matches an await's return instruction, identifying a potential yield.</span></span> <span data-ttu-id="0f3ef-113">Cada `breakpointMethod` / `breakpointOffset` par identifica dónde se reanudará la operación asincrónica; puede estar en un método diferente.</span><span class="sxs-lookup"><span data-stu-id="0f3ef-113">Each `breakpointMethod`/`breakpointOffset` pair identifies where the asynchronous operation will resume; it may be in a different method.</span></span>|  
|[<span data-ttu-id="0f3ef-114">DefineCatchHandlerILOffset (método)</span><span class="sxs-lookup"><span data-stu-id="0f3ef-114">DefineCatchHandlerILOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md)|<span data-ttu-id="0f3ef-115">Establece el IL de desplazamiento para el controlador catch generado por el compilador que encapsula un método asincrónico.</span><span class="sxs-lookup"><span data-stu-id="0f3ef-115">Sets the IL offset for the compiler-generated catch handler that wraps an async method.</span></span><br /><br /> <span data-ttu-id="0f3ef-116">Se usa el desplazamiento IL de catch generado por el depurador para controlar la captura como si fuera código de no usuario, aunque puede producir en un método de código de usuario.</span><span class="sxs-lookup"><span data-stu-id="0f3ef-116">The IL offset of the generated catch is used by the debugger to handle the catch as if it were non-user code, even though it may occur in a user code method.</span></span> <span data-ttu-id="0f3ef-117">En concreto, se utiliza en respuesta a un **CatchHandlerFound** eventos de excepción.</span><span class="sxs-lookup"><span data-stu-id="0f3ef-117">In particular, it is used in response to a **CatchHandlerFound** exception event.</span></span>|  
|[<span data-ttu-id="0f3ef-118">DefineKickoffMethod (método)</span><span class="sxs-lookup"><span data-stu-id="0f3ef-118">DefineKickoffMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md)|<span data-ttu-id="0f3ef-119">Establece el método inicial que inicia la operación asincrónica.</span><span class="sxs-lookup"><span data-stu-id="0f3ef-119">Sets the starting method that initiates the async operation.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0f3ef-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0f3ef-120">Requirements</span></span>  
 <span data-ttu-id="0f3ef-121">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="0f3ef-121">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f3ef-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="0f3ef-122">See also</span></span>

- [<span data-ttu-id="0f3ef-123">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="0f3ef-123">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
