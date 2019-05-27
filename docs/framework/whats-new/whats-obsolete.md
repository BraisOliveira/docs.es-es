---
title: Lo obsoleto en la biblioteca de clases de .NET Framework
ms.custom: updateeachrelease
ms.date: 04/02/2019
helpviewer_keywords:
- obsolete [.NET Framework]
- what's obsolete [.NET Framework]
- deprecated [.NET Framework]
ms.assetid: d356a43a-73df-4ae2-a457-b9628074c7cd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6ca7bf5ad4b4d145f484f46ee46220a58f326333
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65635592"
---
# <a name="whats-obsolete-in-the-net-framework-class-library"></a><span data-ttu-id="2ad12-102">Lo obsoleto en la biblioteca de clases de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="2ad12-102">What's obsolete in the .NET Framework class library</span></span>

<span data-ttu-id="2ad12-103">.NET Framework cambia con el tiempo.</span><span class="sxs-lookup"><span data-stu-id="2ad12-103">The .NET Framework changes over time.</span></span> <span data-ttu-id="2ad12-104">Cada nueva versión agrega nuevos tipos y miembros de tipos que proporcionan una nueva funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="2ad12-104">Each new version adds new types and type members that provide new functionality.</span></span> <span data-ttu-id="2ad12-105">Los tipos existentes y sus miembros también cambian con el tiempo.</span><span class="sxs-lookup"><span data-stu-id="2ad12-105">Existing types and their members also change over time.</span></span> <span data-ttu-id="2ad12-106">Por ejemplo, algunos tipos pierden importancia cuando la tecnología que admiten es reemplazada por una nueva y algunos métodos son sustituidos por métodos más nuevos que resultan más cómodos o están más completos.</span><span class="sxs-lookup"><span data-stu-id="2ad12-106">For example, some types become less important as the technology they support is replaced by a new technology, and some methods are superseded by newer methods that are either more convenient or more full-featured.</span></span>

<span data-ttu-id="2ad12-107">.NET Framework y Common Language Runtime se esfuerzan por ser compatibles con versiones anteriores (permitir que aplicaciones que se desarrollaron con una versión de .NET Framework puedan ejecutarse en la versión siguiente de .NET Framework).</span><span class="sxs-lookup"><span data-stu-id="2ad12-107">The .NET Framework and the common language runtime strive to support backward compatibility (allowing applications that were developed with one version of the .NET Framework to run on the next version of the .NET Framework).</span></span> <span data-ttu-id="2ad12-108">Esto hace más difícil quitar simplemente un tipo o un miembro de tipo.</span><span class="sxs-lookup"><span data-stu-id="2ad12-108">This makes it difficult to simply remove a type or a type member.</span></span> <span data-ttu-id="2ad12-109">En su lugar, .NET Framework indica que no se debería seguir utilizando un tipo o un miembro de tipo marcándolo como obsoleto o desusado.</span><span class="sxs-lookup"><span data-stu-id="2ad12-109">Instead, the .NET Framework indicates that a type or a type member should no longer be used by marking it as obsolete or deprecated.</span></span> <span data-ttu-id="2ad12-110">El desuso de un tipo o un miembro implica marcarlo para que los desarrolladores sean conscientes de que va a desaparecer y tengan tiempo para reaccionar antes de su eliminación.</span><span class="sxs-lookup"><span data-stu-id="2ad12-110">Deprecating a type or a member involves marking it so that developers are aware it will go away and have time to respond to its removal.</span></span> <span data-ttu-id="2ad12-111">Sin embargo, el código existente que utiliza el tipo o el miembro continúa ejecutándose en la nueva versión de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2ad12-111">However, existing code that uses the type or member continues to run in the new version of the .NET Framework.</span></span>

> [!NOTE]
> <span data-ttu-id="2ad12-112">Los términos *obsoleto* y *en desuso* tienen el mismo significado cuando se aplican a los tipos y miembros de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2ad12-112">The terms *obsolete* and *deprecated* have the same meaning when applied to the types and members of the .NET Framework.</span></span>

## <a name="the-obsoleteattribute-attribute"></a><span data-ttu-id="2ad12-113">El atributo ObsoleteAttribute</span><span class="sxs-lookup"><span data-stu-id="2ad12-113">The ObsoleteAttribute attribute</span></span>

<span data-ttu-id="2ad12-114">.NET Framework indica que un tipo o un miembro de tipo está obsoleto marcándolo con el atributo <xref:System.ObsoleteAttribute>.</span><span class="sxs-lookup"><span data-stu-id="2ad12-114">The .NET Framework indicates that a type or type member is obsolete by marking it with the <xref:System.ObsoleteAttribute> attribute.</span></span> <span data-ttu-id="2ad12-115">La aplicación del atributo a un tipo o miembro indica que ese tipo o miembro se quitará de alguna versión futura de .NET Framework sin interrumpir el código compilado que utiliza este miembro.</span><span class="sxs-lookup"><span data-stu-id="2ad12-115">Applying the attribute to a type or member indicates that type or member will be removed in some future version of the .NET Framework without breaking compiled code that uses that member.</span></span>

<span data-ttu-id="2ad12-116">Además de indicar que un tipo o miembro de tipo está obsoleto, <xref:System.ObsoleteAttribute> define cómo administra el compilador el código fuente que incluye este tipo o miembro.</span><span class="sxs-lookup"><span data-stu-id="2ad12-116">In addition to indicating that a type or a type member is obsolete, <xref:System.ObsoleteAttribute> defines how the compiler handles source code that includes that type or member.</span></span> <span data-ttu-id="2ad12-117">El compilador puede compilar el código pero emitir un mensaje de advertencia o puede tratar el uso del tipo o miembro como un error.</span><span class="sxs-lookup"><span data-stu-id="2ad12-117">The compiler can compile the code but emit a warning message, or it can treat the use of the type or member as an error.</span></span> <span data-ttu-id="2ad12-118">En el primer caso, el código puede compilarse correctamente, pero un mensaje de advertencia indica que el tipo o miembro está obsoleto.</span><span class="sxs-lookup"><span data-stu-id="2ad12-118">In the first case, the code can successfully compile, but a warning message indicates that the type or member is obsolete.</span></span> <span data-ttu-id="2ad12-119">En el segundo caso, se produce un error de compilación.</span><span class="sxs-lookup"><span data-stu-id="2ad12-119">In the second case, compilation fails.</span></span>

<span data-ttu-id="2ad12-120">Incluso si la compilación genera un error en lugar de un mensaje de advertencia, <xref:System.ObsoleteAttribute> no afecta al comportamiento en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="2ad12-120">Even if compilation produces an error instead of a warning message, <xref:System.ObsoleteAttribute> does not affect run-time behavior.</span></span> <span data-ttu-id="2ad12-121">Es decir, las aplicaciones que utilizan el tipo o miembro y que se han compilado correctamente siempre se ejecutarán correctamente.</span><span class="sxs-lookup"><span data-stu-id="2ad12-121">That is, applications that use the type or member and that have compiled successfully will always run successfully.</span></span> <span data-ttu-id="2ad12-122">Solo se produce un error en el intento de volver a compilar una aplicación que utiliza el tipo o miembro.</span><span class="sxs-lookup"><span data-stu-id="2ad12-122">Only the attempt to recompile an application that uses the type or member fails.</span></span>

## <a name="how-to-handle-obsolete-types-and-members"></a><span data-ttu-id="2ad12-123">Cómo controlar los tipos y miembros obsoletos</span><span class="sxs-lookup"><span data-stu-id="2ad12-123">How to handle obsolete types and members</span></span>

<span data-ttu-id="2ad12-124">Al actualizar y volver a compilar el código existente, el uso de un tipo o miembro obsoleto que genera una advertencia del compilador en su aplicación es absolutamente aceptable.</span><span class="sxs-lookup"><span data-stu-id="2ad12-124">When you upgrade and recompile existing code, using an obsolete type or member that produces a compiler warning in your application is perfectly acceptable.</span></span> <span data-ttu-id="2ad12-125">Sin embargo, debería revisar el mensaje de advertencia del compilador para determinar si tiene que cambiar el código de aplicación.</span><span class="sxs-lookup"><span data-stu-id="2ad12-125">However, you should review the compiler warning message to determine whether you should change your application code.</span></span> <span data-ttu-id="2ad12-126">Si el mensaje no indica ninguna alternativa adecuada, debe realizar una de las siguientes operaciones:</span><span class="sxs-lookup"><span data-stu-id="2ad12-126">If the message does not point to a suitable alternative, you should do either of the following:</span></span>

- <span data-ttu-id="2ad12-127">Cambie su código quitando el uso del tipo o miembro, si es posible.</span><span class="sxs-lookup"><span data-stu-id="2ad12-127">Change your code by removing the use of the type or member, if possible.</span></span>

     <span data-ttu-id="2ad12-128">o bien</span><span class="sxs-lookup"><span data-stu-id="2ad12-128">-or-</span></span>

- <span data-ttu-id="2ad12-129">Revise la documentación para que esta área de tecnología determine cómo responder al desuso.</span><span class="sxs-lookup"><span data-stu-id="2ad12-129">Review the documentation for this technology area to determine how to respond to the deprecation.</span></span>

<span data-ttu-id="2ad12-130">Puede decidir no volver a compilar un código existente con una versión posterior de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2ad12-130">You may choose not to recompile existing code against a later version of the .NET Framework.</span></span> <span data-ttu-id="2ad12-131">En su lugar, puede especificar la versión de .NET Framework con la que se ejecuta el código compilado existente.</span><span class="sxs-lookup"><span data-stu-id="2ad12-131">Instead, you can specify the version of the .NET Framework against which your existing compiled code runs.</span></span> <span data-ttu-id="2ad12-132">Por ejemplo, suponga que tiene una aplicación denominada app1.exe que se compiló con [!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)], pero desea que la aplicación se ejecute con [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2ad12-132">For example, suppose that you have an application named app1.exe that was compiled against the [!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)], but you want the application to run against the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].</span></span> <span data-ttu-id="2ad12-133">Para ello, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="2ad12-133">This requires the following steps:</span></span>

1. <span data-ttu-id="2ad12-134">Cree un archivo de configuración para el ejecutable principal y denomínelo *appName*.exe.config, donde *appName* es el nombre del ejecutable de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2ad12-134">Create a configuration file for your main executable and name it *appName*.exe.config, where *appName* is the name of the application executable.</span></span> <span data-ttu-id="2ad12-135">Para la aplicación denominada app1.exe en nuestro ejemplo, va a crear un archivo de configuración denominado app1.exe.config.</span><span class="sxs-lookup"><span data-stu-id="2ad12-135">For the application named app1.exe in our example, you would create a configuration file named app1.exe.config.</span></span>

2. <span data-ttu-id="2ad12-136">Agregue lo siguiente al archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="2ad12-136">Add the following to the configuration file.</span></span>

    ```xml
    <configuration>
       <startup> 
          <supportedRuntime version="v4.0" />
       </startup>
    </configuration>
    ```

<span data-ttu-id="2ad12-137">En la siguiente tabla se muestra una lista de los valores de cadena que puede asignar al atributo `version` para destinarlo a una versión concreta de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="2ad12-137">The following table lists the string values that you can assign to the `version` attribute to target a specific version of the .NET Framework:</span></span>

|<span data-ttu-id="2ad12-138">Versión de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="2ad12-138">.NET Framework version</span></span>|<span data-ttu-id="2ad12-139">Cadena de `version`</span><span class="sxs-lookup"><span data-stu-id="2ad12-139">`version` string</span></span>|
|-|-|
|<span data-ttu-id="2ad12-140">4.8</span><span class="sxs-lookup"><span data-stu-id="2ad12-140">4.8</span></span>|<span data-ttu-id="2ad12-141">v4.0</span><span class="sxs-lookup"><span data-stu-id="2ad12-141">v4.0</span></span>|
|<span data-ttu-id="2ad12-142">4.7 (incluidas 4.7.1 y 4.7.2)</span><span class="sxs-lookup"><span data-stu-id="2ad12-142">4.7 (including 4.7.1 and 4.7.2)</span></span>|<span data-ttu-id="2ad12-143">v4.0</span><span class="sxs-lookup"><span data-stu-id="2ad12-143">v4.0</span></span>|
|<span data-ttu-id="2ad12-144">4.6 (incluidas 4.6.1 y 4.6.2)</span><span class="sxs-lookup"><span data-stu-id="2ad12-144">4.6 (including 4.6.1 and 4.6.2)</span></span>|<span data-ttu-id="2ad12-145">v4.0</span><span class="sxs-lookup"><span data-stu-id="2ad12-145">v4.0</span></span>|
|<span data-ttu-id="2ad12-146">4.5 (incluidas 4.5.1 y 4.5.2)</span><span class="sxs-lookup"><span data-stu-id="2ad12-146">4.5 (including 4.5.1 and 4.5.2)</span></span>|<span data-ttu-id="2ad12-147">v4.0</span><span class="sxs-lookup"><span data-stu-id="2ad12-147">v4.0</span></span>|
|<span data-ttu-id="2ad12-148">4</span><span class="sxs-lookup"><span data-stu-id="2ad12-148">4</span></span>|<span data-ttu-id="2ad12-149">v4.0</span><span class="sxs-lookup"><span data-stu-id="2ad12-149">v4.0</span></span>|
|<span data-ttu-id="2ad12-150">3.5</span><span class="sxs-lookup"><span data-stu-id="2ad12-150">3.5</span></span>|<span data-ttu-id="2ad12-151">v2.0.50727</span><span class="sxs-lookup"><span data-stu-id="2ad12-151">v2.0.50727</span></span>|
|<span data-ttu-id="2ad12-152">2.0</span><span class="sxs-lookup"><span data-stu-id="2ad12-152">2.0</span></span>|<span data-ttu-id="2ad12-153">v2.0.50727</span><span class="sxs-lookup"><span data-stu-id="2ad12-153">v2.0.50727</span></span>|
|<span data-ttu-id="2ad12-154">1.1</span><span class="sxs-lookup"><span data-stu-id="2ad12-154">1.1</span></span>|<span data-ttu-id="2ad12-155">v1.1.4322</span><span class="sxs-lookup"><span data-stu-id="2ad12-155">v1.1.4322</span></span>|
|<span data-ttu-id="2ad12-156">1.0</span><span class="sxs-lookup"><span data-stu-id="2ad12-156">1.0</span></span>|<span data-ttu-id="2ad12-157">v1.0.3705</span><span class="sxs-lookup"><span data-stu-id="2ad12-157">v1.0.3705</span></span>|

## <a name="obsolete-lists-for-the-net-framework-45-and-later-versions"></a><span data-ttu-id="2ad12-158">Listas de elementos obsoletos en .NET Framework 4.5 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="2ad12-158">Obsolete lists for the .NET Framework 4.5 and later versions</span></span>

- [<span data-ttu-id="2ad12-159">Tipos obsoletos</span><span class="sxs-lookup"><span data-stu-id="2ad12-159">Obsolete Types</span></span>](obsolete-types.md)
- [<span data-ttu-id="2ad12-160">Miembros obsoletos</span><span class="sxs-lookup"><span data-stu-id="2ad12-160">Obsolete Members</span></span>](obsolete-members.md)

## <a name="obsolete-lists-for-previous-versions"></a><span data-ttu-id="2ad12-161">Listas de elementos obsoletos en versiones anteriores</span><span class="sxs-lookup"><span data-stu-id="2ad12-161">Obsolete lists for previous versions</span></span>

- <span data-ttu-id="2ad12-162">[Tipos obsoletos en .NET Framework 4](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ee461503(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="2ad12-162">[Obsolete Types in the .NET Framework 4](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ee461503(v=vs.100))</span></span>

- <span data-ttu-id="2ad12-163">[Miembros obsoletos en .NET Framework 4](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ee471421(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="2ad12-163">[Obsolete Members in the .NET Framework 4](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ee471421(v=vs.100))</span></span>

- <span data-ttu-id="2ad12-164">[Lista de API obsoletas en .NET Framework 3.5](https://docs.microsoft.com/previous-versions/cc835481(v=msdn.10))</span><span class="sxs-lookup"><span data-stu-id="2ad12-164">[.NET Framework 3.5 Obsolete List](https://docs.microsoft.com/previous-versions/cc835481(v=msdn.10))</span></span>

- <span data-ttu-id="2ad12-165">[Lista de API obsoletas en .NET Framework 2.0](https://docs.microsoft.com/previous-versions/aa497286(v=msdn.10))</span><span class="sxs-lookup"><span data-stu-id="2ad12-165">[.NET Framework 2.0 Obsolete List](https://docs.microsoft.com/previous-versions/aa497286(v=msdn.10))</span></span>

## <a name="see-also"></a><span data-ttu-id="2ad12-166">Vea también</span><span class="sxs-lookup"><span data-stu-id="2ad12-166">See also</span></span>

- [<span data-ttu-id="2ad12-167">\<supportedRuntime > Elemento</span><span class="sxs-lookup"><span data-stu-id="2ad12-167">\<supportedRuntime> Element</span></span>](../configure-apps/file-schema/startup/supportedruntime-element.md)
