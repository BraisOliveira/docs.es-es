---
title: Procedimiento para representar columnas como columnas generadas por la base de datos
ms.date: 03/30/2017
ms.assetid: 6524b8a6-e5d2-4a3b-8e08-beafc4a84fd2
ms.openlocfilehash: bb9510986581ad6d3bcd0711aed681ef3a7c4e45
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781784"
---
# <a name="how-to-represent-columns-as-database-generated"></a><span data-ttu-id="c4ecc-102">Procedimiento para representar columnas como columnas generadas por la base de datos</span><span class="sxs-lookup"><span data-stu-id="c4ecc-102">How to: Represent Columns as Database-Generated</span></span>
<span data-ttu-id="c4ecc-103">Utilice la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> propiedad en el <xref:System.Data.Linq.Mapping.ColumnAttribute> atributo para designar que un campo o propiedad representa una columna generada por la base de datos.</span><span class="sxs-lookup"><span data-stu-id="c4ecc-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> property on the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to designate a field or property as representing a database-generated column.</span></span>  
  
 <span data-ttu-id="c4ecc-104">Para obtener ejemplos de código, vea <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>.</span><span class="sxs-lookup"><span data-stu-id="c4ecc-104">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>.</span></span>  
  
### <a name="to-designate-a-field-or-property-as-representing-a-database-generated-column"></a><span data-ttu-id="c4ecc-105">Para designar que un campo o propiedad representa una columna generada por base de datos</span><span class="sxs-lookup"><span data-stu-id="c4ecc-105">To designate a field or property as representing a database-generated column</span></span>  
  
1. <span data-ttu-id="c4ecc-106">Agregue la propiedad <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> al atributo <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span><span class="sxs-lookup"><span data-stu-id="c4ecc-106">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2. <span data-ttu-id="c4ecc-107">Establezca el valor de propiedad en `true`.</span><span class="sxs-lookup"><span data-stu-id="c4ecc-107">Set the property value to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4ecc-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="c4ecc-108">See also</span></span>

- [<span data-ttu-id="c4ecc-109">Modelo de objetos de LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="c4ecc-109">The LINQ to SQL Object Model</span></span>](the-linq-to-sql-object-model.md)
- [<span data-ttu-id="c4ecc-110">Cómo: Personalización de clases de entidad mediante el editor de código</span><span class="sxs-lookup"><span data-stu-id="c4ecc-110">How to: Customize Entity Classes by Using the Code Editor</span></span>](how-to-customize-entity-classes-by-using-the-code-editor.md)
