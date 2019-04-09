---
title: IMetaDataAssemblyImport::FindExportedTypeByName (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.FindExportedTypeByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::FindExportedTypeByName
helpviewer_keywords:
- FindExportedTypeByName method [.NET Framework metadata]
- IMetaDataAssemblyImport::FindExportedTypeByName method [.NET Framework metadata]
ms.assetid: 46264b2c-574d-4dde-aafc-77187a104fdd
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 32a7b7b498cc4e52b8be3f43ae52293de380d9f7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59182265"
---
# <a name="imetadataassemblyimportfindexportedtypebyname-method"></a><span data-ttu-id="3fb53-102">IMetaDataAssemblyImport::FindExportedTypeByName (Método)</span><span class="sxs-lookup"><span data-stu-id="3fb53-102">IMetaDataAssemblyImport::FindExportedTypeByName Method</span></span>
<span data-ttu-id="3fb53-103">Obtiene un puntero a un tipo exportado, dados su nombre y el tipo envolvente.</span><span class="sxs-lookup"><span data-stu-id="3fb53-103">Gets a pointer to an exported type, given its name and enclosing type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3fb53-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3fb53-104">Syntax</span></span>  
  
```  
HRESULT FindExportedTypeByName (  
    [in]  LPCWSTR           szName,   
    [in]  mdToken           mdtExportedType,   
    [out] mdExportedType    *ptkExportedType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3fb53-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3fb53-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="3fb53-106">[in] El nombre del tipo exportado.</span><span class="sxs-lookup"><span data-stu-id="3fb53-106">[in] The name of the exported type.</span></span>  
  
 `mdtExportedType`  
 <span data-ttu-id="3fb53-107">[in] El token de metadatos para la clase envolvente del tipo exportado.</span><span class="sxs-lookup"><span data-stu-id="3fb53-107">[in] The metadata token for the enclosing class of the exported type.</span></span> <span data-ttu-id="3fb53-108">Este valor es `mdExportedTypeNil` si exporta solicitado tipo no es un tipo anidado.</span><span class="sxs-lookup"><span data-stu-id="3fb53-108">This value is `mdExportedTypeNil` if the requested exported type is not a nested type.</span></span>  
  
 `ptkExportedType`  
 <span data-ttu-id="3fb53-109">[out] Un puntero a la `mdExportedType` token que representa el tipo exportado.</span><span class="sxs-lookup"><span data-stu-id="3fb53-109">[out] A pointer to the `mdExportedType` token that represents the exported type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3fb53-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3fb53-110">Remarks</span></span>  
 <span data-ttu-id="3fb53-111">El `FindExportedTypeByName` método usa las reglas estándares empleadas por common language runtime para resolver las referencias.</span><span class="sxs-lookup"><span data-stu-id="3fb53-111">The `FindExportedTypeByName` method uses the standard rules employed by the common language runtime for resolving references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3fb53-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3fb53-112">Requirements</span></span>  
 <span data-ttu-id="3fb53-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3fb53-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3fb53-114">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="3fb53-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3fb53-115">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3fb53-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="3fb53-116">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="3fb53-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3fb53-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="3fb53-117">See also</span></span>

- [<span data-ttu-id="3fb53-118">IMetaDataAssemblyImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3fb53-118">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [<span data-ttu-id="3fb53-119">Cómo el motor en tiempo de ejecución ubica ensamblados</span><span class="sxs-lookup"><span data-stu-id="3fb53-119">How the Runtime Locates Assemblies</span></span>](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
