---
title: 'Archivo XML de ejemplo: Configuración de pruebas en un Namespace3'
ms.date: 07/20/2015
ms.assetid: aff02614-30ee-45e1-bc0f-d64b193d20b8
ms.openlocfilehash: aef70e1ff7a7d61a1730588cc9e2ad26e6b67007
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61786950"
---
# <a name="sample-xml-file-test-configuration-in-a-namespace"></a><span data-ttu-id="701a1-102">Archivo XML de ejemplo: Configuración de prueba en un espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="701a1-102">Sample XML File: Test Configuration in a Namespace</span></span>
<span data-ttu-id="701a1-103">El siguiente archivo XML se usa en numerosos ejemplos de la documentación de [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="701a1-103">The following XML file is used in various examples in the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] documentation.</span></span> <span data-ttu-id="701a1-104">Se trata de un archivo de configuración de pruebas.</span><span class="sxs-lookup"><span data-stu-id="701a1-104">This is a test configuration file.</span></span> <span data-ttu-id="701a1-105">El XML se encuentra en un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="701a1-105">The XML is in a namespace.</span></span>  
  
## <a name="testconfiginnamespacexml"></a><span data-ttu-id="701a1-106">TestConfigInNamespace.xml</span><span class="sxs-lookup"><span data-stu-id="701a1-106">TestConfigInNamespace.xml</span></span>  
  
```xml  
<?xml version="1.0"?>  
<Tests xmlns="http://www.adatum.com">  
  <Test TestId="0001" TestType="CMD">  
    <Name>Convert number to string</Name>  
    <CommandLine>Examp1.EXE</CommandLine>  
    <Input>1</Input>  
    <Output>One</Output>  
  </Test>  
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
  <Test TestId="0005" TestType="GUI">  
    <Name>Count characters</Name>  
    <CommandLine>FinalExamp.EXE</CommandLine>  
    <Input>This is a test</Input>  
    <Output>14</Output>  
  </Test>  
  <Test TestId="0006" TestType="GUI">  
    <Name>Another Test</Name>  
    <CommandLine>Examp2.EXE</CommandLine>  
    <Input>Test Input</Input>  
    <Output>10</Output>  
  </Test>  
</Tests>  
```  
  
## <a name="see-also"></a><span data-ttu-id="701a1-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="701a1-107">See also</span></span>

- [<span data-ttu-id="701a1-108">Documentos XML de ejemplo (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="701a1-108">Sample XML Documents (LINQ to XML)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-documents-linq-to-xml.md)
