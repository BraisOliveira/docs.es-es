---
title: Correspondencias de DataTable y DataColumn en un objeto DataAdapter
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d023260a-a66a-4c39-b8f4-090cd130e730
ms.openlocfilehash: a9c81c8554c0fb393c10ed69f84c8b2d936ec1e6
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040129"
---
# <a name="dataadapter-datatable-and-datacolumn-mappings"></a>Correspondencias de DataTable y DataColumn en un objeto DataAdapter
Un objeto **DataAdapter** contiene una colección de cero o más objetos <xref:System.Data.Common.DataTableMapping> en su propiedad **TableMappings** . Un **DataTableMapping** proporciona una asignación maestra entre los datos devueltos de una consulta en un origen de datos y un <xref:System.Data.DataTable>. Se puede pasar el nombre de **DataTableMapping** en lugar del nombre de **DataTable** al método **Fill** de **DataAdapter**. En el ejemplo siguiente se crea un **DataTableMapping** denominado **AuthorsMapping** para la tabla **authors** .  
  
```vb  
workAdapter.TableMappings.Add("AuthorsMapping", "Authors")  
```  
  
```csharp  
workAdapter.TableMappings.Add("AuthorsMapping", "Authors");  
```  
  
 Un objeto **DataTableMapping** permite usar nombres de columna en un **DataTable** que son diferentes de los de la base de datos. El **DataAdapter** utiliza la asignación para buscar coincidencias con las columnas cuando se actualiza la tabla.  
  
 Si no especifica un nombre **TableName** o **DataTableMapping** al llamar al método **Fill** o **Update** de **DataAdapter**, el **DataAdapter** busca un **DataTableMapping** denominado "Table". Si ese objeto **DataTableMapping** no existe, el **TableName** de la **DataTable** es "Table". Puede especificar un **DataTableMapping** predeterminado mediante la creación de un **DataTableMapping** con el nombre "Table".  
  
 En el ejemplo de código siguiente se crea un **DataTableMapping** (a partir del espacio de nombres <xref:System.Data.Common>) y se convierte en la asignación predeterminada para el **DataAdapter** especificado asignándole el nombre "Table". A continuación, en el ejemplo se asignan las columnas de la primera tabla del resultado de la consulta (la tabla **Customers** de la base de datos **Northwind** ) a un conjunto de nombres más descriptivos de la tabla **Customers de Northwind** en el <xref:System.Data.DataSet>. En las columnas que no se asignan se usa el nombre de la columna en el origen de datos.  
  
```vb  
Dim mapping As DataTableMapping = _  
  adapter.TableMappings.Add("Table", "NorthwindCustomers")  
mapping.ColumnMappings.Add("CompanyName", "Company")  
mapping.ColumnMappings.Add("ContactName", "Contact")  
mapping.ColumnMappings.Add("PostalCode", "ZIPCode")  
  
adapter.Fill(custDS)  
```  
  
```csharp  
DataTableMapping mapping =   
  adapter.TableMappings.Add("Table", "NorthwindCustomers");  
mapping.ColumnMappings.Add("CompanyName", "Company");  
mapping.ColumnMappings.Add("ContactName", "Contact");  
mapping.ColumnMappings.Add("PostalCode", "ZIPCode");  
  
adapter.Fill(custDS);  
```  
  
 En situaciones más avanzadas, puede decidir que desea que el mismo **DataAdapter** admita la carga de tablas diferentes con asignaciones diferentes. Para ello, basta con agregar objetos de **DataTableMapping** adicionales.  
  
 Cuando se pasa al método **Fill** una instancia de un **DataSet** y un nombre de **DataTableMapping** , si existe una asignación con ese nombre, se utiliza; de lo contrario, se utiliza un **objeto DataTable** con ese nombre.  
  
 En los ejemplos siguientes se crea un objeto **DataTableMapping** con un nombre de **Customers** y un nombre **DataTable** de **BizTalkSchema**. A continuación, en el ejemplo se asignan las filas devueltas por la instrucción SELECT a la **DataTable** **BizTalkSchema** .  
  
```vb  
Dim mapping As ITableMapping = _  
  adapter.TableMappings.Add("Customers", "BizTalkSchema")  
mapping.ColumnMappings.Add("CustomerID", "ClientID")  
mapping.ColumnMappings.Add("CompanyName", "ClientName")  
mapping.ColumnMappings.Add("ContactName", "Contact")  
mapping.ColumnMappings.Add("PostalCode", "ZIP")  
  
adapter.Fill(custDS, "Customers")  
```  
  
```csharp  
ITableMapping mapping =   
  adapter.TableMappings.Add("Customers", "BizTalkSchema");  
mapping.ColumnMappings.Add("CustomerID", "ClientID");  
mapping.ColumnMappings.Add("CompanyName", "ClientName");  
mapping.ColumnMappings.Add("ContactName", "Contact");  
mapping.ColumnMappings.Add("PostalCode", "ZIP");  
  
adapter.Fill(custDS, "Customers");  
```  
  
> [!NOTE]
> Si no se proporciona un nombre de columna de origen en una asignación de columnas o no se identifica un nombre de tabla de origen en una asignación de tablas, se generan nombres predeterminados de forma automática. Si no se proporciona ninguna columna de origen para una asignación de columnas, a la asignación de columnas se le asigna un nombre predeterminado incremental de **SourceColumn** *N,* comenzando por **SourceColumn1**. Si no se proporciona ningún nombre de tabla de origen para una asignación de tabla, la asignación de tabla recibe un nombre predeterminado incremental de **SourceTable** *N*, comenzando por **SourceTable1**.  
  
> [!NOTE]
> Se recomienda evitar la Convención de nomenclatura de **SourceColumn** *n* para una asignación de columnas o **SourceTable** *n* para una asignación de tabla, ya que el nombre proporcionado puede entrar en conflicto con un nombre de asignación de columna predeterminado existente en el  **ColumnMappingCollection** o nombre de asignación de tabla en **DataTableMappingCollection**. Si el nombre proporcionado ya existe, se iniciará una excepción.  
  
## <a name="handling-multiple-result-sets"></a>Controlar varios conjuntos de resultados  
 Si **SelectCommand** devuelve varias tablas, **Fill** genera automáticamente nombres de tabla con valores incrementales para las tablas del **conjunto de DataSet**, comenzando por el nombre de tabla especificado y continuando en el formulario **TableName** *N*, comenzando por **TableName1**. Puede usar asignaciones de tabla para asignar el nombre de tabla generado automáticamente a un nombre que desee especificar para la tabla en el **conjunto de DataSet**. Por ejemplo, para un **SelectCommand** que devuelve dos tablas, **Customers** y **Orders**, emita la siguiente llamada a **Fill**.  
  
```vb  
adapter.Fill(customersDataSet, "Customers")  
```  

```csharp  
adapter.Fill(customersDataSet, "Customers");  
```  

 Se crean dos tablas en el **conjunto de DataSet**: **Customers** y **Customers1**. Puede usar asignaciones de tabla para asegurarse de que la segunda tabla se denomina **Orders** en lugar de **Customers1**. Para ello, asigne la tabla de origen de **Customers1** a los **pedidos**de la tabla del **conjunto** de elementos, tal como se muestra en el ejemplo siguiente.  
  
```vb  
adapter.TableMappings.Add("Customers1", "Orders")  
adapter.Fill(customersDataSet, "Customers")  
```  

```csharp  
adapter.TableMappings.Add("Customers1", "Orders");  
adapter.Fill(customersDataSet, "Customers");  
```
  
## <a name="see-also"></a>Vea también

- [Objetos DataAdapter y DataReader](dataadapters-and-datareaders.md)
- [Recuperar y modificar datos en ADO.NET](retrieving-and-modifying-data.md)
- [Información general sobre ADO.NET](ado-net-overview.md)
