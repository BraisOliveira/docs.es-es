---
title: IMetaDataImport2 (Interfaz)
ms.date: 03/30/2017
api_name:
- IMetaDataImport2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2
helpviewer_keywords:
- IMetaDataImport2 interface [.NET Framework metadata]
ms.assetid: d39b2b87-ba53-4771-ae53-952a68452511
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6717c48fca14f2200f783a984594388ef3b29c15
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59211938"
---
# <a name="imetadataimport2-interface"></a><span data-ttu-id="3ba09-102">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3ba09-102">IMetaDataImport2 Interface</span></span>
<span data-ttu-id="3ba09-103">Extiende la [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interfaz para proporcionar la capacidad de trabajar con tipos genéricos.</span><span class="sxs-lookup"><span data-stu-id="3ba09-103">Extends the [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface to provide the capability of working with generic types.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3ba09-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="3ba09-104">Methods</span></span>  
  
|<span data-ttu-id="3ba09-105">Método</span><span class="sxs-lookup"><span data-stu-id="3ba09-105">Method</span></span>|<span data-ttu-id="3ba09-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="3ba09-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3ba09-107">EnumGenericParamConstraints (método)</span><span class="sxs-lookup"><span data-stu-id="3ba09-107">EnumGenericParamConstraints Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enumgenericparamconstraints-method.md)|<span data-ttu-id="3ba09-108">Obtiene un enumerador para una matriz de restricciones de parámetros genéricos asociados con el parámetro genérico representado por el token especificado.</span><span class="sxs-lookup"><span data-stu-id="3ba09-108">Gets an enumerator for an array of generic parameter constraints associated with the generic parameter represented by the specified token.</span></span>|  
|[<span data-ttu-id="3ba09-109">EnumGenericParams (método)</span><span class="sxs-lookup"><span data-stu-id="3ba09-109">EnumGenericParams Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enumgenericparams-method.md)|<span data-ttu-id="3ba09-110">Obtiene un enumerador para una matriz de los tokens de parámetro genérico asociado con la definición de tipo especificado o MethodDef (token).</span><span class="sxs-lookup"><span data-stu-id="3ba09-110">Gets an enumerator for an array of generic parameter tokens associated with the specified TypeDef or MethodDef token.</span></span>|  
|[<span data-ttu-id="3ba09-111">EnumMethodSpecs (método)</span><span class="sxs-lookup"><span data-stu-id="3ba09-111">EnumMethodSpecs Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enummethodspecs-method.md)|<span data-ttu-id="3ba09-112">Obtiene un enumerador para una matriz de símbolos (tokens) de MethodSpec asociada al MethodDef o MemberRef especificado (token).</span><span class="sxs-lookup"><span data-stu-id="3ba09-112">Gets an enumerator for an array of MethodSpec tokens associated with the specified MethodDef or MemberRef token.</span></span>|  
|[<span data-ttu-id="3ba09-113">GetGenericParamConstraintProps (método)</span><span class="sxs-lookup"><span data-stu-id="3ba09-113">GetGenericParamConstraintProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getgenericparamconstraintprops-method.md)|<span data-ttu-id="3ba09-114">Obtiene los metadatos asociados con la restricción de parámetro genérico representada por el token de restricción especificada.</span><span class="sxs-lookup"><span data-stu-id="3ba09-114">Gets the metadata associated with the generic parameter constraint represented by the specified constraint token.</span></span>|  
|[<span data-ttu-id="3ba09-115">GetGenericParamProps (método)</span><span class="sxs-lookup"><span data-stu-id="3ba09-115">GetGenericParamProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getgenericparamprops-method.md)|<span data-ttu-id="3ba09-116">Obtiene los metadatos asociados con el parámetro genérico representado por el token especificado.</span><span class="sxs-lookup"><span data-stu-id="3ba09-116">Gets the metadata associated with the generic parameter represented by the specified token.</span></span>|  
|[<span data-ttu-id="3ba09-117">GetMethodSpecProps (método)</span><span class="sxs-lookup"><span data-stu-id="3ba09-117">GetMethodSpecProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getmethodspecprops-method.md)|<span data-ttu-id="3ba09-118">Obtiene la firma de metadatos del método al que hace referencia el MethodSpec especificado (token).</span><span class="sxs-lookup"><span data-stu-id="3ba09-118">Gets the metadata signature of the method referenced by the specified MethodSpec token.</span></span>|  
|[<span data-ttu-id="3ba09-119">GetPEKind (método)</span><span class="sxs-lookup"><span data-stu-id="3ba09-119">GetPEKind Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getpekind-method.md)|<span data-ttu-id="3ba09-120">Obtiene un valor que identifica la naturaleza del código en un archivo ejecutable portable (PE) de archivo, normalmente un archivo DLL o EXE, definido en el ámbito de metadatos actual</span><span class="sxs-lookup"><span data-stu-id="3ba09-120">Gets a value identifying the nature of the code in a portable executable (PE) file, typically a DLL or EXE file, defined in the current metadata scope</span></span>|  
|[<span data-ttu-id="3ba09-121">GetVersionString (método)</span><span class="sxs-lookup"><span data-stu-id="3ba09-121">GetVersionString Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getversionstring-method.md)|<span data-ttu-id="3ba09-122">Obtiene el número de versión del runtime que se usó para generar el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="3ba09-122">Gets the version number of the runtime that was used to build the assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3ba09-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3ba09-123">Requirements</span></span>  
 <span data-ttu-id="3ba09-124">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3ba09-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ba09-125">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="3ba09-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3ba09-126">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3ba09-126">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3ba09-127">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3ba09-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ba09-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="3ba09-128">See also</span></span>

- <xref:System.Reflection.PortableExecutableKinds>
- [<span data-ttu-id="3ba09-129">Interfaces de metadatos</span><span class="sxs-lookup"><span data-stu-id="3ba09-129">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="3ba09-130">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3ba09-130">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
