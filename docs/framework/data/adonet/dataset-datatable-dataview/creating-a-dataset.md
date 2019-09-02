---
title: Crear un objeto DataSet
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 57629d8f-393e-4677-8b83-29ffde27f5fc
ms.openlocfilehash: 19badb009ebe95c52ab1dbbaef96f280c769553b
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2019
ms.locfileid: "70205154"
---
# <a name="creating-a-dataset"></a><span data-ttu-id="0a71f-102">Crear un objeto DataSet</span><span class="sxs-lookup"><span data-stu-id="0a71f-102">Creating a DataSet</span></span>
<span data-ttu-id="0a71f-103">Puede crear una instancia de <xref:System.Data.DataSet> llamando al constructor <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="0a71f-103">You create an instance of a <xref:System.Data.DataSet> by calling the <xref:System.Data.DataSet> constructor.</span></span> <span data-ttu-id="0a71f-104">Si lo desea, especifique un nombre de argumento.</span><span class="sxs-lookup"><span data-stu-id="0a71f-104">Optionally specify a name argument.</span></span> <span data-ttu-id="0a71f-105">Si no especifica ningún nombre para el <xref:System.Data.DataSet>, se establecerá el nombre "NewDataSet".</span><span class="sxs-lookup"><span data-stu-id="0a71f-105">If you do not specify a name for the <xref:System.Data.DataSet>, the name is set to "NewDataSet".</span></span>  
  
 <span data-ttu-id="0a71f-106">También es posible crear un nuevo <xref:System.Data.DataSet> basado en un <xref:System.Data.DataSet>existente.</span><span class="sxs-lookup"><span data-stu-id="0a71f-106">You can also create a new <xref:System.Data.DataSet> based on an existing <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="0a71f-107">El nuevo <xref:System.Data.DataSet> puede ser una copia exacta del <xref:System.Data.DataSet> existente; un clon del <xref:System.Data.DataSet> que copia la estructura relacional o el esquema, pero que no contiene ningún dato del <xref:System.Data.DataSet> existente; o un subconjunto del <xref:System.Data.DataSet>, que contiene solamente las filas modificadas del <xref:System.Data.DataSet> existente mediante el método <xref:System.Data.DataSet.GetChanges%2A>.</span><span class="sxs-lookup"><span data-stu-id="0a71f-107">The new <xref:System.Data.DataSet> can be an exact copy of the existing <xref:System.Data.DataSet>; a clone of the <xref:System.Data.DataSet> that copies the relational structure or schema but that does not contain any of the data from the existing <xref:System.Data.DataSet>; or a subset of the <xref:System.Data.DataSet>, containing only the modified rows from the existing <xref:System.Data.DataSet> using the <xref:System.Data.DataSet.GetChanges%2A> method.</span></span> <span data-ttu-id="0a71f-108">Para obtener más información, vea [copiar el contenido del conjunto](copying-dataset-contents.md)de datos.</span><span class="sxs-lookup"><span data-stu-id="0a71f-108">For more information, see [Copying DataSet Contents](copying-dataset-contents.md).</span></span>  
  
 <span data-ttu-id="0a71f-109">En el siguiente ejemplo de código se muestra cómo construir una instancia de un <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="0a71f-109">The following code example demonstrates how to construct an instance of a <xref:System.Data.DataSet>.</span></span>  
  
```vb  
Dim customerOrders As DataSet = New DataSet("CustomerOrders")  
```  
  
```csharp  
DataSet customerOrders = new DataSet("CustomerOrders");  
```  
  
## <a name="see-also"></a><span data-ttu-id="0a71f-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="0a71f-110">See also</span></span>

- [<span data-ttu-id="0a71f-111">Rellenar un conjunto de datos desde un objeto DataAdapter</span><span class="sxs-lookup"><span data-stu-id="0a71f-111">Populating a DataSet from a DataAdapter</span></span>](../populating-a-dataset-from-a-dataadapter.md)
- [<span data-ttu-id="0a71f-112">Objetos DataSet, DataTable y DataView</span><span class="sxs-lookup"><span data-stu-id="0a71f-112">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="0a71f-113">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="0a71f-113">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
