---
title: 'Modificador extern: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- extern_CSharpKeyword
- extern
helpviewer_keywords:
- DllImport attribute
- extern keyword [C#]
ms.assetid: 9c3f02c4-51b8-4d80-9cb2-f2b6e1ae15c7
ms.openlocfilehash: 387ef707166705c4df501bd6740d438683aa2d69
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2019
ms.locfileid: "70203015"
---
# <a name="extern-c-reference"></a><span data-ttu-id="246f7-102">extern (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="246f7-102">extern (C# Reference)</span></span>

<span data-ttu-id="246f7-103">El modificador `extern` se usa para declarar un método que se implementa externamente.</span><span class="sxs-lookup"><span data-stu-id="246f7-103">The `extern` modifier is used to declare a method that is implemented externally.</span></span> <span data-ttu-id="246f7-104">Un uso común del modificador `extern` es con el atributo `DllImport` al usar servicios de interoperabilidad para llamar a código no administrado.</span><span class="sxs-lookup"><span data-stu-id="246f7-104">A common use of the `extern` modifier is with the `DllImport` attribute when you are using Interop services to call into unmanaged code.</span></span> <span data-ttu-id="246f7-105">En este caso, el método se debe declarar también como `static`, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="246f7-105">In this case, the method must also be declared as `static`, as shown in the following example:</span></span>

```csharp
[DllImport("avifil32.dll")]
private static extern void AVIFileInit();
```

<span data-ttu-id="246f7-106">La palabra clave `extern` también puede definir un alias del ensamblado externo, lo que permite hacer referencia a diferentes versiones del mismo componente desde un único ensamblado.</span><span class="sxs-lookup"><span data-stu-id="246f7-106">The `extern` keyword can also define an external assembly alias, which makes it possible to reference different versions of the same component from within a single assembly.</span></span> <span data-ttu-id="246f7-107">Para obtener más información, vea [alias externo](extern-alias.md).</span><span class="sxs-lookup"><span data-stu-id="246f7-107">For more information, see [extern alias](extern-alias.md).</span></span>

<span data-ttu-id="246f7-108">Es un error usar los modificadores [abstract](abstract.md) y `extern` juntos para modificar el mismo miembro.</span><span class="sxs-lookup"><span data-stu-id="246f7-108">It is an error to use the [abstract](abstract.md) and `extern` modifiers together to modify the same member.</span></span> <span data-ttu-id="246f7-109">El uso del modificador `extern` significa que el método se implementa fuera del código de C#, mientras que el uso del modificador `abstract` significa que la implementación del método no se proporciona en la clase.</span><span class="sxs-lookup"><span data-stu-id="246f7-109">Using the `extern` modifier means that the method is implemented outside the C# code, whereas using the `abstract` modifier means that the method implementation is not provided in the class.</span></span>

<span data-ttu-id="246f7-110">La palabra clave extern tiene usos más limitados en C# que en C++.</span><span class="sxs-lookup"><span data-stu-id="246f7-110">The extern keyword has more limited uses in C# than in C++.</span></span> <span data-ttu-id="246f7-111">Para comparar la palabra clave de C# con la de C++, consulte el tema sobre el uso de extern para especificar vinculación en la referencia del lenguaje C++.</span><span class="sxs-lookup"><span data-stu-id="246f7-111">To compare the C# keyword with the C++ keyword, see Using extern to Specify Linkage in the C++ Language Reference.</span></span>

## <a name="example-1"></a><span data-ttu-id="246f7-112">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="246f7-112">Example 1</span></span>

<span data-ttu-id="246f7-113">En este ejemplo, el programa recibe una cadena del usuario y la muestra en un cuadro de mensaje.</span><span class="sxs-lookup"><span data-stu-id="246f7-113">In this example, the program receives a string from the user and displays it inside a message box.</span></span> <span data-ttu-id="246f7-114">El programa usa el método `MessageBox` importado de la biblioteca User32.dll.</span><span class="sxs-lookup"><span data-stu-id="246f7-114">The program uses the `MessageBox` method imported from the User32.dll library.</span></span>

[!code-csharp[csrefKeywordsModifiers#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#8)]

## <a name="example-2"></a><span data-ttu-id="246f7-115">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="246f7-115">Example 2</span></span>

<span data-ttu-id="246f7-116">En este ejemplo se muestra un programa de C# que llama a una biblioteca de C (una DLL nativa).</span><span class="sxs-lookup"><span data-stu-id="246f7-116">This example illustrates a C# program that calls into a C library (a native DLL).</span></span>

1. <span data-ttu-id="246f7-117">Cree el archivo de C siguiente y denomínelo `cmdll.c`:</span><span class="sxs-lookup"><span data-stu-id="246f7-117">Create the following C file and name it `cmdll.c`:</span></span>

    ```c
    // cmdll.c
    // Compile with: -LD
    int __declspec(dllexport) SampleMethod(int i)
    {
      return i*10;
    }
    ```

2. <span data-ttu-id="246f7-118">Abra una ventana del símbolo del sistema de las herramientas nativas de Visual Studio x64 (o x32) desde el directorio de instalación de Visual Studio y compile el archivo `cmdll.c` escribiendo **cl -LD cmdll.c** en el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="246f7-118">Open a Visual Studio x64 (or x32) Native Tools Command Prompt window from the Visual Studio installation directory and compile the `cmdll.c` file by typing **cl -LD cmdll.c** at the command prompt.</span></span>

3. <span data-ttu-id="246f7-119">En el mismo directorio, cree el siguiente archivo de C# y denomínelo `cm.cs`:</span><span class="sxs-lookup"><span data-stu-id="246f7-119">In the same directory, create the following C# file and name it `cm.cs`:</span></span>

    ```csharp
    // cm.cs
    using System;
    using System.Runtime.InteropServices;
    public class MainClass
    {
        [DllImport("Cmdll.dll")]
          public static extern int SampleMethod(int x);

        static void Main()
        {
            Console.WriteLine("SampleMethod() returns {0}.", SampleMethod(5));
        }
    }
    ```

4. <span data-ttu-id="246f7-120">Abra una ventana del símbolo del sistema de las herramientas nativas de Visual Studio x64 (o x32) del directorio de instalación de Visual Studio y compile el archivo `cm.cs` escribiendo:</span><span class="sxs-lookup"><span data-stu-id="246f7-120">Open a Visual Studio x64 (or x32) Native Tools Command Prompt window from the Visual Studio installation directory and compile the `cm.cs` file by typing:</span></span>

    > <span data-ttu-id="246f7-121">**csc cm.cs** (para el símbolo del sistema x64), o bien **csc -platform:x86 cm.cs** (para el símbolo del sistema x32)</span><span class="sxs-lookup"><span data-stu-id="246f7-121">**csc cm.cs** (for the x64 command prompt) —or— **csc -platform:x86 cm.cs** (for the x32 command prompt)</span></span>

    <span data-ttu-id="246f7-122">De esta forma, se creará el archivo ejecutable `cm.exe`.</span><span class="sxs-lookup"><span data-stu-id="246f7-122">This will create the executable file `cm.exe`.</span></span>

5. <span data-ttu-id="246f7-123">Ejecute `cm.exe`.</span><span class="sxs-lookup"><span data-stu-id="246f7-123">Run `cm.exe`.</span></span> <span data-ttu-id="246f7-124">El método `SampleMethod` pasa el valor 5 al archivo DLL, que devuelve el valor multiplicado por 10.</span><span class="sxs-lookup"><span data-stu-id="246f7-124">The `SampleMethod` method passes the value 5 to the DLL file, which returns the value multiplied by 10.</span></span>  <span data-ttu-id="246f7-125">El programa produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="246f7-125">The program produces the following output:</span></span>

    ```output
    SampleMethod() returns 50.
    ```

## <a name="c-language-specification"></a><span data-ttu-id="246f7-126">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="246f7-126">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="246f7-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="246f7-127">See also</span></span>

- <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=nameWithType>
- [<span data-ttu-id="246f7-128">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="246f7-128">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="246f7-129">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="246f7-129">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="246f7-130">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="246f7-130">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="246f7-131">Modificadores</span><span class="sxs-lookup"><span data-stu-id="246f7-131">Modifiers</span></span>](modifiers.md)
