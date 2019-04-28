---
title: Inferir relaciones
ms.date: 03/30/2017
ms.assetid: 8fa86a9d-6545-4a9d-b1f5-58d9742179c7
ms.openlocfilehash: f8a9aba493dfe82466608ea60932ddfec5ef64f1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61879676"
---
# <a name="inferring-relationships"></a><span data-ttu-id="313ba-102">Inferir relaciones</span><span class="sxs-lookup"><span data-stu-id="313ba-102">Inferring Relationships</span></span>
<span data-ttu-id="313ba-103">Si un elemento que se deduce como una tabla tiene un elemento secundario que también se deduce como una tabla, se creará una <xref:System.Data.DataRelation> entre las dos tablas.</span><span class="sxs-lookup"><span data-stu-id="313ba-103">If an element that is inferred as a table has a child element that is also inferred as a table, a <xref:System.Data.DataRelation> will be created between the two tables.</span></span> <span data-ttu-id="313ba-104">Una nueva columna con el nombre de **ParentTableName_Id** se agregará a la tabla creada para el elemento primario y la tabla creada para el elemento secundario.</span><span class="sxs-lookup"><span data-stu-id="313ba-104">A new column with a name of **ParentTableName_Id** will be added to both the table created for the parent element, and the table created for the child element.</span></span> <span data-ttu-id="313ba-105">El **ColumnMapping** propiedad de esta columna de identidad se establecerá en **MappingType.Hidden**.</span><span class="sxs-lookup"><span data-stu-id="313ba-105">The **ColumnMapping** property of this identity column will be set to **MappingType.Hidden**.</span></span> <span data-ttu-id="313ba-106">La columna será una clave principal de incremento automático para la tabla primaria y se usará para la **DataRelation** entre las dos tablas.</span><span class="sxs-lookup"><span data-stu-id="313ba-106">The column will be an auto-incrementing primary key for the parent table, and will be used for the **DataRelation** between the two tables.</span></span> <span data-ttu-id="313ba-107">El tipo de datos de la columna de identidad agregada será **System.Int32**, a diferencia del tipo de datos de todas las demás columnas deducidas, que es **System.String**.</span><span class="sxs-lookup"><span data-stu-id="313ba-107">The data type of the added identity column will be **System.Int32**, unlike the data type of all other inferred columns, which is **System.String**.</span></span> <span data-ttu-id="313ba-108">Un <xref:System.Data.ForeignKeyConstraint> con **DeleteRule** = **Cascade** también se creará con la nueva columna en el elemento primario y secundario de las tablas.</span><span class="sxs-lookup"><span data-stu-id="313ba-108">A <xref:System.Data.ForeignKeyConstraint> with **DeleteRule** = **Cascade** will also be created using the new column in both the parent and child tables.</span></span>  
  
 <span data-ttu-id="313ba-109">Por ejemplo, tomemos el siguiente código XML:</span><span class="sxs-lookup"><span data-stu-id="313ba-109">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1 attr1="value1" attr2="value2"/>  
    <ChildElement2>Text2</ChildElement2>  
  </Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="313ba-110">El proceso de inferencia producirá dos tablas: **Element1** y **ChildElement1**.</span><span class="sxs-lookup"><span data-stu-id="313ba-110">The inference process will produce two tables: **Element1** and **ChildElement1**.</span></span>  
  
 <span data-ttu-id="313ba-111">El **Element1** tabla tendrá dos columnas: **Element1_Id** y **ChildElement2**.</span><span class="sxs-lookup"><span data-stu-id="313ba-111">The **Element1** table will have two columns: **Element1_Id** and **ChildElement2**.</span></span> <span data-ttu-id="313ba-112">El **ColumnMapping** propiedad de la **Element1_Id** columna se establecerá en **MappingType.Hidden**.</span><span class="sxs-lookup"><span data-stu-id="313ba-112">The **ColumnMapping** property of the **Element1_Id** column will be set to **MappingType.Hidden**.</span></span> <span data-ttu-id="313ba-113">El **ColumnMapping** propiedad de la **ChildElement2** columna se establecerá en **MappingType.Element**.</span><span class="sxs-lookup"><span data-stu-id="313ba-113">The **ColumnMapping** property of the **ChildElement2** column will be set to **MappingType.Element**.</span></span> <span data-ttu-id="313ba-114">El **Element1_Id** columna se establecerá como la clave principal de la **Element1** tabla.</span><span class="sxs-lookup"><span data-stu-id="313ba-114">The **Element1_Id** column will be set as the primary key of the **Element1** table.</span></span>  
  
 <span data-ttu-id="313ba-115">El **ChildElement1** tabla tendrá tres columnas: **attr1**, **attr2** y **Element1_Id**.</span><span class="sxs-lookup"><span data-stu-id="313ba-115">The **ChildElement1** table will have three columns: **attr1**, **attr2** and **Element1_Id**.</span></span> <span data-ttu-id="313ba-116">El **ColumnMapping** propiedad para el **attr1** y **attr2** columnas se establecerá en **MappingType.Attribute**.</span><span class="sxs-lookup"><span data-stu-id="313ba-116">The **ColumnMapping** property for the **attr1** and **attr2** columns will be set to **MappingType.Attribute**.</span></span> <span data-ttu-id="313ba-117">El **ColumnMapping** propiedad de la **Element1_Id** columna se establecerá en **MappingType.Hidden**.</span><span class="sxs-lookup"><span data-stu-id="313ba-117">The **ColumnMapping** property of the **Element1_Id** column will be set to **MappingType.Hidden**.</span></span>  
  
 <span data-ttu-id="313ba-118">Un **DataRelation** y **ForeignKeyConstraint** , se creará con el **Element1_Id** columnas de ambas tablas.</span><span class="sxs-lookup"><span data-stu-id="313ba-118">A **DataRelation** and **ForeignKeyConstraint** will be created using the **Element1_Id** columns from both tables.</span></span>  
  
 <span data-ttu-id="313ba-119">**DataSet:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="313ba-119">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="313ba-120">**Tabla:** Element1</span><span class="sxs-lookup"><span data-stu-id="313ba-120">**Table:** Element1</span></span>  
  
|<span data-ttu-id="313ba-121">Element1_Id</span><span class="sxs-lookup"><span data-stu-id="313ba-121">Element1_Id</span></span>|<span data-ttu-id="313ba-122">ChildElement2</span><span class="sxs-lookup"><span data-stu-id="313ba-122">ChildElement2</span></span>|  
|------------------|-------------------|  
|<span data-ttu-id="313ba-123">0</span><span class="sxs-lookup"><span data-stu-id="313ba-123">0</span></span>|<span data-ttu-id="313ba-124">Text2</span><span class="sxs-lookup"><span data-stu-id="313ba-124">Text2</span></span>|  
  
 <span data-ttu-id="313ba-125">**Tabla:** ChildElement1</span><span class="sxs-lookup"><span data-stu-id="313ba-125">**Table:** ChildElement1</span></span>  
  
|<span data-ttu-id="313ba-126">attr1</span><span class="sxs-lookup"><span data-stu-id="313ba-126">attr1</span></span>|<span data-ttu-id="313ba-127">attr2</span><span class="sxs-lookup"><span data-stu-id="313ba-127">attr2</span></span>|<span data-ttu-id="313ba-128">Element1_Id</span><span class="sxs-lookup"><span data-stu-id="313ba-128">Element1_Id</span></span>|  
|-----------|-----------|------------------|  
|<span data-ttu-id="313ba-129">value1</span><span class="sxs-lookup"><span data-stu-id="313ba-129">value1</span></span>|<span data-ttu-id="313ba-130">value2</span><span class="sxs-lookup"><span data-stu-id="313ba-130">value2</span></span>|<span data-ttu-id="313ba-131">0</span><span class="sxs-lookup"><span data-stu-id="313ba-131">0</span></span>|  
  
 <span data-ttu-id="313ba-132">**DataRelation:** Element1_ChildElement1</span><span class="sxs-lookup"><span data-stu-id="313ba-132">**DataRelation:** Element1_ChildElement1</span></span>  
  
 <span data-ttu-id="313ba-133">**ParentTable:** Element1</span><span class="sxs-lookup"><span data-stu-id="313ba-133">**ParentTable:** Element1</span></span>  
  
 <span data-ttu-id="313ba-134">**ParentColumn:** Element1_Id</span><span class="sxs-lookup"><span data-stu-id="313ba-134">**ParentColumn:** Element1_Id</span></span>  
  
 <span data-ttu-id="313ba-135">**ChildTable:** ChildElement1</span><span class="sxs-lookup"><span data-stu-id="313ba-135">**ChildTable:** ChildElement1</span></span>  
  
 <span data-ttu-id="313ba-136">**ChildColumn:** Element1_Id</span><span class="sxs-lookup"><span data-stu-id="313ba-136">**ChildColumn:** Element1_Id</span></span>  
  
 <span data-ttu-id="313ba-137">**Anidado:** True</span><span class="sxs-lookup"><span data-stu-id="313ba-137">**Nested:** True</span></span>  
  
 <span data-ttu-id="313ba-138">**ForeignKeyConstraint:** Element1_ChildElement1</span><span class="sxs-lookup"><span data-stu-id="313ba-138">**ForeignKeyConstraint:** Element1_ChildElement1</span></span>  
  
 <span data-ttu-id="313ba-139">**Columna:** Element1_Id</span><span class="sxs-lookup"><span data-stu-id="313ba-139">**Column:** Element1_Id</span></span>  
  
 <span data-ttu-id="313ba-140">**ParentTable:** Element1</span><span class="sxs-lookup"><span data-stu-id="313ba-140">**ParentTable:** Element1</span></span>  
  
 <span data-ttu-id="313ba-141">**ChildTable:** ChildElement1</span><span class="sxs-lookup"><span data-stu-id="313ba-141">**ChildTable:** ChildElement1</span></span>  
  
 <span data-ttu-id="313ba-142">**DeleteRule:** Cascade</span><span class="sxs-lookup"><span data-stu-id="313ba-142">**DeleteRule:** Cascade</span></span>  
  
 <span data-ttu-id="313ba-143">**AcceptRejectRule:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="313ba-143">**AcceptRejectRule:** None</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="313ba-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="313ba-144">See also</span></span>

- [<span data-ttu-id="313ba-145">Inferencia de una estructura relacional de un conjunto de datos a partir de XML</span><span class="sxs-lookup"><span data-stu-id="313ba-145">Inferring DataSet Relational Structure from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="313ba-146">Carga de un conjunto de datos desde XML</span><span class="sxs-lookup"><span data-stu-id="313ba-146">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)
- [<span data-ttu-id="313ba-147">Carga de información del esquema de un conjunto de datos desde XML</span><span class="sxs-lookup"><span data-stu-id="313ba-147">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="313ba-148">Anidado de objetos DataRelation</span><span class="sxs-lookup"><span data-stu-id="313ba-148">Nesting DataRelations</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md)
- [<span data-ttu-id="313ba-149">Usar XML en un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="313ba-149">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)
- [<span data-ttu-id="313ba-150">Objetos DataSet, DataTable y DataView</span><span class="sxs-lookup"><span data-stu-id="313ba-150">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [<span data-ttu-id="313ba-151">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="313ba-151">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
