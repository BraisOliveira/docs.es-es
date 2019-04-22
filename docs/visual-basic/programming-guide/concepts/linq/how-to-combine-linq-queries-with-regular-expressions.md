---
title: Procedimiento Combinar consultas LINQ con expresiones regulares (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 3da1bd10-b0d8-4d5b-a637-966891c13592
ms.openlocfilehash: da693b682e9b44970f167c030f6803f8dc6d2d36
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58820378"
---
# <a name="how-to-combine-linq-queries-with-regular-expressions-visual-basic"></a><span data-ttu-id="b88e5-102">Procedimiento Combinar consultas LINQ con expresiones regulares (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b88e5-102">How to: Combine LINQ Queries with Regular Expressions (Visual Basic)</span></span>
<span data-ttu-id="b88e5-103">En este ejemplo se muestra cómo usar la clase <xref:System.Text.RegularExpressions.Regex> para crear una expresión regular para coincidencias más complejas en cadenas de texto.</span><span class="sxs-lookup"><span data-stu-id="b88e5-103">This example shows how to use the <xref:System.Text.RegularExpressions.Regex> class to create a regular expression for more complex matching in text strings.</span></span> <span data-ttu-id="b88e5-104">Con la consulta LINQ, resulta fácil filtrar por los archivos exactos que se quieren buscar con la expresión regular y dar forma a los resultados.</span><span class="sxs-lookup"><span data-stu-id="b88e5-104">The LINQ query makes it easy to filter on exactly the files that you want to search with the regular expression, and to shape the results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b88e5-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b88e5-105">Example</span></span>  
  
```vb  
Class LinqRegExVB  
  
    Shared Sub Main()  
  
        ' Root folder to query, along with all subfolders.  
        ' Modify this path as necessary so that it accesses your Visual Studio folder.  
        Dim startFolder As String = "C:\Program Files (x86)\Microsoft Visual Studio 14.0\"
        ' One of the following paths may be more appropriate on your computer.  
        'Dim startFolder As String = "C:\Program Files (x86)\Microsoft Visual Studio\2017\"
  
        ' Take a snapshot of the file system.  
        Dim fileList As IEnumerable(Of System.IO.FileInfo) = GetFiles(startFolder)  
  
        ' Create a regular expression to find all things "Visual".  
        Dim searchTerm As System.Text.RegularExpressions.Regex =   
            New System.Text.RegularExpressions.Regex("Visual (Basic|C#|C\+\+|Studio)")  
  
        ' Search the contents of each .htm file.  
        ' Remove the where clause to find even more matches!  
        ' This query produces a list of files where a match  
        ' was found, and a list of the matches in that file.  
        ' Note: Explicit typing of "Match" in select clause.  
        ' This is required because MatchCollection is not a   
        ' generic IEnumerable collection.  
        Dim queryMatchingFiles = From afile In fileList  
                                Where afile.Extension = ".htm"  
                                Let fileText = System.IO.File.ReadAllText(afile.FullName)  
                                Let matches = searchTerm.Matches(fileText)  
                                Where (matches.Count > 0)  
                                Select Name = afile.FullName,  
                                       Matches = From match As System.Text.RegularExpressions.Match In matches  
                                                 Select match.Value  
  
        ' Execute the query.  
        Console.WriteLine("The term " & searchTerm.ToString() & " was found in:")  
  
        For Each fileMatches In queryMatchingFiles  
            ' Trim the path a bit, then write   
            ' the file name in which a match was found.  
            Dim s = fileMatches.Name.Substring(startFolder.Length - 1)  
            Console.WriteLine(s)  
  
            ' For this file, write out all the matching strings  
            For Each match In fileMatches.Matches  
                Console.WriteLine("  " + match)  
            Next  
        Next  
  
        ' Keep the console window open in debug mode  
        Console.WriteLine("Press any key to exit")  
        Console.ReadKey()  
    End Sub  
  
    ' Function to retrieve a list of files. Note that this is a copy  
    ' of the file information.  
    Shared Function GetFiles(ByVal root As String) As IEnumerable(Of System.IO.FileInfo)  
        Return From file In My.Computer.FileSystem.GetFiles(  
                   root, FileIO.SearchOption.SearchAllSubDirectories, "*.*")   
               Select New System.IO.FileInfo(file)  
    End Function  
  
End Class  
```  
  
 <span data-ttu-id="b88e5-106">Tenga en cuenta que también puede consultar el objeto <xref:System.Text.RegularExpressions.MatchCollection> devuelto por una búsqueda `RegEx`.</span><span class="sxs-lookup"><span data-stu-id="b88e5-106">Note that you can also query the <xref:System.Text.RegularExpressions.MatchCollection> object that is returned by a `RegEx` search.</span></span> <span data-ttu-id="b88e5-107">En este ejemplo se genera solo el valor de cada coincidencia en los resultados.</span><span class="sxs-lookup"><span data-stu-id="b88e5-107">In this example only the value of each match is produced in the results.</span></span> <span data-ttu-id="b88e5-108">Pero también es posible usar LINQ para realizar todo tipo de filtrado, ordenación y agrupación en esa colección.</span><span class="sxs-lookup"><span data-stu-id="b88e5-108">However, it is also possible to use LINQ to perform all kinds of filtering, sorting, and grouping on that collection.</span></span> <span data-ttu-id="b88e5-109">Dado que <xref:System.Text.RegularExpressions.MatchCollection> no es una colección genérica <xref:System.Collections.IEnumerable>, tendrá que indicar explícitamente el tipo de la variable de rango en la consulta.</span><span class="sxs-lookup"><span data-stu-id="b88e5-109">Because <xref:System.Text.RegularExpressions.MatchCollection> is a non-generic <xref:System.Collections.IEnumerable> collection, you have to explicitly state the type of the range variable in the query.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b88e5-110">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="b88e5-110">Compiling the Code</span></span>  
 <span data-ttu-id="b88e5-111">Cree un proyecto que tenga como destino la versión 3.5 de .NET Framework, o bien una posterior, con una referencia a System.Core.dll y una instrucción `Imports` para el espacio de nombres System.Linq.</span><span class="sxs-lookup"><span data-stu-id="b88e5-111">Create a project that targets the .NET Framework version 3.5 or higher with a reference to System.Core.dll and a `Imports` statement for the System.Linq namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b88e5-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="b88e5-112">See also</span></span>

- [<span data-ttu-id="b88e5-113">LINQ y cadenas (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b88e5-113">LINQ and Strings (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)
- [<span data-ttu-id="b88e5-114">LINQ y directorios de archivos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b88e5-114">LINQ and File Directories (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)
