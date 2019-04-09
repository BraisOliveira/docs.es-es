---
title: CorMethodAttr (Enumeración)
ms.date: 03/30/2017
api_name:
- CorMethodAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorMethodAttr
helpviewer_keywords:
- CorMethodAttr enumeration [.NET Framework metadata]
ms.assetid: 4e0c3521-e54d-43c1-9857-cc76b49b8ffc
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 249de91483117db6b497fa8eae6f97c3eb0a0587
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59177000"
---
# <a name="cormethodattr-enumeration"></a><span data-ttu-id="9fef0-102">CorMethodAttr (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="9fef0-102">CorMethodAttr Enumeration</span></span>
<span data-ttu-id="9fef0-103">Contiene valores que describen las características de un método.</span><span class="sxs-lookup"><span data-stu-id="9fef0-103">Contains values that describe the features of a method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9fef0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9fef0-104">Syntax</span></span>  
  
```  
typedef enum CorMethodAttr {  
  
    mdMemberAccessMask          =   0x0007,  
    mdPrivateScope              =   0x0000,  
    mdPrivate                   =   0x0001,  
    mdFamANDAssem               =   0x0002,  
    mdAssem                     =   0x0003,  
    mdFamily                    =   0x0004,  
    mdFamORAssem                =   0x0005,  
    mdPublic                    =   0x0006,  
  
    mdStatic                    =   0x0010,  
    mdFinal                     =   0x0020,  
    mdVirtual                   =   0x0040,  
    mdHideBySig                 =   0x0080,  
  
    mdVtableLayoutMask          =   0x0100,  
    mdReuseSlot                 =   0x0000,  
    mdNewSlot                   =   0x0100,  
  
    mdCheckAccessOnOverride     =   0x0200,  
    mdAbstract                  =   0x0400,  
    mdSpecialName               =   0x0800,  
  
    mdPinvokeImpl               =   0x2000,  
    mdUnmanagedExport           =   0x0008,  
  
    mdReservedMask              =   0xd000,  
    mdRTSpecialName             =   0x1000,  
    mdHasSecurity               =   0x4000,  
    mdRequireSecObject          =   0x8000,  
  
} CorMethodAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="9fef0-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="9fef0-105">Members</span></span>  
  
|<span data-ttu-id="9fef0-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="9fef0-106">Member</span></span>|<span data-ttu-id="9fef0-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="9fef0-107">Description</span></span>|  
|------------|-----------------|  
|`mdMemberAccessMask`|<span data-ttu-id="9fef0-108">Especifica el acceso a miembros.</span><span class="sxs-lookup"><span data-stu-id="9fef0-108">Specifies member access.</span></span>|  
|`mdPrivateScope`|<span data-ttu-id="9fef0-109">Especifica que no se pueden hacer referencia a los miembros.</span><span class="sxs-lookup"><span data-stu-id="9fef0-109">Specifies that the member cannot be referenced.</span></span>|  
|`mdPrivate`|<span data-ttu-id="9fef0-110">Especifica que el miembro es accesible solo para el tipo primario.</span><span class="sxs-lookup"><span data-stu-id="9fef0-110">Specifies that the member is accessible only by the parent type.</span></span>|  
|`mdFamANDAssem`|<span data-ttu-id="9fef0-111">Especifica que el miembro es accesible para los subtipos sólo en este ensamblado.</span><span class="sxs-lookup"><span data-stu-id="9fef0-111">Specifies that the member is accessible by subtypes only in this assembly.</span></span>|  
|`mdAssem`|<span data-ttu-id="9fef0-112">Especifica que el miembro es accesible por cualquier usuario en el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="9fef0-112">Specifies that the member is accessibly by anyone in the assembly.</span></span>|  
|`mdFamily`|<span data-ttu-id="9fef0-113">Especifica que el miembro es accesible sólo mediante tipos y subtipos.</span><span class="sxs-lookup"><span data-stu-id="9fef0-113">Specifies that the member is accessible only by type and subtypes.</span></span>|  
|`mdFamORAssem`|<span data-ttu-id="9fef0-114">Especifica que el miembro es accesible para las clases derivadas y para otros tipos en su ensamblado.</span><span class="sxs-lookup"><span data-stu-id="9fef0-114">Specifies that the member is accessible by derived classes and by other types in its assembly.</span></span>|  
|`mdPublic`|<span data-ttu-id="9fef0-115">Especifica que el miembro es accesible para todos los tipos con acceso al ámbito.</span><span class="sxs-lookup"><span data-stu-id="9fef0-115">Specifies that the member is accessible by all types with access to the scope.</span></span>|  
|`mdStatic`|<span data-ttu-id="9fef0-116">Especifica que el miembro está definido como parte del tipo en lugar de un miembro de una instancia.</span><span class="sxs-lookup"><span data-stu-id="9fef0-116">Specifies that the member is defined as part of the type rather than as a member of an instance.</span></span>|  
|`mdFinal`|<span data-ttu-id="9fef0-117">Especifica que no se puede invalidar el método.</span><span class="sxs-lookup"><span data-stu-id="9fef0-117">Specifies that the method cannot be overridden.</span></span>|  
|`mdVirtual`|<span data-ttu-id="9fef0-118">Especifica que se puede invalidar el método.</span><span class="sxs-lookup"><span data-stu-id="9fef0-118">Specifies that the method can be overridden.</span></span>|  
|`mdHideBySig`|<span data-ttu-id="9fef0-119">Especifica que el método oculta por nombre y firma, en lugar de simplemente por su nombre.</span><span class="sxs-lookup"><span data-stu-id="9fef0-119">Specifies that the method hides by name and signature, rather than just by name.</span></span>|  
|`mdVtableLayoutMask`|<span data-ttu-id="9fef0-120">Especifica el diseño de la tabla virtual.</span><span class="sxs-lookup"><span data-stu-id="9fef0-120">Specifies virtual table layout.</span></span>|  
|`mdReuseSlot`|<span data-ttu-id="9fef0-121">Especifica que se debe reutilizar el espacio utilizado para este método en la tabla virtual.</span><span class="sxs-lookup"><span data-stu-id="9fef0-121">Specifies that the slot used for this method in the virtual table be reused.</span></span> <span data-ttu-id="9fef0-122">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="9fef0-122">This is the default.</span></span>|  
|`mdNewSlot`|<span data-ttu-id="9fef0-123">Especifica que el método siempre obtiene una nueva ranura en la tabla virtual.</span><span class="sxs-lookup"><span data-stu-id="9fef0-123">Specifies that the method always gets a new slot in the virtual table.</span></span>|  
|`mdCheckAccessOnOverride`|<span data-ttu-id="9fef0-124">Especifica que el método puede reemplazarse por los mismos tipos a la que está visible.</span><span class="sxs-lookup"><span data-stu-id="9fef0-124">Specifies that the method can be overridden by the same types to which it is visible.</span></span>|  
|`mdAbstract`|<span data-ttu-id="9fef0-125">Especifica que no se implementa el método.</span><span class="sxs-lookup"><span data-stu-id="9fef0-125">Specifies that the method is not implemented.</span></span>|  
|`mdSpecialName`|<span data-ttu-id="9fef0-126">Especifica que el método es especial y que su nombre describe cómo.</span><span class="sxs-lookup"><span data-stu-id="9fef0-126">Specifies that the method is special, and that its name describes how.</span></span>|  
|`mdPinvokeImpl`|<span data-ttu-id="9fef0-127">Especifica que la implementación del método se reenvía mediante PInvoke.</span><span class="sxs-lookup"><span data-stu-id="9fef0-127">Specifies that the method implementation is forwarded using PInvoke.</span></span>|  
|`mdUnmanagedExport`|<span data-ttu-id="9fef0-128">Especifica que el método es un método administrado exportado a código no administrado.</span><span class="sxs-lookup"><span data-stu-id="9fef0-128">Specifies that the method is a managed method exported to unmanaged code.</span></span>|  
|`mdReservedMask`|<span data-ttu-id="9fef0-129">Reservado para uso interno por common language runtime.</span><span class="sxs-lookup"><span data-stu-id="9fef0-129">Reserved for internal use by the common language runtime.</span></span>|  
|`mdRTSpecialName`|<span data-ttu-id="9fef0-130">Especifica que common language runtime debe comprobar la codificación del nombre del método.</span><span class="sxs-lookup"><span data-stu-id="9fef0-130">Specifies that the common language runtime should check the encoding of the method name.</span></span>|  
|`mdHasSecurity`|<span data-ttu-id="9fef0-131">Especifica que el método tiene seguridad asociada a él.</span><span class="sxs-lookup"><span data-stu-id="9fef0-131">Specifies that the method has security associated with it.</span></span>|  
|`mdRequireSecObject`|<span data-ttu-id="9fef0-132">Especifica que el método llama a otro método que contiene código de seguridad.</span><span class="sxs-lookup"><span data-stu-id="9fef0-132">Specifies that the method calls another method containing security code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9fef0-133">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9fef0-133">Requirements</span></span>  
 <span data-ttu-id="9fef0-134">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9fef0-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9fef0-135">**Encabezado**: CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="9fef0-135">**Header:** CorHdr.h</span></span>  
  
 **<span data-ttu-id="9fef0-136">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="9fef0-136">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9fef0-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="9fef0-137">See also</span></span>

- [<span data-ttu-id="9fef0-138">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="9fef0-138">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
