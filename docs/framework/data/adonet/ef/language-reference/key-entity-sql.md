---
title: KEY (Entity SQL)
ms.date: 03/30/2017
ms.assetid: cbaa97a8-c89c-4460-8c74-00474695789f
ms.openlocfilehash: 14c0b5d273b26c71c9c63e8bbbcef863ac95a5f3
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319700"
---
# <a name="key-entity-sql"></a>KEY (Entity SQL)
Extrae la clave de una referencia o de una expresión de entidad.  
  
## <a name="syntax"></a>Sintaxis  
  
```sql  
KEY(createref_expression)  
```  
  
## <a name="remarks"></a>Comentarios  
 Una clave de entidad contiene los valores de clave en el orden correcto de la entidad especificada o referencia a entidad. Dado que varios conjuntos de entidades pueden estar basados en el mismo tipo, la misma clave podría aparecer en cada conjunto de entidades. Para obtener una referencia única, utilice `REF`. El tipo de valor devuelto del operador KEY es un tipo de fila que incluye un campo para cada clave de la entidad, en el mismo orden.  
  
 En el ejemplo siguiente, al operador Key se le pasa una referencia a la entidad BadOrder y devuelve la parte de la clave de esa referencia. En este caso, un tipo de registro con exactamente un campo que corresponde a la propiedad `Id` .  
  
```sql  
select Key( CreateRef(LOB.BadOrders, row(o.Id)) )   
from LOB.Orders as o  
```  
  
## <a name="example"></a>Ejemplo  
 La consulta de Entity SQL siguiente utiliza el operador KEY para extraer la parte de la clave de una expresión con referencia de tipo. La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1. Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :  
  
 [!code-sql[DP EntityServices Concepts#KEY](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#key)]  
  
## <a name="see-also"></a>Vea también

- [Referencia de Entity SQL](entity-sql-reference.md)
- [CREATEREF](createref-entity-sql.md)
- [REF](ref-entity-sql.md)
- [DEREF](deref-entity-sql.md)
