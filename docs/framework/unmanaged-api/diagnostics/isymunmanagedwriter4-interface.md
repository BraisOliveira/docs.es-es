---
title: ISymUnmanagedWriter4 (Interfaz)
ms.date: 03/30/2017
ms.assetid: 4af5e8c0-987d-405e-b934-8b9e70fcae6e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e5732cc08512df25a14cc8ea9dcaa03c56207dde
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59202051"
---
# <a name="isymunmanagedwriter4-interface"></a><span data-ttu-id="af63e-102">ISymUnmanagedWriter4 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="af63e-102">ISymUnmanagedWriter4 Interface</span></span>
<span data-ttu-id="af63e-103">ISymUnmanagedWriter4 (interfaz).</span><span class="sxs-lookup"><span data-stu-id="af63e-103">ISymUnmanagedWriter4 interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af63e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="af63e-104">Syntax</span></span>  
  
```idl  
[object,uuid(BC7E3F53-F458-4C23-9DBD-A189E6E96594),pointer_default(unique)]interface ISymUnmanagedWriter4 : ISymUnmanagedWriter3  
```  
  
## <a name="methods"></a><span data-ttu-id="af63e-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="af63e-105">Methods</span></span>  
 <span data-ttu-id="af63e-106">Esta interfaz contiene los siguientes métodos:</span><span class="sxs-lookup"><span data-stu-id="af63e-106">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="af63e-107">Método</span><span class="sxs-lookup"><span data-stu-id="af63e-107">Method</span></span>|<span data-ttu-id="af63e-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="af63e-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="af63e-109">GetDebugInfoWithPadding (método)</span><span class="sxs-lookup"><span data-stu-id="af63e-109">GetDebugInfoWithPadding Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-getdebuginfowithpadding-method.md)|<span data-ttu-id="af63e-110">Funciona igual que [GetDebugInfo (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md) , salvo que la cadena de ruta de acceso se rellena con ceros que siguen el carácter nulo de terminación para que los datos de cadena de un tamaño fijo de `MAX_PATH`.</span><span class="sxs-lookup"><span data-stu-id="af63e-110">Functions the same as [GetDebugInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md) except that the path string is padded with zeros following the terminating null character to make the string data a fixed size of `MAX_PATH`.</span></span> <span data-ttu-id="af63e-111">Relleno solo se da si la longitud de cadena de ruta de acceso propio es menor que `MAX_PATH`.</span><span class="sxs-lookup"><span data-stu-id="af63e-111">Padding is only given if the path string length itself is less than `MAX_PATH`.</span></span><br /><br /> <span data-ttu-id="af63e-112">Esto facilita la escritura herramientas que los archivos PE de diferencia.</span><span class="sxs-lookup"><span data-stu-id="af63e-112">This makes it easier to write tools that difference PE files.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="af63e-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="af63e-113">Requirements</span></span>  
 <span data-ttu-id="af63e-114">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="af63e-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af63e-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="af63e-115">See also</span></span>

- [<span data-ttu-id="af63e-116">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="af63e-116">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="af63e-117">ISymUnmanagedWriter3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="af63e-117">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)
