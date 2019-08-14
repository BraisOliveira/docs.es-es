---
title: Ensamblados de confianza (C#)
ms.date: 03/03/2019
ms.assetid: b65ea7de-0801-477a-a39c-e914c2cc107c
ms.openlocfilehash: 770eb70a5350d7d26e03cb4e605b442100da2a53
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "68671200"
---
# <a name="friend-assemblies"></a><span data-ttu-id="d838c-102">Ensamblados de confianza</span><span class="sxs-lookup"><span data-stu-id="d838c-102">Friend assemblies</span></span>

<span data-ttu-id="d838c-103">Un *ensamblado de confianza* puede acceder a los tipos y miembros [internal](../../csharp/language-reference/keywords/internal.md) de otro ensamblado (en C# o [Friend](../../visual-basic/language-reference/modifiers/friend.md) en Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="d838c-103">A *friend assembly* is an assembly that can access another assembly's [internal](../../csharp/language-reference/keywords/internal.md) (in C# or [Friend](../../visual-basic/language-reference/modifiers/friend.md) in Visual Basic) types and members.</span></span> <span data-ttu-id="d838c-104">Si identifica un ensamblado como ensamblado de confianza, ya no hay que marcar los tipos y miembros como públicos para que otros ensamblados accedan a ellos.</span><span class="sxs-lookup"><span data-stu-id="d838c-104">If you identify an assembly as a friend assembly, you no longer have to mark types and members as public in order for them to be accessed by other assemblies.</span></span> <span data-ttu-id="d838c-105">Esto resulta especialmente útil en los siguientes escenarios:</span><span class="sxs-lookup"><span data-stu-id="d838c-105">This is especially convenient in the following scenarios:</span></span>

- <span data-ttu-id="d838c-106">Durante las pruebas unitarias, cuando se ejecuta código de prueba en un ensamblado independiente que requiere acceso a miembros del ensamblado en pruebas marcados como `internal` en C# o `Friend` en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="d838c-106">During unit testing, when test code runs in a separate assembly but requires access to members in the assembly being tested that are marked as `internal` in C# or `Friend` in Visual Basic.</span></span>

- <span data-ttu-id="d838c-107">Cuando desarrolla una biblioteca de clases y las adiciones a la biblioteca se incluyen en ensamblados independientes que requieren acceso a miembros de ensamblados existentes marcados como `internal` en C# o `Friend` en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="d838c-107">When you are developing a class library and additions to the library are contained in separate assemblies but require access to members in existing assemblies that are marked as `internal` in C# or `Friend` in Visual Basic.</span></span>

## <a name="remarks"></a><span data-ttu-id="d838c-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d838c-108">Remarks</span></span>

<span data-ttu-id="d838c-109">Puede usar el atributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> para identificar uno o más ensamblados de confianza para un ensamblado determinado.</span><span class="sxs-lookup"><span data-stu-id="d838c-109">You can use the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute to identify one or more friend assemblies for a given assembly.</span></span> <span data-ttu-id="d838c-110">En el ejemplo siguiente se usa el atributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> en el ensamblado A y se especifica el ensamblado `AssemblyB` como un ensamblado de confianza.</span><span class="sxs-lookup"><span data-stu-id="d838c-110">The following example uses the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute in assembly A and specifies assembly `AssemblyB` as a friend assembly.</span></span> <span data-ttu-id="d838c-111">Esto proporciona al ensamblado `AssemblyB` acceso a todos los tipos y miembros del ensamblado A marcados como `internal` en C# o `Friend` en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="d838c-111">This gives assembly `AssemblyB` access to all types and members in assembly A that are marked as `internal` in C# or `Friend` in Visual Basic.</span></span>

> [!NOTE]
> <span data-ttu-id="d838c-112">Cuando se compila un ensamblado (ensamblado `AssemblyB`) que accederá a tipos o miembros internos de otro ensamblado (ensamblado *A*), hay que especificar explícitamente el nombre del archivo de salida (.exe o .dll) mediante la opción **/out** del compilador.</span><span class="sxs-lookup"><span data-stu-id="d838c-112">When you compile an assembly (assembly `AssemblyB`) that will access internal types or internal members of another assembly (assembly *A*), you must explicitly specify the name of the output file (.exe or .dll) by using the **/out** compiler option.</span></span> <span data-ttu-id="d838c-113">Esto es necesario porque el compilador no ha generado aún el nombre del ensamblado que está creando en el momento en que se enlaza a referencias externas.</span><span class="sxs-lookup"><span data-stu-id="d838c-113">This is required because the compiler has not yet generated the name for the assembly it is building at the time it is binding to external references.</span></span> <span data-ttu-id="d838c-114">Para más información, consulte [/out (C#)](../../csharp/language-reference/compiler-options/out-compiler-option.md) o [/out (Visual Basic)](../../visual-basic/reference/command-line-compiler/out.md).</span><span class="sxs-lookup"><span data-stu-id="d838c-114">For more information, see [/out (C#)](../../csharp/language-reference/compiler-options/out-compiler-option.md) or [/out (Visual Basic)](../../visual-basic/reference/command-line-compiler/out.md).</span></span>

# <a name="ctabcsharp"></a>[<span data-ttu-id="d838c-115">C#</span><span class="sxs-lookup"><span data-stu-id="d838c-115">C#</span></span>](#tab/csharp)

```csharp
using System.Runtime.CompilerServices;
using System;

[assembly: InternalsVisibleTo("AssemblyB")]

// The class is internal by default.
class FriendClass
{
    public void Test()
    {
        Console.WriteLine("Sample Class");
    }
}

// Public class that has an internal method.
public class ClassWithFriendMethod
{
    internal void Test()
    {
        Console.WriteLine("Sample Method");
    }

}
```

# <a name="visual-basictabvb"></a>[<span data-ttu-id="d838c-116">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d838c-116">Visual Basic</span></span>](#tab/vb)

```vb
Imports System.Runtime.CompilerServices
Imports System
<Assembly: InternalsVisibleTo("AssemblyB")>

' Friend class.
Friend Class FriendClass
    Public Sub Test()
        Console.WriteLine("Sample Class")
    End Sub
End Class

' Public class with a Friend method.
Public Class ClassWithFriendMethod
    Friend Sub Test()
        Console.WriteLine("Sample Method")
    End Sub
End Class
```

---

<span data-ttu-id="d838c-117">Solo los ensamblados que se especifiquen explícitamente como de confianza pueden acceder a tipos y miembros `internal` (en C# o `Friend` en Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="d838c-117">Only assemblies that you explicitly specify as friends can access `internal` (in C# or `Friend` in Visual Basic) types and members.</span></span> <span data-ttu-id="d838c-118">Por ejemplo, si el ensamblado B es de confianza para el ensamblado A y el ensamblado C hace referencia al ensamblado B, C no tiene acceso a tipos `internal` (en C# o `Friend` en Visual Basic) en A.</span><span class="sxs-lookup"><span data-stu-id="d838c-118">For example, if assembly B is a friend of assembly A and assembly C references assembly B, C does not have access to `internal` (in C# or `Friend` in Visual Basic) types in A.</span></span>

<span data-ttu-id="d838c-119">El compilador realiza una validación básica del nombre del ensamblado de confianza que se ha pasado al atributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>.</span><span class="sxs-lookup"><span data-stu-id="d838c-119">The compiler performs some basic validation of the friend assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute.</span></span> <span data-ttu-id="d838c-120">Si el ensamblado *A* declara a *B* como ensamblado de confianza, las reglas de validación son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="d838c-120">If assembly *A* declares *B* as a friend assembly, the validation rules are as follows:</span></span>

- <span data-ttu-id="d838c-121">Si el ensamblado *A* tiene un nombre seguro, el ensamblado *B* también deben tener un nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="d838c-121">If assembly *A* is strong named, assembly *B* must also be strong named.</span></span> <span data-ttu-id="d838c-122">El nombre de ensamblado de confianza que se pasa al atributo debe estar formado por el nombre del ensamblado y la clave pública de la clave de nombre seguro que se usa para firmar el ensamblado *B*.</span><span class="sxs-lookup"><span data-stu-id="d838c-122">The friend assembly name that is passed to the attribute must consist of the assembly name and the public key of the strong-name key that is used to sign assembly *B*.</span></span>

     <span data-ttu-id="d838c-123">El nombre de ensamblado de confianza que se pasa al atributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> no puede ser el nombre seguro del ensamblado *B*: no se incluyen la versión del ensamblado, la referencia cultural, la arquitectura o el token de clave pública.</span><span class="sxs-lookup"><span data-stu-id="d838c-123">The friend assembly name that is passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute cannot be the strong name of assembly *B*: do not include the assembly version, culture, architecture, or public key token.</span></span>

- <span data-ttu-id="d838c-124">Si el ensamblado *A* no tiene nombre seguro, el nombre de ensamblado de confianza solo debe consistir en el nombre del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d838c-124">If assembly *A* is not strong named, the friend assembly name should consist of only the assembly name.</span></span> <span data-ttu-id="d838c-125">Para obtener más información, vea [Cómo: Procedimiento Crear ensamblados de confianza sin firmar (C#)](../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md) o [Procedimiento Crear ensamblados de confianza sin firmar (Visual Basic)](../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="d838c-125">For more information, see [How to: Create Unsigned Friend Assemblies (C#)](../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md) or [How to: Create Unsigned Friend Assemblies (Visual Basic)](../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md).</span></span>

- <span data-ttu-id="d838c-126">Si el ensamblado *B* tiene nombre seguro, hay que especificar la clave de nombre seguro del ensamblado *B* mediante la configuración del proyecto o la opción `/keyfile` de línea de comandos del compilador.</span><span class="sxs-lookup"><span data-stu-id="d838c-126">If assembly *B* is strong named, you must specify the strong-name key for assembly *B* by using the project setting or the command-line `/keyfile` compiler option.</span></span> <span data-ttu-id="d838c-127">Para obtener más información, vea [Cómo: Procedimiento Crear ensamblados de confianza firmados (C#)](../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md) o [Procedimiento Crear ensamblados de confianza firmados (Visual Basic)](../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="d838c-127">For more information, see [How to: Create Signed Friend Assemblies (C#)](../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md) or [How to: Create Signed Friend Assemblies (Visual Basic)](../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md).</span></span>

 <span data-ttu-id="d838c-128">La clase <xref:System.Security.Permissions.StrongNameIdentityPermission> también proporciona la capacidad de compartir tipos, con las siguientes diferencias:</span><span class="sxs-lookup"><span data-stu-id="d838c-128">The <xref:System.Security.Permissions.StrongNameIdentityPermission> class also provides the ability to share types, with the following differences:</span></span>

- <span data-ttu-id="d838c-129"><xref:System.Security.Permissions.StrongNameIdentityPermission> se aplica a un tipo individual, mientras que un ensamblado de confianza se aplica al ensamblado completo.</span><span class="sxs-lookup"><span data-stu-id="d838c-129"><xref:System.Security.Permissions.StrongNameIdentityPermission> applies to an individual type, while a friend assembly applies to the whole assembly.</span></span>

- <span data-ttu-id="d838c-130">Si hay cientos de tipos en el ensamblado *A* que quiere compartir con el ensamblado *B*, tiene que agregarles <xref:System.Security.Permissions.StrongNameIdentityPermission> a todos.</span><span class="sxs-lookup"><span data-stu-id="d838c-130">If there are hundreds of types in assembly *A* that you want to share with assembly *B*, you have to add <xref:System.Security.Permissions.StrongNameIdentityPermission> to all of them.</span></span> <span data-ttu-id="d838c-131">Si usa un ensamblado de confianza, solo tiene que declarar una vez la relación de confianza.</span><span class="sxs-lookup"><span data-stu-id="d838c-131">If you use a friend assembly, you only need to declare the friend relationship once.</span></span>

- <span data-ttu-id="d838c-132">Si usa <xref:System.Security.Permissions.StrongNameIdentityPermission>, los tipos que quiere compartir tienen que declararse como públicos.</span><span class="sxs-lookup"><span data-stu-id="d838c-132">If you use <xref:System.Security.Permissions.StrongNameIdentityPermission>, the types you want to share have to be declared as public.</span></span> <span data-ttu-id="d838c-133">Si usa un ensamblado de confianza, los tipos compartidos se declaran como `internal` (en C# o `Friend` en Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="d838c-133">If you use a friend assembly, the shared types are declared as `internal` (in C# or `Friend` in Visual Basic).</span></span>

<span data-ttu-id="d838c-134">Para información sobre cómo acceder a los tipos y métodos `internal` (en C# o `Friend` en Visual Basic) de un ensamblado desde un archivo de módulo (un archivo con la extensión .netmodule), consulte [/moduleassemblyname (C#)](../../csharp/language-reference/compiler-options/moduleassemblyname-compiler-option.md) o [/moduleassemblyname (Visual Basic)](../../visual-basic/reference/command-line-compiler/moduleassemblyname.md).</span><span class="sxs-lookup"><span data-stu-id="d838c-134">For information about how to access an assembly's `internal` (in C# or `Friend` in Visual Basic) types and methods from a module file (a file with the .netmodule extension), see [/moduleassemblyname (C#)](../../csharp/language-reference/compiler-options/moduleassemblyname-compiler-option.md) or [/moduleassemblyname (Visual Basic)](../../visual-basic/reference/command-line-compiler/moduleassemblyname.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d838c-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="d838c-135">See also</span></span>

- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- <xref:System.Security.Permissions.StrongNameIdentityPermission>
- [<span data-ttu-id="d838c-136">Cómo: Crear ensamblados de confianza sin firmar (C#)</span><span class="sxs-lookup"><span data-stu-id="d838c-136">How to: Create Unsigned Friend Assemblies (C#)</span></span>](../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md)
- [<span data-ttu-id="d838c-137">Cómo: Crear ensamblados de confianza sin firmar (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d838c-137">How to: Create Unsigned Friend Assemblies (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md)
- [<span data-ttu-id="d838c-138">Cómo: Crear ensamblados de confianza firmados (C#)</span><span class="sxs-lookup"><span data-stu-id="d838c-138">How to: Create Signed Friend Assemblies (C#)</span></span>](../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md)
- [<span data-ttu-id="d838c-139">Cómo: Crear ensamblados de confianza firmados (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d838c-139">How to: Create Signed Friend Assemblies (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md)
- [<span data-ttu-id="d838c-140">Ensamblados de .NET</span><span class="sxs-lookup"><span data-stu-id="d838c-140">Assemblies in .NET</span></span>](index.md)
- [<span data-ttu-id="d838c-141">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="d838c-141">C# Programming Guide</span></span>](../../csharp/programming-guide/index.md)
- [<span data-ttu-id="d838c-142">Conceptos de programación</span><span class="sxs-lookup"><span data-stu-id="d838c-142">Programming Concepts</span></span>](../../visual-basic/programming-guide/concepts/index.md)
