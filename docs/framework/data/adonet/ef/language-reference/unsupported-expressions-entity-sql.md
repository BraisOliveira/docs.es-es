---
title: Expresiones no admitidas (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5e79da7e-e78a-413c-8fb0-f3f9cd84f579
dev_langs:
- sql
ms.openlocfilehash: 956fe117eb0c59392c3999046bc70deaed268ac6
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70248779"
---
# <a name="unsupported-expressions"></a><span data-ttu-id="33bff-102">Expresiones no admitidas</span><span class="sxs-lookup"><span data-stu-id="33bff-102">Unsupported expressions</span></span>

<span data-ttu-id="33bff-103">En este tema se describen las expresiones de Transact-SQL que [!INCLUDE[esql](../../../../../../includes/esql-md.md)]no se admiten en.</span><span class="sxs-lookup"><span data-stu-id="33bff-103">This topic describes Transact-SQL expressions that are not supported in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span> <span data-ttu-id="33bff-104">Para obtener más información, vea [Cómo difiere Entity SQL de Transact-SQL](how-entity-sql-differs-from-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="33bff-104">For more information, see [How Entity SQL Differs from Transact-SQL](how-entity-sql-differs-from-transact-sql.md).</span></span>

## <a name="quantified-predicates"></a><span data-ttu-id="33bff-105">Predicados cuantificados</span><span class="sxs-lookup"><span data-stu-id="33bff-105">Quantified predicates</span></span>

<span data-ttu-id="33bff-106">Transact-SQL permite construcciones de la forma siguiente:</span><span class="sxs-lookup"><span data-stu-id="33bff-106">Transact-SQL allows constructs of the following form:</span></span>

```sql
sal > all (select salary from employees)
sal > any (select salary from employees)
```

[!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="33bff-107">, sin embargo, no admite tales construcciones.</span><span class="sxs-lookup"><span data-stu-id="33bff-107">, however, does not support such constructs.</span></span> <span data-ttu-id="33bff-108">En [!INCLUDE[esql](../../../../../../includes/esql-md.md)], se pueden escribir expresiones equivalentes del siguiente modo:</span><span class="sxs-lookup"><span data-stu-id="33bff-108">Equivalent expressions can be written in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] as follows:</span></span>

```sql
not exists(select 0 from employees as e where sal <= e.salary)
exists(select 0 from employees as e where sal > e.salary)
```

## <a name="-operator"></a><span data-ttu-id="33bff-109">\* (operador)</span><span class="sxs-lookup"><span data-stu-id="33bff-109">\* operator</span></span>

<span data-ttu-id="33bff-110">Transact-SQL admite el uso del operador \* en la cláusula SELECT para indicar que se deben proyectar todas las columnas. Esto no se admite en [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="33bff-110">Transact-SQL supports the use of the \* operator in the SELECT clause to indicate that all columns should be projected out. This is not supported in [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span></span>

## <a name="see-also"></a><span data-ttu-id="33bff-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="33bff-111">See also</span></span>

- [<span data-ttu-id="33bff-112">Información general sobre Entity SQL</span><span class="sxs-lookup"><span data-stu-id="33bff-112">Entity SQL Overview</span></span>](entity-sql-overview.md)
- [<span data-ttu-id="33bff-113">Diferencias entre Entity SQL y Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="33bff-113">How Entity SQL Differs from Transact-SQL</span></span>](how-entity-sql-differs-from-transact-sql.md)
