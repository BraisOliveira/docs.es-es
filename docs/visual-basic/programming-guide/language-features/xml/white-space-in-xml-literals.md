---
title: Espacio en blanco en literales XML (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- white space [XML in Visual Basic]
- XML literals [Visual Basic], white space
ms.assetid: dfe3a9ff-d69a-418e-a6b5-476f4ed84219
ms.openlocfilehash: f72dcc25b158d793850069e5cc32c3a3c02fad17
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69939207"
---
# <a name="white-space-in-xml-literals-visual-basic"></a>Espacio en blanco en literales XML (Visual Basic)
El compilador de Visual Basic incorpora solo los caracteres de espacio en blanco significativos de un literal [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] XML cuando crea un objeto. No se incorporan los caracteres de espacio en blanco insignificantes.  
  
## <a name="significant-and-insignificant-white-space"></a>Espacio en blanco significativo e insignificante  
 Los caracteres de espacio en blanco de los literales XML solo son significativos en tres áreas:  
  
- Cuando se encuentran en un valor de atributo.  
  
- Cuando forman parte del contenido de texto de un elemento y el texto también contiene otros caracteres.  
  
- Cuando están en una expresión incrustada para el contenido de texto de un elemento.  
  
 De lo contrario, el compilador trata los caracteres de espacio en blanco como insignificantes y no incluye en el [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objeto para el literal.  
  
 Para incluir un espacio en blanco insignificante en un literal XML, use una expresión incrustada que contenga un literal de cadena con el espacio en blanco.  
  
> [!NOTE]
> Si el `xml:space` atributo aparece en un literal de elemento XML, el compilador Visual Basic incluye el <xref:System.Xml.Linq.XElement> atributo en el objeto, pero al agregar este atributo no se cambia el modo en que el compilador trata los espacios en blanco.  
  
## <a name="examples"></a>Ejemplos  
 El ejemplo siguiente contiene dos elementos XML, Outer e Inner. Ambos elementos contienen espacios en blanco en el contenido de texto. El espacio en blanco del elemento exterior es insignificante porque solo contiene espacios en blanco y un elemento XML. El espacio en blanco del elemento interno es significativo porque contiene un espacio en blanco y texto.  
  
 [!code-vb[VbXMLSamples#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#29)]  
  
 Cuando se ejecuta, este código muestra el texto siguiente.  
  
```xml  
<outer>  
  <inner>  
                                          Inner text  
                                      </inner>  
</outer>  
```  
  
## <a name="see-also"></a>Vea también

- [Crear XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
