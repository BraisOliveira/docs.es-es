---
title: 'Interoperabilidad: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- COM interop
- interoperability
- platform invoke, accessing APIs with C#
- C# language, interoperability
ms.assetid: 238bb95a-e962-4026-bbd5-197055bdb8ee
ms.openlocfilehash: 50f2a72bf4981a49d5597a9bc8922db81197d810
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61710230"
---
# <a name="interoperability-c-programming-guide"></a><span data-ttu-id="f53ff-102">Interoperabilidad (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="f53ff-102">Interoperability (C# Programming Guide)</span></span>
<span data-ttu-id="f53ff-103">La interoperabilidad permite conservar y aprovechar las inversiones existentes en código no administrado.</span><span class="sxs-lookup"><span data-stu-id="f53ff-103">Interoperability enables you to preserve and take advantage of existing investments in unmanaged code.</span></span> <span data-ttu-id="f53ff-104">El código que se ejecuta bajo el control de Common Language Runtime (CLR) se denomina *código administrado*, y el código que se ejecuta fuera de CLR se denomina *código no administrado*.</span><span class="sxs-lookup"><span data-stu-id="f53ff-104">Code that runs under the control of the common language runtime (CLR) is called *managed code*, and code that runs outside the CLR is called *unmanaged code*.</span></span> <span data-ttu-id="f53ff-105">COM, COM+, los componentes de C++, los componentes de ActiveX y la API Windows de Microsoft son ejemplos de código no administrado.</span><span class="sxs-lookup"><span data-stu-id="f53ff-105">COM, COM+, C++ components, ActiveX components, and Microsoft Windows API are examples of unmanaged code.</span></span>  
  
 <span data-ttu-id="f53ff-106">[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] habilita la interoperabilidad con código no administrado a través de los servicios de invocación de plataforma, el espacio de nombres <xref:System.Runtime.InteropServices>, la interoperabilidad de C++ y la interoperabilidad COM.</span><span class="sxs-lookup"><span data-stu-id="f53ff-106">The [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] enables interoperability with unmanaged code through platform invoke services, the <xref:System.Runtime.InteropServices> namespace, C++ interoperability, and COM interoperability (COM interop).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f53ff-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="f53ff-107">In This Section</span></span>  
 [<span data-ttu-id="f53ff-108">Información general sobre interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="f53ff-108">Interoperability Overview</span></span>](../../../csharp/programming-guide/interop/interoperability-overview.md)  
 <span data-ttu-id="f53ff-109">Se describen métodos para habilitar la interoperabilidad entre el código administrado y el código no administrado de C#.</span><span class="sxs-lookup"><span data-stu-id="f53ff-109">Describes methods to interoperate between C# managed code and unmanaged code.</span></span>  
  
 [<span data-ttu-id="f53ff-110">Cómo: Tener acceso a objetos de interoperabilidad de Office mediante las características de Visual C#</span><span class="sxs-lookup"><span data-stu-id="f53ff-110">How to: Access Office Interop Objects by Using Visual C# Features</span></span>](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md)  
 <span data-ttu-id="f53ff-111">Describe las características introducidas en Visual C# para facilitar la programación de Office.</span><span class="sxs-lookup"><span data-stu-id="f53ff-111">Describes features that are introduced in Visual C# to facilitate Office programming.</span></span>  
  
 [<span data-ttu-id="f53ff-112">Cómo: Utilizar propiedades indizadas en la programación de interoperabilidad COM</span><span class="sxs-lookup"><span data-stu-id="f53ff-112">How to: Use Indexed Properties in COM Interop Programming</span></span>](../../../csharp/programming-guide/interop/how-to-use-indexed-properties-in-com-interop-rogramming.md)  
 <span data-ttu-id="f53ff-113">Se describe cómo utilizar las propiedades indizadas para acceder a las propiedades de COM que tienen parámetros.</span><span class="sxs-lookup"><span data-stu-id="f53ff-113">Describes how to use indexed properties to access COM properties that have parameters.</span></span>  
  
 [<span data-ttu-id="f53ff-114">Cómo: Utilizar la invocación de plataforma para reproducir un archivo de sonido</span><span class="sxs-lookup"><span data-stu-id="f53ff-114">How to: Use Platform Invoke to Play a Wave File</span></span>](../../../csharp/programming-guide/interop/how-to-use-platform-invoke-to-play-a-wave-file.md)  
 <span data-ttu-id="f53ff-115">Se describe cómo usar los servicios de invocación de plataforma para reproducir un archivo de sonido .wav en el sistema operativo Windows.</span><span class="sxs-lookup"><span data-stu-id="f53ff-115">Describes how to use platform invoke services to play a .wav sound file on the Windows operating system.</span></span>  
  
 [<span data-ttu-id="f53ff-116">Tutorial: Programación de Office</span><span class="sxs-lookup"><span data-stu-id="f53ff-116">Walkthrough: Office Programming</span></span>](../../../csharp/programming-guide/interop/walkthrough-office-programming.md)  
 <span data-ttu-id="f53ff-117">Muestra cómo crear un libro de Excel y un documento de Word que contiene un vínculo al libro.</span><span class="sxs-lookup"><span data-stu-id="f53ff-117">Shows how to create an Excel workbook and a Word document that contains a link to the workbook.</span></span>  
  
 [<span data-ttu-id="f53ff-118">Clase COM de ejemplo</span><span class="sxs-lookup"><span data-stu-id="f53ff-118">Example COM Class</span></span>](../../../csharp/programming-guide/interop/example-com-class.md)  
 <span data-ttu-id="f53ff-119">Muestra cómo exponer una clase de C# como un objeto COM.</span><span class="sxs-lookup"><span data-stu-id="f53ff-119">Demonstrates how to expose a C# class as a COM object.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="f53ff-120">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="f53ff-120">C# Language Specification</span></span>  

<span data-ttu-id="f53ff-121">Para obtener más información, consulte la sección [Conceptos básicos](~/_csharplang/spec/unsafe-code.md) de [Especificación del lenguaje C#](../../language-reference/language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="f53ff-121">For more information, see [Basic concepts](~/_csharplang/spec/unsafe-code.md) in the [C# Language Specification](../../language-reference/language-specification/index.md).</span></span> <span data-ttu-id="f53ff-122">La especificación del lenguaje es la fuente definitiva de la sintaxis y el uso de C#.</span><span class="sxs-lookup"><span data-stu-id="f53ff-122">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f53ff-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="f53ff-123">See also</span></span>

- <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A?displayProperty=nameWithType>
- [<span data-ttu-id="f53ff-124">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="f53ff-124">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- <span data-ttu-id="f53ff-125">[Interoperating with Unmanaged Code](../../../../docs/framework/interop/index.md) (Interoperar con código no administrado)</span><span class="sxs-lookup"><span data-stu-id="f53ff-125">[Interoperating with Unmanaged Code](../../../../docs/framework/interop/index.md)</span></span>
- [<span data-ttu-id="f53ff-126">Tutorial: Programación de Office</span><span class="sxs-lookup"><span data-stu-id="f53ff-126">Walkthrough: Office Programming</span></span>](../../../csharp/programming-guide/interop/walkthrough-office-programming.md)
