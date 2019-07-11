---
title: IMetaDataImport::EnumInterfaceImpls (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumInterfaceImpls
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumInterfaceImpls
helpviewer_keywords:
- IMetaDataImport::EnumInterfaceImpls method [.NET Framework metadata]
- EnumInterfaceImpls method [.NET Framework metadata]
ms.assetid: ba6e178f-128b-4e47-a13c-b4be73eb106c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0d0f94949cdc82cdecd52f003f3400c43014fabf
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780461"
---
# <a name="imetadataimportenuminterfaceimpls-method"></a><span data-ttu-id="f81e8-102">IMetaDataImport::EnumInterfaceImpls (Método)</span><span class="sxs-lookup"><span data-stu-id="f81e8-102">IMetaDataImport::EnumInterfaceImpls Method</span></span>
<span data-ttu-id="f81e8-103">Enumera todas las interfaces implementadas por especificado `TypeDef`.</span><span class="sxs-lookup"><span data-stu-id="f81e8-103">Enumerates all interfaces implemented by the specified `TypeDef`.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="f81e8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f81e8-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumInterfaceImpls (  
   [in, out]  HCORENUM       *phEnum,   
   [in]   mdTypeDef          td,  
   [out]  mdInterfaceImpl    rImpls[],   
   [in]   ULONG              cMax,  
   [out]  ULONG*             pcImpls  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f81e8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f81e8-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="f81e8-106">[in, out] Un puntero en el enumerador.</span><span class="sxs-lookup"><span data-stu-id="f81e8-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `td`  
 <span data-ttu-id="f81e8-107">[in] El token de la definición de tipo cuyos tokens de MethodDef que representan implementaciones de interfaz son que hay que enumerar.</span><span class="sxs-lookup"><span data-stu-id="f81e8-107">[in] The token of the TypeDef whose MethodDef tokens representing interface implementations are to be enumerated.</span></span>  
  
 `rImpls`  
 <span data-ttu-id="f81e8-108">[out] Matriz utilizada para almacenar los tokens de MethodDef.</span><span class="sxs-lookup"><span data-stu-id="f81e8-108">[out] The array used to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="f81e8-109">[in] Tamaño máximo de la matriz `rImpls`.</span><span class="sxs-lookup"><span data-stu-id="f81e8-109">[in] The maximum size of the `rImpls` array.</span></span>  
  
 `pcImpls`  
 <span data-ttu-id="f81e8-110">[out] El número real de los tokens que se devuelven en `rImpls`.</span><span class="sxs-lookup"><span data-stu-id="f81e8-110">[out] The actual number of tokens returned in `rImpls`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f81e8-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f81e8-111">Return Value</span></span>  
  
|<span data-ttu-id="f81e8-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f81e8-112">HRESULT</span></span>|<span data-ttu-id="f81e8-113">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="f81e8-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="f81e8-114">`EnumInterfaceImpls` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="f81e8-114">`EnumInterfaceImpls` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="f81e8-115">No hay ningún token de MethodDef que enumerar.</span><span class="sxs-lookup"><span data-stu-id="f81e8-115">There are no MethodDef tokens to enumerate.</span></span> <span data-ttu-id="f81e8-116">En ese caso, `pcImpls` se establece en cero.</span><span class="sxs-lookup"><span data-stu-id="f81e8-116">In that case, `pcImpls` is set to zero.</span></span>|  

## <a name="remarks"></a><span data-ttu-id="f81e8-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f81e8-117">Remarks</span></span>

<span data-ttu-id="f81e8-118">La enumeración devuelve una colección de `mdInterfaceImpl` tokens para cada interfaz implementada por el `TypeDef`.</span><span class="sxs-lookup"><span data-stu-id="f81e8-118">The enumeration returns a collection of `mdInterfaceImpl` tokens for each interface implemented by the specified `TypeDef`.</span></span> <span data-ttu-id="f81e8-119">Interfaz tokens se devuelven en el orden en que se especificaron las interfaces (a través de `DefineTypeDef` o `SetTypeDefProps`).</span><span class="sxs-lookup"><span data-stu-id="f81e8-119">Interface tokens are returned in the order the interfaces were specified (through `DefineTypeDef` or `SetTypeDefProps`).</span></span> <span data-ttu-id="f81e8-120">Propiedades de devuelto `mdInterfaceImpl` los tokens se pueden consultar mediante [GetInterfaceImplProps](imetadataimport-getinterfaceimplprops-method.md).</span><span class="sxs-lookup"><span data-stu-id="f81e8-120">Properties of the returned `mdInterfaceImpl` tokens can be queried using [GetInterfaceImplProps](imetadataimport-getinterfaceimplprops-method.md).</span></span>
  
## <a name="requirements"></a><span data-ttu-id="f81e8-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f81e8-121">Requirements</span></span>  
 <span data-ttu-id="f81e8-122">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f81e8-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f81e8-123">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="f81e8-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f81e8-124">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f81e8-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f81e8-125">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f81e8-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f81e8-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="f81e8-126">See also</span></span>

- [<span data-ttu-id="f81e8-127">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f81e8-127">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="f81e8-128">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f81e8-128">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
