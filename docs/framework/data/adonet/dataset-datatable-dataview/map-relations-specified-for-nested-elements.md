---
title: Asignar relaciones especificadas para elementos anidados
ms.date: 03/30/2017
ms.assetid: 24a2d3e5-4af7-4f9a-ab7a-fe6684c9e4fe
ms.openlocfilehash: cd0fd66fe70be4b8dea14ac7420e95c4b8bb1158
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64604019"
---
# <a name="map-relations-specified-for-nested-elements"></a><span data-ttu-id="6510d-102">Asignar relaciones especificadas para elementos anidados</span><span class="sxs-lookup"><span data-stu-id="6510d-102">Map Relations Specified for Nested Elements</span></span>
<span data-ttu-id="6510d-103">Un esquema puede incluir una **msdata: Relationship** anotación para especificar explícitamente la asignación entre dos elementos cualesquiera del esquema.</span><span class="sxs-lookup"><span data-stu-id="6510d-103">A schema can include an **msdata:Relationship** annotation to explicitly specify the mapping between any two elements in the schema.</span></span> <span data-ttu-id="6510d-104">Los dos elementos especificados en **msdata: Relationship** se pueden anidar en el esquema, pero no es necesario.</span><span class="sxs-lookup"><span data-stu-id="6510d-104">The two elements specified in **msdata:Relationship** can be nested in the schema, but do not have to be.</span></span> <span data-ttu-id="6510d-105">El proceso de asignación utiliza **msdata: Relationship** en el esquema para generar la relación de clave principal/clave externa entre las dos columnas.</span><span class="sxs-lookup"><span data-stu-id="6510d-105">The mapping process uses **msdata:Relationship** in the schema to generate the primary key/foreign key relationship between the two columns.</span></span>  
  
 <span data-ttu-id="6510d-106">En el ejemplo siguiente se muestra un esquema XML en el que el **OrderDetail** es un elemento secundario del **orden**.</span><span class="sxs-lookup"><span data-stu-id="6510d-106">The following example shows an XML Schema in which the **OrderDetail** element is a child element of **Order**.</span></span> <span data-ttu-id="6510d-107">El **msdata: Relationship** identifica esta relación primaria-secundaria y especifica que el **OrderNumber** columna del resultante **orden** tabla se relaciona con el **OrderNo** columna del resultante **OrderDetail** tabla.</span><span class="sxs-lookup"><span data-stu-id="6510d-107">The **msdata:Relationship** identifies this parent-child relationship and specifies that the **OrderNumber** column of the resulting **Order** table is related to the **OrderNo** column of the resulting **OrderDetail** table.</span></span>  
  
```xml  
<xs:schema id="MyDataSet" xmlns=""   
            xmlns:xs="http://www.w3.org/2001/XMLSchema"   
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
<xs:element name="MyDataSet" msdata:IsDataSet="true">  
 <xs:complexType>  
  <xs:choice maxOccurs="unbounded">  
   <xs:element name="Order">  
    <xs:complexType>  
     <xs:sequence>  
       <xs:element name="OrderNumber" type="xs:string" />  
       <xs:element name="EmpNumber" type="xs:string" />  
       <xs:element name="OrderDetail">  
          <xs:annotation>  
           <xs:appinfo>  
            <msdata:Relationship name="OrdODRelation"   
                                msdata:parent="Order"   
                                msdata:child="OrderDetail"   
                                msdata:parentkey="OrderNumber"   
                                msdata:childkey="OrderNo"/>  
           </xs:appinfo>  
          </xs:annotation>  
          <xs:complexType>  
            <xs:sequence>  
             <xs:element name="OrderNo" type="xs:string" />  
             <xs:element name="ItemNo" type="xs:string" />  
            </xs:sequence>  
         </xs:complexType>  
       </xs:element>  
     </xs:sequence>  
    </xs:complexType>  
   </xs:element>  
  </xs:choice>  
 </xs:complexType>  
</xs:element>  
</xs:schema>  
```  
  
 <span data-ttu-id="6510d-108">El proceso de asignación del esquema XML crea lo siguiente en el <xref:System.Data.DataSet>:</span><span class="sxs-lookup"><span data-stu-id="6510d-108">The XML Schema mapping process creates the following in the <xref:System.Data.DataSet>:</span></span>  
  
- <span data-ttu-id="6510d-109">Un **orden** y un **OrderDetail** tabla.</span><span class="sxs-lookup"><span data-stu-id="6510d-109">An **Order** and an **OrderDetail** table.</span></span>  
  
    ```  
    Order(OrderNumber, EmpNumber)  
    OrderDetail(OrderNo, ItemNo)  
    ```  
  
- <span data-ttu-id="6510d-110">Una relación entre el **orden** y **OrderDetail** tablas.</span><span class="sxs-lookup"><span data-stu-id="6510d-110">A relationship between the **Order** and **OrderDetail** tables.</span></span> <span data-ttu-id="6510d-111">El **Nested** propiedad para esta relación se establece en **True** porque el **orden** y **OrderDetail** elementos están anidados en el esquema .</span><span class="sxs-lookup"><span data-stu-id="6510d-111">The **Nested** property for this relationship is set to **True** because the **Order** and **OrderDetail** elements are nested in the schema.</span></span>  
  
    ```  
    ParentTable: Order  
    ParentColumns: OrderNumber   
    ChildTable: OrderDetail  
    ChildColumns: OrderNo   
    RelationName: OrdODRelation  
    Nested: True  
    ```  
  
 <span data-ttu-id="6510d-112">El proceso de asignación no crea ninguna restricción.</span><span class="sxs-lookup"><span data-stu-id="6510d-112">The mapping process does not create any constraints.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6510d-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="6510d-113">See also</span></span>

- [<span data-ttu-id="6510d-114">Generación de relaciones de objetos DataSet en un esquema XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="6510d-114">Generating DataSet Relations from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)
- [<span data-ttu-id="6510d-115">Asignación de restricciones de un esquema XML (XSD) a restricciones de conjuntos de datos</span><span class="sxs-lookup"><span data-stu-id="6510d-115">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [<span data-ttu-id="6510d-116">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="6510d-116">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
