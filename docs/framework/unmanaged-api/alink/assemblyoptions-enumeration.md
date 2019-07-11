---
title: AssemblyOptions (Enumeración)
ms.date: 03/30/2017
api_name:
- AssemblyOptions
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AssemblyOptions
helpviewer_keywords:
- Alink API, AssemblyOptions enumeration
- AssemblyOptions enumeration
ms.assetid: 84f83921-64cb-49e3-ac8b-22a0b77b18a8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 324e30f6cbcaa1d1d81c7c03967dbb629d2cd6e9
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67742268"
---
# <a name="assemblyoptions-enumeration"></a><span data-ttu-id="49308-102">AssemblyOptions (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="49308-102">AssemblyOptions Enumeration</span></span>
<span data-ttu-id="49308-103">Enumera las opciones de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="49308-103">Enumerates the assembly options.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49308-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="49308-104">Syntax</span></span>  
  
```cpp  
typedef enum _AssemblyOptions {  
    optAssemTitle = 0,  
    optAssemDescription,  
    optAssemConfig,  
    optAssemOS,  
    optAssemProcessor,  
    optAssemLocale,  
    optAssemVersion,  
    optAssemCompany,  
    optAssemProduct,  
    optAssemProductVersion,  
    optAssemCopyright,  
    optAssemTrademark,  
    optAssemKeyFile,  
    optAssemKeyName,  
    optAssemAlgID,  
    optAssemFlags,  
    optAssemHalfSign,  
    optAssemFileVersion,  
    optAssemSatelliteVer,  
    optLastAssemOption  
}   AssemblyOptions;  
```  
  
## <a name="fields"></a><span data-ttu-id="49308-105">Fields</span><span class="sxs-lookup"><span data-stu-id="49308-105">Fields</span></span>  
  
|<span data-ttu-id="49308-106">Campo</span><span class="sxs-lookup"><span data-stu-id="49308-106">Field</span></span>|<span data-ttu-id="49308-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="49308-107">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="49308-108">optAssemTitle</span><span class="sxs-lookup"><span data-stu-id="49308-108">optAssemTitle</span></span>|<span data-ttu-id="49308-109">Cadena: representa el título del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="49308-109">String - Represents the assembly title.</span></span>|  
|<span data-ttu-id="49308-110">optAssemDescription</span><span class="sxs-lookup"><span data-stu-id="49308-110">optAssemDescription</span></span>|<span data-ttu-id="49308-111">Cadena: contiene la descripción del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="49308-111">String - Contains the assembly description.</span></span>|  
|<span data-ttu-id="49308-112">optAssemConfig</span><span class="sxs-lookup"><span data-stu-id="49308-112">optAssemConfig</span></span>|<span data-ttu-id="49308-113">Cadena: contiene la configuración del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="49308-113">String - Contains the assembly configuration.</span></span>|  
|<span data-ttu-id="49308-114">optAssemOS</span><span class="sxs-lookup"><span data-stu-id="49308-114">optAssemOS</span></span>|<span data-ttu-id="49308-115">Cadena: codificada como: "dwOSPlatformId.dwOSMajorVersion.dwOSMinorVersion".</span><span class="sxs-lookup"><span data-stu-id="49308-115">String - Encoded as: "dwOSPlatformId.dwOSMajorVersion.dwOSMinorVersion".</span></span>|  
|<span data-ttu-id="49308-116">optAssemProcessor</span><span class="sxs-lookup"><span data-stu-id="49308-116">optAssemProcessor</span></span>|<span data-ttu-id="49308-117">ULONG</span><span class="sxs-lookup"><span data-stu-id="49308-117">ULONG</span></span>|  
|<span data-ttu-id="49308-118">optAssemLocale</span><span class="sxs-lookup"><span data-stu-id="49308-118">optAssemLocale</span></span>|<span data-ttu-id="49308-119">Cadena: contiene la configuración regional del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="49308-119">String - Contains the assembly locale.</span></span>|  
|<span data-ttu-id="49308-120">optAssemVersion</span><span class="sxs-lookup"><span data-stu-id="49308-120">optAssemVersion</span></span>|<span data-ttu-id="49308-121">Cadena: codificada como: "Principal.secundaria.compilación.revisión".</span><span class="sxs-lookup"><span data-stu-id="49308-121">String - Encoded as: "Major.Minor.Build.Revision".</span></span>|  
|<span data-ttu-id="49308-122">optAssemCompany</span><span class="sxs-lookup"><span data-stu-id="49308-122">optAssemCompany</span></span>|<span data-ttu-id="49308-123">Cadena: contiene la empresa.</span><span class="sxs-lookup"><span data-stu-id="49308-123">String - Contains the company.</span></span>|  
|<span data-ttu-id="49308-124">optAssemProduct</span><span class="sxs-lookup"><span data-stu-id="49308-124">optAssemProduct</span></span>|<span data-ttu-id="49308-125">Cadena: contiene el nombre del producto.</span><span class="sxs-lookup"><span data-stu-id="49308-125">String - Contains the product name.</span></span>|  
|<span data-ttu-id="49308-126">optAssemProductVersion</span><span class="sxs-lookup"><span data-stu-id="49308-126">optAssemProductVersion</span></span>|<span data-ttu-id="49308-127">Cadena (también conocido como InformationalVersion).</span><span class="sxs-lookup"><span data-stu-id="49308-127">String (also known as InformationalVersion).</span></span>|  
|<span data-ttu-id="49308-128">optAssemCopyright</span><span class="sxs-lookup"><span data-stu-id="49308-128">optAssemCopyright</span></span>|<span data-ttu-id="49308-129">Cadena: contiene la información de copyright.</span><span class="sxs-lookup"><span data-stu-id="49308-129">String - Contains the copyright information.</span></span>|  
|<span data-ttu-id="49308-130">optAssemTrademark</span><span class="sxs-lookup"><span data-stu-id="49308-130">optAssemTrademark</span></span>|<span data-ttu-id="49308-131">Cadena: contiene la información de marca comercial.</span><span class="sxs-lookup"><span data-stu-id="49308-131">String - Contains the trademark information.</span></span>|  
|<span data-ttu-id="49308-132">optAssemKeyFile</span><span class="sxs-lookup"><span data-stu-id="49308-132">optAssemKeyFile</span></span>|<span data-ttu-id="49308-133">String (nombre de archivo).</span><span class="sxs-lookup"><span data-stu-id="49308-133">String (file name).</span></span>|  
|<span data-ttu-id="49308-134">optAssemKeyName</span><span class="sxs-lookup"><span data-stu-id="49308-134">optAssemKeyName</span></span>|<span data-ttu-id="49308-135">Cadena (el nombre de clave).</span><span class="sxs-lookup"><span data-stu-id="49308-135">String (The key name).</span></span>|  
|<span data-ttu-id="49308-136">optAssemAlgID</span><span class="sxs-lookup"><span data-stu-id="49308-136">optAssemAlgID</span></span>|<span data-ttu-id="49308-137">ULONG</span><span class="sxs-lookup"><span data-stu-id="49308-137">ULONG</span></span>|  
|<span data-ttu-id="49308-138">optAssemFlags</span><span class="sxs-lookup"><span data-stu-id="49308-138">optAssemFlags</span></span>|<span data-ttu-id="49308-139">ULONG</span><span class="sxs-lookup"><span data-stu-id="49308-139">ULONG</span></span>|  
|<span data-ttu-id="49308-140">optAssemHalfSign</span><span class="sxs-lookup"><span data-stu-id="49308-140">optAssemHalfSign</span></span>|<span data-ttu-id="49308-141">BOOL (también conocida como DelaySign).</span><span class="sxs-lookup"><span data-stu-id="49308-141">Bool (Also known as DelaySign).</span></span>|  
|<span data-ttu-id="49308-142">optAssemFileVersion</span><span class="sxs-lookup"><span data-stu-id="49308-142">optAssemFileVersion</span></span>|<span data-ttu-id="49308-143">Cadena: codificada como "Major.Minor.Build.Revision" como ProductVersion.</span><span class="sxs-lookup"><span data-stu-id="49308-143">String - Encoded as "Major.Minor.Build.Revision"--same as ProductVersion.</span></span>|  
|<span data-ttu-id="49308-144">optAssemSatelliteVer</span><span class="sxs-lookup"><span data-stu-id="49308-144">optAssemSatelliteVer</span></span>|<span data-ttu-id="49308-145">Cadena - codificada como "Principal.secundaria.compilación.revisión".</span><span class="sxs-lookup"><span data-stu-id="49308-145">String - Encoded as "Major.Minor.Build.Revision".</span></span>|  
|<span data-ttu-id="49308-146">optLastAssemOption</span><span class="sxs-lookup"><span data-stu-id="49308-146">optLastAssemOption</span></span>|<span data-ttu-id="49308-147">Un contador del número de elementos.</span><span class="sxs-lookup"><span data-stu-id="49308-147">A counter of the number of elements.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="49308-148">Requisitos</span><span class="sxs-lookup"><span data-stu-id="49308-148">Requirements</span></span>  
 <span data-ttu-id="49308-149">**Encabezado:** alink.h</span><span class="sxs-lookup"><span data-stu-id="49308-149">**Header:** alink.h</span></span>  
  
 <span data-ttu-id="49308-150">**Biblioteca**: alink.dll</span><span class="sxs-lookup"><span data-stu-id="49308-150">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49308-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="49308-151">See also</span></span>

- [<span data-ttu-id="49308-152">Al.exe (Assembly Linker)</span><span class="sxs-lookup"><span data-stu-id="49308-152">Al.exe (Assembly Linker)</span></span>](../../../../docs/framework/tools/al-exe-assembly-linker.md)
