---
title: CorSymSearchPolicyAttributes (Enumeración)
ms.date: 03/30/2017
api_name:
- CorSymSearchPolicyAttributes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSymSearchPolicyAttributes
helpviewer_keywords:
- CorSymSearchPolicyAttributes enumeration [.NET Framework debugging]
ms.assetid: 03abde84-930a-49d3-bac3-23abb34a0184
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 29766636cd151744d25cf66deb60cd2e066e1b32
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67775782"
---
# <a name="corsymsearchpolicyattributes-enumeration"></a><span data-ttu-id="f681a-102">CorSymSearchPolicyAttributes (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="f681a-102">CorSymSearchPolicyAttributes Enumeration</span></span>
<span data-ttu-id="f681a-103">Especifica la directiva que se usará al realizar una búsqueda de un lector de símbolos.</span><span class="sxs-lookup"><span data-stu-id="f681a-103">Specifies the policy to be used when doing a search for a symbol reader.</span></span> <span data-ttu-id="f681a-104">Estas constantes se utilizan por el [ISymUnmanagedBinder2:: Getreaderforfile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) y [ISymUnmanagedBinder3:: GetReaderFromCallback](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md) métodos.</span><span class="sxs-lookup"><span data-stu-id="f681a-104">These constants are used by the [ISymUnmanagedBinder2::GetReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) and [ISymUnmanagedBinder3::GetReaderFromCallback](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md) methods.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f681a-105">Es un riesgo de seguridad para abrir un archivo de programa (PDB) de la base de datos desde un origen de confianza.</span><span class="sxs-lookup"><span data-stu-id="f681a-105">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f681a-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f681a-106">Syntax</span></span>  
  
```cpp  
typedef enum CorSymSearchPolicyAttributes  
{  
    AllowRegistryAccess      = 0x1,       
    AllowSymbolServerAccess  = 0x2,  
    AllowOriginalPathAccess  = 0x4,     //      
    AllowReferencePathAccess = 0x8  
} CorSymSearchPolicyAttributes;  
```  
  
## <a name="members"></a><span data-ttu-id="f681a-107">Miembros</span><span class="sxs-lookup"><span data-stu-id="f681a-107">Members</span></span>  
  
|<span data-ttu-id="f681a-108">Member</span><span class="sxs-lookup"><span data-stu-id="f681a-108">Member</span></span>|<span data-ttu-id="f681a-109">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="f681a-109">Description</span></span>|  
|------------|-----------------|  
|`AllowRegistryAccess`|<span data-ttu-id="f681a-110">Consulta el registro para las rutas de búsqueda de símbolos.</span><span class="sxs-lookup"><span data-stu-id="f681a-110">Queries the registry for symbol search paths.</span></span>|  
|`AllowSymbolServerAccess`|<span data-ttu-id="f681a-111">Tiene acceso a un servidor de símbolos.</span><span class="sxs-lookup"><span data-stu-id="f681a-111">Accesses a symbol server.</span></span>|  
|`AllowOriginalPathAccess`|<span data-ttu-id="f681a-112">Busca la ruta de acceso especificada en el directorio de depuración.</span><span class="sxs-lookup"><span data-stu-id="f681a-112">Searches the path specified in the Debug directory.</span></span>|  
|`AllowReferencePathAccess`|<span data-ttu-id="f681a-113">Busca el archivo PDB en el lugar donde está el archivo .exe.</span><span class="sxs-lookup"><span data-stu-id="f681a-113">Searches for the PDB in the place where the .exe file is.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f681a-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f681a-114">Requirements</span></span>  
 <span data-ttu-id="f681a-115">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="f681a-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f681a-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="f681a-116">See also</span></span>

- [<span data-ttu-id="f681a-117">Enumeraciones de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="f681a-117">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
