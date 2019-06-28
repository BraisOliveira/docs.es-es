---
title: Procedimiento para hospedar un servicio WCF escrito con .NET Framework 3.5 en IIS que ejecuta .NET Framework 4
ms.date: 03/30/2017
ms.assetid: 9aabc785-068d-4d32-8841-3ef39308d8d6
ms.openlocfilehash: eb4f0538380bf2e1d0e36d69020787055230dbaf
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/28/2019
ms.locfileid: "67425560"
---
# <a name="how-to-host-a-wcf-service-written-with-net-framework-35-in-iis-running-under-net-framework-4"></a><span data-ttu-id="16b47-102">Procedimiento para hospedar un servicio WCF escrito con .NET Framework 3.5 en IIS que ejecuta .NET Framework 4</span><span class="sxs-lookup"><span data-stu-id="16b47-102">How to: Host a WCF Service Written with .NET Framework 3.5 in IIS Running Under .NET Framework 4</span></span>
<span data-ttu-id="16b47-103">Al hospedar un servicio de Windows Communication Foundation (WCF) que se escriben con [!INCLUDE[netfx35_long](../../../includes/netfx35-long-md.md)] en un equipo que ejecuta [!INCLUDE[netfx40_long](../../../includes/netfx40-long-md.md)], es posible que obtenga un <xref:System.ServiceModel.ProtocolException> con el siguiente texto.</span><span class="sxs-lookup"><span data-stu-id="16b47-103">When hosting a Windows Communication Foundation (WCF) service written with [!INCLUDE[netfx35_long](../../../includes/netfx35-long-md.md)] on a machine running [!INCLUDE[netfx40_long](../../../includes/netfx40-long-md.md)], you may get a <xref:System.ServiceModel.ProtocolException> with the following text.</span></span>  
  
```Output  
Unhandled Exception: System.ServiceModel.ProtocolException: The content type text/html; charset=utf-8 of the response message does not match the content type of the binding (application/soap+xml; charset=utf-8). If using a custom encoder, be sure that the IsContentTypeSupported method is implemented properly. The first 1024 bytes of the response were: '<html>    <head>        <title>The application domain or application pool is currently running version 4.0 or later of the .NET Framework. This can occur if IIS settings have been set to 4.0 or later for this Web application, or if you are using version 4.0 or later of the ASP.NET Web Development Server. The <compilation> element in the Web.config file for this Web application does not contain the required 'targetFrameworkMoniker' attribute for this version of the .NET Framework (for example, '<compilation targetFrameworkMoniker=".NETFramework,Version=v4.0">'). Update the Web.config file with this attribute, or configure the Web application to use a different version of the .NET Framework.</title>...  
```  
  
 <span data-ttu-id="16b47-104">O bien, si intenta ir al archivo .svc del servicio, puede ver una página de error con el siguiente texto.</span><span class="sxs-lookup"><span data-stu-id="16b47-104">Or if you try to browse to the service's .svc file you may see an error page with the following text.</span></span>  
  
```Output  
The application domain or application pool is currently running version 4.0 or later of the .NET Framework. This can occur if IIS settings have been set to 4.0 or later for this Web application, or if you are using version 4.0 or later of the ASP.NET Web Development Server. The <compilation> element in the Web.config file for this Web application does not contain the required 'targetFrameworkMoniker' attribute for this version of the .NET Framework (for example, '<compilation targetFrameworkMoniker=".NETFramework,Version=v4.0">'). Update the Web.config file with this attribute, or configure the Web application to use a different version of the .NET Framework.  
```  
  
 <span data-ttu-id="16b47-105">Estos errores se producen porque el dominio de aplicación en el que se ejecuta IIS está ejecutando [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] y el servicio de WCF esperaba ejecutarse en [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="16b47-105">These errors occur because the application domain IIS is running within is running [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] and the WCF service is expecting to run under [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)].</span></span> <span data-ttu-id="16b47-106">Este tema explica las modificaciones necesarias para hacer que el servicio se ejecute.</span><span class="sxs-lookup"><span data-stu-id="16b47-106">This topic explains the modifications required to get the service to run.</span></span>  
  
 <span data-ttu-id="16b47-107">A continuación busque el <`compilers`> elemento y cambie la opción de proveedor de CompilerVersion para tener un valor de 4.0.</span><span class="sxs-lookup"><span data-stu-id="16b47-107">Next find the <`compilers`> element and change the CompilerVersion provider option to have a value of 4.0.</span></span> <span data-ttu-id="16b47-108">De forma predeterminada, hay dos <`compiler`> elementos en el <`compilers`> elemento.</span><span class="sxs-lookup"><span data-stu-id="16b47-108">By default, there are two <`compiler`> elements under the <`compilers`> element.</span></span> <span data-ttu-id="16b47-109">Debe actualizar la opción de proveedor de CompilerVersion para ambos tal y como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="16b47-109">You must update the CompilerVersion provider option for both as shown in the following example.</span></span>  
  
```xml  
<system.codedom>  
      <compilers>  
        <compiler language="c#;cs;csharp" extension=".cs" warningLevel="4"  
                  type="Microsoft.CSharp.CSharpCodeProvider, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
          <providerOption name="CompilerVersion" value="v3.5"/>  
          <providerOption name="WarnAsError" value="false"/>  
        </compiler>  
        <compiler language="vb;vbs;visualbasic;vbscript" extension=".vb" warningLevel="4"  
                  type="Microsoft.VisualBasic.VBCodeProvider, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
          <providerOption name="CompilerVersion" value="v3.5"/>  
          <providerOption name="OptionInfer" value="true"/>  
          <providerOption name="WarnAsError" value="false"/>  
        </compiler>  
      </compilers>  
    </system.codedom>  
```  
  
### <a name="add-the-required-targetframework-attribute"></a><span data-ttu-id="16b47-110">Adición del atributo targetFramework necesario</span><span class="sxs-lookup"><span data-stu-id="16b47-110">Add the required targetFramework attribute</span></span>  
  
1. <span data-ttu-id="16b47-111">Abra el archivo Web.config del servicio y busque el <`compilation`> elemento.</span><span class="sxs-lookup"><span data-stu-id="16b47-111">Open the service's Web.config file and look for the <`compilation`> element.</span></span>  
  
2. <span data-ttu-id="16b47-112">Agregar el `targetFramework` atributo a la <`compilation`> elemento tal como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="16b47-112">Add the `targetFramework` attribute to the <`compilation`> element as shown in the following example.</span></span>  
  
    ```xml  
    <compilation debug="false"  
            targetFramework="4.0">  
  
            <assemblies>  
              <add assembly="System.Core, Version=3.5.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089"/>  
              <add assembly="System.Xml.Linq, Version=3.5.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089"/>  
              <add assembly="System.Web.Extensions, Version=3.5.0.0, Culture=neutral, PublicKeyToken=31BF3856AD364E35"/>  
              <add assembly="System.Data.DataSetExtensions, Version=3.5.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089"/>  
            </assemblies>  
  
          </compilation>  
    ```  
  
3. <span data-ttu-id="16b47-113">Buscar el <`compilers`> elemento y cambie la opción de proveedor de CompilerVersion para tener un valor de 4.0.</span><span class="sxs-lookup"><span data-stu-id="16b47-113">Find the <`compilers`> element and change the CompilerVersion provider option to have a value of 4.0.</span></span> <span data-ttu-id="16b47-114">De forma predeterminada, hay dos <`compiler`> elementos en el <`compilers`> elemento.</span><span class="sxs-lookup"><span data-stu-id="16b47-114">By default, there are two <`compiler`> elements under the <`compilers`> element.</span></span> <span data-ttu-id="16b47-115">Debe actualizar la opción de proveedor de CompilerVersion para ambos tal y como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="16b47-115">You must update the CompilerVersion provider option for both as shown in the following example.</span></span>  
  
    ```xml  
    <system.codedom>  
          <compilers>  
            <compiler language="c#;cs;csharp" extension=".cs" warningLevel="4"  
                      type="Microsoft.CSharp.CSharpCodeProvider, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
              <providerOption name="CompilerVersion" value="v3.5"/>  
              <providerOption name="WarnAsError" value="false"/>  
            </compiler>  
            <compiler language="vb;vbs;visualbasic;vbscript" extension=".vb" warningLevel="4"  
                      type="Microsoft.VisualBasic.VBCodeProvider, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
              <providerOption name="CompilerVersion" value="v3.5"/>  
              <providerOption name="OptionInfer" value="true"/>  
              <providerOption name="WarnAsError" value="false"/>  
            </compiler>  
          </compilers>  
        </system.codedom>  
    ```
