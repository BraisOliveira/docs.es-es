---
title: Elemento <sectionGroup> para <configSections>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/sectionGroup
helpviewer_keywords:
- sectionGroup Element
- <sectionGroup> Element
ms.assetid: 6c27f9e2-809c-4bc9-aca9-72f90360e7a3
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9113811557ded3a580a0bbacb24f2fe7e8d05ccf
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73114779"
---
# <a name="sectiongroup-element-for-configsections"></a>\<elemento sectionGroup > para \<configSections >

Define un espacio de nombres para las secciones de configuración.

[ **\<configuration>** ](configuration-element.md)   
&nbsp;&nbsp;[ **\<configSections >** ](configsections-element-for-configuration.md)   
&nbsp;&nbsp;&nbsp;&nbsp; **\<sectionGroup >**

## <a name="syntax"></a>Sintaxis

```xml
<sectionGroup name="section group name">
  <!-- Configuration sections -->
</sectionGroup>
```

## <a name="attribute"></a>Atributo

|           | Descripción |
| --------- | ----------- |
| **name**  | Atributo necesario.<br><br>Especifica el nombre del grupo de sección que se está definiendo. |

## <a name="parent-element"></a>Elemento primario

|     | Descripción |
| --- | ----------- |
| [ **\<configSections >** Element](configsections-element-for-configuration.md) | Contiene la sección de configuración y las declaraciones de espacio de nombres. |

## <a name="child-elements"></a>Elementos secundarios

|     | Descripción |
| --- | ----------- |
| [ **\<sección >** ](section-element.md) | Contiene una declaración de sección de configuración. |

## <a name="remarks"></a>Comentarios

Al declarar un grupo de secciones, se crea una etiqueta de contenedor para las secciones de configuración y se garantiza que no hay conflictos de nomenclatura con las secciones de configuración definidas por otro usuario. Puede anidar **\<elementos > sectionGroup** entre sí.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra cómo declarar un grupo de secciones y declarar secciones dentro de un grupo de secciones:

```xml
<configuration>
  <configSections>
    <sectionGroup name="mySectionGroup">
      <section name="mySection"
               type="System.Configuration.NameValueSectionHandler,System" />
    </sectionGroup>
  </configSections>
  <mySectionGroup>
    <mySection>
      <add key="key1" value="value1" />
    </mySection>
  </mySectionGroup>
</configuration>
```

## <a name="configuration-file"></a>Archivo de configuración

Este elemento puede usarse en el archivo de configuración de la aplicación, el archivo de configuración del equipo (*Machine. config*) y los archivos *Web. config* que no están en el nivel de directorio de la aplicación.

## <a name="see-also"></a>Vea también

- [Esquema del archivo de configuración para el .NET Framework](index.md)
