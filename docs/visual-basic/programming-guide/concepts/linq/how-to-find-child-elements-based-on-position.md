---
title: Procedimiento Buscar elementos secundarios en función de la posición (XPath-LINQ to XML) (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 6831e1db-5e97-444f-a7a1-d0a87104b005
ms.openlocfilehash: 11a9fdd7ed8565c38b0527d266af75b8fb611a20
ms.sourcegitcommit: d7c298f6c2e3aab0c7498bfafc0a0a94ea1fe23e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/10/2019
ms.locfileid: "72249703"
---
# <a name="how-to-find-child-elements-based-on-position-xpath-linq-to-xml-visual-basic"></a>Procedimiento Buscar elementos secundarios en función de la posición (XPath-LINQ to XML) (Visual Basic)
En ocasiones, deseará buscar elementos en función de su posición. Quizá desee buscar el segundo elemento o buscar el tercero en el quinto elemento.  
  
 La expresión XPath es:  
  
 `Test[position() >= 2 and position() <= 4]`  
  
 Existen dos aproximaciones posibles para escribir esta consulta de [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] de forma diferida. Puede utilizar los operadores <xref:System.Linq.Enumerable.Skip%2A> y <xref:System.Linq.Enumerable.Take%2A>, o bien utilizar la sobrecarga <xref:System.Linq.Enumerable.Where%2A> que recibe un índice. Si utiliza la sobrecarga <xref:System.Linq.Enumerable.Where%2A>, estará utilizando una expresión lambda que recibe dos argumentos. El siguiente ejemplo muestra ambos métodos para seleccionar elementos en base a la posición.  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo encontrará el segundo en el cuarto elemento de `Test`. El resultado es una colección de elementos.  
  
 Este ejemplo utiliza el siguiente documento XML: [Archivo XML de ejemplo: Configuración de prueba (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-test-configuration-linq-to-xml.md).  
  
```vb  
Dim testCfg As XElement = XElement.Load("TestConfig.xml")  
  
' LINQ to XML query  
Dim list1 As IEnumerable(Of XElement) = _  
    testCfg.Elements("Test").Skip(1).Take(3)  
  
'LINQ to XML query  
Dim list2 As IEnumerable(Of XElement) = _  
    testCfg.Elements("Test"). _  
    Where(Function(ByVal el, ByVal idx) idx >= 1 And idx <= 3)  
  
' XPath expression  
Dim list3 As IEnumerable(Of XElement) = _  
    testCfg.XPathSelectElements("Test[position() >= 2 and position() <= 4]")  
  
If list1.Count() = list2.Count() And _  
       list1.Count() = list3.Count() And _  
       list1.Intersect(list2).Count() = list1.Count() And _  
       list1.Intersect(list3).Count() = list1.Count() Then  
  
    Console.WriteLine("Results are identical")  
Else  
    Console.WriteLine("Results differ")  
End If  
  
For Each el As XElement In list1  
    Console.WriteLine(el)  
Next  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```console  
Results are identical  
<Test TestId="0002" TestType="CMD">  
  <Name>Find succeeding characters</Name>  
  <CommandLine>Examp2.EXE</CommandLine>  
  <Input>abc</Input>  
  <Output>def</Output>  
</Test>  
<Test TestId="0003" TestType="GUI">  
  <Name>Convert multiple numbers to strings</Name>  
  <CommandLine>Examp2.EXE /Verbose</CommandLine>  
  <Input>123</Input>  
  <Output>One Two Three</Output>  
</Test>  
<Test TestId="0004" TestType="GUI">  
  <Name>Find correlated key</Name>  
  <CommandLine>Examp3.EXE</CommandLine>  
  <Input>a1</Input>  
  <Output>b1</Output>  
</Test>  
```  
  
## <a name="see-also"></a>Vea también

- [LINQ to XML para los usuarios de XPath (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
