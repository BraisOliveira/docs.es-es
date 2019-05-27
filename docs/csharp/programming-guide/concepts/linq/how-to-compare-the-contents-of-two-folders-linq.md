---
title: Procedimiento para comparar el contenido de dos carpetas (LINQ) (C#)
ms.date: 07/20/2015
ms.assetid: c7c4870e-c500-4de3-afa4-2c8e07f510e6
ms.openlocfilehash: 5d944025d8d442bb80c492d1898487dff88c5bc1
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2019
ms.locfileid: "65585919"
---
# <a name="how-to-compare-the-contents-of-two-folders-linq-c"></a><span data-ttu-id="12e1b-102">Procedimiento para comparar el contenido de dos carpetas (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="12e1b-102">How to: Compare the Contents of Two Folders (LINQ) (C#)</span></span>
<span data-ttu-id="12e1b-103">En este ejemplo se muestran tres maneras de comparar dos listados de archivos:</span><span class="sxs-lookup"><span data-stu-id="12e1b-103">This example demonstrates three ways to compare two file listings:</span></span>  
  
- <span data-ttu-id="12e1b-104">Mediante la consulta de un valor booleano que especifica si las dos listas de archivos son idénticas.</span><span class="sxs-lookup"><span data-stu-id="12e1b-104">By querying for a Boolean value that specifies whether the two file lists are identical.</span></span>  
  
- <span data-ttu-id="12e1b-105">Mediante la consulta de la intersección para recuperar los archivos que están en ambas carpetas.</span><span class="sxs-lookup"><span data-stu-id="12e1b-105">By querying for the intersection to retrieve the files that are in both folders.</span></span>  
  
- <span data-ttu-id="12e1b-106">Mediante la consulta de la diferencia de conjuntos para recuperar los archivos que se encuentran en una carpeta, pero no en la otra.</span><span class="sxs-lookup"><span data-stu-id="12e1b-106">By querying for the set difference to retrieve the files that are in one folder but not the other.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="12e1b-107">Las técnicas que se mencionan aquí pueden adaptarse para comparar secuencias de objetos de cualquier tipo.</span><span class="sxs-lookup"><span data-stu-id="12e1b-107">The techniques shown here can be adapted to compare sequences of objects of any type.</span></span>  
  
 <span data-ttu-id="12e1b-108">La clase `FileComparer` que aparece a continuación muestra cómo usar una clase de comparador personalizada junto con los operadores de consulta estándar.</span><span class="sxs-lookup"><span data-stu-id="12e1b-108">The `FileComparer` class shown here demonstrates how to use a custom comparer class together with the Standard Query Operators.</span></span> <span data-ttu-id="12e1b-109">La clase no está diseñada para su uso en escenarios reales.</span><span class="sxs-lookup"><span data-stu-id="12e1b-109">The class is not intended for use in real-world scenarios.</span></span> <span data-ttu-id="12e1b-110">Simplemente usa el nombre y la longitud en bytes de cada archivo para determinar si el contenido de cada una de las carpetas es idéntico o no.</span><span class="sxs-lookup"><span data-stu-id="12e1b-110">It just uses the name and length in bytes of each file to determine whether the contents of each folder are identical or not.</span></span> <span data-ttu-id="12e1b-111">En un escenario real, debería modificar este comparador para realizar una comprobación de igualdad más rigurosa.</span><span class="sxs-lookup"><span data-stu-id="12e1b-111">In a real-world scenario, you should modify this comparer to perform a more rigorous equality check.</span></span>  
  
## <a name="example"></a><span data-ttu-id="12e1b-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="12e1b-112">Example</span></span>  
  
```csharp  
namespace QueryCompareTwoDirs  
{  
    class CompareDirs  
    {  
  
        static void Main(string[] args)  
        {  
  
            // Create two identical or different temporary folders   
            // on a local drive and change these file paths.  
            string pathA = @"C:\TestDir";  
            string pathB = @"C:\TestDir2";  
  
            System.IO.DirectoryInfo dir1 = new System.IO.DirectoryInfo(pathA);  
            System.IO.DirectoryInfo dir2 = new System.IO.DirectoryInfo(pathB);  
  
            // Take a snapshot of the file system.  
            IEnumerable<System.IO.FileInfo> list1 = dir1.GetFiles("*.*", System.IO.SearchOption.AllDirectories);  
            IEnumerable<System.IO.FileInfo> list2 = dir2.GetFiles("*.*", System.IO.SearchOption.AllDirectories);  
  
            //A custom file comparer defined below  
            FileCompare myFileCompare = new FileCompare();  
  
            // This query determines whether the two folders contain  
            // identical file lists, based on the custom file comparer  
            // that is defined in the FileCompare class.  
            // The query executes immediately because it returns a bool.  
            bool areIdentical = list1.SequenceEqual(list2, myFileCompare);  
  
            if (areIdentical == true)  
            {  
                Console.WriteLine("the two folders are the same");  
            }  
            else  
            {  
                Console.WriteLine("The two folders are not the same");  
            }  
  
            // Find the common files. It produces a sequence and doesn't   
            // execute until the foreach statement.  
            var queryCommonFiles = list1.Intersect(list2, myFileCompare);  
  
            if (queryCommonFiles.Count() > 0)  
            {  
                Console.WriteLine("The following files are in both folders:");  
                foreach (var v in queryCommonFiles)  
                {  
                    Console.WriteLine(v.FullName); //shows which items end up in result list  
                }  
            }  
            else  
            {  
                Console.WriteLine("There are no common files in the two folders.");  
            }  
  
            // Find the set difference between the two folders.  
            // For this example we only check one way.  
            var queryList1Only = (from file in list1  
                                  select file).Except(list2, myFileCompare);  
  
            Console.WriteLine("The following files are in list1 but not list2:");  
            foreach (var v in queryList1Only)  
            {  
                Console.WriteLine(v.FullName);  
            }  
  
            // Keep the console window open in debug mode.  
            Console.WriteLine("Press any key to exit.");  
            Console.ReadKey();  
        }  
    }  
  
    // This implementation defines a very simple comparison  
    // between two FileInfo objects. It only compares the name  
    // of the files being compared and their length in bytes.  
    class FileCompare : System.Collections.Generic.IEqualityComparer<System.IO.FileInfo>  
    {  
        public FileCompare() { }  
  
        public bool Equals(System.IO.FileInfo f1, System.IO.FileInfo f2)  
        {  
            return (f1.Name == f2.Name &&  
                    f1.Length == f2.Length);  
        }  
  
        // Return a hash that reflects the comparison criteria. According to the   
        // rules for IEqualityComparer<T>, if Equals is true, then the hash codes must  
        // also be equal. Because equality as defined here is a simple value equality, not  
        // reference identity, it is possible that two or more objects will produce the same  
        // hash code.  
        public int GetHashCode(System.IO.FileInfo fi)  
        {  
            string s = $"{fi.Name}{fi.Length}";
            return s.GetHashCode();  
        }  
    }  
}  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="12e1b-113">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="12e1b-113">Compiling the Code</span></span>  
 <span data-ttu-id="12e1b-114">Cree un proyecto de aplicación de consola de C# con directivas `using` para los espacios de nombres System.Linq y System.IO.</span><span class="sxs-lookup"><span data-stu-id="12e1b-114">Create a C# console application project, with `using` directives for the System.Linq and System.IO namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12e1b-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="12e1b-115">See also</span></span>

- [<span data-ttu-id="12e1b-116">LINQ to Objects (C#)</span><span class="sxs-lookup"><span data-stu-id="12e1b-116">LINQ to Objects (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-objects.md)
- [<span data-ttu-id="12e1b-117">LINQ y directorios de archivos (C#)</span><span class="sxs-lookup"><span data-stu-id="12e1b-117">LINQ and File Directories (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-and-file-directories.md)
