---
title: Generar relaciones de objetos DataSet en un esquema XML (XSD)
ms.date: 03/30/2017
ms.assetid: 1c9a1413-c0d2-4447-88ba-9a2b0cbc0aa8
ms.openlocfilehash: d00f07ee3338941b7de1bb890f71cd3c2d120246
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70784644"
---
# <a name="generating-dataset-relations-from-xml-schema-xsd"></a>Generar relaciones de objetos DataSet en un esquema XML (XSD)
En un <xref:System.Data.DataSet>, para formar una asociación entre dos o más columnas se debe crear una relación primaria-secundaria. Hay tres formas de representar una relación de **conjunto de datasets** dentro de un esquema del lenguaje de definición de esquemas XML (XSD):  
  
- Especificar tipos complejos anidados.  
  
- Use la anotación **msdata: Relationship** .  
  
- Especifique **xs: keyref** sin la anotación **msdata: ConstraintOnly** .  
  
## <a name="nested-complex-types"></a>Tipos complejos anidados  
 Las definiciones de tipos complejos anidados de un esquema indican las relaciones primaria-secundaria de los elementos. El siguiente fragmento de esquema XML muestra que **OrderDetail** es un elemento secundario del elemento **Order** .  
  
```xml  
<xs:element name="Order">  
  <xs:complexType>  
     <xs:sequence>          
       <xs:element name="OrderDetail" />  
           <xs:complexType>               
           </xs:complexType>  
     </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 El proceso de asignación del esquema XML crea tablas en el **conjunto de DataSet** que corresponden a los tipos complejos anidados en el esquema. También crea columnas adicionales que se usan como columnas primarias **-** secundarias para las tablas generadas. Tenga en cuenta que **-** estas columnas principales secundarias especifican relaciones, lo que no es lo mismo que especificar restricciones de clave principal y clave externa.  
  
## <a name="msdatarelationship-annotation"></a>Anotación msdata:Relationship  
 La anotación **msdata: Relationship** permite especificar explícitamente las relaciones primario-secundario entre los elementos del esquema que no están anidados. En el ejemplo siguiente se muestra la estructura del elemento **Relationship** .  
  
```xml  
<msdata:Relationship name="CustOrderRelationship"    
msdata:parent=""    
msdata:child=""    
msdata:parentkey=""    
msdata:childkey="" />  
```  
  
 Los atributos de la anotación **msdata: Relationship** identifican los elementos implicados en la relación primario-secundario, así como los elementos **ParentKey** y **childkey** y los atributos implicados en la relación. El proceso de asignación utiliza esta información para generar tablas en el **conjunto** de datos y para crear la relación de clave principal y clave externa entre estas tablas.  
  
 Por ejemplo, en el siguiente fragmento de esquema se especifican los elementos **Order** y **OrderDetail** en el mismo nivel (no anidado). El esquema especifica una anotación **msdata: Relationship** , que especifica la relación primaria-secundaria entre estos dos elementos. En este caso, se debe especificar una relación explícita mediante la anotación **msdata: Relationship** .  
  
```xml  
 <xs:element name="MyDataSet" msdata:IsDataSet="true">  
  <xs:complexType>  
    <xs:choice maxOccurs="unbounded">  
        <xs:element name="OrderDetail">  
          <xs:complexType>  
  
          </xs:complexType>  
       </xs:element>  
       <xs:element name="Order">  
          <xs:complexType>  
  
          </xs:complexType>  
       </xs:element>  
    </xs:choice>  
  </xs:complexType>  
</xs:element>  
   <xs:annotation>  
     <xs:appinfo>  
       <msdata:Relationship name="OrdOrdDetailRelation"  
          msdata:parent="Order"  
          msdata:child="OrderDetail"   
          msdata:parentkey="OrderNumber"  
          msdata:childkey="OrderNo"/>  
     </xs:appinfo>  
  </xs:annotation>  
```  
  
 El proceso de asignación utiliza el elemento **Relationship** para crear una relación de elementos primarios y secundarios entre la columna **OrderNumber** de la tabla **Order** y la columna **OrderNo** de la tabla **OrderDetail** del **conjunto**de elementos. El proceso de asignación sólo especifica la relación; no especifica automáticamente ninguna restricción para los valores de estas columnas, como ocurre en las restricciones de clave principal y clave externa de las bases de datos relacionales.  
  
### <a name="in-this-section"></a>En esta sección  
 [Asignación de relaciones implícitas entre elementos de esquema anidados](map-implicit-relations-between-nested-schema-elements.md)  
 Describe las restricciones y las relaciones que se crean implícitamente en un **conjunto** de objetos cuando se encuentran elementos anidados en el esquema XML.  
  
 [Asignación de relaciones especificadas para elementos anidados](map-relations-specified-for-nested-elements.md)  
 Describe cómo establecer explícitamente las relaciones de un **conjunto** de objetos para los elementos anidados en el esquema XML.  
  
 [Definición de relaciones entre elementos sin anidamiento](specify-relations-between-elements-with-no-nesting.md)  
 Describe cómo crear relaciones en un **DataSet** entre elementos del esquema XML que no están anidados.  
  
### <a name="related-sections"></a>Secciones relacionadas  
 [Derivación de una estructura relacional de un conjunto de datos a partir de un esquema XML (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 Describe la estructura relacional, o esquema, de un **DataSet** que se crea a partir del esquema del lenguaje de definición de esquemas XML (XSD).  
  
 [Asignación de restricciones de un esquema XML (XSD) a restricciones de conjuntos de datos](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 Describe los elementos de esquema XML utilizados para crear restricciones de clave única y externa en un **conjunto de DataSet**.  
  
## <a name="see-also"></a>Vea también

- [Información general sobre ADO.NET](../ado-net-overview.md)
