---
title: Inferir relaciones
ms.date: 03/30/2017
ms.assetid: 8fa86a9d-6545-4a9d-b1f5-58d9742179c7
ms.openlocfilehash: 92a4953dc7f5119ffbf171ff2a7bf5b58e896638
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2019
ms.locfileid: "70204773"
---
# <a name="inferring-relationships"></a><span data-ttu-id="8d62b-102">Inferir relaciones</span><span class="sxs-lookup"><span data-stu-id="8d62b-102">Inferring Relationships</span></span>
<span data-ttu-id="8d62b-103">Si un elemento que se deduce como una tabla tiene un elemento secundario que también se deduce como una tabla, se creará una <xref:System.Data.DataRelation> entre las dos tablas.</span><span class="sxs-lookup"><span data-stu-id="8d62b-103">If an element that is inferred as a table has a child element that is also inferred as a table, a <xref:System.Data.DataRelation> will be created between the two tables.</span></span> <span data-ttu-id="8d62b-104">Se agregará una nueva columna con el nombre **ParentTableName_Id** a la tabla creada para el elemento primario y a la tabla creada para el elemento secundario.</span><span class="sxs-lookup"><span data-stu-id="8d62b-104">A new column with a name of **ParentTableName_Id** will be added to both the table created for the parent element, and the table created for the child element.</span></span> <span data-ttu-id="8d62b-105">La propiedad **ColumnMapping** de esta columna de identidad se establecerá en **MappingType. Hidden**.</span><span class="sxs-lookup"><span data-stu-id="8d62b-105">The **ColumnMapping** property of this identity column will be set to **MappingType.Hidden**.</span></span> <span data-ttu-id="8d62b-106">La columna será una clave principal de incremento automático para la tabla primaria y se utilizará para la **DataRelation** entre las dos tablas.</span><span class="sxs-lookup"><span data-stu-id="8d62b-106">The column will be an auto-incrementing primary key for the parent table, and will be used for the **DataRelation** between the two tables.</span></span> <span data-ttu-id="8d62b-107">El tipo de datos de la columna de identidad agregada será **System. Int32**, a diferencia del tipo de datos de todas las demás columnas inferidos, que es **System. String**.</span><span class="sxs-lookup"><span data-stu-id="8d62b-107">The data type of the added identity column will be **System.Int32**, unlike the data type of all other inferred columns, which is **System.String**.</span></span> <span data-ttu-id="8d62b-108">También <xref:System.Data.ForeignKeyConstraint> se creará una con la**cascada** de **DeleteRule** = utilizando la nueva columna en las tablas primaria y secundaria.</span><span class="sxs-lookup"><span data-stu-id="8d62b-108">A <xref:System.Data.ForeignKeyConstraint> with **DeleteRule** = **Cascade** will also be created using the new column in both the parent and child tables.</span></span>  
  
 <span data-ttu-id="8d62b-109">Por ejemplo, tomemos el siguiente código XML:</span><span class="sxs-lookup"><span data-stu-id="8d62b-109">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1 attr1="value1" attr2="value2"/>  
    <ChildElement2>Text2</ChildElement2>  
  </Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="8d62b-110">El proceso de inferencia producirá dos tablas: **Element1** y **ChildElement1**.</span><span class="sxs-lookup"><span data-stu-id="8d62b-110">The inference process will produce two tables: **Element1** and **ChildElement1**.</span></span>  
  
 <span data-ttu-id="8d62b-111">La tabla **Element1** tendrá dos columnas: **Element1_Id** y **ChildElement2**.</span><span class="sxs-lookup"><span data-stu-id="8d62b-111">The **Element1** table will have two columns: **Element1_Id** and **ChildElement2**.</span></span> <span data-ttu-id="8d62b-112">La propiedad **ColumnMapping** de la columna **Element1_Id** se establecerá en **MappingType. Hidden**.</span><span class="sxs-lookup"><span data-stu-id="8d62b-112">The **ColumnMapping** property of the **Element1_Id** column will be set to **MappingType.Hidden**.</span></span> <span data-ttu-id="8d62b-113">La propiedad **ColumnMapping** de la columna **ChildElement2** se establecerá en **MappingType. Element**.</span><span class="sxs-lookup"><span data-stu-id="8d62b-113">The **ColumnMapping** property of the **ChildElement2** column will be set to **MappingType.Element**.</span></span> <span data-ttu-id="8d62b-114">La columna **Element1_Id** se establecerá como la clave principal de la tabla **Element1** .</span><span class="sxs-lookup"><span data-stu-id="8d62b-114">The **Element1_Id** column will be set as the primary key of the **Element1** table.</span></span>  
  
 <span data-ttu-id="8d62b-115">La tabla **ChildElement1** tendrá tres columnas: **attr1**, **attr2** y **Element1_Id**.</span><span class="sxs-lookup"><span data-stu-id="8d62b-115">The **ChildElement1** table will have three columns: **attr1**, **attr2** and **Element1_Id**.</span></span> <span data-ttu-id="8d62b-116">La propiedad **ColumnMapping** de las columnas **attr1** y **Attr2** se establecerá en **MappingType. Attribute**.</span><span class="sxs-lookup"><span data-stu-id="8d62b-116">The **ColumnMapping** property for the **attr1** and **attr2** columns will be set to **MappingType.Attribute**.</span></span> <span data-ttu-id="8d62b-117">La propiedad **ColumnMapping** de la columna **Element1_Id** se establecerá en **MappingType. Hidden**.</span><span class="sxs-lookup"><span data-stu-id="8d62b-117">The **ColumnMapping** property of the **Element1_Id** column will be set to **MappingType.Hidden**.</span></span>  
  
 <span data-ttu-id="8d62b-118">Se creará una **DataRelation** y **ForeignKeyConstraint** usando las columnas **Element1_Id** de ambas tablas.</span><span class="sxs-lookup"><span data-stu-id="8d62b-118">A **DataRelation** and **ForeignKeyConstraint** will be created using the **Element1_Id** columns from both tables.</span></span>  
  
 <span data-ttu-id="8d62b-119">**Authors1** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="8d62b-119">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="8d62b-120">**Tabla:** Element1</span><span class="sxs-lookup"><span data-stu-id="8d62b-120">**Table:** Element1</span></span>  
  
|<span data-ttu-id="8d62b-121">Element1_Id</span><span class="sxs-lookup"><span data-stu-id="8d62b-121">Element1_Id</span></span>|<span data-ttu-id="8d62b-122">ChildElement2</span><span class="sxs-lookup"><span data-stu-id="8d62b-122">ChildElement2</span></span>|  
|------------------|-------------------|  
|<span data-ttu-id="8d62b-123">0</span><span class="sxs-lookup"><span data-stu-id="8d62b-123">0</span></span>|<span data-ttu-id="8d62b-124">Text2</span><span class="sxs-lookup"><span data-stu-id="8d62b-124">Text2</span></span>|  
  
 <span data-ttu-id="8d62b-125">**Tabla:** ChildElement1</span><span class="sxs-lookup"><span data-stu-id="8d62b-125">**Table:** ChildElement1</span></span>  
  
|<span data-ttu-id="8d62b-126">attr1</span><span class="sxs-lookup"><span data-stu-id="8d62b-126">attr1</span></span>|<span data-ttu-id="8d62b-127">attr2</span><span class="sxs-lookup"><span data-stu-id="8d62b-127">attr2</span></span>|<span data-ttu-id="8d62b-128">Element1_Id</span><span class="sxs-lookup"><span data-stu-id="8d62b-128">Element1_Id</span></span>|  
|-----------|-----------|------------------|  
|<span data-ttu-id="8d62b-129">value1</span><span class="sxs-lookup"><span data-stu-id="8d62b-129">value1</span></span>|<span data-ttu-id="8d62b-130">value2</span><span class="sxs-lookup"><span data-stu-id="8d62b-130">value2</span></span>|<span data-ttu-id="8d62b-131">0</span><span class="sxs-lookup"><span data-stu-id="8d62b-131">0</span></span>|  
  
 <span data-ttu-id="8d62b-132">**DataRelation** Element1_ChildElement1</span><span class="sxs-lookup"><span data-stu-id="8d62b-132">**DataRelation:** Element1_ChildElement1</span></span>  
  
 <span data-ttu-id="8d62b-133">**ParentTable:** Element1</span><span class="sxs-lookup"><span data-stu-id="8d62b-133">**ParentTable:** Element1</span></span>  
  
 <span data-ttu-id="8d62b-134">**ParentColumn:** Element1_Id</span><span class="sxs-lookup"><span data-stu-id="8d62b-134">**ParentColumn:** Element1_Id</span></span>  
  
 <span data-ttu-id="8d62b-135">**ChildTable:** ChildElement1</span><span class="sxs-lookup"><span data-stu-id="8d62b-135">**ChildTable:** ChildElement1</span></span>  
  
 <span data-ttu-id="8d62b-136">**ChildColumn:** Element1_Id</span><span class="sxs-lookup"><span data-stu-id="8d62b-136">**ChildColumn:** Element1_Id</span></span>  
  
 <span data-ttu-id="8d62b-137">**Anidada** True</span><span class="sxs-lookup"><span data-stu-id="8d62b-137">**Nested:** True</span></span>  
  
 <span data-ttu-id="8d62b-138">**ForeignKeyConstraint:** Element1_ChildElement1</span><span class="sxs-lookup"><span data-stu-id="8d62b-138">**ForeignKeyConstraint:** Element1_ChildElement1</span></span>  
  
 <span data-ttu-id="8d62b-139">**Artículo** Element1_Id</span><span class="sxs-lookup"><span data-stu-id="8d62b-139">**Column:** Element1_Id</span></span>  
  
 <span data-ttu-id="8d62b-140">**ParentTable:** Element1</span><span class="sxs-lookup"><span data-stu-id="8d62b-140">**ParentTable:** Element1</span></span>  
  
 <span data-ttu-id="8d62b-141">**ChildTable:** ChildElement1</span><span class="sxs-lookup"><span data-stu-id="8d62b-141">**ChildTable:** ChildElement1</span></span>  
  
 <span data-ttu-id="8d62b-142">**DeleteRule:** Cascade</span><span class="sxs-lookup"><span data-stu-id="8d62b-142">**DeleteRule:** Cascade</span></span>  
  
 <span data-ttu-id="8d62b-143">**AcceptRejectRule:** None</span><span class="sxs-lookup"><span data-stu-id="8d62b-143">**AcceptRejectRule:** None</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d62b-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="8d62b-144">See also</span></span>

- [<span data-ttu-id="8d62b-145">Inferencia de una estructura relacional de un conjunto de datos a partir de XML</span><span class="sxs-lookup"><span data-stu-id="8d62b-145">Inferring DataSet Relational Structure from XML</span></span>](inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="8d62b-146">Carga de un conjunto de datos desde XML</span><span class="sxs-lookup"><span data-stu-id="8d62b-146">Loading a DataSet from XML</span></span>](loading-a-dataset-from-xml.md)
- [<span data-ttu-id="8d62b-147">Carga de información del esquema de un conjunto de datos desde XML</span><span class="sxs-lookup"><span data-stu-id="8d62b-147">Loading DataSet Schema Information from XML</span></span>](loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="8d62b-148">Anidado de objetos DataRelation</span><span class="sxs-lookup"><span data-stu-id="8d62b-148">Nesting DataRelations</span></span>](nesting-datarelations.md)
- [<span data-ttu-id="8d62b-149">Usar XML en un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="8d62b-149">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="8d62b-150">Objetos DataSet, DataTable y DataView</span><span class="sxs-lookup"><span data-stu-id="8d62b-150">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="8d62b-151">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="8d62b-151">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
