---
title: Información de error de fila
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8b1f9070-d032-48c7-b030-bd8fbb2ca59a
ms.openlocfilehash: 89889c5543e6518046bb59b59646ecba715f5e03
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61607571"
---
# <a name="row-error-information"></a><span data-ttu-id="832aa-102">Información de error de fila</span><span class="sxs-lookup"><span data-stu-id="832aa-102">Row Error Information</span></span>
<span data-ttu-id="832aa-103">Para evitar responder a errores de fila durante la edición de valores en una <xref:System.Data.DataTable>, puede agregar la información de error a la fila para utilizarla más adelante.</span><span class="sxs-lookup"><span data-stu-id="832aa-103">To avoid having to respond to row errors while editing values in a <xref:System.Data.DataTable>, you can add the error information to the row for later use.</span></span> <span data-ttu-id="832aa-104">Para ello, el objeto <xref:System.Data.DataRow> proporciona una propiedad <xref:System.Data.DataRow.RowError%2A> en cada fila.</span><span class="sxs-lookup"><span data-stu-id="832aa-104">The <xref:System.Data.DataRow> object provides a <xref:System.Data.DataRow.RowError%2A> property on each row for this purpose.</span></span> <span data-ttu-id="832aa-105">Agregar datos a la **RowError** propiedad de un **DataRow** establece la <xref:System.Data.DataRow.HasErrors%2A> propiedad de la **DataRow** a **true**.</span><span class="sxs-lookup"><span data-stu-id="832aa-105">Adding data to the **RowError** property of a **DataRow** sets the <xref:System.Data.DataRow.HasErrors%2A> property of the **DataRow** to **true**.</span></span> <span data-ttu-id="832aa-106">Si el **DataRow** forma parte de un **DataTable**, y **DataRow.HasErrors** es **true**, el **DataTable.HasErrors** propiedad también es **true**.</span><span class="sxs-lookup"><span data-stu-id="832aa-106">If the **DataRow** is part of a **DataTable**, and **DataRow.HasErrors** is **true**, the **DataTable.HasErrors** property is also **true**.</span></span> <span data-ttu-id="832aa-107">Esto se aplica también a la **DataSet** a la que el **DataTable** pertenece.</span><span class="sxs-lookup"><span data-stu-id="832aa-107">This applies as well to the **DataSet** to which the **DataTable** belongs.</span></span> <span data-ttu-id="832aa-108">Al probar si hay errores, puede comprobar el **HasErrors** propiedad para determinar si se ha agregado información de error en las filas.</span><span class="sxs-lookup"><span data-stu-id="832aa-108">When testing for errors, you can check the **HasErrors** property to determine if error information has been added to any rows.</span></span> <span data-ttu-id="832aa-109">Si **HasErrors** es **true**, puede usar el <xref:System.Data.DataTable.GetErrors%2A> método de la **DataTable** para devolver y examinar sólo las filas con errores, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="832aa-109">If **HasErrors** is **true**, you can use the <xref:System.Data.DataTable.GetErrors%2A> method of the **DataTable** to return and examine only the rows with errors, as shown in the following example.</span></span>  
  
```vb  
Dim workTable As DataTable = New DataTable("Customers")  
workTable.Columns.Add("CustID", Type.GetType("System.Int32"))  
workTable.Columns.Add("Total", Type.GetType("System.Double"))  
  
AddHandler workTable.RowChanged, New DataRowChangeEventHandler(AddressOf OnRowChanged)  
  
Dim i  As Int32  
  
For i  = 0 To 10  
  workTable.Rows.Add(New Object() {i , i *100})  
Next  
  
If workTable.HasErrors Then  
  Console.WriteLine("Errors in Table " & workTable.TableName)  
  
  Dim myRow As DataRow  
  
  For Each myRow In workTable.GetErrors()  
    Console.WriteLine("CustID = " & myRow("CustID").ToString())  
    Console.WriteLine(" Error = " & myRow.RowError & vbCrLf)  
  Next  
End If  
  
Private Shared Sub OnRowChanged( _  
    sender As Object, args As DataRowChangeEventArgs)  
  ' Check for zero values.  
  If CDbl(args.Row("Total")) = 0 Then args.Row.RowError = _  
      "Total cannot be 0."  
End Sub  
```  
  
```csharp  
DataTable  workTable = new DataTable("Customers");  
workTable.Columns.Add("CustID", typeof(Int32));  
workTable.Columns.Add("Total", typeof(Double));  
  
workTable.RowChanged += new DataRowChangeEventHandler(OnRowChanged);  
  
for (int i = 0; i < 10; i++)  
  workTable.Rows.Add(new Object[] {i, i*100});  
  
if (workTable.HasErrors)  
{  
  Console.WriteLine("Errors in Table " + workTable.TableName);  
  
  foreach (DataRow myRow in workTable.GetErrors())  
  {  
    Console.WriteLine("CustID = " + myRow["CustID"]);  
    Console.WriteLine(" Error = " + myRow.RowError + "\n");  
  }  
}  
  
protected static void OnRowChanged(  
    Object sender, DataRowChangeEventArgs args)  
{  
  // Check for zero values.  
  if (args.Row["Total"].Equals(0D))  
    args.Row.RowError = "Total cannot be 0.";  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="832aa-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="832aa-110">See also</span></span>

- <xref:System.Data.DataColumnCollection>
- <xref:System.Data.DataRow>
- <xref:System.Data.DataTable>
- [<span data-ttu-id="832aa-111">Manipulación de datos en un objeto DataTable</span><span class="sxs-lookup"><span data-stu-id="832aa-111">Manipulating Data in a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="832aa-112">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="832aa-112">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
