---
title: Crear un objeto DataTable
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: eecf9d78-60e3-4fdc-8de0-e56c13a89414
ms.openlocfilehash: 272976d3c581d3e8a5860ba5cf3f9695ca370d8c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59112390"
---
# <a name="creating-a-datatable"></a><span data-ttu-id="46db8-102">Crear un objeto DataTable</span><span class="sxs-lookup"><span data-stu-id="46db8-102">Creating a DataTable</span></span>
<span data-ttu-id="46db8-103">Un objeto <xref:System.Data.DataTable>, que representa una tabla de datos relacionales en la memoria, se puede crear y usar de manera independiente o lo pueden usar otros objetos de .NET Framework, normalmente como miembro de un objeto <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="46db8-103">A <xref:System.Data.DataTable>, which represents one table of in-memory relational data, can be created and used independently, or can be used by other .NET Framework objects, most commonly as a member of a <xref:System.Data.DataSet>.</span></span>  
  
 <span data-ttu-id="46db8-104">Puede crear un **DataTable** objeto mediante el uso adecuado **DataTable** constructor.</span><span class="sxs-lookup"><span data-stu-id="46db8-104">You can create a **DataTable** object by using the appropriate **DataTable** constructor.</span></span> <span data-ttu-id="46db8-105">Puede agregarlo a la **conjunto de datos** mediante el uso de la **agregar** método para agregarlo a la **DataTable** del objeto **tablas** colección.</span><span class="sxs-lookup"><span data-stu-id="46db8-105">You can add it to the **DataSet** by using the **Add** method to add it to the **DataTable** object's **Tables** collection.</span></span>  
  
 <span data-ttu-id="46db8-106">También puede crear **DataTable** objetos dentro de un **DataSet** mediante el uso de la **rellenar** o **FillSchema** métodos de la  **DataAdapter** objeto, o desde un predefinido o deducido de esquema XML con el **ReadXml**, **ReadXmlSchema**, o **InferXmlSchema** métodos de la **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="46db8-106">You can also create **DataTable** objects within a **DataSet** by using the **Fill** or **FillSchema** methods of the **DataAdapter** object, or from a predefined or inferred XML schema using the **ReadXml**, **ReadXmlSchema**, or **InferXmlSchema** methods of the **DataSet**.</span></span> <span data-ttu-id="46db8-107">Tenga en cuenta que después de haber agregado un **DataTable** como un miembro de la **tablas** colección de uno **DataSet**, no se puede agregar a la colección de tablas de cualquier otro **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="46db8-107">Note that after you have added a **DataTable** as a member of the **Tables** collection of one **DataSet**, you cannot add it to the collection of tables of any other **DataSet**.</span></span>  
  
 <span data-ttu-id="46db8-108">Cuando crea un **DataTable**, no tiene un esquema (es decir, una estructura).</span><span class="sxs-lookup"><span data-stu-id="46db8-108">When you first create a **DataTable**, it does not have a schema (that is, a structure).</span></span> <span data-ttu-id="46db8-109">Para definir el esquema de la tabla, debe crear y agregar <xref:System.Data.DataColumn> objetos a la **columnas** colección de la tabla.</span><span class="sxs-lookup"><span data-stu-id="46db8-109">To define the schema of the table, you must create and add <xref:System.Data.DataColumn> objects to the **Columns** collection of the table.</span></span> <span data-ttu-id="46db8-110">También puede definir una columna de clave principal para la tabla y crear y agregar **restricción** objetos a la **restricciones** colección de la tabla.</span><span class="sxs-lookup"><span data-stu-id="46db8-110">You can also define a primary key column for the table, and create and add **Constraint** objects to the **Constraints** collection of the table.</span></span> <span data-ttu-id="46db8-111">Después de haber definido el esquema para un **DataTable**, puede agregar filas de datos a la tabla agregando **DataRow** objetos a la **filas** colección de la tabla.</span><span class="sxs-lookup"><span data-stu-id="46db8-111">After you have defined the schema for a **DataTable**, you can add rows of data to the table by adding **DataRow** objects to the **Rows** collection of the table.</span></span>  
  
 <span data-ttu-id="46db8-112">No se debe proporcionar un valor para el <xref:System.Data.DataTable.TableName%2A> propiedad cuando se crea un **DataTable**; puede especificar la propiedad en otro momento, o puede dejarlo vacío.</span><span class="sxs-lookup"><span data-stu-id="46db8-112">You are not required to supply a value for the <xref:System.Data.DataTable.TableName%2A> property when you create a **DataTable**; you can specify the property at another time, or you can leave it empty.</span></span> <span data-ttu-id="46db8-113">Sin embargo, cuando agrega una tabla sin un **TableName** valor a un **DataSet**, la tabla recibirá un nombre predeterminado incremental de tabla*N*, comenzando por "Table" para Table0.</span><span class="sxs-lookup"><span data-stu-id="46db8-113">However, when you add a table without a **TableName** value to a **DataSet**, the table will be given an incremental default name of Table*N*, starting with "Table" for Table0.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="46db8-114">Se recomienda evitar la "tabla*N*" convención de nomenclatura al proporcionar un **TableName** valor, porque el nombre que se proporcione podría entrar en conflicto con un nombre de tabla predeterminado existente en el **conjunto de datos** .</span><span class="sxs-lookup"><span data-stu-id="46db8-114">We recommend that you avoid the "Table*N*" naming convention when you supply a **TableName** value, because the name you supply may conflict with an existing default table name in the **DataSet**.</span></span> <span data-ttu-id="46db8-115">Si el nombre proporcionado ya existe, se inicia una excepción.</span><span class="sxs-lookup"><span data-stu-id="46db8-115">If the supplied name already exists, an exception is thrown.</span></span>  
  
 <span data-ttu-id="46db8-116">En el ejemplo siguiente se crea una instancia de un **DataTable** objeto y lo asigna el nombre "Customers".</span><span class="sxs-lookup"><span data-stu-id="46db8-116">The following example creates an instance of a **DataTable** object and assigns it the name "Customers."</span></span>  
  
```vb  
Dim workTable as DataTable = New DataTable("Customers")  
```  
  
```csharp  
DataTable workTable = new DataTable("Customers");  
```  
  
 <span data-ttu-id="46db8-117">En el ejemplo siguiente se crea una instancia de un **DataTable** agregándolo a la **tablas** colección de un **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="46db8-117">The following example creates an instance of a **DataTable** by adding it to the **Tables** collection of a **DataSet**.</span></span>  
  
```vb  
Dim customers As DataSet = New DataSet  
Dim customersTable As DataTable = _  
   customers.Tables.Add("CustomersTable")  
```  
  
```csharp  
DataSet customers = new DataSet();  
DataTable customersTable = customers.Tables.Add("CustomersTable");  
```  
  
## <a name="see-also"></a><span data-ttu-id="46db8-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="46db8-118">See also</span></span>

- <xref:System.Data.DataTable>
- <xref:System.Data.DataTableCollection>
- [<span data-ttu-id="46db8-119">Objetos DataTable</span><span class="sxs-lookup"><span data-stu-id="46db8-119">DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)
- [<span data-ttu-id="46db8-120">Rellenar un conjunto de datos desde un objeto DataAdapter</span><span class="sxs-lookup"><span data-stu-id="46db8-120">Populating a DataSet from a DataAdapter</span></span>](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md)
- [<span data-ttu-id="46db8-121">Cargar un conjunto de datos desde XML</span><span class="sxs-lookup"><span data-stu-id="46db8-121">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)
- [<span data-ttu-id="46db8-122">Cargar información del esquema de un conjunto de datos desde XML</span><span class="sxs-lookup"><span data-stu-id="46db8-122">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="46db8-123">Proveedores administrados de ADO.NET y centro de desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="46db8-123">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
