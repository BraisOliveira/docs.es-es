---
title: MDA de jitCompilationStart
ms.date: 03/30/2017
helpviewer_keywords:
- JIT compilation
- MDAs (managed debugging assistants), JIT compilation
- JitCompilationStart MDA
- managed debugging assistants (MDAs), JIT compilation
ms.assetid: 5ffd2857-d0ba-4342-9824-9ffe04ec135d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 62064286fecc4736f39ad790f0fd7f0e6d84b149
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59162350"
---
# <a name="jitcompilationstart-mda"></a><span data-ttu-id="18e8f-102">MDA de jitCompilationStart</span><span class="sxs-lookup"><span data-stu-id="18e8f-102">jitCompilationStart MDA</span></span>
<span data-ttu-id="18e8f-103">El Asistente para la depuración administrada (MDA) `jitCompilationStart` se activa para informar del momento en el que el compilador Just-In-Time (JIT) empieza a compilar una función.</span><span class="sxs-lookup"><span data-stu-id="18e8f-103">The `jitCompilationStart` managed debugging assistant (MDA) is activated to report when the just-in-time (JIT) compiler starts to compile a function.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="18e8f-104">Síntomas</span><span class="sxs-lookup"><span data-stu-id="18e8f-104">Symptoms</span></span>  
 <span data-ttu-id="18e8f-105">El conjunto de trabajo aumenta de tamaño para un programa que ya está en formato de imagen nativo porque mscorjit.dll se carga en el proceso.</span><span class="sxs-lookup"><span data-stu-id="18e8f-105">The working set size increases for a program that is already in native image format because mscorjit.dll is loaded into the process.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="18e8f-106">Motivo</span><span class="sxs-lookup"><span data-stu-id="18e8f-106">Cause</span></span>  
 <span data-ttu-id="18e8f-107">No todos los ensamblados de los que depende el programa se han generado en formato nativo o los que sí se han generado no están registrados correctamente.</span><span class="sxs-lookup"><span data-stu-id="18e8f-107">Not all the assemblies the program depends on have been generated into native format, or those that have are not registered correctly.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="18e8f-108">Resolución</span><span class="sxs-lookup"><span data-stu-id="18e8f-108">Resolution</span></span>  
 <span data-ttu-id="18e8f-109">Al habilitar este MDA, puede determinar qué función va a ser compilada mediante JIT.</span><span class="sxs-lookup"><span data-stu-id="18e8f-109">Enabling this MDA allows you to determine which function is being JIT-compiled.</span></span> <span data-ttu-id="18e8f-110">Determine si el ensamblado que contiene la función se genera en formato nativo y se registra correctamente.</span><span class="sxs-lookup"><span data-stu-id="18e8f-110">Determine whether the assembly that contains the function is generated to native format and properly registered.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="18e8f-111">Efecto en el Runtime</span><span class="sxs-lookup"><span data-stu-id="18e8f-111">Effect on the Runtime</span></span>  
 <span data-ttu-id="18e8f-112">Este MDA registra un mensaje justo antes de que un método se compile con JIT, por lo que habilitar este MDA tiene un impacto significativo en el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="18e8f-112">This MDA logs a message just before a method is JIT-compiled, so enabling this MDA has significant impact on performance.</span></span> <span data-ttu-id="18e8f-113">Tenga en cuenta que si un método está en línea, este MDA no generará un mensaje independiente.</span><span class="sxs-lookup"><span data-stu-id="18e8f-113">Note that if a method is inline, this MDA will not generate a separate message.</span></span>  
  
## <a name="output"></a><span data-ttu-id="18e8f-114">Salida</span><span class="sxs-lookup"><span data-stu-id="18e8f-114">Output</span></span>  
 <span data-ttu-id="18e8f-115">En el ejemplo de código siguiente se muestran los resultados del ejemplo.</span><span class="sxs-lookup"><span data-stu-id="18e8f-115">The following code sample shows sample output.</span></span> <span data-ttu-id="18e8f-116">En este caso, el resultado muestra que en el ensamblado Test el método "m" de la clase "ns2.CO" se compiló con JIT.</span><span class="sxs-lookup"><span data-stu-id="18e8f-116">In this case the output shows that in assembly Test the method "m" on class "ns2.CO" was JIT-compiled.</span></span>  
  
```  
method name="Test!ns2.C0::m"  
```  
  
## <a name="configuration"></a><span data-ttu-id="18e8f-117">Configuración</span><span class="sxs-lookup"><span data-stu-id="18e8f-117">Configuration</span></span>  
 <span data-ttu-id="18e8f-118">En el archivo de configuración siguiente se muestra una variedad de filtros que se pueden emplear para filtrar qué métodos se notifican cuando se compilan con JIT por primera vez.</span><span class="sxs-lookup"><span data-stu-id="18e8f-118">The following configuration file shows a variety of filters that can be employed to filter out which methods are reported when they are first JIT-compiled.</span></span> <span data-ttu-id="18e8f-119">Puede especificar que se le facturen todos los métodos estableciendo el valor del atributo name a \*.</span><span class="sxs-lookup"><span data-stu-id="18e8f-119">You can specify that all methods be reported by setting the value of the name attribute to \*.</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <jitCompilationStart>  
      <methods>  
        <match name="C0::m" />  
        <match name="MyMethod" />  
        <match name="C2::*" />  
        <match name="ns0::*" />  
        <match name="ns1.C0::*" />  
        <match name="ns2.C0::m" />  
        <match name="ns2.C0+N0::m" />  
      </methods>  
    </jitCompilationStart >  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a><span data-ttu-id="18e8f-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="18e8f-120">Example</span></span>  
 <span data-ttu-id="18e8f-121">El ejemplo de código siguiente está pensado para usarse con el archivo de configuración anterior.</span><span class="sxs-lookup"><span data-stu-id="18e8f-121">The following code sample is intended to be used with the preceding configuration file.</span></span>  
  
```csharp
using System;  
using System.Reflection;  
using System.Runtime.CompilerServices;  
using System.Runtime.InteropServices;  
  
public class Entry  
{  
    public static void Main(string[] args)  
    {  
        C0.m();  
        C1.MyMethod();  
        C2.m();  
  
        ns0.C0.m();  
        ns0.C0.N0.m();  
        ns0.C1.m();  
  
        ns1.C0.m();  
        ns1.C0.N0.m();  
  
        ns2.C0.m();  
        ns2.C0.N0.m();  
    }  
}  
  
public class C0  
{  
    [MethodImpl(MethodImplOptions.NoInlining)]  
    public static void m() { }  
}  
  
public class C1  
{  
    [MethodImpl(MethodImplOptions.NoInlining)]  
    public static void MyMethod() { }  
}  
  
public class C2  
{  
    [MethodImpl(MethodImplOptions.NoInlining)]  
    public static void m() { }  
}  
  
namespace ns0  
{  
    public class C0  
    {  
        [MethodImpl(MethodImplOptions.NoInlining)]  
        public static void m() { }  
  
        public class N0  
        {  
            [MethodImpl(MethodImplOptions.NoInlining)]  
            public static void m() { }  
        }  
    }  
  
    public class C1  
    {  
        [MethodImpl(MethodImplOptions.NoInlining)]  
        public static void m() { }  
    }  
}  
  
namespace ns1  
{  
    public class C0  
    {  
        [MethodImpl(MethodImplOptions.NoInlining)]  
        public static void m() { }  
        public class N0  
        {  
            [MethodImpl(MethodImplOptions.NoInlining)]  
            public static void m() { }  
        }  
    }  
}  
  
namespace ns2  
{  
    public class C0  
    {  
        [MethodImpl(MethodImplOptions.NoInlining)]  
        public static void m() { }  
  
        public class N0  
        {  
            [MethodImpl(MethodImplOptions.NoInlining)]  
            public static void m() { }  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="18e8f-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="18e8f-122">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="18e8f-123">Diagnosing Errors with Managed Debugging Assistants (Diagnóstico de errores con asistentes para la depuración administrada)</span><span class="sxs-lookup"><span data-stu-id="18e8f-123">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="18e8f-124">Serialización de interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="18e8f-124">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
