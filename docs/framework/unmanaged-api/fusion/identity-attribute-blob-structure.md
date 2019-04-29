---
title: IDENTITY_ATTRIBUTE_BLOB (Estructura)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- IDENTITY_ATTRIBUTE_BLOB
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IDENTITY_ATTRIBUTE_BLOB
helpviewer_keywords:
- IDENTITY_ATTRIBUTE_BLOB structure [.NET Framework fusion]
ms.assetid: af14ae5f-d226-47dd-ba90-8fc6e6605d4d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 074cca51cee2b0227e1d124f1d40a2ffc31e3c85
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61697360"
---
# <a name="identityattributeblob-structure"></a><span data-ttu-id="27937-102">IDENTITY_ATTRIBUTE_BLOB (Estructura)</span><span class="sxs-lookup"><span data-stu-id="27937-102">IDENTITY_ATTRIBUTE_BLOB Structure</span></span>
<span data-ttu-id="27937-103">Contiene información sobre un solo atributo en un ensamblado y consta de tres `DWORD`s.</span><span class="sxs-lookup"><span data-stu-id="27937-103">Contains information about a single attribute in an assembly, and consists of three `DWORD`s.</span></span> <span data-ttu-id="27937-104">Cada `DWORD` es un desplazamiento en un búfer de caracteres producido por la `CurrentIntoBuffer` método de la [IEnumIDENTITY_ATTRIBUTE](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md) interfaz</span><span class="sxs-lookup"><span data-stu-id="27937-104">Each `DWORD` is an offset into a character buffer produced by the `CurrentIntoBuffer` method of the [IEnumIDENTITY_ATTRIBUTE](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md) interface</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27937-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="27937-105">Syntax</span></span>  
  
```  
typedef struct _IDENTITY_ATTRIBUTE_BLOB {  
    DWORD  ofsNamespace;  
    DWORD  ofsName;  
    DWORD  ofsValue;  
}   IDENTITY_ATTRIBUTE_BLOB;  
```  
  
## <a name="members"></a><span data-ttu-id="27937-106">Miembros</span><span class="sxs-lookup"><span data-stu-id="27937-106">Members</span></span>  
  
|<span data-ttu-id="27937-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="27937-107">Member</span></span>|<span data-ttu-id="27937-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="27937-108">Description</span></span>|  
|------------|-----------------|  
|`ofsNamespace`|<span data-ttu-id="27937-109">El primer desplazamiento en el búfer de caracteres.</span><span class="sxs-lookup"><span data-stu-id="27937-109">The first offset into the character buffer.</span></span> <span data-ttu-id="27937-110">Este desplazamiento no va seguido por espacio de nombres del atributo, sino por una serie de caracteres nulos.</span><span class="sxs-lookup"><span data-stu-id="27937-110">This offset is not followed by the attribute's namespace, but by a series of null characters.</span></span> <span data-ttu-id="27937-111">Por lo tanto, no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="27937-111">Therefore, it is not used.</span></span>|  
|`ofsName`|<span data-ttu-id="27937-112">El segundo desplazamiento en el búfer de caracteres.</span><span class="sxs-lookup"><span data-stu-id="27937-112">The second offset into the character buffer.</span></span> <span data-ttu-id="27937-113">Esta ubicación marca el inicio del nombre del atributo.</span><span class="sxs-lookup"><span data-stu-id="27937-113">This location marks the start of the attribute's name.</span></span>|  
|`ofsValue`|<span data-ttu-id="27937-114">El tercer desplazamiento en el búfer de caracteres.</span><span class="sxs-lookup"><span data-stu-id="27937-114">The third offset into the character buffer.</span></span> <span data-ttu-id="27937-115">Esta ubicación marca el inicio del valor del atributo.</span><span class="sxs-lookup"><span data-stu-id="27937-115">This location marks the start of the attribute's value.</span></span>|  
  
## <a name="sample"></a><span data-ttu-id="27937-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="27937-116">Sample</span></span>  
 <span data-ttu-id="27937-117">El ejemplo siguiente muestra varios pasos básicos que suponer de relleno `IDENTITY_ATTRIBUTE_BLOB` estructura:</span><span class="sxs-lookup"><span data-stu-id="27937-117">The following example illustrates several basic steps, which eventually result in a populated `IDENTITY_ATTRIBUTE_BLOB` structure:</span></span>  
  
1. <span data-ttu-id="27937-118">Obtener un [IReferenceIdentity](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md) para el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="27937-118">Obtain an [IReferenceIdentity](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md) for the assembly.</span></span>  
  
2. <span data-ttu-id="27937-119">Llame a la `IReferenceIdentity::EnumAttributes` método y obtener un [IEnumIDENTITY_ATTRIBUTE](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md).</span><span class="sxs-lookup"><span data-stu-id="27937-119">Call the `IReferenceIdentity::EnumAttributes` method, and obtain an [IEnumIDENTITY_ATTRIBUTE](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md).</span></span>  
  
3. <span data-ttu-id="27937-120">Crear un búfer de caracteres y convertirla a una `IDENTITY_ATTRIBUTE_BLOB` estructura.</span><span class="sxs-lookup"><span data-stu-id="27937-120">Create a character buffer, and cast it as an `IDENTITY_ATTRIBUTE_BLOB` structure.</span></span>  
  
4. <span data-ttu-id="27937-121">Llame a la `CurrentIntoBuffer` método de la `IEnumIDENTITY_ATTRIBUTE` interfaz.</span><span class="sxs-lookup"><span data-stu-id="27937-121">Call the `CurrentIntoBuffer` method of the `IEnumIDENTITY_ATTRIBUTE` interface.</span></span> <span data-ttu-id="27937-122">Este método copia los atributos `Namespace`, `Name`, y `Value` en el búfer de caracteres.</span><span class="sxs-lookup"><span data-stu-id="27937-122">This method copies the attributes `Namespace`, `Name`, and `Value` into the character buffer.</span></span> <span data-ttu-id="27937-123">Los desplazamientos de tres a esas cadenas pasará a estar disponibles en el `IDENTITY_ATTRIBUTE_BLOB` estructura.</span><span class="sxs-lookup"><span data-stu-id="27937-123">The three offsets to those strings will become available in the `IDENTITY_ATTRIBUTE_BLOB` structure.</span></span>  
  
```  
// EnumAssemblyAttributes.cpp : main project file.  
  
#include "stdafx.h"  
  
#include "fusion.h"  
#include "windows.h"  
#include "stdio.h"  
#include "mscoree.h"  
#include "isolation.h"  
  
typedef HRESULT (__stdcall *PFNGETREF)(LPCWSTR pwzFile, REFIID riid, IUnknown **ppUnk);  
typedef HRESULT (__stdcall *PFNGETAUTH)(IIdentityAuthority **ppIIdentityAuthority);  
  
PFNGETREF                   g_pfnGetAssemblyIdentityFromFile = NULL;  
PFNGETAUTH                  g_pfnGetIdentityAuthority = NULL;  
IUnknown                    *g_pUnk = NULL;  
  
bool Init()  
{  
    HRESULT     hr = S_OK;  
    DWORD       dwSize = 0;  
    bool        bRC = false;  
  
    hr = CorBindToRuntimeEx(NULL, L"wks", 0, CLSID_CorRuntimeHost,  
                           IID_ICorRuntimeHost, (void **)&g_pUnk);  
    if(FAILED(hr)) {  
        printf("Error: Failed to initialize CLR runtime! hr = 0x%0x\n",  
                hr);  
        goto Exit;  
    }  
  
    if (SUCCEEDED(hr)) {  
        hr = GetRealProcAddress("GetAssemblyIdentityFromFile",  
                         (VOID **)&g_pfnGetAssemblyIdentityFromFile);  
    }  
  
    if (SUCCEEDED(hr)) {  
        hr = GetRealProcAddress("GetIdentityAuthority",  
                                (VOID **)&g_pfnGetIdentityAuthority);  
    }  
  
    if (!g_pfnGetAssemblyIdentityFromFile ||   
        !g_pfnGetIdentityAuthority)  
    {  
        printf("Error: Cannot get required APIs from fusion.dll!\n");  
        goto Exit;  
    }  
  
    bRC = true;  
  
Exit:  
    return bRC;  
}  
  
void Shutdown()  
{  
    if(g_pUnk) {  
        g_pUnk->Release();  
        g_pUnk = NULL;  
    }  
}  
  
void Usage()  
{  
    printf("EnumAssemblyAttributes: A tool to enumerate the identity   
            attributes of a given assembly.\n\n");  
    printf("Usage: EnumAssemblyAttributes AssemblyFilePath\n");  
    printf("\n");  
}  
  
int _cdecl wmain(int argc, LPCWSTR argv[])  
{  
    int     iResult = 1;  
    IUnknown                    *pUnk  = NULL;  
    IReferenceIdentity          *pRef  = NULL;  
    HRESULT                     hr     = S_OK;     
    IEnumIDENTITY_ATTRIBUTE     *pEnum = NULL;  
    BYTE                        abData[1024];  
    DWORD                       cbAvailable;  
    DWORD                       cbUsed;  
    IDENTITY_ATTRIBUTE_BLOB     *pBlob;  
  
    if(argc != 2) {  
        Usage();  
        goto Exit;  
    }  
  
    if(!Init()) {  
        printf("Failure initializing EnumIdAttr.\n");  
        goto Exit;  
    }  
  
    hr = g_pfnGetAssemblyIdentityFromFile(argv[1],   
                            __uuidof(IReferenceIdentity), &pUnk);  
  
    if (FAILED(hr)) {  
        printf("GetAssemblyIdentityFromFile failed with hr = 0x%x",   
                hr);  
        goto Exit;  
    }  
  
    hr = pUnk->QueryInterface(__uuidof(IReferenceIdentity),   
                              (void**)&pRef);  
    if (FAILED(hr)) {  
        goto Exit;  
    }  
  
    hr = pRef->EnumAttributes(&pEnum);  
    if (FAILED(hr)) {  
        printf("IReferenceIdentity::EnumAttributes failed with hr =   
                0x%x", hr);  
        goto Exit;  
    }  
  
    pBlob = (IDENTITY_ATTRIBUTE_BLOB *)(abData);  
    while (1) {  
        cbAvailable = sizeof(abData);  
        hr = pEnum->CurrentIntoBuffer(cbAvailable, abData, &cbUsed);  
        if (FAILED(hr)) {  
            printf("IEnumIDENTITY_ATTRIBUTE::CurrentIntoBuffer failed   
                    with hr = 0x%x", hr);  
            goto Exit;  
        }  
  
        if (! cbUsed) {  
            break;  
        }  
  
        LPWSTR pwzNameSpace = (LPWSTR)(abData + pBlob->ofsNamespace);  
        LPWSTR pwzName      = (LPWSTR)(abData + pBlob->ofsName);  
        LPWSTR pwzValue     = (LPWSTR)(abData + pBlob->ofsValue);  
        printf("%ws: %ws = %ws\n", pwzNameSpace, pwzName, pwzValue);  
  
        hr = pEnum->Skip(1);  
        if (FAILED(hr)) {  
            printf("IEnumIDENTITY_ATTRIBUTE::Skip failed with hr =   
                    0x%x", hr);  
            goto Exit;  
        }  
    }  
  
    iResult = 0;  
  
Exit:  
  
    Shutdown();  
  
    if (pUnk) {  
        pUnk->Release();  
    }  
  
    if (pRef) {  
        pRef->Release();  
    }  
  
    if (pEnum) {  
        pEnum->Release();  
    }  
  
    return iResult;  
}  
```  
  
### <a name="to-run-the-sample"></a><span data-ttu-id="27937-124">Para ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="27937-124">To run the sample</span></span>  
 <span data-ttu-id="27937-125">C:\\> EnumAssemblyAttributes.exe C:\WINDOWS\Microsoft.NET\Framework\v2.0.50727\System.dll</span><span class="sxs-lookup"><span data-stu-id="27937-125">C:\\> EnumAssemblyAttributes.exe C:\WINDOWS\Microsoft.NET\Framework\v2.0.50727\System.dll</span></span>  
  
### <a name="sample-output"></a><span data-ttu-id="27937-126">Resultados de ejemplo</span><span class="sxs-lookup"><span data-stu-id="27937-126">Sample output</span></span>  
 <span data-ttu-id="27937-127">Referencia cultural = neutral</span><span class="sxs-lookup"><span data-stu-id="27937-127">Culture = neutral</span></span>  
  
 <span data-ttu-id="27937-128">nombre = sistema</span><span class="sxs-lookup"><span data-stu-id="27937-128">name = System</span></span>  
  
 <span data-ttu-id="27937-129">processorArchitecture = MSIL</span><span class="sxs-lookup"><span data-stu-id="27937-129">processorArchitecture = MSIL</span></span>  
  
 <span data-ttu-id="27937-130">PublicKeyToken = b77a5c561934e089</span><span class="sxs-lookup"><span data-stu-id="27937-130">PublicKeyToken = b77a5c561934e089</span></span>  
  
 <span data-ttu-id="27937-131">Versión = 2.0.0.0</span><span class="sxs-lookup"><span data-stu-id="27937-131">Version = 2.0.0.0</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27937-132">Requisitos</span><span class="sxs-lookup"><span data-stu-id="27937-132">Requirements</span></span>  
 <span data-ttu-id="27937-133">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="27937-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27937-134">**Encabezado**: Isolation.h</span><span class="sxs-lookup"><span data-stu-id="27937-134">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="27937-135">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27937-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27937-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="27937-136">See also</span></span>

- [<span data-ttu-id="27937-137">IReferenceIdentity (interfaz)</span><span class="sxs-lookup"><span data-stu-id="27937-137">IReferenceIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md)
- [<span data-ttu-id="27937-138">IEnumIDENTITY_ATTRIBUTE (interfaz)</span><span class="sxs-lookup"><span data-stu-id="27937-138">IEnumIDENTITY_ATTRIBUTE Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md)
- [<span data-ttu-id="27937-139">IDENTITY_ATTRIBUTE (estructura)</span><span class="sxs-lookup"><span data-stu-id="27937-139">IDENTITY_ATTRIBUTE Structure</span></span>](../../../../docs/framework/unmanaged-api/fusion/identity-attribute-structure.md)
- [<span data-ttu-id="27937-140">Estructuras de fusión</span><span class="sxs-lookup"><span data-stu-id="27937-140">Fusion Structures</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)
