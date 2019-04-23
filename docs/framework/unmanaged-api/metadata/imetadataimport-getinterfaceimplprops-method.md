---
title: IMetaDataImport::GetInterfaceImplProps (Método)
ms.date: 02/25/2019
api_name:
- IMetaDataImport.GetInterfaceImplProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetInterfaceImplProps
helpviewer_keywords:
- IMetaDataImport::GetInterfaceImplProps method [.NET Framework metadata]
- GetInterfaceImpProps method [.NET Framework metadata]
ms.assetid: be3f5985-b1e4-4036-8602-c16e8508d4af
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 76e2ebbd47a5e36a722fce33ba67d7efb4db8675
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59115939"
---
# <a name="imetadataimportgetinterfaceimplprops-method"></a><span data-ttu-id="dc80e-102">IMetaDataImport::GetInterfaceImplProps (Método)</span><span class="sxs-lookup"><span data-stu-id="dc80e-102">IMetaDataImport::GetInterfaceImplProps Method</span></span>
<span data-ttu-id="dc80e-103">Obtiene un puntero a los tokens de metadatos para el <xref:System.Type> que implementa el método especificado, y para la interfaz que declara ese método.</span><span class="sxs-lookup"><span data-stu-id="dc80e-103">Gets a pointer to the metadata tokens for the <xref:System.Type> that implements the specified method, and for the interface that declares that method.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="dc80e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dc80e-104">Syntax</span></span>  
  
```  
HRESULT GetInterfaceImplProps (  
   [in]  mdInterfaceImpl        iiImpl,  
   [out] mdTypeDef              *pClass,  
   [out] mdToken                *ptkIface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dc80e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="dc80e-105">Parameters</span></span>  
 `iiImpl`  
 <span data-ttu-id="dc80e-106">[in] El token de metadatos que representa el método para devolver los tokens de clase y la interfaz de.</span><span class="sxs-lookup"><span data-stu-id="dc80e-106">[in] The metadata token representing the method to return the class and interface tokens for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="dc80e-107">[out] El token de metadatos que representa la clase que implementa el método.</span><span class="sxs-lookup"><span data-stu-id="dc80e-107">[out] The metadata token representing the class that implements the method.</span></span>  
  
 `ptkIface`  
 <span data-ttu-id="dc80e-108">[out] El token de metadatos que representa la interfaz que define el método implementado.</span><span class="sxs-lookup"><span data-stu-id="dc80e-108">[out] The metadata token representing the interface that defines the implemented method.</span></span>  

## <a name="remarks"></a><span data-ttu-id="dc80e-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="dc80e-109">Remarks</span></span>

 <span data-ttu-id="dc80e-110">Obtener el valor de `iImpl` mediante una llamada a la [EnumInterfaceImpls](imetadataimport-enuminterfaceimpls-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="dc80e-110">You obtain the value for `iImpl` by calling the [EnumInterfaceImpls](imetadataimport-enuminterfaceimpls-method.md) method.</span></span>
 
 <span data-ttu-id="dc80e-111">Por ejemplo, suponga que una clase tiene un `mdTypeDef` valor de 0 x 02000007 y que implementa tres interfaces cuyos tipos tienen tokens de token:</span><span class="sxs-lookup"><span data-stu-id="dc80e-111">For example, suppose that a class has an `mdTypeDef` token value of 0x02000007 and that it implements three interfaces whose types have tokens:</span></span> 

- <span data-ttu-id="dc80e-112">0x02000003 (TypeDef)</span><span class="sxs-lookup"><span data-stu-id="dc80e-112">0x02000003 (TypeDef)</span></span>
- <span data-ttu-id="dc80e-113">0x0100000A (TypeRef)</span><span class="sxs-lookup"><span data-stu-id="dc80e-113">0x0100000A (TypeRef)</span></span>
- <span data-ttu-id="dc80e-114">0x0200001C (TypeDef)</span><span class="sxs-lookup"><span data-stu-id="dc80e-114">0x0200001C (TypeDef)</span></span>

<span data-ttu-id="dc80e-115">Conceptualmente, esta información se almacena en una tabla de la implementación de interfaz como:</span><span class="sxs-lookup"><span data-stu-id="dc80e-115">Conceptually, this information is stored into an interface implementation table as:</span></span>

| <span data-ttu-id="dc80e-116">Número de fila</span><span class="sxs-lookup"><span data-stu-id="dc80e-116">Row number</span></span> | <span data-ttu-id="dc80e-117">Símbolo (token) de clase</span><span class="sxs-lookup"><span data-stu-id="dc80e-117">Class token</span></span> | <span data-ttu-id="dc80e-118">Símbolo (token) de interfaz</span><span class="sxs-lookup"><span data-stu-id="dc80e-118">Interface token</span></span> |
|------------|-------------|-----------------|
| <span data-ttu-id="dc80e-119">4</span><span class="sxs-lookup"><span data-stu-id="dc80e-119">4</span></span>          |             |                 |
| <span data-ttu-id="dc80e-120">5</span><span class="sxs-lookup"><span data-stu-id="dc80e-120">5</span></span>          | <span data-ttu-id="dc80e-121">02000007</span><span class="sxs-lookup"><span data-stu-id="dc80e-121">02000007</span></span>    | <span data-ttu-id="dc80e-122">02000003</span><span class="sxs-lookup"><span data-stu-id="dc80e-122">02000003</span></span>        |
| <span data-ttu-id="dc80e-123">6</span><span class="sxs-lookup"><span data-stu-id="dc80e-123">6</span></span>          | <span data-ttu-id="dc80e-124">02000007</span><span class="sxs-lookup"><span data-stu-id="dc80e-124">02000007</span></span>    | <span data-ttu-id="dc80e-125">0100000A</span><span class="sxs-lookup"><span data-stu-id="dc80e-125">0100000A</span></span>        |
| <span data-ttu-id="dc80e-126">7</span><span class="sxs-lookup"><span data-stu-id="dc80e-126">7</span></span>          |             |                 |
| <span data-ttu-id="dc80e-127">8</span><span class="sxs-lookup"><span data-stu-id="dc80e-127">8</span></span>          | <span data-ttu-id="dc80e-128">02000007</span><span class="sxs-lookup"><span data-stu-id="dc80e-128">02000007</span></span>    | <span data-ttu-id="dc80e-129">0200001C</span><span class="sxs-lookup"><span data-stu-id="dc80e-129">0200001C</span></span>        |

<span data-ttu-id="dc80e-130">Recuerde que el token es un valor de 4 bytes:</span><span class="sxs-lookup"><span data-stu-id="dc80e-130">Recall, the token is a 4-byte value:</span></span>

- <span data-ttu-id="dc80e-131">Los 3 bytes más bajos mantenga el número de fila o de RID.</span><span class="sxs-lookup"><span data-stu-id="dc80e-131">The lower 3 bytes hold the row number, or RID.</span></span>
- <span data-ttu-id="dc80e-132">El byte superior contiene el tipo de token: 0 x 09 para `mdtInterfaceImpl`.</span><span class="sxs-lookup"><span data-stu-id="dc80e-132">The upper byte holds the token type – 0x09 for `mdtInterfaceImpl`.</span></span>

<span data-ttu-id="dc80e-133">`GetInterfaceImplProps` Devuelve la información contenida en la fila cuyo token proporciona en el `iImpl` argumento.</span><span class="sxs-lookup"><span data-stu-id="dc80e-133">`GetInterfaceImplProps` returns the information held in the row whose token you provide in the `iImpl` argument.</span></span> 
  
## <a name="requirements"></a><span data-ttu-id="dc80e-134">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dc80e-134">Requirements</span></span>  
 <span data-ttu-id="dc80e-135">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dc80e-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc80e-136">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="dc80e-136">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="dc80e-137">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="dc80e-137">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="dc80e-138">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc80e-138">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc80e-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="dc80e-139">See also</span></span>

- [<span data-ttu-id="dc80e-140">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="dc80e-140">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="dc80e-141">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="dc80e-141">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
