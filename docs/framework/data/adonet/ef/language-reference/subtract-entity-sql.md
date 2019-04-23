---
title: '- (Restar) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: bc4327f9-09c0-438f-a008-927c5c478040
ms.openlocfilehash: 2e4c08788ea57000e189c8371f0494641931184b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59316692"
---
# <a name="--subtract-entity-sql"></a><span data-ttu-id="1445a-102">- (Restar) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="1445a-102">- (Subtract) (Entity SQL)</span></span>
<span data-ttu-id="1445a-103">Resta dos números.</span><span class="sxs-lookup"><span data-stu-id="1445a-103">Subtracts two numbers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1445a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1445a-104">Syntax</span></span>  
  
```  
expression - expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="1445a-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="1445a-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="1445a-106">Expresión válida de cualquier tipo de datos numérico.</span><span class="sxs-lookup"><span data-stu-id="1445a-106">Any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="1445a-107">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="1445a-107">Result Types</span></span>  
 <span data-ttu-id="1445a-108">El tipo de datos que resulta de la promoción de tipos implícita de dos argumentos.</span><span class="sxs-lookup"><span data-stu-id="1445a-108">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="1445a-109">Para obtener más información acerca de la promoción de tipos implícita, vea [Type System](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="1445a-109">For more information about implicit type promotion, see [Type System](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1445a-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1445a-110">Example</span></span>  
 <span data-ttu-id="1445a-111">La siguiente consulta de Entity SQL usa el operador aritmético - para restar dos números.</span><span class="sxs-lookup"><span data-stu-id="1445a-111">The following Entity SQL query uses the - arithmetic operator to subtract two numbers.</span></span> <span data-ttu-id="1445a-112">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="1445a-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="1445a-113">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="1445a-113">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="1445a-114">Siga el procedimiento de [Cómo: Ejecutar una consulta que devuelve resultados StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="1445a-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="1445a-115">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="1445a-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#SUBTRACT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#subtract)]  
  
## <a name="see-also"></a><span data-ttu-id="1445a-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="1445a-116">See also</span></span>

- [<span data-ttu-id="1445a-117">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="1445a-117">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
