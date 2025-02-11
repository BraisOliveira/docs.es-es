---
title: 'Cómo: Implementar una operación de servicios asincrónica'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 4e5d2ea5-d8f8-4712-bd18-ea3c5461702c
ms.openlocfilehash: b706ec49db123f33b3fc1ab0f420ed9a47e32f67
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2019
ms.locfileid: "72320947"
---
# <a name="how-to-implement-an-asynchronous-service-operation"></a>Cómo: Implementar una operación de servicios asincrónica
En las aplicaciones Windows Communication Foundation (WCF), una operación de servicio se puede implementar de forma asincrónica o sincrónica sin indicar al cliente cómo llamarla. Por ejemplo, se puede llamar a las operaciones de servicio asincrónicas de forma sincrónica y se puede llamar a las operaciones de servicio sincrónicamente. Para obtener un ejemplo en el que se muestra cómo llamar a una operación de forma asincrónica en una aplicación cliente, vea [Cómo: llamar a operaciones de servicio de forma asincrónica](./feature-details/how-to-call-wcf-service-operations-asynchronously.md). Para obtener más información sobre las operaciones sincrónicas y asincrónicas, vea [diseñar contratos de servicio](designing-service-contracts.md) y [operaciones sincrónicas y asincrónicas](synchronous-and-asynchronous-operations.md). En este tema se describe la estructura básica de una operación de servicio asincrónica, el código no está completo. Para obtener un ejemplo completo de los lados del servicio y del cliente, consulte [asincrónica](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms751505(v=vs.100)).  
  
### <a name="implement-a-service-operation-asynchronously"></a>Implementación de una operación de servicio de manera asincrónica  
  
1. En su contrato de servicio, declare un par de métodos asincrónicos según las instrucciones de diseño asincrónico de .NET. El método `Begin` toma un parámetro, un objeto de devolución de llamada y un objeto de estado, y devuelve un <xref:System.IAsyncResult?displayProperty=nameWithType> y un método `End` correspondiente que toma <xref:System.IAsyncResult?displayProperty=nameWithType> y devuelven el valor devuelto. Para obtener más información sobre las llamadas asincrónicas, consulte [patrones de diseño de programación asincrónica](https://go.microsoft.com/fwlink/?LinkId=248221).  
  
2. Marque el método `Begin` del par de métodos asincrónicos con el atributo <xref:System.ServiceModel.OperationContractAttribute?displayProperty=nameWithType> y establezca la propiedad <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern%2A?displayProperty=nameWithType> en `true`. Por ejemplo, el código siguiente realiza los pasos 1 y 2.  
  
     [!code-csharp[C_SyncAsyncClient#6](../../../samples/snippets/csharp/VS_Snippets_CFX/c_syncasyncclient/cs/services.cs#6)]
     [!code-vb[C_SyncAsyncClient#6](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_syncasyncclient/vb/services.vb#6)]  
  
3. Implemente el par de método `Begin/End` en su clase de servicio según las instrucciones de diseño asincrónicas. Por ejemplo, el siguiente ejemplo de código muestra una implementación en la que una cadena se escribe en la consola en porciones `Begin` y `End` de la operación de servicio asincrónica y el valor devuelto de la operación `End` se devuelve al cliente. Para obtener el ejemplo de código completo, consulte la sección Ejemplo.  
  
     [!code-csharp[C_SyncAsyncClient#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_syncasyncclient/cs/services.cs#3)]
     [!code-vb[C_SyncAsyncClient#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_syncasyncclient/vb/services.vb#3)]  
  
## <a name="example"></a>Ejemplo  
 Los siguientes ejemplos de código muestran:  
  
1. Una interfaz del contrato de servicio con:  
  
    1. Una operación `SampleMethod` sincrónica.  
  
    2. Una operación `BeginSampleMethod` asincrónica.  
  
    3. Un par de operaciones asincrónica `BeginServiceAsyncMethod` @ no__t-1 @ no__t-2.  
  
2. Una implementación de servicio mediante un objeto <xref:System.IAsyncResult?displayProperty=nameWithType>.  
  
 [!code-csharp[C_SyncAsyncClient#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_syncasyncclient/cs/services.cs#1)]
 [!code-vb[C_SyncAsyncClient#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_syncasyncclient/vb/services.vb#1)]  
  
## <a name="see-also"></a>Vea también

- [Diseño de contratos de servicio](designing-service-contracts.md)
- [Operaciones sincrónicas y asincrónicas](synchronous-and-asynchronous-operations.md)
