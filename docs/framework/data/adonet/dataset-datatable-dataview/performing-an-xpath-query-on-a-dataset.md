---
title: Realizar una consulta XPath en un objeto DataSet
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7e828566-fffe-4d38-abb2-4d68fd73f663
ms.openlocfilehash: 29d1e5ae494b2fff4e13886159bb937041152382
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59209481"
---
# <a name="performing-an-xpath-query-on-a-dataset"></a><span data-ttu-id="e1416-102">Realizar una consulta XPath en un objeto DataSet</span><span class="sxs-lookup"><span data-stu-id="e1416-102">Performing an XPath Query on a DataSet</span></span>
<span data-ttu-id="e1416-103">La relación entre un sincronizada <xref:System.Data.DataSet> y <xref:System.Xml.XmlDataDocument> le permite hacer uso de XML servicios, como la consulta XML Path Language (XPath), que tienen acceso a la **XmlDataDocument** y puede realizar ciertas funciones una manera más conveniente que el acceso a la **DataSet** directamente.</span><span class="sxs-lookup"><span data-stu-id="e1416-103">The relationship between a synchronized <xref:System.Data.DataSet> and <xref:System.Xml.XmlDataDocument> allows you to make use of XML services, such as the XML Path Language (XPath) query, that access the **XmlDataDocument** and can perform certain functionality more conveniently than accessing the **DataSet** directly.</span></span> <span data-ttu-id="e1416-104">Por ejemplo, en lugar de usar el **seleccione** método de un <xref:System.Data.DataTable> para navegar por relaciones con otras tablas en un **DataSet**, puede realizar una consulta XPath en un **XmlDataDocument**  que está sincronizada con la **DataSet**, para obtener una lista de elementos XML en forma de un <xref:System.Xml.XmlNodeList>.</span><span class="sxs-lookup"><span data-stu-id="e1416-104">For example, rather than using the **Select** method of a <xref:System.Data.DataTable> to navigate relationships to other tables in a **DataSet**, you can perform an XPath query on an **XmlDataDocument** that is synchronized with the **DataSet**, to get a list of XML elements in the form of an <xref:System.Xml.XmlNodeList>.</span></span> <span data-ttu-id="e1416-105">Los nodos en el **XmlNodeList**, convierta como <xref:System.Xml.XmlElement> nodos, a continuación, se puede pasar a la **GetRowFromElement** método de la **XmlDataDocument**para devolver la coincidencia <xref:System.Data.DataRow> referencias a las filas de la tabla en sincronizado **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="e1416-105">The nodes in the **XmlNodeList**, cast as <xref:System.Xml.XmlElement> nodes, can then be passed to the **GetRowFromElement** method of the **XmlDataDocument**, to return matching <xref:System.Data.DataRow> references to the rows of the table in the synchronized **DataSet**.</span></span>  
  
 <span data-ttu-id="e1416-106">Por ejemplo, en el siguiente ejemplo de código se realiza una consulta "secundaria" de XPath.</span><span class="sxs-lookup"><span data-stu-id="e1416-106">For example, the following code sample performs a "grandchild" XPath query.</span></span> <span data-ttu-id="e1416-107">El **DataSet** se rellena con tres tablas: **Los clientes**, **pedidos**, y **OrderDetails**.</span><span class="sxs-lookup"><span data-stu-id="e1416-107">The **DataSet** is filled with three tables: **Customers**, **Orders**, and **OrderDetails**.</span></span> <span data-ttu-id="e1416-108">En el ejemplo, primero se crea una relación de elementos primarios y secundarios entre los **clientes** y **pedidos** tablas y entre el **pedidos** y **OrderDetails** tablas.</span><span class="sxs-lookup"><span data-stu-id="e1416-108">In the sample, a parent-child relation is first created between the **Customers** and **Orders** tables, and between the **Orders** and **OrderDetails** tables.</span></span> <span data-ttu-id="e1416-109">A continuación, se realiza una consulta XPath para devolver una **XmlNodeList** de **clientes** nodos donde un secundario **OrderDetails** nodo tiene un **ProductID**nodo con el valor 43.</span><span class="sxs-lookup"><span data-stu-id="e1416-109">An XPath query is then performed to return an **XmlNodeList** of **Customers** nodes where a grandchild **OrderDetails** node has a **ProductID** node with the value of 43.</span></span> <span data-ttu-id="e1416-110">En esencia, el ejemplo utiliza la consulta XPath para determinar qué clientes han pedido el producto que tiene el **ProductID** 43.</span><span class="sxs-lookup"><span data-stu-id="e1416-110">In essence, the sample is using the XPath query to determine which customers have ordered the product that has the **ProductID** of 43.</span></span>  
  
```vb  
' Assumes that connection is a valid SqlConnection.  
connection.Open()  
Dim dataSet As DataSet = New DataSet("CustomerOrders")  
Dim customerAdapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT * FROM Customers", connection)  
customerAdapter.Fill(dataSet, "Customers")  
  
Dim orderAdapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT * FROM Orders", connection)  
orderAdapter.Fill(dataSet, "Orders")  
  
Dim detailAdapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT * FROM [Order Details]", connection)  
detailAdapter.Fill(dataSet, "OrderDetails")  
  
connection.Close()  
  
dataSet.Relations.Add("CustOrders", _  
dataSet.Tables("Customers").Columns("CustomerID"), _  
dataSet.Tables("Orders").Columns("CustomerID")).Nested = true  
  
dataSet.Relations.Add("OrderDetail", _  
  dataSet.Tables("Orders").Columns("OrderID"), _  
dataSet.Tables("OrderDetails").Columns("OrderID"), false).Nested = true  
  
Dim xmlDoc As XmlDataDocument = New XmlDataDocument(dataSet)   
  
Dim nodeList As XmlNodeList = xmlDoc.DocumentElement.SelectNodes( _  
  "descendant::Customers[*/OrderDetails/ProductID=43]")  
  
Dim dataRow As DataRow  
Dim xmlNode As XmlNode  
  
For Each xmlNode In nodeList  
  dataRow = xmlDoc.GetRowFromElement(CType(xmlNode, XmlElement))  
  
  If Not dataRow Is Nothing then Console.WriteLine(xmlRow(0).ToString())  
Next  
```  
  
```csharp  
// Assumes that connection is a valid SqlConnection.  
connection.Open();  
  
DataSet dataSet = new DataSet("CustomerOrders");  
  
SqlDataAdapter customerAdapter = new SqlDataAdapter(  
  "SELECT * FROM Customers", connection);  
customerAdapter.Fill(dataSet, "Customers");  
  
SqlDataAdapter orderAdapter = new SqlDataAdapter(  
  "SELECT * FROM Orders", connection);  
orderAdapter.Fill(dataSet, "Orders");  
  
SqlDataAdapter detailAdapter = new SqlDataAdapter(  
  "SELECT * FROM [Order Details]", connection);  
detailAdapter.Fill(dataSet, "OrderDetails");  
  
connection.Close();  
  
dataSet.Relations.Add("CustOrders",  
  dataSet.Tables["Customers"].Columns["CustomerID"],  
 dataSet.Tables["Orders"].Columns["CustomerID"]).Nested = true;  
  
dataSet.Relations.Add("OrderDetail",  
  dataSet.Tables["Orders"].Columns["OrderID"],  
  dataSet.Tables["OrderDetails"].Columns["OrderID"],   
  false).Nested = true;  
  
XmlDataDocument xmlDoc = new XmlDataDocument(dataSet);   
  
XmlNodeList nodeList = xmlDoc.DocumentElement.SelectNodes(  
  "descendant::Customers[*/OrderDetails/ProductID=43]");  
  
DataRow dataRow;  
foreach (XmlNode xmlNode in nodeList)  
{  
  dataRow = xmlDoc.GetRowFromElement((XmlElement)xmlNode);  
  if (dataRow != null)  
    Console.WriteLine(dataRow[0]);  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="e1416-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="e1416-111">See also</span></span>

- [<span data-ttu-id="e1416-112">Sincronización de DataSet y XmlDataDocument</span><span class="sxs-lookup"><span data-stu-id="e1416-112">DataSet and XmlDataDocument Synchronization</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataset-and-xmldatadocument-synchronization.md)
- [<span data-ttu-id="e1416-113">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="e1416-113">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
