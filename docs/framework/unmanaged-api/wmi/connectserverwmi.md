---
title: Función ConnectServerWmi (referencia de API no administrada)
description: La función ConnectServerWmi usa DCOM para crear una conexión a un espacio de nombres WMI.
ms.date: 11/06/2017
api_name:
- ConnectServerWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- ConnectServerWmi
helpviewer_keywords:
- ConnectServerWmi function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e88129f737ee493432d06acc6ad45f8653dd1eb4
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65636768"
---
# <a name="connectserverwmi-function"></a><span data-ttu-id="0cb71-103">Función ConnectServerWmi</span><span class="sxs-lookup"><span data-stu-id="0cb71-103">ConnectServerWmi function</span></span>

<span data-ttu-id="0cb71-104">Crea una conexión a un espacio de nombres de WMI a través de DCOM en un equipo especificado.</span><span class="sxs-lookup"><span data-stu-id="0cb71-104">Creates a connection through DCOM to a WMI namespace on a specified computer.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="0cb71-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0cb71-105">Syntax</span></span>

```cpp
HRESULT ConnectServerWmi (
   [in] BSTR               strNetworkResource,
   [in] BSTR               strUser,
   [in] BSTR               strPassword,
   [in] BSTR               strLocale,
   [in] long               lSecurityFlags,
   [in] BSTR               strAuthority,
   [in] IWbemContext*      pCtx,
   [out] IWbemServices**   ppNamespace,
   [in] DWORD              impLevel,
   [in] DWORD              authLevel
);
```

## <a name="parameters"></a><span data-ttu-id="0cb71-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0cb71-106">Parameters</span></span>

`strNetworkResource`\
<span data-ttu-id="0cb71-107">[in] Puntero a una `BSTR` que contiene la ruta de acceso del espacio de nombres WMI correcto.</span><span class="sxs-lookup"><span data-stu-id="0cb71-107">[in] Pointer to a valid `BSTR` that contains the object path of the correct WMI namespace.</span></span> <span data-ttu-id="0cb71-108">Consulte la [comentarios](#remarks) sección para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="0cb71-108">See the [Remarks](#remarks) section for more information.</span></span>

`strUser`\
<span data-ttu-id="0cb71-109">[in] Un puntero a una `BSTR` que contiene el nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="0cb71-109">[in] A pointer to a valid `BSTR` that contains the user name.</span></span> <span data-ttu-id="0cb71-110">Un `null` valor indica el contexto de seguridad actual.</span><span class="sxs-lookup"><span data-stu-id="0cb71-110">A `null` value indicates the current security context.</span></span> <span data-ttu-id="0cb71-111">Si el usuario es de un dominio diferente que el actual, `strUser` también puede contener el nombre de usuario y dominio separado por una barra diagonal inversa.</span><span class="sxs-lookup"><span data-stu-id="0cb71-111">If the user is from a different domain than the current one, `strUser` can also contain the domain and user name separated by a backslash.</span></span> <span data-ttu-id="0cb71-112">`strUser` También pueden estar en formato de nombre principal (UPN) del usuario, como `userName@domainName`.</span><span class="sxs-lookup"><span data-stu-id="0cb71-112">`strUser` can also be in user principal name (UPN) format, such as `userName@domainName`.</span></span> <span data-ttu-id="0cb71-113">Consulte la [comentarios](#remarks) sección para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="0cb71-113">See the [Remarks](#remarks) section for more information.</span></span>

`strPassword`\
<span data-ttu-id="0cb71-114">[in] Un puntero a una `BSTR` que contiene la contraseña.</span><span class="sxs-lookup"><span data-stu-id="0cb71-114">[in] A pointer to a valid `BSTR` that contains the password.</span></span> <span data-ttu-id="0cb71-115">Un `null` indica el contexto de seguridad actual.</span><span class="sxs-lookup"><span data-stu-id="0cb71-115">A `null` indicates the current security context.</span></span> <span data-ttu-id="0cb71-116">Una cadena vacía ("") indica que una contraseña válida de longitud cero.</span><span class="sxs-lookup"><span data-stu-id="0cb71-116">An empty string ("") indicates a valid zero-length password.</span></span>

`strLocale`\
<span data-ttu-id="0cb71-117">[in] Un puntero a una `BSTR` que indica la configuración regional correcta para la recuperación de información.</span><span class="sxs-lookup"><span data-stu-id="0cb71-117">[in] A pointer to a valid `BSTR` that indicates the correct locale for information retrieval.</span></span> <span data-ttu-id="0cb71-118">Para los identificadores de configuración regional de Microsoft, el formato de la cadena es "MS\_*xxx*", donde *xxx* es una cadena en formato hexadecimal que indica el identificador de configuración regional (LCID).</span><span class="sxs-lookup"><span data-stu-id="0cb71-118">For Microsoft locale identifiers, the format of the string is "MS\_*xxx*", where *xxx* is a string in hexadecimal form that indicates the locale identifier (LCID).</span></span> <span data-ttu-id="0cb71-119">Si se especifica una configuración regional no válido, el método devuelve `WBEM_E_INVALID_PARAMETER` excepto en Windows 7, donde la configuración regional predeterminada del servidor se usa en su lugar.</span><span class="sxs-lookup"><span data-stu-id="0cb71-119">If an invalid locale is specified, the method returns `WBEM_E_INVALID_PARAMETER` except on Windows 7, where the default locale of the server is used instead.</span></span> <span data-ttu-id="0cb71-120">Si ' se usa null1, la configuración regional actual.</span><span class="sxs-lookup"><span data-stu-id="0cb71-120">If \`null1, the current locale is used.</span></span>

`lSecurityFlags`\
<span data-ttu-id="0cb71-121">[in] Marcas para pasar a la `ConnectServerWmi` método.</span><span class="sxs-lookup"><span data-stu-id="0cb71-121">[in] Flags to pass to the `ConnectServerWmi` method.</span></span> <span data-ttu-id="0cb71-122">Da como resultado un valor de cero (0) para este parámetro en la llamada a `ConnectServerWmi` devolver solo una vez establecida una conexión al servidor.</span><span class="sxs-lookup"><span data-stu-id="0cb71-122">A value of zero (0) for this parameter results in the call to `ConnectServerWmi` returning only after a connection to the server is established.</span></span> <span data-ttu-id="0cb71-123">Esto podría dar lugar a una aplicación no responde indefinidamente si el servidor se interrumpe.</span><span class="sxs-lookup"><span data-stu-id="0cb71-123">This could result in an application not responding indefinitely if the server is broken.</span></span> <span data-ttu-id="0cb71-124">Los otros valores válidos son:</span><span class="sxs-lookup"><span data-stu-id="0cb71-124">The other valid values are:</span></span>

| <span data-ttu-id="0cb71-125">Constante</span><span class="sxs-lookup"><span data-stu-id="0cb71-125">Constant</span></span>  | <span data-ttu-id="0cb71-126">Valor</span><span class="sxs-lookup"><span data-stu-id="0cb71-126">Value</span></span>  | <span data-ttu-id="0cb71-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="0cb71-127">Description</span></span>  |
|---------|---------|---------|
| `CONNECT_REPOSITORY_ONLY` | <span data-ttu-id="0cb71-128">0x40</span><span class="sxs-lookup"><span data-stu-id="0cb71-128">0x40</span></span> | <span data-ttu-id="0cb71-129">Reservado para uso interno.</span><span class="sxs-lookup"><span data-stu-id="0cb71-129">Reserved for internal use.</span></span> <span data-ttu-id="0cb71-130">No utilizar.</span><span class="sxs-lookup"><span data-stu-id="0cb71-130">Do not use.</span></span> |
| `WBEM_FLAG_CONNECT_USE_MAX_WAIT` | <span data-ttu-id="0cb71-131">0x80</span><span class="sxs-lookup"><span data-stu-id="0cb71-131">0x80</span></span> | <span data-ttu-id="0cb71-132">`ConnectServerWmi` se devuelve en dos minutos o menos.</span><span class="sxs-lookup"><span data-stu-id="0cb71-132">`ConnectServerWmi` returns in two minutes or less.</span></span> |

`strAuthority`\
<span data-ttu-id="0cb71-133">[in] El nombre de dominio del usuario.</span><span class="sxs-lookup"><span data-stu-id="0cb71-133">[in] The domain name of the user.</span></span> <span data-ttu-id="0cb71-134">Puede tener los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="0cb71-134">It can have the following values:</span></span>

| <span data-ttu-id="0cb71-135">Valor</span><span class="sxs-lookup"><span data-stu-id="0cb71-135">Value</span></span> | <span data-ttu-id="0cb71-136">Descripción</span><span class="sxs-lookup"><span data-stu-id="0cb71-136">Description</span></span> |
|---------|---------|
| <span data-ttu-id="0cb71-137">En blanco</span><span class="sxs-lookup"><span data-stu-id="0cb71-137">blank</span></span> | <span data-ttu-id="0cb71-138">Se usa la autenticación NTLM y se utiliza el dominio NTLM del usuario actual.</span><span class="sxs-lookup"><span data-stu-id="0cb71-138">NTLM authentication is used, and the NTLM domain of the current user is used.</span></span> <span data-ttu-id="0cb71-139">Si `strUser` especifica el dominio (la ubicación recomendada), no debe especificarse aquí.</span><span class="sxs-lookup"><span data-stu-id="0cb71-139">If `strUser` specifies the domain (the recommended location), it must not be specified here.</span></span> <span data-ttu-id="0cb71-140">La función devuelve `WBEM_E_INVALID_PARAMETER` si especifica el dominio en los dos parámetros.</span><span class="sxs-lookup"><span data-stu-id="0cb71-140">The function returns `WBEM_E_INVALID_PARAMETER` if you specify the domain in both parameters.</span></span> |
| <span data-ttu-id="0cb71-141">Kerberos:*nombre principal*</span><span class="sxs-lookup"><span data-stu-id="0cb71-141">Kerberos:*principal name*</span></span> | <span data-ttu-id="0cb71-142">Se utiliza la autenticación Kerberos, y este parámetro contiene un nombre principal de Kerberos.</span><span class="sxs-lookup"><span data-stu-id="0cb71-142">Kerberos authentication is used, and this parameter contains a Kerberos principal name.</span></span> |
| <span data-ttu-id="0cb71-143">NTLMDOMAIN:*nombre de dominio*</span><span class="sxs-lookup"><span data-stu-id="0cb71-143">NTLMDOMAIN:*domain name*</span></span> | <span data-ttu-id="0cb71-144">Se utiliza la autenticación NT LAN Manager y este parámetro contiene un nombre de dominio NTLM.</span><span class="sxs-lookup"><span data-stu-id="0cb71-144">NT LAN Manager authentication is used, and this parameter contains an NTLM domain name.</span></span> |

`pCtx`\
<span data-ttu-id="0cb71-145">[in] Normalmente, este parámetro es `null`.</span><span class="sxs-lookup"><span data-stu-id="0cb71-145">[in] Typically, this parameter is `null`.</span></span> <span data-ttu-id="0cb71-146">En caso contrario, es un puntero a un [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) objeto requerido por uno o varios proveedores de la clase dinámica.</span><span class="sxs-lookup"><span data-stu-id="0cb71-146">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) object required by one or more dynamic class providers.</span></span>

`ppNamespace`\
<span data-ttu-id="0cb71-147">[out] Devuelve la función recibe un puntero a un [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) objeto enlazado al espacio de nombres especificado.</span><span class="sxs-lookup"><span data-stu-id="0cb71-147">[out] When the function returns, receives a pointer to an [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object bound to the specified namespace.</span></span> <span data-ttu-id="0cb71-148">Se establece para que apunte a `null` cuando se produce un error.</span><span class="sxs-lookup"><span data-stu-id="0cb71-148">It is set to point to `null` when there is an error.</span></span>

`impLevel`\
<span data-ttu-id="0cb71-149">[in] El nivel de suplantación.</span><span class="sxs-lookup"><span data-stu-id="0cb71-149">[in] The impersonation level.</span></span>

`authLevel`\
<span data-ttu-id="0cb71-150">[in] El nivel de autorización.</span><span class="sxs-lookup"><span data-stu-id="0cb71-150">[in] The authorization level.</span></span>

## <a name="return-value"></a><span data-ttu-id="0cb71-151">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="0cb71-151">Return value</span></span>

<span data-ttu-id="0cb71-152">Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, también puede definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="0cb71-152">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="0cb71-153">Constante</span><span class="sxs-lookup"><span data-stu-id="0cb71-153">Constant</span></span>  |<span data-ttu-id="0cb71-154">Valor</span><span class="sxs-lookup"><span data-stu-id="0cb71-154">Value</span></span>  |<span data-ttu-id="0cb71-155">Descripción</span><span class="sxs-lookup"><span data-stu-id="0cb71-155">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="0cb71-156">0x80041001</span><span class="sxs-lookup"><span data-stu-id="0cb71-156">0x80041001</span></span> | <span data-ttu-id="0cb71-157">Ha habido un error general.</span><span class="sxs-lookup"><span data-stu-id="0cb71-157">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="0cb71-158">0x80041008</span><span class="sxs-lookup"><span data-stu-id="0cb71-158">0x80041008</span></span> | <span data-ttu-id="0cb71-159">Un parámetro no es válido.</span><span class="sxs-lookup"><span data-stu-id="0cb71-159">A parameter is not valid.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="0cb71-160">0x80041006</span><span class="sxs-lookup"><span data-stu-id="0cb71-160">0x80041006</span></span> | <span data-ttu-id="0cb71-161">No hay suficiente memoria disponible para completar la operación.</span><span class="sxs-lookup"><span data-stu-id="0cb71-161">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="0cb71-162">0</span><span class="sxs-lookup"><span data-stu-id="0cb71-162">0</span></span> | <span data-ttu-id="0cb71-163">La llamada de función fue correcta.</span><span class="sxs-lookup"><span data-stu-id="0cb71-163">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="0cb71-164">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0cb71-164">Remarks</span></span>

<span data-ttu-id="0cb71-165">Esta función contiene una llamada a la [IWbemLocator:: ConnectServer](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemlocator-connectserver) método.</span><span class="sxs-lookup"><span data-stu-id="0cb71-165">This function wraps a call to the [IWbemLocator::ConnectServer](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemlocator-connectserver) method.</span></span>

<span data-ttu-id="0cb71-166">Para el acceso local al espacio de nombres predeterminado, `strNetworkResource` puede ser una ruta de acceso de objeto simple: "root\default" o "\\.\root\default".</span><span class="sxs-lookup"><span data-stu-id="0cb71-166">For local access to the default namespace, `strNetworkResource` can be a simple object path: "root\default" or "\\.\root\default".</span></span> <span data-ttu-id="0cb71-167">Para el acceso al espacio de nombres predeterminado en un equipo remoto mediante redes de COM o compatible con Microsoft, incluya el nombre del equipo: "\\myserver\root\default".</span><span class="sxs-lookup"><span data-stu-id="0cb71-167">For access to the default namespace on a remote computer using COM or Microsoft-compatible networking, include the computer name: "\\myserver\root\default".</span></span> <span data-ttu-id="0cb71-168">El nombre del equipo también puede ser un nombre DNS o dirección IP.</span><span class="sxs-lookup"><span data-stu-id="0cb71-168">The computer name also can be a DNS name or IP address.</span></span> <span data-ttu-id="0cb71-169">El `ConnectServerWmi` función también puede conectar con equipos que ejecutan IPv6 mediante una dirección IPv6.</span><span class="sxs-lookup"><span data-stu-id="0cb71-169">The `ConnectServerWmi` function can also connect with computers running IPv6 using an IPv6 address.</span></span>

<span data-ttu-id="0cb71-170">`strUser` no puede ser una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="0cb71-170">`strUser` cannot be an empty string.</span></span> <span data-ttu-id="0cb71-171">Si se especifica el dominio en `strAuthority`, no también debe incluirse en `strUser`, o la función devuelve `WBEM_E_INVALID_PARAMETER`.</span><span class="sxs-lookup"><span data-stu-id="0cb71-171">If the domain is specified in `strAuthority`, it must not also be included in `strUser`, or the function returns `WBEM_E_INVALID_PARAMETER`.</span></span>

## <a name="requirements"></a><span data-ttu-id="0cb71-172">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0cb71-172">Requirements</span></span>

 <span data-ttu-id="0cb71-173">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0cb71-173">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

 <span data-ttu-id="0cb71-174">**Encabezado**: WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="0cb71-174">**Header:** WMINet_Utils.idl</span></span>

 <span data-ttu-id="0cb71-175">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="0cb71-175">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="0cb71-176">Vea también</span><span class="sxs-lookup"><span data-stu-id="0cb71-176">See also</span></span>

- [<span data-ttu-id="0cb71-177">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="0cb71-177">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
