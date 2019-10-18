---
title: 'Cómo: contar las repeticiones de una palabra en una cadena (LINQ) (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: bc367e46-f7cc-45f9-936f-754e661b7bb9
ms.openlocfilehash: 3a2ae52a3380e4a0d8df4adb580e84362e3f13f3
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524165"
---
# <a name="how-to-count-occurrences-of-a-word-in-a-string-linq-visual-basic"></a><span data-ttu-id="3790e-102">Cómo: contar las repeticiones de una palabra en una cadena (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3790e-102">How to: Count Occurrences of a Word in a String (LINQ) (Visual Basic)</span></span>

<span data-ttu-id="3790e-103">En este ejemplo se muestra cómo usar una consulta LINQ para contar las apariciones de una palabra determinada en una cadena.</span><span class="sxs-lookup"><span data-stu-id="3790e-103">This example shows how to use a LINQ query to count the occurrences of a specified word in a string.</span></span> <span data-ttu-id="3790e-104">Observe que para realizar el recuento, primero se llama al método <xref:System.String.Split%2A> para crear una matriz de palabras.</span><span class="sxs-lookup"><span data-stu-id="3790e-104">Note that to perform the count, first the <xref:System.String.Split%2A> method is called to create an array of words.</span></span> <span data-ttu-id="3790e-105">Existe un costo de rendimiento en el método <xref:System.String.Split%2A>.</span><span class="sxs-lookup"><span data-stu-id="3790e-105">There is a performance cost to the <xref:System.String.Split%2A> method.</span></span> <span data-ttu-id="3790e-106">Si la única operación de la cadena es para contar las palabras, debe considerar la posibilidad de usar en su lugar los métodos <xref:System.Text.RegularExpressions.Regex.Matches%2A> o <xref:System.String.IndexOf%2A>.</span><span class="sxs-lookup"><span data-stu-id="3790e-106">If the only operation on the string is to count the words, you should consider using the <xref:System.Text.RegularExpressions.Regex.Matches%2A> or <xref:System.String.IndexOf%2A> methods instead.</span></span> <span data-ttu-id="3790e-107">Pero si el rendimiento no es un problema crítico, o si ya ha dividido la frase para realizar otros tipos de consultas, tiene sentido usar LINQ para además contar las palabras o frases.</span><span class="sxs-lookup"><span data-stu-id="3790e-107">However, if performance is not a critical issue, or you have already split the sentence in order to perform other types of queries over it, then it makes sense to use LINQ to count the words or phrases as well.</span></span>

## <a name="example"></a><span data-ttu-id="3790e-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3790e-108">Example</span></span>

```vb
Class CountWords

    Shared Sub Main()

        Dim text As String = "Historically, the world of data and the world of objects" &
                  " have not been well integrated. Programmers work in C# or Visual Basic" &
                  " and also in SQL or XQuery. On the one side are concepts such as classes," &
                  " objects, fields, inheritance, and .NET Framework APIs. On the other side" &
                  " are tables, columns, rows, nodes, and separate languages for dealing with" &
                  " them. Data types often require translation between the two worlds; there are" &
                  " different standard functions. Because the object world has no notion of query, a" &
                  " query can only be represented as a string without compile-time type checking or" &
                  " IntelliSense support in the IDE. Transferring data from SQL tables or XML trees to" &
                  " objects in memory is often tedious and error-prone."

        Dim searchTerm As String = "data"

        ' Convert the string into an array of words.
        Dim dataSource As String() = text.Split(New Char() {" ", ",", ".", ";", ":"},
                                                 StringSplitOptions.RemoveEmptyEntries)

        ' Create and execute the query. It executes immediately
        ' because a singleton value is produced.
        ' Use ToLower to match "data" and "Data"
        Dim matchQuery = From word In dataSource
                      Where word.ToLowerInvariant() = searchTerm.ToLowerInvariant()
                      Select word

        ' Count the matches.
        Dim count As Integer = matchQuery.Count()
        Console.WriteLine(count & " occurrence(s) of the search term """ &
                          searchTerm & """ were found.")

        ' Keep console window open in debug mode.
        Console.WriteLine("Press any key to exit.")
        Console.ReadKey()
    End Sub
End Class
' Output:
' 3 occurrence(s) of the search term "data" were found.
```

## <a name="compiling-the-code"></a><span data-ttu-id="3790e-109">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="3790e-109">Compiling the Code</span></span>

<span data-ttu-id="3790e-110">Cree un proyecto de aplicación de consola de VB.NET con una instrucción `Imports` para el espacio de nombres System. Linq.</span><span class="sxs-lookup"><span data-stu-id="3790e-110">Create a VB.NET console application project, with an `Imports` statement for the System.Linq namespace.</span></span>

## <a name="see-also"></a><span data-ttu-id="3790e-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="3790e-111">See also</span></span>

- [<span data-ttu-id="3790e-112">LINQ y cadenas (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3790e-112">LINQ and Strings (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)
