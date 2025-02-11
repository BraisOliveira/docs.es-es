---
title: Asignación entre JSON y XML
ms.date: 03/30/2017
ms.assetid: 22ee1f52-c708-4024-bbf0-572e0dae64af
ms.openlocfilehash: 9049e622803396126890d4c88b9fee2a100f17c5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67747741"
---
# <a name="mapping-between-json-and-xml"></a>Asignación entre JSON y XML
Los sistemas de lectura y escritura generados por el <xref:System.Runtime.Serialization.Json.JsonReaderWriterFactory> proporcionan una API de XML sobre contenido de notación de objetos JavaScript (JSON) JSON codifica datos mediante un subconjunto de literales de objeto de JavaScript. Los lectores y escritores producidos por este generador también se usan cuando se está contenido JSON enviados o recibidos por las aplicaciones de Windows Communication Foundation (WCF) mediante el <xref:System.ServiceModel.Channels.WebMessageEncodingBindingElement> o <xref:System.ServiceModel.WebHttpBinding>.

Cuando se inicializa con contenido de JSON, el lector de JSON se comporta del mismo modo que un lector XML textual sobre una instancia de XML. El sistema de escritura de JSON, cuando se proporciona una secuencia de llamadas que en un lector XML textual genera una cierta instancia XML, escribe contenido JSON. La asignación entre esta instancia de XML y el contenido de JSON se describe en este tema para su uso en escenarios avanzados.

Internamente, JSON se representa como un conjunto de información XML cuando se procesa mediante WCF. Normalmente no tiene que preocuparse por esta representación interna como la asignación es sólo una lógica: JSON se convierten a XML en memoria normalmente no físicamente o se convierte en JSON desde XML. La asignación significa que API XML se utilizan para obtener acceso al contenido de JSON.

Cuando WCF usa JSON, el escenario habitual es que el <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> sea conectado automáticamente mediante el <xref:System.ServiceModel.Description.WebScriptEnablingBehavior> comportamiento, o mediante la <xref:System.ServiceModel.Description.WebHttpBehavior> comportamiento cuando corresponda. <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> entiende la asignación entre JSON y los conjuntos de información XML y actúa como si tratase directamente con JSON. (Es posible utilizar el <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> con cualquier sistema de lectura o escritura XML, siempre que se comprenda que el XML cumple la asignación siguiente).

En escenarios avanzados, puede volverse necesario tener acceso directamente a la siguiente asignación. Estos escenarios se producen cuando desea serializar y deserializar JSON de maneras personalizadas, sin basarse en el <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>, o cuando se trata directamente con el tipo <xref:System.ServiceModel.Channels.Message> para mensajes que contienen JSON. La asignación JSON-XML también se utiliza para el registro de mensajes. Cuando se usa la característica de registro de mensajes en WCF, se registran mensajes JSON como XML según la asignación descrita en la sección siguiente.

Para aclarar el concepto de asignación, se proporciona el siguiente ejemplo, que procede de un documento JSON.

```json
{"product":"pencil","price":12}
```

Para leer este documento JSON mediante uno de los lectores previamente mencionados, utilice la misma secuencia de llamadas a <xref:System.Xml.XmlDictionaryReader> que utilizaría para leer el siguiente documento XML.

```xml
<root type="object">
    <product type="string">pencil</product>
    <price type="number">12</price>
</root>
```

Además, si el mensaje JSON en el ejemplo es recibido por WCF y registra, vería el fragmento XML en el registro anterior.

## <a name="mapping-between-json-and-the-xml-infoset"></a>Asignación entre JSON y el conjunto de información XML
Formalmente, la asignación es entre JSON como se describe en [RFC 4627](https://go.microsoft.com/fwlink/?LinkId=98808) (excepto con algunas restricciones flexibles y otras restricciones adicionales) y el XML infoset (y no XML textual) como se describe en [información XML Establecer](https://go.microsoft.com/fwlink/?LinkId=98809). Vea este tema para obtener las definiciones de *elementos de información* y campos entre [corchetes].

Un documento JSON en blanco se asigna a un documento XML en blanco y un documento XML en blanco se asigna a un documento JSON en blanco. En la asignación de XML a JSON, no se permiten anterior espacios en blanco iniciales y finales de espacio en blanco después del documento.

La asignación se define entre un elemento de información de documento (DII) o un elemento de información de elemento (EII) y JSON. El EII o la propiedad [document element] (elemento de documento) del DII, se conoce como el elemento JSON raíz. Observe que los fragmentos del documento (XML con varios elementos raíz) no se admiten en esta asignación.

Ejemplo: el siguiente documento:

```xml
<?xml version="1.0"?>
<root type="number">42</root>
```

Y el siguiente elemento:

```xml
<root type="number">42</root>
```

Ambos tienen una asignación a JSON. El <`root`> es el elemento JSON raíz en ambos casos.

Es más, en el caso de un DII, se debería tener considerar lo siguiente:

- Algunos elementos en la lista [children] (elemento secundario) no deben estar presentes. No se base en este hecho al leer XML asignado desde JSON.

- La lista [children] no conserva elementos de información de comentarios.

- La lista [children] no conserva elementos de información de DTD.

- La lista [children] no conserva ningún elemento de información personal de información (PI) (el `<?xml…>` declaración no se considera un elemento de información de PI)

- El conjunto [notations] (notaciones) está vacío.

- El conjunto [unparsed entities] (entidades no analizadas) está vacío.

Ejemplo: El siguiente documento no tiene ninguna asignación a JSON porque [children] conserva un PI y un comentario.

```xml
<?xml version="1.0"?>
<!--comment--><?pi?>
<root type="number">42</root>
```

El EII del elemento JSON raíz tiene las siguientes características:

- [local name] (nombre local) tiene el valor "root" (raíz).

- [namespace name] (nombre de espacio de nombres) no tiene ningún valor.

- [prefix] (prefijo) no tiene ningún valor.

- [children] puede contener elementos EII (que representan los elementos internos, tal y como se describe más adelante) o elementos CII (elementos de información de caracteres, tal y como se describe más adelante) o ninguno de éstos, pero no ambos.

- [attributes] (atributos) puede contener los siguientes elementos de información de atributos opcionales (AII)

- El atributo de tipo JSON ("type"), tal y como se describe más adelante. Este atributo se utiliza para conservar el tipo JSON (cadena, número, booleano, objeto, matriz o nulo) en el XML asignado.

- El atributo de nombre de contrato de datos ("\_\_tipo") como se describe más adelante. Este atributo solo puede estar presente si el atributo de tipo de JSON también está presente y su [normalized value] (valor normalizado) es "object". `DataContractJsonSerializer` utiliza este atributo para conservar información del tipo de contrato de datos; por ejemplo, en casos polimórficos donde se serializa un tipo derivado y donde se espera un tipo base. Si no está trabajando con el `DataContractJsonSerializer`, en la mayoría de los casos, se pasa por alto este atributo.

- [en el ámbito de espacios de nombres] contiene el enlace de "xml" a `http://www.w3.org/XML/1998/namespace` como obligatorias por la especificación de conjunto de información.

- [children], [attributes] e [in-scope namespaces] no deben tener elementos distintos de los especificados previamente y [namespace attributes] (atributos del espacio de nombres) no debe tener ningún miembro, pero no se base en estos hechos al leer XML asignado a partir de JSON.

Ejemplo: El siguiente documento no tiene ninguna asignación a JSON porque [namespace attributes] no está vacío.

```xml
<?xml version="1.0"?>
<root xmlns:a="myattributevalue">42</root>
```

El AII para el atributo de tipo JSON tiene las siguientes características:

- [namespace name] (nombre de espacio de nombres) no tiene ningún valor.
- [prefix] (prefijo) no tiene ningún valor.
- [local name] es "type".
- [normalized value] es uno de los valores de tipo posibles descritos en la siguiente sección.
- [specified] (especificado) es `true`.
- [attribute type] (tipo de atributo) no tiene valor.
- [references] (referencias) no tiene valor.

El AII para el atributo de nombre del contrato de datos tiene las siguientes características:

- [namespace name] (nombre de espacio de nombres) no tiene ningún valor.
- [prefix] (prefijo) no tiene ningún valor.
- [local name] es "\_\_tipo" (dos caracteres de subrayado y, a continuación, "type").
- [normalized value] (valor normalizado) es cualquier cadena Unicode válida (la asignación de esta cadena a JSON se describe en la siguiente sección).
- [specified] (especificado) es `true`.
- [attribute type] (tipo de atributo) no tiene valor.
- [references] (referencias) no tiene valor.

Los elementos internos contenidos dentro del elemento JSON raíz u otros elementos internos tienen las siguientes características:

- [local name] puede tener cualquier valor tal y como se describe más adelante.
- [namespace name], [prefix], [children], [attributes], [namespace attributes] e [in-scope namespaces] están sujetos a las mismas reglas que el elemento JSON raíz.

En el elemento JSON raíz y los elementos internos, el atributo de tipo JSON define la asignación a JSON y el posible [children] (elemento secundario) y su interpretación. [Normalized value] del atributo distingue mayúsculas de minúsculas y debe estar en minúscula y no puede contener espacios en blanco.

|[normalized valor] del AII del atributo de tipo JSON|[children] permitido del EII correspondiente|Asignación a JSON|
|---------------------------------------------------------|---------------------------------------------------|---------------------|
|`string` (o ausencia del AII de tipo JSON)<br /><br /> Una `string` y la ausencia del AII de tipo JSON son lo mismo, y hace que `string` sea el valor predeterminado.<br /><br /> De modo que, `<root> string1</root>``string` asigna a la "string1"  de JSON.|0 o más CII|`string` JSON (RFC de JSON, sección 2.5). Cada `char` es un carácter que corresponde al [character code] (código de carácter) del CII. Si no hay ningún CII, asigna a una `string`de JSON vacía.<br /><br /> Ejemplo: El elemento siguiente se asigna a un fragmento de JSON:<br /><br /> `<root type="string">42</root>`<br /><br /> El fragmento de JSON es "42".<br /><br /> En la asignación de XML a JSON, los caracteres que deben establecerse como secuencia de escape se asignan a caracteres con escape, el resto se asigna a caracteres sin escape. El carácter "/" es especial, tiene escape aunque no tiene que ser (escrito como "\\/").<br /><br /> Ejemplo: El siguiente elemento que se asigna a un fragmento de JSON.<br /><br /> `<root type="string">the "da/ta"</root>`<br /><br /> El fragmento de JSON es "la \\" Acelerador de desarrollo\\/ta\\"".<br /><br /> En la asignación de JSON a XML, cualquier carácter con escape y sin escape se asignan correctamente al [character code] correspondiente.<br /><br /> Ejemplo: El fragmento de JSON "\u0041BC" se asigna al elemento XML siguiente.<br /><br /> `<root type="string">ABC</root>`<br /><br /> La cadena puede estar rodeada por espacios en blanco ('ws' en la sección 2 de JSON RFC) que no se asignan a XML.<br /><br /> Ejemplo: El JSON de fragmentos "ABC", (hay espacios delante de la primera comilla doble), se asigna al siguiente elemento XML.<br /><br /> `<root type="string">ABC</root>`<br /><br /> Los espacios en blanco en XML se asigna a un espacio en blanco en JSON.<br /><br /> Ejemplo: El siguiente elemento XML se asigna a un fragmento de JSON.<br /><br /> `<root type="string">  A BC      </root>`<br /><br /> El fragmento de JSON es " A BC ".|
|`number`|1 o más CII|Un valor JSON `number` (JSON RFC, sección 2.4), posiblemente rodeado por espacios en blanco. Cada carácter de la combinación de espacio en blanco o número es un carácter que corresponde al [character code] del CII.<br /><br /> Ejemplo: El siguiente elemento que se asigna a un fragmento de JSON.<br /><br /> `<root type="number">    42</root>`<br /><br /> El fragmento JSON es    42<br /><br /> (Se conserva el espacio en blanco).|
|`boolean`|4 ó 5 CII (que corresponde a `true` o `false`), posiblemente rodeado por CII de espacios en blanco adicionales.|Una secuencia de CII que corresponde a la cadena "true" se asigna al `true` literal, y una secuencia de CII que corresponde a la cadena "false" se asigna al `false` literal. Se conserva el espacio en blanco que rodea a.<br /><br /> Ejemplo: El siguiente elemento que se asigna a un fragmento de JSON.<br /><br /> `<root type="boolean"> false</root>`<br /><br /> El fragmento de JSON es `false`.|
|`null`|Ninguno permitido.|El literal `null`. En JSON a XML, el `null` puede estar rodeado por espacios en blanco ('ws' en la sección 2) que no se asignan a XML.<br /><br /> Ejemplo: El siguiente elemento que se asigna a un fragmento de JSON.<br /><br /> `<root type="null"/>`<br /><br /> o<br /><br /> `<root type="null"></root>`<br /><br /> :<br /><br /> El fragmento de JSON es en ambos casos `Null`.|
|`object`|0 o más EII.|`begin-object` (llave izquierda) como en la sección 2.2 de la RFC de JSON, seguida por un registro de miembros para cada EII, tal y como se describe más adelante. Si hay más de un EII, hay separadores de valores (comas) entre los registros de miembros. Todo esto va seguido de un objeto de fin (llave derecha).<br /><br /> Ejemplo: El elemento siguiente se asigna al fragmento de JSON.<br /><br /> `<root type="object">`<br /><br /> `<type1 type="string">aaa\</type1>`<br /><br /> `<type2 type="string">bbb\</type2>`<br /><br /> `</root >`<br /><br /> El fragmento de JSON es `{"type1":"aaa","type2":"bbb"}`.<br /><br /> Si el atributo del tipo de contrato de datos está presente en la asignación de XML a JSON, se inserta un registro de miembro adicional al principio. Su nombre es el [local name] del atributo de tipo del contrato de datos ("\_\_tipo"), y su valor es el atributo [valor normalizado]. Por el contrario, en JSON a XML, si el primer miembro-nombre del registro es el [local name] del atributo de tipo del contrato de datos (es decir, "\_\_tipo"), un atributo de tipo de contrato de datos correspondiente está presente en el XML asignado, pero un EII correspondiente no está presente. Observe que este registro de miembro debe producirse primero en el objeto JSON para que se aplique esta asignación especial. Esto representa una salida del procesamiento de JSON habitual, donde el orden de los registros de miembros no es importante.<br /><br /> Ejemplo:<br /><br /> El siguiente fragmento de JSON se asigna a XML.<br /><br /> `{"__type":"Person","name":"John"}`<br /><br /> El XML es el código siguiente.<br /><br /> `<root type="object" __type="Person">   <name type="string">John</name> </root>`<br /><br /> Tenga en cuenta que el \_ \_AII de tipo está presente, pero no hay ningún \_ \_escriba EII.<br /><br /> Sin embargo, si se invierte el orden en JSON como se muestra en el ejemplo siguiente.<br /><br /> `{"name":"John","\_\_type":"Person"}`<br /><br /> Se muestra el XML correspondiente.<br /><br /> `<root type="object">   <name type="string">John</name>   <__type type="string">Person</__type> </root>`<br /><br /> Es decir, \__tipo deja de tener un significado especial y se asigna a un EII como es habitual, no AII.<br /><br /> Las reglas de escapado/no escapado para el [normalized value] del AII cuando se asigna a un valor JSON son las mismas que para las cadenas de JSON, especificadas en la fila "string" de esta tabla.<br /><br /> Ejemplo:<br /><br /> `<root type="object" __type="\abc" />`<br /><br /> en el ejemplo anterior puede asignarse al siguiente JSON.<br /><br /> `{"__type":"\\abc"}`<br /><br /> En una asignación de XML a JSON, no debe ser del primer EII [local name] "\_\_tipo".<br /><br /> Espacio en blanco (`ws`) nunca se genera en XML para la asignación de JSON de objetos y se omite en JSON a XML.<br /><br /> Ejemplo: El siguiente fragmento JSON se asigna a un elemento XML.<br /><br /> `{ "ccc" : "aaa", "ddd" :"bbb"}`<br /><br /> El elemento XML se muestra en el siguiente código.<br /><br /> `<root type="object">    <ccc type="string">aaa</ccc>    <ddd type="string">bbb</bar> </root >`|
|array|0 o más EII|Una matriz de comienzo (corchete de apertura) como en la sección 2.3 de la JSON RFC, seguida por un registro de matriz para cada EII, tal y como se describe más adelante. Si hay más de un EII, hay separadores de valores (comas) entre los registros de matrices. Una matriz es seguida por una matriz de final.<br /><br /> Ejemplo: El siguiente elemento XML se asigna a un fragmento de JSON.<br /><br /> `<root type="array"/>    <item type="string">aaa</item>    <item type="string">bbb</item> </root >`<br /><br /> El fragmento de JSON `["aaa","bbb"]`<br /><br /> Espacio en blanco (`ws`) nunca se genera en XML para la asignación de JSON para matrices y se omite en JSON a XML.<br /><br /> Ejemplo: Un fragmento de JSON.<br /><br />`["aaa", "bbb"]`<br /><br /> El elemento XML al que se asigna.<br /><br /> `<root type="array"/>    <item type="string">aaa</item>    <item type="string">bbb</item> </root >`|

Los registros de miembros funcionan de la siguiente manera:

- El [local name] del elemento interno se asigna a la parte de `string` del `member`, tal y como se define en la sección 2.2 de la JSON RFC.

Ejemplo: El siguiente elemento que se asigna a un fragmento de JSON.

```xml
<root type="object"/>
<myLocalName type="string">aaa</myLocalName>
</root >
```

Se muestra el siguiente fragmento de JSON.

```json
{"myLocalName":"aaa"}
```

- En la asignación de XML a JSON, los caracteres que deben tener escape en JSON tienen escape, y el resto no tiene escape. El carácter "/", aunque no es ningún carácter que deba tener escape, lo tiene (no es necesario que tenga escape en la asignación de JSON a XML). Esto es necesario para admitir el formato AJAX de ASP.NET para los datos `DateTime` en JSON.

- En la asignación de JSON a XML, todos los caracteres (incluidos los que no tienen escape, si fuese necesario) se toman para formar una `string` que genera un [local name].

- Los elementos internos [children] se asignan al valor en la sección 2.2, de acuerdo con el `JSON Type Attribute` de la misma manera que para el `Root JSON Element`. Se permiten varios niveles de anidación de EII (incluida la anidación dentro de matrices).

Ejemplo: El siguiente elemento que se asigna a un fragmento de JSON.

```xml
<root type="object">
    <myLocalName1 type="string">myValue1</myLocalName1>
    <myLocalName2 type="number">2</myLocalName2>
    <myLocalName3 type="object">
        <myNestedName1 type="boolean">true</myNestedName1>
        <myNestedName2 type="null"/>
    </myLocalName3>
</root >
```

El fragmento de JSON siguiente es a lo que se asigna.

```json
{"myLocalName1":"myValue1","myLocalName2":2,"myLocalName3":{"myNestedName1":true,"myNestedName2":null}}
```

> [!NOTE]
> No hay ningún paso de codificación XML en la asignación anterior. Por lo tanto, WCF solo admite documentos JSON donde todos los caracteres en nombres de clave son caracteres válidos en nombres de elementos XML. Por ejemplo, el documento JSON {"<": "a"} no se admite porque < no es un nombre válido para un elemento XML.

La situación inversa (caracteres válidos en XML, pero no en JSON) no produce ningún problema, puesto que la asignación anterior incluye pasos de escape/sin escape de JSON.

Los registros de matrices funcionan de la siguiente manera:

- El [local name] del elemento interno es "item".

- Los [children] (elementos secundarios) del elemento interno se asignan al valor en la sección 2.3, según el atributo de tipo JSON, como se hace para el elemento JSON raíz. Se permiten varios niveles de anidación de EII (incluida la anidación dentro de objetos).

Ejemplo: El siguiente elemento que se asigna a un fragmento de JSON.

```xml
<root type="array"/>
    <item type="string">myValue1</item>
    <item type="number">2</item>
    <item type="array">
    <item type="boolean">true</item>
    <item type="null"/></item>
</root >
```

A continuación, se muestra el fragmento JSON.

```json
["myValue1",2,[true,null]]
```

## <a name="see-also"></a>Vea también

- <xref:System.Runtime.Serialization.Json.JsonReaderWriterFactory>
- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>
- [Serialización independiente de JSON](stand-alone-json-serialization.md)
