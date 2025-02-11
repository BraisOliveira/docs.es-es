---
ms.openlocfilehash: e9278320ee3fdf9e6b89698d187f047c309ea791
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2019
ms.locfileid: "73198570"
---
### <a name="signalr-handshakeprotocolsuccesshandshakedata-replaced"></a>SignalR: se ha reemplazado HandshakeProtocol.SuccessHandshakeData

El campo [HandshakeProtocol.SuccessHandshakeData](https://github.com/aspnet/AspNetCore/blob/c5b2bc0df2a0027832bf7d01dfb19ca39cd08ae6/src/SignalR/common/SignalR.Common/src/Protocol/HandshakeProtocol.cs#L27) se ha quitado y se ha reemplazado por un método auxiliar que genera una respuesta de protocolo de enlace correcta dado un protocolo `IHubProtocol` específico.

#### <a name="version-introduced"></a>Versión introducida

3.0

#### <a name="old-behavior"></a>Comportamiento anterior

`HandshakeProtocol.SuccessHandshakeData` era un campo `public static ReadOnlyMemory<byte>`.

#### <a name="new-behavior"></a>Comportamiento nuevo

`HandshakeProtocol.SuccessHandshakeData` se ha reemplazado por un método `GetSuccessfulHandshake(IHubProtocol protocol)` `static` que devuelve un objeto `ReadOnlyMemory<byte>` basado en el protocolo especificado.

#### <a name="reason-for-change"></a>Motivo del cambio

Se han agregado campos adicionales a la _respuesta_ del protocolo de enlace que no son constantes y cambian en función del protocolo seleccionado.

#### <a name="recommended-action"></a>Acción recomendada

Ninguno. Este tipo no está diseñado para su uso desde el código de usuario. Es `public`, por lo que se puede compartir entre el servidor de SignalR y el cliente. También lo pueden usar clientes de SignalR personalizados escritos en .NET. Los **usuarios** de SignalR no deberían verse afectados por este cambio.

#### <a name="category"></a>Categoría

ASP.NET Core

#### <a name="affected-apis"></a>API afectadas

<xref:Microsoft.AspNetCore.SignalR.Protocol.HandshakeProtocol.SuccessHandshakeData?displayProperty=namewithType>

<!--

#### Affected APIs

`F:Microsoft.AspNetCore.SignalR.Protocol.HandshakeProtocol.SuccessHandshakeData`

-->
