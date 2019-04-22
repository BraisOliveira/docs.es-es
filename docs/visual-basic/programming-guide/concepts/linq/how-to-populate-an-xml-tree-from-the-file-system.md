---
title: Procedimiento Rellenar un árbol XML desde el sistema de archivos (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 34eec79e-7945-4ba8-9f74-d05bb8ec67f6
ms.openlocfilehash: 55c182134e0cc1a7472cfaa6bb4355e9457a6977
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58820846"
---
# <a name="how-to-populate-an-xml-tree-from-the-file-system-visual-basic"></a><span data-ttu-id="0b049-102">Procedimiento Rellenar un árbol XML desde el sistema de archivos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0b049-102">How to: Populate an XML Tree from the File System (Visual Basic)</span></span>
<span data-ttu-id="0b049-103">Una aplicación habitual y útil de los árboles XML es un almacén de datos de nombres y valores jerárquicos.</span><span class="sxs-lookup"><span data-stu-id="0b049-103">A common and useful application of XML trees is as a hierarchical name/value data store.</span></span> <span data-ttu-id="0b049-104">Puede rellenar un árbol XML con datos jerárquicos y, a continuación, consultarlo, transformarlo y, si es necesario, serializarlo.</span><span class="sxs-lookup"><span data-stu-id="0b049-104">You can populate an XML tree with hierarchical data, and then query it, transform it, and if necessary, serialize it.</span></span> <span data-ttu-id="0b049-105">En este escenario de uso, gran parte de la semántica específica XML (por ejemplo, el comportamiento de los espacios en blanco y los espacios de nombres) no es importante.</span><span class="sxs-lookup"><span data-stu-id="0b049-105">In this usage scenario, many of the XML specific semantics, such as namespaces and white space behavior, are not important.</span></span> <span data-ttu-id="0b049-106">En su lugar, usará el árbol XML como una base de datos jerárquica, pequeña y en memoria, de usuario único.</span><span class="sxs-lookup"><span data-stu-id="0b049-106">Instead, you are using the XML tree as a small, in memory, single user hierarchical database.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0b049-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0b049-107">Example</span></span>  
 <span data-ttu-id="0b049-108">El ejemplo siguiente rellena un árbol XML desde el sistema de archivos local mediante la recursividad.</span><span class="sxs-lookup"><span data-stu-id="0b049-108">The following example populates an XML tree from the local file system using recursion.</span></span> <span data-ttu-id="0b049-109">A continuación, consulta el árbol y calcula el total de los tamaños de todos los archivos del árbol.</span><span class="sxs-lookup"><span data-stu-id="0b049-109">It then queries the tree, calculating the total of the sizes of all files in the tree.</span></span>  
  
```vb  
Module Module1  
    Function CreateFileSystemXmlTree(ByVal source As String) As XElement  
        Dim di As DirectoryInfo = New DirectoryInfo(source)  
        Return <Dir Name=<%= di.Name %>>  
                   <%= From d In Directory.GetDirectories(source) _  
                       Select CreateFileSystemXmlTree(d) %>  
                   <%= From fi In di.GetFiles() _  
                       Select <File>  
                                  <Name><%= fi.Name %></Name>  
                                  <Length><%= fi.Length %></Length>  
                              </File> %>  
               </Dir>  
    End Function  
  
    Sub Main()  
        Dim fileSystemTree As XElement = CreateFileSystemXmlTree("C:/Tmp")  
        Console.WriteLine(fileSystemTree)  
        Console.WriteLine("------")  
        Dim totalFileSize As Long = _  
            ( _  
                From f In fileSystemTree...<File> _  
                Select CLng(f.<Length>(0)) _  
            ).Sum()  
        Console.WriteLine("Total File Size:{0}", totalFileSize)  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="0b049-110">Este ejemplo genera un resultado similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="0b049-110">This example produces output similar to the following:</span></span>  
  
```xml  
<Dir Name="Tmp">  
  <Dir Name="ConsoleApplication1">  
    <Dir Name="bin">  
      <Dir Name="Debug">  
        <File>  
          <Name>ConsoleApplication1.exe</Name>  
          <Length>4608</Length>  
        </File>  
        <File>  
          <Name>ConsoleApplication1.pdb</Name>  
          <Length>11776</Length>  
        </File>  
        <File>  
          <Name>ConsoleApplication1.vshost.exe</Name>  
          <Length>9568</Length>  
        </File>  
        <File>  
          <Name>ConsoleApplication1.vshost.exe.manifest</Name>  
          <Length>473</Length>  
        </File>  
      </Dir>  
    </Dir>  
    <Dir Name="obj">  
      <Dir Name="Debug">  
        <Dir Name="TempPE" />  
        <File>  
          <Name>ConsoleApplication1.csproj.FileListAbsolute.txt</Name>  
          <Length>322</Length>  
        </File>  
        <File>  
          <Name>ConsoleApplication1.exe</Name>  
          <Length>4608</Length>  
        </File>  
        <File>  
          <Name>ConsoleApplication1.pdb</Name>  
          <Length>11776</Length>  
        </File>  
      </Dir>  
    </Dir>  
    <Dir Name="Properties">  
      <File>  
        <Name>AssemblyInfo.cs</Name>  
        <Length>1454</Length>  
      </File>  
    </Dir>  
    <File>  
      <Name>ConsoleApplication1.csproj</Name>  
      <Length>2546</Length>  
    </File>  
    <File>  
      <Name>ConsoleApplication1.sln</Name>  
      <Length>937</Length>  
    </File>  
    <File>  
      <Name>ConsoleApplication1.suo</Name>  
      <Length>10752</Length>  
    </File>  
    <File>  
      <Name>Program.cs</Name>  
      <Length>269</Length>  
    </File>  
  </Dir>  
</Dir>  
------  
Total File Size:59089  
```  
  
## <a name="see-also"></a><span data-ttu-id="0b049-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="0b049-111">See also</span></span>

- [<span data-ttu-id="0b049-112">Consulta técnicas avanzadas (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0b049-112">Advanced Query Techniques (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/advanced-query-techniques-linq-to-xml.md)
