---
title: Procedimiento para controlar la ordenación en una consulta PLINQ
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, how to control ordering
ms.assetid: c67eccc7-004d-4b2f-987e-919cbbd62ef7
ms.openlocfilehash: d38c039fa99433d9476d62c1e96dff7e306fd766
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123122"
---
# <a name="how-to-control-ordering-in-a-plinq-query"></a>Procedimiento para controlar la ordenación en una consulta PLINQ
En estos ejemplos se muestra cómo controlar la ordenación de una consulta PLINQ con el método de extensión <xref:System.Linq.ParallelEnumerable.AsOrdered%2A>.  
  
> [!WARNING]
> La finalidad principal de estos ejemplos es mostrar el uso, y puede que su ejecución sea o no tan rápida como la de las consultas LINQ to Objects secuenciales equivalentes.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se conserva el orden de la secuencia de origen. Esto a veces es necesario; por ejemplo, algunos operadores de consulta requieren una secuencia de origen ordenada para generar resultados correctos.  
  
 [!code-csharp[PLINQ#12](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#12)]
 [!code-vb[PLINQ#12](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#12)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestran algunos operadores de consulta cuya secuencia de origen probablemente se espera que esté ordenada. Estos operadores pueden funcionar en secuencias no ordenadas, pero podrían producir resultados inesperados.  
  
 [!code-csharp[PLINQ#14](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#14)]
 [!code-vb[PLINQ#14](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#14)]  
  
 Para ejecutar este método, péguelo en la clase PLINQDataSample en el [ejemplo de datos de PLINQ](../../../docs/standard/parallel-programming/plinq-data-sample.md) del proyecto y presione F5.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo se conserva el orden de la primera parte de una consulta, después se quita el orden para aumentar el rendimiento de una cláusula de combinación y, por último, se vuelve a aplicar el orden de la secuencia del resultado final.  
  
 [!code-csharp[PLINQ#15](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#15)]
 [!code-vb[PLINQ#15](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#15)]  
  
 Para ejecutar este método, péguelo en la clase PLINQDataSample en el [ejemplo de datos de PLINQ](../../../docs/standard/parallel-programming/plinq-data-sample.md) del proyecto y presione F5.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Linq.ParallelEnumerable>
- [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
