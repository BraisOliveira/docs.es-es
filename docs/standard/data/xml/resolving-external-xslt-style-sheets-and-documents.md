---
title: Resolver hojas de estilos XSLT y documentos externos
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 920cfe3b-d525-4bb2-abf6-9431651f9cf9
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 381b7c1eb091bafbcdc8ea842597c539c6be3a57
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945633"
---
# <a name="resolving-external-xslt-style-sheets-and-documents"></a>Resolver hojas de estilos XSLT y documentos externos
Hay varios momentos a lo largo de una transformación en los cuales puede que necesite resolver recursos externos:  
  
> [!NOTE]
> La clase <xref:System.Xml.Xsl.XslTransform> está obsoleta en .NET Framework 2.0. Puede llevar a cabo Extensible Stylesheet Language for Transformations (XSLT) mediante la clase <xref:System.Xml.Xsl.XslCompiledTransform>.  
  
 Hay varios momentos a lo largo de una transformación en los cuales puede que necesite resolver recursos externos:  
  
- Durante la operación <xref:System.Xml.Xsl.XslTransform.Load%2A> para localizar una hoja de estilos externa.  
  
- Durante <xref:System.Xml.Xsl.XslTransform.Load%2A> para resolver cualquier elemento `<xsl:include>` o `<xsl:import>` que se encuentre en la hoja de estilos.  
  
- Durante la operación <xref:System.Xml.Xsl.XslTransform.Transform%2A> para resolver las funciones `document()`.  
  
## <a name="using-the-xmlresolver-class"></a>Utilizar la clase XmlResolver  
 Si se precisa autenticación para tener acceso a un recurso de red, utilice los métodos <xref:System.Xml.Xsl.XslTransform.Load%2A> que tengan un parámetro <xref:System.Xml.XmlResolver> para pasar el objeto <xref:System.Xml.XmlResolver> que tenga establecido el conjunto de propiedades de credenciales necesarias.  
  
 Si tiene un <xref:System.Xml.XmlResolver> personalizado que desea utilizar o si tiene que especificar unas credenciales distintas, en la tabla siguiente se enumeran las tareas requeridas en función de que sea o no necesario resolver el recurso externo.  
  
|Proceso que requiere resolución|Tareas necesarias|  
|--------------------------------------|-------------------|  
|Durante <xref:System.Xml.Xsl.XslTransform.Load%2A> para localizar la hoja de estilos.|Especificar el método <xref:System.Xml.Xsl.XslTransform.Load%2A> sobrecargado que toma como parámetro un <xref:System.Xml.XmlResolver> si la hoja de estilos se encuentra en un recurso que requiere credenciales.|  
|Durante <xref:System.Xml.Xsl.XslTransform.Load%2A> para resolver `<xsl:include>` o `<xsl:import>`.|Especificar el método <xref:System.Xml.Xsl.XslTransform.Load%2A> sobrecargado que admite, como parámetro, un <xref:System.Xml.XmlResolver>. <xref:System.Xml.XmlResolver> se utiliza para cargar las hojas de estilos a las que hacen referencia las instrucciones `import` o `include`. Si proporciona un valor `null`, los recursos externos no se resuelven.|  
|Durante una transformación para resolver las funciones `document()`.|Especifique <xref:System.Xml.XmlResolver> durante la transformación utilizando el método <xref:System.Xml.Xsl.XslTransform.Transform%2A> que toma un argumento <xref:System.Xml.XmlResolver>.|  
  
 La función `document()` recupera otros recursos XML desde una hoja de estilos, además de los datos XML iniciales proporcionados por el flujo de entrada. Como esta función permite la inclusión de datos XML que pueden localizarse en cualquier otro lugar, <xref:System.Xml.XmlResolver> con un valor `null` suministrado al método <xref:System.Xml.Xsl.XslTransform.Transform%2A> evita que la función `document()` se ejecute. Si desea utilizar la función `document()`, utilice el método <xref:System.Xml.Xsl.XslTransform.Transform%2A> que toma un <xref:System.Xml.XmlResolver> como parámetro.  
  
 Para más información sobre el método <xref:System.Xml.Xsl.XslTransform.Load%2A> y su uso de <xref:System.Xml.XmlResolver>, consulte <xref:System.Xml.Xsl.XslTransform.Load%28System.String%2CSystem.Xml.XmlResolver%29?displayProperty=nameWithType>.  
  
 Cuando se llama al método <xref:System.Xml.Xsl.XslTransform.Transform%2A>, los permisos se calculan con la evidencia proporcionada durante el tiempo de carga y dicho conjunto de permisos se asigna a todo el proceso de transformación. Si la función `document()` intenta iniciar una acción que requiere permisos que no se han encontrado en el conjunto, se inicia una excepción.  
  
## <a name="see-also"></a>Vea también

- [Transformaciones XSLT con la clase XslTransform](../../../../docs/standard/data/xml/xslt-transformations-with-the-xsltransform-class.md)
- [La clase XslTransform implementa el procesador XSLT](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)
- [Salidas de XslTransform](../../../../docs/standard/data/xml/outputs-from-an-xsltransform.md)
- [Transformaciones XSLT en distintos almacenes](../../../../docs/standard/data/xml/xslt-transformations-over-different-stores.md)
- [XsltArgumentList para parámetros Stylesheet y objetos de extensión](../../../../docs/standard/data/xml/xsltargumentlist-for-style-sheet-parameters-and-extension-objects.md)
- [Escritura de scripts de hojas de estilos XSLT mediante \<msxsl:script>](../../../../docs/standard/data/xml/xslt-stylesheet-scripting-using-msxsl-script.md)
- [Compatibilidad con la función msxsl:node-set()](../../../../docs/standard/data/xml/support-for-the-msxsl-node-set-function.md)
- [XPathNavigator en transformaciones](../../../../docs/standard/data/xml/xpathnavigator-in-transformations.md)
- [XPathNodeIterator en transformaciones](../../../../docs/standard/data/xml/xpathnodeiterator-in-transformations.md)
- [Entrada XPathDocument en XslTransform](../../../../docs/standard/data/xml/xpathdocument-input-to-xsltransform.md)
- [Entrada de XmlDataDocument en XslTransform](../../../../docs/standard/data/xml/xmldatadocument-input-to-xsltransform.md)
- [Entrada de XmlDocument en XslTransform](../../../../docs/standard/data/xml/xmldocument-input-to-xsltransform.md)
