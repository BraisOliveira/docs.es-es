---
title: mc:ProcessContent (Atributo)
ms.date: 03/30/2017
helpviewer_keywords:
- mc:ProcessContent attribute
- XAML [WPF], mc:ProcessContent attribute
ms.assetid: 2689b2c8-b4dc-4b71-b9bd-f95e619122d7
ms.openlocfilehash: dde304cc2b9db9cb01f9264ca1359b8979512cfa
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458781"
---
# <a name="mcprocesscontent-attribute"></a>mc:ProcessContent (Atributo)
Especifica qué elementos [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] deben seguir teniendo el contenido procesado por los elementos primarios pertinentes, incluso si un procesador de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] puede omitir el elemento primario inmediato debido a la especificación de un [atributo MC: ignorable](mc-ignorable-attribute.md). El atributo `mc:ProcessContent` admite la compatibilidad de marcado para la asignación de espacios de nombres personalizados y para el control de versiones de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
## <a name="xaml-attribute-usage"></a>Uso de atributos XAML  
  
```xaml  
<object  
  xmlns:ignorablePrefix="ignorableUri"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix"...  
  mc:ProcessContent="ignorablePrefix:ThisElementCanBeIgnored"  
>  
    <ignorablePrefix:ThisElementCanBeIgnored>  
        [content]  
    </ignorablePrefix:ThisElementCanBeIgnored>  
</object>  
```  
  
## <a name="xaml-values"></a>Valores XAML  
  
|||  
|-|-|  
|*ignorablePrefix*|Cualquier cadena de prefijo válida, según la especificación de XML 1,0.|  
|*ignorableUri*|Cualquier URI válido para designar un espacio de nombres, según la especificación de XML 1,0.|  
|*ThisElementCanBeIgnored*|Un elemento que puede ser omitido por implementaciones de procesador [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], si no se puede resolver el tipo subyacente.|  
|*Content*|*ThisElementCanBeIgnored* está marcado como ignorable. Si el procesador omite ese elemento, el *objeto*procesa *[Content]* .|  
  
## <a name="remarks"></a>Comentarios  
 De forma predeterminada, un procesador [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] omitirá el contenido dentro de un elemento omitido. Puede especificar un elemento específico por `mc:ProcessContent`y un procesador de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] seguirá procesando el contenido dentro del elemento omitido. Esto se suele usar si el contenido está anidado en varias etiquetas, al menos uno de los cuales es ignorable y, al menos, uno de los cuales no se puede omitir.  
  
 Se pueden especificar varios prefijos en el atributo, mediante un separador de espacio, por ejemplo: `mc:ProcessContent="ignore:Element1 ignore:Element2"`.  
  
 El espacio de nombres `http://schemas.openxmlformats.org/markup-compatibility/2006` define otros elementos y atributos que no están documentados en esta área del SDK. Para obtener más información, vea [especificación de compatibilidad de marcado XML](https://go.microsoft.com/fwlink/?LinkId=73824).  
  
## <a name="see-also"></a>Vea también

- [mc:Ignorable (atributo)](mc-ignorable-attribute.md)
- [Información general sobre XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
