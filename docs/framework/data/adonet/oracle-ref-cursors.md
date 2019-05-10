---
title: Parámetros REF CURSOR de Oracle
ms.date: 03/30/2017
ms.assetid: c6b25b8b-0bdd-41b2-9c7c-661f070c2247
ms.openlocfilehash: 0a98bfd401aaabfb754c422cc753bc5092f9f76c
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64633341"
---
# <a name="oracle-ref-cursors"></a><span data-ttu-id="ce18d-102">Parámetros REF CURSOR de Oracle</span><span class="sxs-lookup"><span data-stu-id="ce18d-102">Oracle REF CURSORs</span></span>
<span data-ttu-id="ce18d-103">El proveedor de datos de .NET Framework para Oracle admite Oracle **REF CURSOR** tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="ce18d-103">The .NET Framework Data Provider for Oracle supports the Oracle **REF CURSOR** data type.</span></span> <span data-ttu-id="ce18d-104">Cuando utilice el proveedor de datos para trabajar con cursores REF CURSOR de Oracle, debe tener en cuenta los siguientes comportamientos.</span><span class="sxs-lookup"><span data-stu-id="ce18d-104">When using the data provider to work with Oracle REF CURSORs, you should consider the following behaviors.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ce18d-105">Algunos de ellos difieren de los del proveedor Microsoft OLE DB para Oracle (MSDAORA).</span><span class="sxs-lookup"><span data-stu-id="ce18d-105">Some behaviors differ from those of the Microsoft OLE DB Provider for Oracle (MSDAORA).</span></span>  
  
- <span data-ttu-id="ce18d-106">Por motivos de rendimiento, el proveedor de datos para Oracle no enlaza automáticamente **REF CURSOR** tipos de datos, como hace MSDAORA, a menos que especifique explícitamente.</span><span class="sxs-lookup"><span data-stu-id="ce18d-106">For performance reasons, the Data Provider for Oracle does not automatically bind **REF CURSOR** data types, as MSDAORA does, unless you explicitly specify them.</span></span>  
  
- <span data-ttu-id="ce18d-107">El proveedor de datos no admite ninguna secuencia de escape ODBC, lo que incluye el escape {resultset} usado para especificar parámetros REF CURSOR.</span><span class="sxs-lookup"><span data-stu-id="ce18d-107">The data provider does not support any ODBC escape sequences, including the {resultset} escape used to specify REF CURSOR parameters.</span></span>  
  
- <span data-ttu-id="ce18d-108">Para ejecutar un procedimiento almacenado que devuelva cursores REF CURSOR, debe definir los parámetros en el <xref:System.Data.OracleClient.OracleParameterCollection> con un <xref:System.Data.OracleClient.OracleType> de **Cursor** y un <xref:System.Data.OracleClient.OracleParameter.Direction%2A> de **salida**.</span><span class="sxs-lookup"><span data-stu-id="ce18d-108">To execute a stored procedure that returns REF CURSORs, you must define the parameters in the <xref:System.Data.OracleClient.OracleParameterCollection> with an <xref:System.Data.OracleClient.OracleType> of **Cursor** and a <xref:System.Data.OracleClient.OracleParameter.Direction%2A> of **Output**.</span></span> <span data-ttu-id="ce18d-109">El proveedor de datos admite el enlace de cursores REF CURSOR sólo como parámetros de salida;</span><span class="sxs-lookup"><span data-stu-id="ce18d-109">The data provider supports binding REF CURSORs as output parameters only.</span></span> <span data-ttu-id="ce18d-110">no los admite como parámetros de entrada.</span><span class="sxs-lookup"><span data-stu-id="ce18d-110">The provider does not support REF CURSORs as input parameters.</span></span>  
  
- <span data-ttu-id="ce18d-111">No se permite la obtención de un <xref:System.Data.OracleClient.OracleDataReader> del valor del parámetro.</span><span class="sxs-lookup"><span data-stu-id="ce18d-111">Obtaining an <xref:System.Data.OracleClient.OracleDataReader> from the parameter value is not supported.</span></span> <span data-ttu-id="ce18d-112">Los valores son del tipo <xref:System.DBNull> después de la ejecución del comando.</span><span class="sxs-lookup"><span data-stu-id="ce18d-112">The values are of type <xref:System.DBNull> after command execution.</span></span>  
  
- <span data-ttu-id="ce18d-113">La única **CommandBehavior** valor de enumeración que funciona con cursores REF cursor (por ejemplo, al llamar a <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A>) es **CloseConnection**; se omiten todos los demás.</span><span class="sxs-lookup"><span data-stu-id="ce18d-113">The only **CommandBehavior** enumeration value that works with REF CURSORs (for example, when calling <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A>) is **CloseConnection**; all others are ignored.</span></span>  
  
- <span data-ttu-id="ce18d-114">El orden de los cursores REF cursor en el **OracleDataReader** depende del orden de los parámetros en el **OracleParameterCollection**.</span><span class="sxs-lookup"><span data-stu-id="ce18d-114">The order of REF CURSORs in the **OracleDataReader** depends on the order of the parameters in the **OracleParameterCollection**.</span></span> <span data-ttu-id="ce18d-115">Se omite la propiedad <xref:System.Data.OracleClient.OracleParameter.ParameterName%2A>.</span><span class="sxs-lookup"><span data-stu-id="ce18d-115">The <xref:System.Data.OracleClient.OracleParameter.ParameterName%2A> property is ignored.</span></span>  
  
- <span data-ttu-id="ce18d-116">PL/SQL **tabla** no se admite el tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="ce18d-116">The PL/SQL **TABLE** data type is not supported.</span></span> <span data-ttu-id="ce18d-117">No obstante, los cursores REF CURSOR resultan más eficientes.</span><span class="sxs-lookup"><span data-stu-id="ce18d-117">However, REF CURSORs are more efficient.</span></span> <span data-ttu-id="ce18d-118">Si debe utilizar un **tabla** tipo de datos, utilice el proveedor de datos OLE DB .NET con MSDAORA.</span><span class="sxs-lookup"><span data-stu-id="ce18d-118">If you must use a **TABLE** data type, use the OLE DB .NET Data Provider with MSDAORA.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ce18d-119">En esta sección</span><span class="sxs-lookup"><span data-stu-id="ce18d-119">In This Section</span></span>  
 [<span data-ttu-id="ce18d-120">Ejemplos de REF CURSOR</span><span class="sxs-lookup"><span data-stu-id="ce18d-120">REF CURSOR Examples</span></span>](../../../../docs/framework/data/adonet/ref-cursor-examples.md)  
 <span data-ttu-id="ce18d-121">Contiene tres ejemplos en los que se muestra el uso de cursores REF CURSOR.</span><span class="sxs-lookup"><span data-stu-id="ce18d-121">Contains three examples that demonstrate using REF CURSORs.</span></span>  
  
 [<span data-ttu-id="ce18d-122">Parámetros REF CURSOR en un objeto OracleDataReader</span><span class="sxs-lookup"><span data-stu-id="ce18d-122">REF CURSOR Parameters in an OracleDataReader</span></span>](../../../../docs/framework/data/adonet/ref-cursor-parameters-in-an-oracledatareader.md)  
 <span data-ttu-id="ce18d-123">Muestra cómo ejecutar un procedimiento almacenado PL/SQL que devuelve un parámetro REF CURSOR y lee el valor como un **OracleDataReader**.</span><span class="sxs-lookup"><span data-stu-id="ce18d-123">Demonstrates how to execute a PL/SQL stored procedure that returns a REF CURSOR parameter, and reads the value as an **OracleDataReader**.</span></span>  
  
 [<span data-ttu-id="ce18d-124">Recuperación de datos desde varios parámetros REF CURSOR utilizando un objeto OracleDataReader</span><span class="sxs-lookup"><span data-stu-id="ce18d-124">Retrieving Data from Multiple REF CURSORs Using an OracleDataReader</span></span>](../../../../docs/framework/data/adonet/retrieving-data-from-multiple-ref-cursors.md)  
 <span data-ttu-id="ce18d-125">Muestra cómo ejecutar un procedimiento almacenado PL/SQL que devuelve dos parámetros REF CURSOR y lee los valores mediante una **OracleDataReader**.</span><span class="sxs-lookup"><span data-stu-id="ce18d-125">Demonstrates how to execute a PL/SQL stored procedure that returns two REF CURSOR parameters, and reads the values using an **OracleDataReader**.</span></span>  
  
 [<span data-ttu-id="ce18d-126">Relleno de un conjunto de datos utilizando uno o varios parámetros REF CURSOR</span><span class="sxs-lookup"><span data-stu-id="ce18d-126">Filling a DataSet Using One or More REF CURSORs</span></span>](../../../../docs/framework/data/adonet/filling-a-dataset-using-one-or-more-ref-cursors.md)  
 <span data-ttu-id="ce18d-127">Muestra cómo ejecutar un procedimiento almacenado PL/SQL que devuelve dos parámetros REF CURSOR y llena un <xref:System.Data.DataSet> con las filas que se devuelven.</span><span class="sxs-lookup"><span data-stu-id="ce18d-127">Demonstrates how to execute a PL/SQL stored procedure that returns two REF CURSOR parameters, and fills a <xref:System.Data.DataSet> with the rows that are returned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce18d-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="ce18d-128">See also</span></span>

- [<span data-ttu-id="ce18d-129">Oracle y ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ce18d-129">Oracle and ADO.NET</span></span>](../../../../docs/framework/data/adonet/oracle-and-adonet.md)
- [<span data-ttu-id="ce18d-130">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="ce18d-130">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
