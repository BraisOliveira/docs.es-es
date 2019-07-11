---
title: IEnumDefinitionIdentity (Interfaz)
ms.date: 03/30/2017
api_name:
- IEnumDefinitionIdentity
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IEnumDefinitionIdentity
helpviewer_keywords:
- IEnumDefinitionIdentity interface [.NET Framework fusion]
ms.assetid: 8263e75d-251b-4abc-8a1a-c62884142232
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4bbd8476b7778de6d0023f3a8522a44be6626884
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67751526"
---
# <a name="ienumdefinitionidentity-interface"></a><span data-ttu-id="6f2a0-102">IEnumDefinitionIdentity (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="6f2a0-102">IEnumDefinitionIdentity Interface</span></span>
<span data-ttu-id="6f2a0-103">Actúa como el enumerador para una colección de `IDefinitionIdentity` objetos.</span><span class="sxs-lookup"><span data-stu-id="6f2a0-103">Serves as the enumerator for a collection of `IDefinitionIdentity` objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f2a0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6f2a0-104">Syntax</span></span>  
  
```cpp  
IEnumDefinitionIdentity : IUnknown {  
  
    HRESULT Clone (  
        [out] IEnumDefinitionIdentity **ppIEnumDefinitionIdentity  
    );  
  
    HRESULT Next (  
        [in]  ULONG               celt,  
        [out, length_is(celt), size_is(*pceltWritten)]  
              IDefinitionIdentity *rgpIDefinitionIdentity[],  
        [out] ULONG               *pceltWritten  
    );  
  
    HRESULT Reset ();  
  
    HRESULT Skip (  
        [in] ULONG celt  
    );  
  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="6f2a0-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="6f2a0-105">Methods</span></span>  
  
|<span data-ttu-id="6f2a0-106">Método</span><span class="sxs-lookup"><span data-stu-id="6f2a0-106">Method</span></span>|<span data-ttu-id="6f2a0-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="6f2a0-107">Description</span></span>|  
|------------|-----------------|  
|`IEnumDefinitionIdentity::Clone`|<span data-ttu-id="6f2a0-108">Obtiene un puntero de interfaz a una nueva `IEnumDefinitionIdentity` objeto que contiene los mismos miembros que esto `IEnumDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="6f2a0-108">Gets an interface pointer to a new `IEnumDefinitionIdentity` object that contains the same members as this `IEnumDefinitionIdentity`.</span></span>|  
|`IEnumDefinitionIdentity::Next`|<span data-ttu-id="6f2a0-109">Obtiene el número especificado de `IDefinitionIdentity` objetos, empezando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="6f2a0-109">Gets the specified number of `IDefinitionIdentity` objects, starting at the current position.</span></span>|  
|`IEnumDefinitionIdentity::Reset`|<span data-ttu-id="6f2a0-110">Mueve el puntero de instrucción al principio de este `IEnumDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="6f2a0-110">Moves the instruction pointer to the beginning of this `IEnumDefinitionIdentity`.</span></span>|  
|`IEnumDefinitionIdentity::Skip`|<span data-ttu-id="6f2a0-111">Mueve el puntero de instrucción al día por el número especificado de elementos, empezando por la posición actual.</span><span class="sxs-lookup"><span data-stu-id="6f2a0-111">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6f2a0-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6f2a0-112">Requirements</span></span>  
 <span data-ttu-id="6f2a0-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6f2a0-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f2a0-114">**Encabezado**: Isolation.h</span><span class="sxs-lookup"><span data-stu-id="6f2a0-114">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="6f2a0-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f2a0-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f2a0-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="6f2a0-116">See also</span></span>

- [<span data-ttu-id="6f2a0-117">Interfaces de Fusion</span><span class="sxs-lookup"><span data-stu-id="6f2a0-117">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [<span data-ttu-id="6f2a0-118">IDefinitionIdentity (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6f2a0-118">IDefinitionIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md)
