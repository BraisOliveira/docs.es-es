---
title: -appconfig (Opciones del compilador de C#)
ms.date: 07/20/2015
f1_keywords:
- /appconfig
helpviewer_keywords:
- /appconfig compiler option [C#]
- -appconfig compiler option [C#]
- appconfig compiler option [C#]
ms.assetid: 1cdbcbcc-7813-4010-b5b8-e67c107c5a98
ms.openlocfilehash: 7a7e8e61f65704a2e99385a1be320048d950324c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69922519"
---
# <a name="-appconfig-c-compiler-options"></a><span data-ttu-id="b1470-102">-appconfig (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="b1470-102">-appconfig (C# Compiler Options)</span></span>
<span data-ttu-id="b1470-103">La opción del compilador **-appconfig** permite a una aplicación de C# especificar la ubicación del archivo de configuración de la aplicación de un ensamblado (app.config) al Common Language Runtime (CLR) en tiempo de enlace del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="b1470-103">The **-appconfig** compiler option enables a C# application to specify the location of an assembly's application configuration (app.config) file to the common language runtime (CLR) at assembly binding time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1470-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b1470-104">Syntax</span></span>  
  
```console  
-appconfig:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="b1470-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="b1470-105">Arguments</span></span>  
 `file`  
 <span data-ttu-id="b1470-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="b1470-106">Required.</span></span> <span data-ttu-id="b1470-107">El archivo de configuración de la aplicación que contiene los valores de enlace del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="b1470-107">The application configuration file that contains assembly binding settings.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b1470-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b1470-108">Remarks</span></span>  
 <span data-ttu-id="b1470-109">Un uso de **-appconfig** es el de escenarios avanzados en los que un ensamblado tiene que hacer referencia a la versión de .NET Framework y a la versión de .NET Framework para Silverlight de un ensamblado de referencia determinado al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="b1470-109">One use of **-appconfig** is advanced scenarios in which an assembly has to reference both the .NET Framework version and the .NET Framework for Silverlight version of a particular reference assembly at the same time.</span></span> <span data-ttu-id="b1470-110">Por ejemplo, un diseñador de XAML escrito en Windows Presentation Foundation (WPF) podría tener que hacer referencia al escritorio de WPF, para la interfaz de usuario del diseñador, y al subconjunto de WPF que se incluye con Silverlight.</span><span class="sxs-lookup"><span data-stu-id="b1470-110">For example, a XAML designer written in Windows Presentation Foundation (WPF) might have to reference both the WPF Desktop, for the designer's user interface, and the subset of WPF that is included with Silverlight.</span></span> <span data-ttu-id="b1470-111">El mismo ensamblado del diseñador tiene que tener acceso a ambos ensamblados.</span><span class="sxs-lookup"><span data-stu-id="b1470-111">The same designer assembly has to access both assemblies.</span></span> <span data-ttu-id="b1470-112">De forma predeterminada, las referencias independientes producen un error del compilador, ya que el enlace del ensamblado considera los dos ensamblados equivalentes.</span><span class="sxs-lookup"><span data-stu-id="b1470-112">By default, the separate references cause a compiler error, because assembly binding sees the two assemblies as equivalent.</span></span>  
  
 <span data-ttu-id="b1470-113">La opción del compilador **-appconfig** permite especificar la ubicación de un archivo app.config que deshabilita el comportamiento predeterminado usando una etiqueta `<supportPortability>`, como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="b1470-113">The **-appconfig** compiler option enables you to specify the location of an app.config file that disables the default behavior by using a `<supportPortability>` tag, as shown in the following example.</span></span>  
  
 `<supportPortability PKT="7cec85d7bea7798e" enable="false"/>`  
  
 <span data-ttu-id="b1470-114">El compilador pasa la ubicación del archivo a la lógica de enlace del ensamblado de CLR.</span><span class="sxs-lookup"><span data-stu-id="b1470-114">The compiler passes the location of the file to the CLR's assembly-binding logic.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b1470-115">Si está usando Microsoft Build Engine (MSBuild) para compilar su aplicación, puede establecer la opción del compilador **-appconfig** mediante la adición de una etiqueta de propiedad al archivo .csproj.</span><span class="sxs-lookup"><span data-stu-id="b1470-115">If you are using the Microsoft Build Engine (MSBuild) to build your application, you can set the **-appconfig** compiler option by adding a property tag to the .csproj file.</span></span> <span data-ttu-id="b1470-116">Para usar el archivo app.config que ya está establecido en el proyecto, agregue la etiqueta `<UseAppConfigForCompiler>` de propiedades al archivo .csproj y establezca su valor en `true`.</span><span class="sxs-lookup"><span data-stu-id="b1470-116">To use the app.config file that is already set in the project, add property tag `<UseAppConfigForCompiler>` to the .csproj file and set its value to `true`.</span></span> <span data-ttu-id="b1470-117">Para especificar otro archivo app.config, agregue la etiqueta `<AppConfigForCompiler>` de propiedades y establezca su valor en la ubicación del archivo.</span><span class="sxs-lookup"><span data-stu-id="b1470-117">To specify a different app.config file, add property tag `<AppConfigForCompiler>` and set its value to the location of the file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b1470-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b1470-118">Example</span></span>  
 <span data-ttu-id="b1470-119">En el siguiente ejemplo se muestra un archivo app.config que permite a una aplicación tener referencias a la implementación de .NET Framework y de .NET Framework para Silverlight de cualquier ensamblado de .NET Framework que exista en ambas implementaciones.</span><span class="sxs-lookup"><span data-stu-id="b1470-119">The following example shows an app.config file that enables an application to have references to both the .NET Framework implementation and the .NET Framework for Silverlight implementation of any .NET Framework assembly that exists in both implementations.</span></span> <span data-ttu-id="b1470-120">La opción del compilador **-appconfig** especifica la ubicación de este archivo app.config.</span><span class="sxs-lookup"><span data-stu-id="b1470-120">The **-appconfig** compiler option specifies the location of this app.config file.</span></span>  
  
```xml  
<configuration>  
      <runtime>  
      <assemblyBinding>  
            <supportPortability PKT="7cec85d7bea7798e" enable="false"/>  
            <supportPortability PKT="31bf3856ad364e35" enable="false"/>  
      </assemblyBinding>  
      </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b1470-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="b1470-121">See also</span></span>

- <span data-ttu-id="b1470-122">[\<supportPortability> Element](../../../framework/configure-apps/file-schema/runtime/supportportability-element.md) (Elemento <supportPortability>)</span><span class="sxs-lookup"><span data-stu-id="b1470-122">[\<supportPortability> Element](../../../framework/configure-apps/file-schema/runtime/supportportability-element.md)</span></span>
- [<span data-ttu-id="b1470-123">Opciones del compilador de C#, por orden alfabético</span><span class="sxs-lookup"><span data-stu-id="b1470-123">C# Compiler Options Listed Alphabetically</span></span>](./listed-alphabetically.md)
