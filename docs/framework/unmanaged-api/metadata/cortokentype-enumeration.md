---
title: CorTokenType (Enumeración)
ms.date: 03/30/2017
api_name:
- CorTokenType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorTokenType
helpviewer_keywords:
- CorTokenType enumeration [.NET Framework metadata]
ms.assetid: 93c9a369-225f-4eff-9b78-3fbee4902cf1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b4f34340c18fddc46695fe64946c3afd90ed7454
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67772295"
---
# <a name="cortokentype-enumeration"></a>CorTokenType (Enumeración)
Indica el tipo de un token de metadatos.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum CorTokenType {  
  
    mdtModule                       = 0x00000000,  
    mdtTypeRef                      = 0x01000000,  
    mdtTypeDef                      = 0x02000000,  
    mdtFieldDef                     = 0x04000000,  
    mdtMethodDef                    = 0x06000000,  
    mdtParamDef                     = 0x08000000,  
    mdtInterfaceImpl                = 0x09000000,  
    mdtMemberRef                    = 0x0a000000,  
    mdtCustomAttribute              = 0x0c000000,  
    mdtPermission                   = 0x0e000000,  
    mdtSignature                    = 0x11000000,  
    mdtEvent                        = 0x14000000,  
    mdtProperty                     = 0x17000000,  
    mdtModuleRef                    = 0x1a000000,  
    mdtTypeSpec                     = 0x1b000000,  
    mdtAssembly                     = 0x20000000,  
    mdtAssemblyRef                  = 0x23000000,  
    mdtFile                         = 0x26000000,  
    mdtExportedType                 = 0x27000000,  
    mdtManifestResource             = 0x28000000,  
    mdtGenericParam                 = 0x2a000000,  
    mdtMethodSpec                   = 0x2b000000,  
    mdtGenericParamConstraint       = 0x2c000000,  
    mdtString                       = 0x70000000,  
    mdtName                         = 0x71000000,  
    mdtBaseType                     = 0x72000000  
  
} CorTokenType;  
```  
  
## <a name="members"></a>Miembros  
  
|Member|DESCRIPCIÓN|  
|------------|-----------------|  
|`mdtModule`|Un `mdModule` token.|  
|`mdtTypeRef`|Un `mdTypeRef` token.|  
|`mdtTypeDef`|Un `mdTypeDef` token.|  
|`mdtFieldDef`|Un `mdFieldDef` token.|  
|`mdtMethodDef`|Un `mdMethodDef` token.|  
|`mdtParamDef`|Un `mdParamDef` token.|  
|`mdtInterfaceImpl`|Un `mdInterfaceImpl` token.|  
|`mdtMemberRef`|Un `mdMemberRef` token.|  
|`mdtCustomAttribute`|Un `mdCustomAttribute` token.|  
|`mdtPermission`|Un `mdPermission` token.|  
|`mdtSignature`|Un `mdSignature` token.|  
|`mdtEvent`|Un `mdEvent` token.|  
|`mdtProperty`|Un `mdProperty` token.|  
|`mdtModuleRef`|Un `mdModuleRef` token.|  
|`mdtTypeSpec`|Un `mdTypeSpec` token.|  
|`mdtAssembly`|Un `mdAssembly` token.|  
|`mdtAssemblyRef`|Un `mdAssemblyRef` token.|  
|`mdtFile`|Un `mdFile` token.|  
|`mdtExportedType`|Un `mdExportedType` token.|  
|`mdtManifestResource`|Un `mdManifestResource` token.|  
|`mdtGenericParam`|Un `mdGenericParam` token.|  
|`mdtMethodSpec`|Un `mdMethodSpec` token.|  
|`mdtGenericParamConstraint`|Un `mdGenericParamConstraint` token.|  
|`mdtString`|Un `mdString` token.|  
|`mdtName`|Un `mdName` token.|  
|`mdtBaseType`|No se utiliza.|  
  
## <a name="remarks"></a>Comentarios  
 Cada valor es igual al valor del byte superior en el token de metadatos correspondiente.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorHdr.h  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones para metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
