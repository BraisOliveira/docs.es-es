---
title: Inferir texto de elemento
ms.date: 03/30/2017
ms.assetid: 789799e5-716f-459f-a168-76c5cf22178b
ms.openlocfilehash: 6ffe8f2fbf01fbe8dfa9d78f3dfb9e39b6e80b16
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59224967"
---
# <a name="inferring-element-text"></a><span data-ttu-id="f95d2-102">Inferir texto de elemento</span><span class="sxs-lookup"><span data-stu-id="f95d2-102">Inferring Element Text</span></span>
<span data-ttu-id="f95d2-103">Si un elemento contiene texto y no tiene elementos secundarios que se deducen como tablas (como elementos con atributos) o elementos repetidos, una nueva columna con el nombre **TableName_Text** se agregarán a la tabla que se deduzca para el elemento.</span><span class="sxs-lookup"><span data-stu-id="f95d2-103">If an element contains text and has no child elements to be inferred as tables (such as elements with attributes or repeated elements), a new column with the name **TableName_Text** will be added to the table that is inferred for the element.</span></span> <span data-ttu-id="f95d2-104">El texto contenido en el elemento se agregará a una fila de la tabla y se almacenará en la nueva columna.</span><span class="sxs-lookup"><span data-stu-id="f95d2-104">The text contained in the element will be added to a row in the table and stored in the new column.</span></span> <span data-ttu-id="f95d2-105">El **ColumnMapping** propiedad de la nueva columna se establecerá en **MappingType.SimpleContent**.</span><span class="sxs-lookup"><span data-stu-id="f95d2-105">The **ColumnMapping** property of the new column will be set to **MappingType.SimpleContent**.</span></span>  
  
 <span data-ttu-id="f95d2-106">Por ejemplo, tomemos el siguiente código XML.</span><span class="sxs-lookup"><span data-stu-id="f95d2-106">For example, consider the following XML.</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1">Text1</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="f95d2-107">El proceso de inferencia producirá una tabla denominada **Element1** con dos columnas: **attr1** y **Element1_Text**.</span><span class="sxs-lookup"><span data-stu-id="f95d2-107">The inference process will produce a table named **Element1** with two columns: **attr1** and **Element1_Text**.</span></span> <span data-ttu-id="f95d2-108">El **ColumnMapping** propiedad de la **attr1** columna se establecerá en **MappingType.Attribute**.</span><span class="sxs-lookup"><span data-stu-id="f95d2-108">The **ColumnMapping** property of the **attr1** column will be set to **MappingType.Attribute**.</span></span> <span data-ttu-id="f95d2-109">El **ColumnMapping** propiedad de la **Element1_Text** columna se establecerá en **MappingType.SimpleContent**.</span><span class="sxs-lookup"><span data-stu-id="f95d2-109">The **ColumnMapping** property of the **Element1_Text** column will be set to **MappingType.SimpleContent**.</span></span>  
  
 <span data-ttu-id="f95d2-110">**DataSet:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="f95d2-110">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="f95d2-111">**Tabla:** Element1</span><span class="sxs-lookup"><span data-stu-id="f95d2-111">**Table:** Element1</span></span>  
  
|<span data-ttu-id="f95d2-112">attr1</span><span class="sxs-lookup"><span data-stu-id="f95d2-112">attr1</span></span>|<span data-ttu-id="f95d2-113">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="f95d2-113">Element1_Text</span></span>|  
|-----------|--------------------|  
|<span data-ttu-id="f95d2-114">value1</span><span class="sxs-lookup"><span data-stu-id="f95d2-114">value1</span></span>|<span data-ttu-id="f95d2-115">Text1</span><span class="sxs-lookup"><span data-stu-id="f95d2-115">Text1</span></span>|  
  
 <span data-ttu-id="f95d2-116">Si un elemento contiene texto, pero también tiene elementos secundarios que contienen texto, no se agregará una columna a la tabla para almacenar el texto contenido en el elemento.</span><span class="sxs-lookup"><span data-stu-id="f95d2-116">If an element contains text, but also has child elements that contain text, a column will not be added to the table to store the text contained in the element.</span></span> <span data-ttu-id="f95d2-117">El texto contenido en el elemento se pasará por alto, mientras que el texto de los elementos secundarios se incluirá en una fila de la tabla.</span><span class="sxs-lookup"><span data-stu-id="f95d2-117">The text contained in the element will be ignored, while the text in the child elements is included in a row in the table.</span></span> <span data-ttu-id="f95d2-118">Por ejemplo, tomemos el siguiente código XML.</span><span class="sxs-lookup"><span data-stu-id="f95d2-118">For example, consider the following XML.</span></span>  
  
```xml  
<Element1>  
  Text1  
  <ChildElement1>Text2</ChildElement1>  
  Text3  
</Element1>  
```  
  
 <span data-ttu-id="f95d2-119">El proceso de inferencia producirá una tabla denominada **Element1** con una columna denominada **ChildElement1**.</span><span class="sxs-lookup"><span data-stu-id="f95d2-119">The inference process will produce a table named **Element1** with one column named **ChildElement1**.</span></span> <span data-ttu-id="f95d2-120">El texto para el **ChildElement1** elemento se incluirá en una fila en la tabla.</span><span class="sxs-lookup"><span data-stu-id="f95d2-120">The text for the **ChildElement1** element will be included in a row in the table.</span></span> <span data-ttu-id="f95d2-121">El otro texto se pasará por alto.</span><span class="sxs-lookup"><span data-stu-id="f95d2-121">The other text will be ignored.</span></span> <span data-ttu-id="f95d2-122">El **ColumnMapping** propiedad de la **ChildElement1** columna se establecerá en **MappingType.Element**.</span><span class="sxs-lookup"><span data-stu-id="f95d2-122">The **ColumnMapping** property of the **ChildElement1** column will be set to **MappingType.Element**.</span></span>  
  
 <span data-ttu-id="f95d2-123">**DataSet:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="f95d2-123">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="f95d2-124">**Tabla:** Element1</span><span class="sxs-lookup"><span data-stu-id="f95d2-124">**Table:** Element1</span></span>  
  
|<span data-ttu-id="f95d2-125">ChildElement1</span><span class="sxs-lookup"><span data-stu-id="f95d2-125">ChildElement1</span></span>|  
|-------------------|  
|<span data-ttu-id="f95d2-126">Text2</span><span class="sxs-lookup"><span data-stu-id="f95d2-126">Text2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f95d2-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="f95d2-127">See also</span></span>

- [<span data-ttu-id="f95d2-128">Inferir una estructura relacional de un conjunto de datos a partir de XML</span><span class="sxs-lookup"><span data-stu-id="f95d2-128">Inferring DataSet Relational Structure from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="f95d2-129">Cargar un conjunto de datos desde XML</span><span class="sxs-lookup"><span data-stu-id="f95d2-129">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)
- [<span data-ttu-id="f95d2-130">Cargar información del esquema de un conjunto de datos desde XML</span><span class="sxs-lookup"><span data-stu-id="f95d2-130">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="f95d2-131">Usar XML en un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="f95d2-131">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)
- [<span data-ttu-id="f95d2-132">Objetos DataSet, DataTable y DataView</span><span class="sxs-lookup"><span data-stu-id="f95d2-132">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [<span data-ttu-id="f95d2-133">Proveedores administrados de ADO.NET y centro de desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="f95d2-133">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
