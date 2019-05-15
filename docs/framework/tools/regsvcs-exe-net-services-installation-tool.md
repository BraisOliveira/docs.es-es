---
title: Regsvcs.exe (Herramienta de instalación de servicios de .NET)
ms.date: 03/30/2017
helpviewer_keywords:
- Regsvcs.exe
- .NET Services Installation tool
- loading assemblies
- assemblies [.NET Framework], registering
- type libraries
- registering assemblies
ms.assetid: 5220fe58-5aaf-4e8e-8bc3-b78c63025804
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0dc05294ae762b4f896bb7f514df102c1f948fe0
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64623407"
---
# <a name="regsvcsexe-net-services-installation-tool"></a><span data-ttu-id="75fb6-102">Regsvcs.exe (Herramienta de instalación de servicios de .NET)</span><span class="sxs-lookup"><span data-stu-id="75fb6-102">Regsvcs.exe (.NET Services Installation Tool)</span></span>
<span data-ttu-id="75fb6-103">La herramienta Instalación de servicios de .NET realiza las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="75fb6-103">The .NET Services Installation tool performs the following actions:</span></span>  
  
- <span data-ttu-id="75fb6-104">Carga y registra un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="75fb6-104">Loads and registers an assembly.</span></span>  
  
- <span data-ttu-id="75fb6-105">Genera, registra e instala una biblioteca de tipos en una aplicación COM+ específica.</span><span class="sxs-lookup"><span data-stu-id="75fb6-105">Generates, registers, and installs a type library into a specified COM+ application.</span></span>  
  
- <span data-ttu-id="75fb6-106">Configura los servicios que se han agregado a la clase mediante programación.</span><span class="sxs-lookup"><span data-stu-id="75fb6-106">Configures services that you have added programmatically to your class.</span></span>  
  
 <span data-ttu-id="75fb6-107">Para ejecutar la herramienta, use Símbolo del sistema para desarrolladores de Visual Studio (o Símbolo del sistema de Visual Studio en Windows 7).</span><span class="sxs-lookup"><span data-stu-id="75fb6-107">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="75fb6-108">Para más información, consulte [Símbolos del sistema](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="75fb6-108">For more information, see [Command Prompts](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="75fb6-109">En el símbolo del sistema, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="75fb6-109">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75fb6-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="75fb6-110">Syntax</span></span>  
  
```  
      regsvcs [/c | /fc | /u] [/tlb:typeLibraryFile] [/extlb]  
[/reconfig] [/componly] [/appname:applicationName]  
[/nologo] [/quiet]assemblyFile.dll   
```  
  
## <a name="parameters"></a><span data-ttu-id="75fb6-111">Parámetros</span><span class="sxs-lookup"><span data-stu-id="75fb6-111">Parameters</span></span>  
  
|<span data-ttu-id="75fb6-112">Argumento</span><span class="sxs-lookup"><span data-stu-id="75fb6-112">Argument</span></span>|<span data-ttu-id="75fb6-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="75fb6-113">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="75fb6-114">*assemblyFile.dll*</span><span class="sxs-lookup"><span data-stu-id="75fb6-114">*assemblyFile.dll*</span></span>|<span data-ttu-id="75fb6-115">Archivo de ensamblado de origen con el que se va a trabajar.</span><span class="sxs-lookup"><span data-stu-id="75fb6-115">The source assembly file.</span></span> <span data-ttu-id="75fb6-116">El ensamblado debe estar firmado con un nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="75fb6-116">The assembly must be signed with a strong name.</span></span> <span data-ttu-id="75fb6-117">Para obtener más información, vea [Signing an Assembly with a Strong Name](../../../docs/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md) (Firmar un ensamblado con un nombre seguro).</span><span class="sxs-lookup"><span data-stu-id="75fb6-117">For more information, see [Signing an Assembly with a Strong Name](../../../docs/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).</span></span>|  
  
|<span data-ttu-id="75fb6-118">Opción</span><span class="sxs-lookup"><span data-stu-id="75fb6-118">Option</span></span>|<span data-ttu-id="75fb6-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="75fb6-119">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="75fb6-120">**/appdir:** *path*</span><span class="sxs-lookup"><span data-stu-id="75fb6-120">**/appdir:** *path*</span></span>|<span data-ttu-id="75fb6-121">Especifica el directorio raíz de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="75fb6-121">Specifies the root directory of the application.</span></span>|  
|<span data-ttu-id="75fb6-122">**/appname:** *applicationName*</span><span class="sxs-lookup"><span data-stu-id="75fb6-122">**/appname:** *applicationName*</span></span>|<span data-ttu-id="75fb6-123">Especifica el nombre de la aplicación COM+ que se busca o se crea.</span><span class="sxs-lookup"><span data-stu-id="75fb6-123">Specifies the name of the COM+ application to either find or create.</span></span>|  
|<span data-ttu-id="75fb6-124">**/c**</span><span class="sxs-lookup"><span data-stu-id="75fb6-124">**/c**</span></span>|<span data-ttu-id="75fb6-125">Crea la aplicación de destino.</span><span class="sxs-lookup"><span data-stu-id="75fb6-125">Creates the target application.</span></span>|  
|<span data-ttu-id="75fb6-126">**/componly**</span><span class="sxs-lookup"><span data-stu-id="75fb6-126">**/componly**</span></span>|<span data-ttu-id="75fb6-127">Solo configura componentes; no tiene en cuenta métodos o interfaces.</span><span class="sxs-lookup"><span data-stu-id="75fb6-127">Configures components only; ignores methods and interfaces.</span></span>|  
|<span data-ttu-id="75fb6-128">**/exapp**</span><span class="sxs-lookup"><span data-stu-id="75fb6-128">**/exapp**</span></span>|<span data-ttu-id="75fb6-129">Indica a la herramienta que debe contar con una aplicación existente.</span><span class="sxs-lookup"><span data-stu-id="75fb6-129">Specifies to the tool to expect an existing application.</span></span>|  
|<span data-ttu-id="75fb6-130">**/extlb**</span><span class="sxs-lookup"><span data-stu-id="75fb6-130">**/extlb**</span></span>|<span data-ttu-id="75fb6-131">Utiliza una biblioteca de tipos existente.</span><span class="sxs-lookup"><span data-stu-id="75fb6-131">Uses an existing type library.</span></span>|  
|<span data-ttu-id="75fb6-132">**/fc**</span><span class="sxs-lookup"><span data-stu-id="75fb6-132">**/fc**</span></span>|<span data-ttu-id="75fb6-133">Busca o crea la aplicación de destino.</span><span class="sxs-lookup"><span data-stu-id="75fb6-133">Finds or creates the target application.</span></span>|  
|<span data-ttu-id="75fb6-134">**/help**</span><span class="sxs-lookup"><span data-stu-id="75fb6-134">**/help**</span></span>|<span data-ttu-id="75fb6-135">Muestra las opciones y la sintaxis de los comandos para la herramienta.</span><span class="sxs-lookup"><span data-stu-id="75fb6-135">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="75fb6-136">**/noreconfig**</span><span class="sxs-lookup"><span data-stu-id="75fb6-136">**/noreconfig**</span></span>|<span data-ttu-id="75fb6-137">No vuelve a configurar una aplicación de destino existente.</span><span class="sxs-lookup"><span data-stu-id="75fb6-137">Does not reconfigure an existing target application.</span></span>|  
|<span data-ttu-id="75fb6-138">**/nologo**</span><span class="sxs-lookup"><span data-stu-id="75fb6-138">**/nologo**</span></span>|<span data-ttu-id="75fb6-139">Suprime la presentación de la portada de inicio de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="75fb6-139">Suppresses the Microsoft startup banner display.</span></span>|  
|<span data-ttu-id="75fb6-140">**/parname:** *name*</span><span class="sxs-lookup"><span data-stu-id="75fb6-140">**/parname:** *name*</span></span>|<span data-ttu-id="75fb6-141">Especifica el nombre o el identificador de la aplicación COM+ que se busca o se crea.</span><span class="sxs-lookup"><span data-stu-id="75fb6-141">Specifies the name or id of the COM+ application to either find or create.</span></span>|  
|<span data-ttu-id="75fb6-142">**/reconfig**</span><span class="sxs-lookup"><span data-stu-id="75fb6-142">**/reconfig**</span></span>|<span data-ttu-id="75fb6-143">Vuelve a configurar una aplicación de destino existente.</span><span class="sxs-lookup"><span data-stu-id="75fb6-143">Reconfigures an existing target application.</span></span> <span data-ttu-id="75fb6-144">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="75fb6-144">This is the default.</span></span>|  
|<span data-ttu-id="75fb6-145">**/tlb:** *typelibraryfile*</span><span class="sxs-lookup"><span data-stu-id="75fb6-145">**/tlb:** *typelibraryfile*</span></span>|<span data-ttu-id="75fb6-146">Especifica el archivo de biblioteca de tipos que se instala.</span><span class="sxs-lookup"><span data-stu-id="75fb6-146">Specifies the type library file to install.</span></span>|  
|<span data-ttu-id="75fb6-147">**/u**</span><span class="sxs-lookup"><span data-stu-id="75fb6-147">**/u**</span></span>|<span data-ttu-id="75fb6-148">Desinstala la aplicación de destino.</span><span class="sxs-lookup"><span data-stu-id="75fb6-148">Uninstalls the target application.</span></span>|  
|<span data-ttu-id="75fb6-149">**/quiet**</span><span class="sxs-lookup"><span data-stu-id="75fb6-149">**/quiet**</span></span>|<span data-ttu-id="75fb6-150">Especifica el modo silencioso; suprime el logotipo y la presentación de mensajes de operaciones correctas.</span><span class="sxs-lookup"><span data-stu-id="75fb6-150">Specifies quiet mode; suppresses the logo and success message display.</span></span>|  
|<span data-ttu-id="75fb6-151">**/?**</span><span class="sxs-lookup"><span data-stu-id="75fb6-151">**/?**</span></span>|<span data-ttu-id="75fb6-152">Muestra las opciones y la sintaxis de los comandos para la herramienta.</span><span class="sxs-lookup"><span data-stu-id="75fb6-152">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="75fb6-153">Comentarios</span><span class="sxs-lookup"><span data-stu-id="75fb6-153">Remarks</span></span>  
 <span data-ttu-id="75fb6-154">Regsvcs.exe requiere un archivo de ensamblado de origen especificado por *assemblyFile.dll*.</span><span class="sxs-lookup"><span data-stu-id="75fb6-154">Regsvcs.exe requires a source assembly file specified by *assemblyFile.dll*.</span></span> <span data-ttu-id="75fb6-155">Este ensamblado debe estar firmado con un nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="75fb6-155">This assembly must be signed with a strong name.</span></span> <span data-ttu-id="75fb6-156">Para obtener más información sobre la firma con nombres seguros, vea [Signing an Assembly with a Strong Name](../../../docs/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md) (Firmar un ensamblado con un nombre seguro).</span><span class="sxs-lookup"><span data-stu-id="75fb6-156">For more information on strong name signing, see [Signing an Assembly with a Strong Name](../../../docs/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).</span></span> <span data-ttu-id="75fb6-157">Los nombres de la aplicación de destino y del archivo de biblioteca de tipos son opcionales.</span><span class="sxs-lookup"><span data-stu-id="75fb6-157">The names of the target application and the type library file are optional.</span></span> <span data-ttu-id="75fb6-158">El argumento *applicationName* se puede generar a partir del archivo de ensamblado de origen, y Regsvcs.exe lo creará si no existe todavía.</span><span class="sxs-lookup"><span data-stu-id="75fb6-158">The *applicationName* argument can be generated from the source assembly file and will be created by Regsvcs.exe, if it does not already exist.</span></span> <span data-ttu-id="75fb6-159">El argumento *typelibraryfile* puede especificar un nombre de biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="75fb6-159">The *typelibraryfile* argument can specify a type library name.</span></span> <span data-ttu-id="75fb6-160">Si no se especifica ningún nombre de biblioteca de tipos, Regsvcs.exe utiliza el nombre del ensamblado como valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="75fb6-160">If you do not specify a type library name, Regsvcs.exe uses the assembly name as the default.</span></span>  
  
 <span data-ttu-id="75fb6-161">Cuando Regsvcs.exe registra los métodos de un componente, se le aplican las [peticiones](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/9kc0c6st(v=vs.100)) y las [peticiones de vínculos](../../../docs/framework/misc/link-demands.md) de estos métodos.</span><span class="sxs-lookup"><span data-stu-id="75fb6-161">When Regsvcs.exe registers a component's methods, it is subject to the [demands](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/9kc0c6st(v=vs.100)) and [link demands](../../../docs/framework/misc/link-demands.md) on those methods.</span></span> <span data-ttu-id="75fb6-162">Como la herramienta se ejecuta en un entorno de confianza total, la mayoría de las peticiones de permisos se llevan a cabo satisfactoriamente.</span><span class="sxs-lookup"><span data-stu-id="75fb6-162">Because the tool executes in a fully-trusted environment, most demands for a permission succeed.</span></span> <span data-ttu-id="75fb6-163">Sin embargo, Regsvcs.exe no puede registrar componentes con métodos protegidos por una petición o una petición de vínculo para <xref:System.Security.Permissions.StrongNameIdentityPermission> o <xref:System.Security.Permissions.PublisherIdentityPermission>.</span><span class="sxs-lookup"><span data-stu-id="75fb6-163">However, Regsvcs.exe cannot register components with methods protected by a demand or link demand for the <xref:System.Security.Permissions.StrongNameIdentityPermission> or the <xref:System.Security.Permissions.PublisherIdentityPermission>.</span></span>  
  
 <span data-ttu-id="75fb6-164">Debe tener privilegios administrativos en el equipo local para utilizar Regsvcs.exe.</span><span class="sxs-lookup"><span data-stu-id="75fb6-164">You must have administrative privileges on the local computer to use Regsvcs.exe.</span></span>  
  
 <span data-ttu-id="75fb6-165">Si Regsvcs.exe genera un error durante la realización de alguna de estas acciones, muestra los mensajes de error correspondientes.</span><span class="sxs-lookup"><span data-stu-id="75fb6-165">If Regsvcs.exe fails while performing any of these actions, it displays corresponding error messages.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="75fb6-166">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="75fb6-166">Examples</span></span>  
 <span data-ttu-id="75fb6-167">El comando siguiente agrega todas las clases públicas incluidas en `myTest.dll` a `myTargetApp` (aplicación COM+ existente) y genera la biblioteca de tipos `myTest.tlb`.</span><span class="sxs-lookup"><span data-stu-id="75fb6-167">The following command adds all public classes contained in `myTest.dll` to `myTargetApp` (an existing COM+ application) and produces the `myTest.tlb` type library.</span></span>  
  
```  
regsvcs /appname:myTargetApp myTest.dll  
```  
  
 <span data-ttu-id="75fb6-168">El comando siguiente agrega todas las clases públicas incluidas en `myTest.dll` a `myTargetApp` (aplicación COM+ existente) y genera la biblioteca de tipos `newTest.tlb`.</span><span class="sxs-lookup"><span data-stu-id="75fb6-168">The following command adds all public classes contained in `myTest.dll` to `myTargetApp` (an existing COM+ application) and produces the `newTest.tlb` type library.</span></span>  
  
```  
regsvcs /appname:myTargetApp /tlb:newTest.tlb myTest.dll  
```  
  
## <a name="see-also"></a><span data-ttu-id="75fb6-169">Vea también</span><span class="sxs-lookup"><span data-stu-id="75fb6-169">See also</span></span>

- [<span data-ttu-id="75fb6-170">Herramientas</span><span class="sxs-lookup"><span data-stu-id="75fb6-170">Tools</span></span>](../../../docs/framework/tools/index.md)
- [<span data-ttu-id="75fb6-171">Cómo: Firma de un ensamblado con un nombre seguro</span><span class="sxs-lookup"><span data-stu-id="75fb6-171">How to: Sign an Assembly with a Strong Name</span></span>](../../../docs/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md)
- [<span data-ttu-id="75fb6-172">Símbolos del sistema</span><span class="sxs-lookup"><span data-stu-id="75fb6-172">Command Prompts</span></span>](../../../docs/framework/tools/developer-command-prompt-for-vs.md)
