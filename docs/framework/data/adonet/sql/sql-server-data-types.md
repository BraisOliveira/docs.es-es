---
title: Tipos de datos de SQL Server y ADO.NET
ms.date: 03/30/2017
ms.assetid: 81b43550-23e8-43bb-b460-7eb8ac825c33
ms.openlocfilehash: 642fe0d541aca01d6ffb2d9279c4d0fa91eadb63
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70780854"
---
# <a name="sql-server-data-types-and-adonet"></a>Tipos de datos de SQL Server y ADO.NET
SQL Server y .NET Framework están basados en sistemas de tipos distintos, lo que puede dar lugar a posibles pérdidas de datos. Para conservar la integridad de los datos, el proveedor de datos .NET Framework para SQL Server (<xref:System.Data.SqlClient>) proporciona métodos de descriptor de acceso con tipo para trabajar con datos de SQL Server. Puede usar las enumeraciones de las clases <xref:System.Data.SqlDbType> para especificar los tipos de datos <xref:System.Data.SqlClient.SqlParameter>.  
  
 Para obtener más información y una tabla que describa las asignaciones de tipos de datos entre SQL Server y .NET Framework tipos de datos, vea [SQL Server asignaciones de tipos de datos](../sql-server-data-type-mappings.md).  
  
 SQL Server 2008 incorpora tipos de datos nuevos diseñados para satisfacer las necesidades empresariales para trabajar con datos de fecha y hora, estructurados, semiestructurados y sin estructurar. Estos tipos se describen en la documentación de los Libros en pantalla de SQL Server 2008.  
  
 Los tipos de datos de SQL Server disponibles para su uso en la aplicación dependen de la versión de SQL Server que se esté usando. Para obtener más información, busque la versión pertinente de los Libros en pantalla de SQL Server en la tabla siguiente.  
  
 **Libros en pantalla de SQL Server**  
  
1. [Tipos de datos (Motor de base de datos)](https://go.microsoft.com/fwlink/?LinkID=107468)  
  
## <a name="in-this-section"></a>En esta sección  
 [SqlTypes y DataSet](sqltypes-and-the-dataset.md)  
 Describe la compatibilidad de tipos con `SqlTypes` en el `DataSet`.  
  
 [Control de valores Null](handling-null-values.md)  
 Muestra cómo trabajar con valores NULL y la lógica de tres valores.  
  
 [Comparación de valores GUID y uniqueidentifier](comparing-guid-and-uniqueidentifier-values.md)  
 Muestra cómo trabajar con los valores GUID y uniqueidentifier en SQL Server y .NET Framework.  
  
 [Datos de fecha y hora](date-and-time-data.md)  
 Describe cómo usar los nuevos tipos de datos de fecha y hora incorporados en SQL Server 2008.  
  
 [UDT grandes](large-udts.md)  
 Muestra cómo recuperar datos de tipos de definidos por el usuario de valores grandes incorporados en SQL Server 2008.  
  
 [Datos XML en SQL Server](xml-data-in-sql-server.md)  
 Describe cómo trabajar con datos XML recuperados de SQL Server.  
  
## <a name="reference"></a>Referencia  
 <xref:System.Data.DataSet>  
 Describe la clase `DataSet`, así como todos sus miembros.  
  
 <xref:System.Data.SqlTypes>  
 Describe el espacio de nombres `SqlTypes`, así como todos sus miembros.  
  
 <xref:System.Data.SqlDbType>  
 Describe la enumeración `SqlDbType`, así como todos sus miembros.  
  
 <xref:System.Data.DbType>  
 Describe la enumeración `DbType`, así como todos sus miembros.  
  
## <a name="see-also"></a>Vea también

- [Asignaciones de tipos de datos de SQL Server](../sql-server-data-type-mappings.md)
- [Configuración de parámetros y tipos de datos de parámetros](../configuring-parameters-and-parameter-data-types.md)
- [Parámetros con valores de tabla](table-valued-parameters.md)
- [Datos binarios y datos de valores grandes de SQL Server](sql-server-binary-and-large-value-data.md)
- [Información general sobre ADO.NET](../ado-net-overview.md)
