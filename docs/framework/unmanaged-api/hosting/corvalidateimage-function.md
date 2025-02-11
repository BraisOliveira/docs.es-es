---
title: _CorValidateImage (Función)
ms.date: 03/30/2017
api_name:
- _CorValidateImage
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- _CorValidateImage
helpviewer_keywords:
- _CorValidateImage function [.NET Framework hosting]
ms.assetid: 0117e080-05f9-4772-885d-e1847230947c
topic_type:
- apiref
ms.openlocfilehash: 42da5bb761ba8ce388bd41d46e8fdc4561ad0290
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136883"
---
# <a name="_corvalidateimage-function"></a>_CorValidateImage (Función)
Valida las imágenes del módulo administrado y notifica al cargador del sistema operativo una vez que se han cargado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
STDAPI _CorValidateImage (   
   [in] PVOID* ImageBase,  
   [in] LPCWSTR FileName  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `ImageBase`  
 de Puntero a la ubicación inicial de la imagen que se va a validar como código administrado. La imagen ya debe estar cargada en la memoria.  
  
 `FileName`  
 de Nombre de archivo de la imagen.  
  
## <a name="return-value"></a>Valor devuelto  
 Esta función devuelve los valores estándar `E_INVALIDARG`, `E_OUTOFMEMORY`, `E_UNEXPECTED`y `E_FAIL`, así como los valores siguientes.  
  
|Valor devuelto|Descripción|  
|------------------|-----------------|  
|`STATUS_INVALID_IMAGE_FORMAT`|La imagen no es válida. Este valor tiene HRESULT 0xC000007BL.|  
|`STATUS_SUCCESS`|La imagen es válida. Este valor tiene HRESULT 0x00000000L.|  
  
## <a name="remarks"></a>Comentarios  
 En Windows XP y versiones posteriores, el cargador del sistema operativo comprueba los módulos administrados examinando el bit del directorio de descriptores COM en el encabezado Common Object File Format (COFF). Un bit establecido indica un módulo administrado. Si el cargador detecta un módulo administrado, carga MsCorEE. dll y llama a `_CorValidateImage`, que realiza las acciones siguientes:  
  
- Confirma que la imagen es un módulo administrado válido.  
  
- Cambia el punto de entrada de la imagen a un punto de entrada en el Common Language Runtime (CLR).  
  
- En las versiones de Windows de 64 bits, modifica la imagen que está en la memoria transformando el formato de PE32 a PE32 +.  
  
- Vuelve al cargador cuando se cargan las imágenes del módulo administrado.  
  
 En el caso de las imágenes ejecutables, el cargador del sistema operativo llama a la función [_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) , independientemente del punto de entrada especificado en el archivo ejecutable. En el caso de las imágenes de ensamblado de DLL, el cargador llama a la función [_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) .  
  
 `_CorExeMain` o `_CorDllMain` realiza las siguientes acciones:  
  
- Inicializa el CLR.  
  
- Busca el punto de entrada administrado del encabezado CLR del ensamblado.  
  
- Comienza la ejecución.  
  
 El cargador llama a la función [_CorImageUnloading](../../../../docs/framework/unmanaged-api/hosting/corimageunloading-function.md) cuando se descargan imágenes del módulo administrado. Sin embargo, esta función no realiza ninguna acción; simplemente devuelve.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se incluye como recurso en MsCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Funciones estáticas globales para metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
