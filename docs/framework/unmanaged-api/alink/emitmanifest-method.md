---
title: EmitManifest (Método)
ms.date: 03/30/2017
api_name:
- EmitManifest
- IALink.EmitManifest
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmitManifest
helpviewer_keywords:
- EmitManifest method
ms.assetid: fdebc1f3-b62e-4d9e-b775-8ccaa8ecb250
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bdab1fd10be8fd245f4348798232964721b4487a
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777342"
---
# <a name="emitmanifest-method"></a><span data-ttu-id="70bd7-102">EmitManifest (Método)</span><span class="sxs-lookup"><span data-stu-id="70bd7-102">EmitManifest Method</span></span>
<span data-ttu-id="70bd7-103">Emite el manifiesto final.</span><span class="sxs-lookup"><span data-stu-id="70bd7-103">Emits the final manifest.</span></span> <span data-ttu-id="70bd7-104">Llame a este método después de importar todos los demás archivos y establecer todas las opciones.</span><span class="sxs-lookup"><span data-stu-id="70bd7-104">Call this method after importing all other files and setting all options.</span></span> <span data-ttu-id="70bd7-105">No llame a este método para módulos sin enlazar.</span><span class="sxs-lookup"><span data-stu-id="70bd7-105">Do not call this method for unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70bd7-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="70bd7-106">Syntax</span></span>  
  
```cpp  
HRESULT EmitManifest(  
    mdAssembly   AssemblyID,  
    DWORD*       pdwReserveSize,  
    mdAssembly*  ptkManifest  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="70bd7-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="70bd7-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="70bd7-108">IDENTIFICADOR del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="70bd7-108">ID of the assembly.</span></span>  
  
 `pdwReserveSize`  
 <span data-ttu-id="70bd7-109">Recibe el tamaño que se va a reservar en el archivo de ensamblado, recuperado de la [función strongnamesignaturesize (](../strong-naming/strongnamesignaturesize-function.md).</span><span class="sxs-lookup"><span data-stu-id="70bd7-109">Receives the size to reserve in the assembly file, retrieved from [StrongNameSignatureSize Function](../strong-naming/strongnamesignaturesize-function.md).</span></span>  
  
 `ptkManifest`  
 <span data-ttu-id="70bd7-110">Opcionalmente, recibe el token del manifiesto del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="70bd7-110">Optionally receives the assembly manifest token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="70bd7-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="70bd7-111">Return Value</span></span>  
 <span data-ttu-id="70bd7-112">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="70bd7-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70bd7-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="70bd7-113">Requirements</span></span>  
 <span data-ttu-id="70bd7-114">Requiere ALink. h.</span><span class="sxs-lookup"><span data-stu-id="70bd7-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70bd7-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="70bd7-115">See also</span></span>

- [<span data-ttu-id="70bd7-116">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="70bd7-116">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="70bd7-117">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="70bd7-117">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="70bd7-118">API de ALink</span><span class="sxs-lookup"><span data-stu-id="70bd7-118">ALink API</span></span>](index.md)
