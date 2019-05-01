---
title: IEnumRAWINPUTDEVICE
ms.date: 03/30/2017
helpviewer_keywords:
- IEnumRAWINPUTDEVICE interface [WPF]
ms.assetid: 88c8b389-a48b-46b9-b895-8ed7b1e26fea
ms.openlocfilehash: 04caca0c580d26fde7fc9a3e3a11b7a8fed26d65
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61949570"
---
# <a name="ienumrawinputdevice"></a><span data-ttu-id="2a1b8-102">IEnumRAWINPUTDEVICE</span><span class="sxs-lookup"><span data-stu-id="2a1b8-102">IEnumRAWINPUTDEVICE</span></span>
<span data-ttu-id="2a1b8-103">Esta interfaz enumera los dispositivos de entrada sin formato y solo la utiliza PresentationHost.exe.</span><span class="sxs-lookup"><span data-stu-id="2a1b8-103">This interface enumerates the raw input devices, and is only used by PresentationHost.exe.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2a1b8-104">Esta API solo está destinada y es compatible con el equipo cliente local</span><span class="sxs-lookup"><span data-stu-id="2a1b8-104">This API is only intended and supported for use on the local client machine</span></span>  
  
## <a name="members"></a><span data-ttu-id="2a1b8-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="2a1b8-105">Members</span></span>  
  
|<span data-ttu-id="2a1b8-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="2a1b8-106">Member</span></span>|<span data-ttu-id="2a1b8-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="2a1b8-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2a1b8-108">IEnumRAWINPUTDEVIC:Next</span><span class="sxs-lookup"><span data-stu-id="2a1b8-108">IEnumRAWINPUTDEVIC:Next</span></span>](ienumrawinputdevic-next.md)|<span data-ttu-id="2a1b8-109">Enumera los elementos `celt` siguientes (es decir, las estructuras RAWINPUTDEVICE) de la lista del enumerador y los devuelve en `rgelt` junto con el número real de elementos enumerados en `pceltFetched`.</span><span class="sxs-lookup"><span data-stu-id="2a1b8-109">Enumerates the next `celt` elements (that is, RAWINPUTDEVICE structures) in the enumerator's list, returning them in `rgelt` along with the actual number of enumerated elements in `pceltFetched`.</span></span>|  
|[<span data-ttu-id="2a1b8-110">IEnumRAWINPUTDEVIC:Skip</span><span class="sxs-lookup"><span data-stu-id="2a1b8-110">IEnumRAWINPUTDEVIC:Skip</span></span>](ienumrawinputdevic-skip.md)|<span data-ttu-id="2a1b8-111">Indica al enumerador para omitir la próxima `celt` elementos de la enumeración para que la siguiente llamada a [IEnumRAWINPUTDEVIC:Next](ienumrawinputdevic-next.md) no devolverá los elementos.</span><span class="sxs-lookup"><span data-stu-id="2a1b8-111">Instructs the enumerator to skip the next `celt` elements in the enumeration so that the next call to [IEnumRAWINPUTDEVIC:Next](ienumrawinputdevic-next.md) will not return those elements.</span></span>|  
|[<span data-ttu-id="2a1b8-112">IEnumRAWINPUTDEVIC:Reset</span><span class="sxs-lookup"><span data-stu-id="2a1b8-112">IEnumRAWINPUTDEVIC:Reset</span></span>](ienumrawinputdevic-reset.md)|<span data-ttu-id="2a1b8-113">Restablece la secuencia de enumeración al principio.</span><span class="sxs-lookup"><span data-stu-id="2a1b8-113">Resets the enumeration sequence to the beginning.</span></span>|  
|[<span data-ttu-id="2a1b8-114">IEnumRAWINPUTDEVIC:Clone</span><span class="sxs-lookup"><span data-stu-id="2a1b8-114">IEnumRAWINPUTDEVIC:Clone</span></span>](ienumrawinputdevic-clone.md)|<span data-ttu-id="2a1b8-115">Crea otro enumerador de dispositivo de entrada sin formato con el mismo estado que el enumerador actual para crear una iteración por la misma lista.</span><span class="sxs-lookup"><span data-stu-id="2a1b8-115">Creates another raw input device enumerator with the same state as the current enumerator to iterate over the same list.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2a1b8-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="2a1b8-116">See also</span></span>

- [<span data-ttu-id="2a1b8-117">Acerca de la entrada sin formato</span><span class="sxs-lookup"><span data-stu-id="2a1b8-117">About Raw Input</span></span>](/windows/desktop/inputdev/about-raw-input)
