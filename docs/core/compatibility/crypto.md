---
title: Cambios importantes de criptografía, versiones de 2.2 a 3.0 - .NET Core
description: Enumera los cambios importantes de la versión 2.2 a la versión 3.0 de .NET Core, ASP.NET Core y EF Core.
ms.date: 09/10/2019
ms.openlocfilehash: ba330bdef4be8cfe0e74f5645adaf66b2e0051ac
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73089583"
---
# <a name="breaking-changes-for-migration-from-version-22-to-30"></a>Cambios importantes para la migración de la versión 2.2 a la 3.0

> [!IMPORTANT]
> Este artículo está en construcción. Esta no es una lista completa de todos los cambios importantes en .NET Core. Para obtener más información sobre los cambios importantes en .NET Core, puede consultar las [propuestas de cambios importantes](https://github.com/dotnet/docs/issues?q=is%3Aissue+is%3Aopen+label%3Abreaking-change) individuales en el repositorio dotnet/docs de GitHub. 

Si va a migrar desde la versión 2.2 a la versión 3.0 de .NET Core, ASP.NET Core o EF Core, revise los temas siguientes para ver los cambios importantes que pueden afectar a la aplicación:

## <a name="corefx"></a>CoreFX

[!INCLUDE[APIs that report version now report product and not file version](~/includes/core-changes/corefx/version-information-changes.md)]

***

[!INCLUDE[Custom EncoderFallbackBuffer instances cannot fall back recursively](~/includes/core-changes/corefx/custom-encoderfallbackbuffer-cannot-be-recursive.md)]

***

[!INCLUDE[Floating point formatting and parsing behavior changes](~/includes/core-changes/corefx/floating-point-changes.md)]

***

[!INCLUDE[InvalidAsynchronousStateException moved to another assembly](~/includes/core-changes/corefx/move-invalidasynchronousstateexception.md)]

***

[!INCLUDE[NET Core 3.0 follows Unicode best practices when replacing ill-formed UTF-8 byte sequences](~/includes/core-changes/corefx/net-core-3-0-follows-unicode-utf8-best-practices.md)]

***

[!INCLUDE[TypeDescriptionProviderAttribute moved to another assembly](~/includes/core-changes/corefx/move-typedescriptionproviderattribute.md)]

***

[!INCLUDE[ZipArchiveEntry no longer handles archives with inconsistent entry sizes](~/includes/core-changes/corefx/ziparchiveentry-and-inconsistent-entry-sizes.md)]

## <a name="cryptography"></a>Criptografía

[!INCLUDE[EnvelopedCms defaults to AES-256 encryption](~/includes/core-changes/cryptography/envelopedcms-defaults-to-aes256.md)]

***

[!INCLUDE[Minimum size for RSAOpenSsl key generation has increased](~/includes/core-changes/cryptography/minimum-rsaopenssl-key-size-change.md)]

***

[!INCLUDE[.NET Core 3.0 prefers OpenSSL 1.1.x to OpenSSL 1.0.x](~/includes/core-changes/cryptography/net-core-3-0-prefers-openssl-1-1-x.md)]

## <a name="globalization"></a>Globalización

[!INCLUDE["C" locale maps to the invariant locale](~/includes/core-changes/globalization/c-locale-maps-to-invariant-locale.md)]

## <a name="visual-basic"></a>Visual Basic

[!INCLUDE[vbNewLine is obsolete](~/includes/core-changes/visualbasic/vbnewline-is-obsolete.md)]

## <a name="entity-framework-core"></a>Entity Framework Core

[Cambios importantes de Entity Framework Core](/ef/core/what-is-new/ef-core-3.0/breaking-changes)
