---
title: HAVING (Entity SQL)
ms.date: 03/30/2017
ms.assetid: b5d52d97-8372-4335-beac-2d0b79dc3707
ms.openlocfilehash: 97ed6e06241804bf2f576c910a2235b0cb570bbb
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833731"
---
# <a name="having-entity-sql"></a>HAVING (Entity SQL)
Especifica una condición de búsqueda para un grupo o agregado.  
  
## <a name="syntax"></a>Sintaxis  
  
```sql  
[ HAVING search_condition ]  
```  
  
## <a name="arguments"></a>Argumentos  
 `search_condition`  
 Especifica la condición de búsqueda del grupo o del agregado que se debe cumplir. Cuando se utiliza HAVING con GROUP BY ALL, la cláusula HAVING invalida ALL.  
  
## <a name="remarks"></a>Comentarios  
 La cláusula HAVING se utiliza para especificar una condición de filtrado adicional en el resultado de una agrupación. Si no se especifica una cláusula GROUP BY en la expresión de consulta, se supone un grupo de conjunto único implícito.  
  
> [!NOTE]
> HAVING solo se puede usar con la instrucción [Select](select-entity-sql.md) . Cuando no se usa [Group by](group-by-entity-sql.md) , having se comporta como una cláusula WHERE.  
  
La cláusula HAVING funciona como la cláusula WHERE salvo que se aplica después de la operación GROUP BY. Esto significa que la cláusula HAVING solo puede hacer referencias a agrupar alias y agregados, como se muestra en el ejemplo siguiente:
  
```sql  
SELECT Name, SUM(o.Price * o.Quantity) AS Total FROM orderLines AS o GROUP BY o.Product AS Name  
HAVING SUM(o.Quantity) > 1  
```  
  
 Todo lo anterior hace que se restrinjan los grupos a solo aquellos que incluyen más de un producto.  
  
## <a name="example"></a>Ejemplo  
 La consulta de Entity SQL siguiente utiliza los operadores HAVING y GROUP BY para especificar una condición de búsqueda para un grupo o un agregado. La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1. Siga el procedimiento descrito en [How para: Ejecute una consulta que devuelva los resultados de PrimitiveType @ no__t-0.  
  
2. Pase la consulta siguiente como argumento al método `ExecutePrimitiveTypeQuery` :  
  
 [!code-sql[DP EntityServices Concepts#HAVING](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#having)]  
  
## <a name="see-also"></a>Vea también

- [Referencia de Entity SQL](entity-sql-reference.md)
- [Expresiones de consulta](query-expressions-entity-sql.md)
