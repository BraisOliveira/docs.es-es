---
title: Crear un proveedor de UI Automation en el cliente
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UI Automation, creating client-side provider
- client-side UI Automation provider, creating
ms.assetid: d91edaf2-be28-41ec-a508-af421cb43c3d
ms.openlocfilehash: df6de47f3ed7373f9065ff7035df90ff09d150c9
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2019
ms.locfileid: "57678298"
---
# <a name="create-a-client-side-ui-automation-provider"></a><span data-ttu-id="a8d9e-102">Crear un proveedor de UI Automation en el cliente</span><span class="sxs-lookup"><span data-stu-id="a8d9e-102">Create a Client-Side UI Automation Provider</span></span>
> [!NOTE]
>  <span data-ttu-id="a8d9e-103">Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="a8d9e-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="a8d9e-104">Para obtener información más reciente sobre [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: Automatización de interfaz de usuario](https://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="a8d9e-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="a8d9e-105">Este tema contiene código de ejemplo que muestra cómo implementar un proveedor de Automatización de la interfaz de usuario del lado cliente.</span><span class="sxs-lookup"><span data-stu-id="a8d9e-105">This topic contains example code that shows how to implement a client-side UI Automation provider.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a8d9e-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a8d9e-106">Example</span></span>  
 <span data-ttu-id="a8d9e-107">El ejemplo de código siguiente se puede compilar en un archivo [!INCLUDE[TLA#tla_dll](../../../includes/tlasharptla-dll-md.md)] que implemente un proveedor de cliente muy simple para una ventana de consola.</span><span class="sxs-lookup"><span data-stu-id="a8d9e-107">The following example code can be built into a [!INCLUDE[TLA#tla_dll](../../../includes/tlasharptla-dll-md.md)] that implements a very simple client-side provider for a console window.</span></span> <span data-ttu-id="a8d9e-108">El código no tiene ninguna funcionalidad práctica, pero está pensado para mostrar los pasos básicos para configurar un ensamblado de proveedor que se pueda registrar mediante una aplicación de cliente de Automatización de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="a8d9e-108">The code does not have any useful functionality, but is intended to demonstrate the basic steps in setting up a provider assembly that can be registered by a UI Automation client application.</span></span>  
  
 [!code-csharp[UIAClientSideProvider_snip#101](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClientSideProvider_snip/CSharp/CSProviderProgram.cs#101)]
 [!code-vb[UIAClientSideProvider_snip#101](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClientSideProvider_snip/visualbasic/csproviderprogram.vb#101)]  
  
## <a name="see-also"></a><span data-ttu-id="a8d9e-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="a8d9e-109">See also</span></span>
- [<span data-ttu-id="a8d9e-110">Información general sobre proveedores de la Automatización de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="a8d9e-110">UI Automation Providers Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-providers-overview.md)
- [<span data-ttu-id="a8d9e-111">Registro de un ensamblado de proveedor del lado cliente</span><span class="sxs-lookup"><span data-stu-id="a8d9e-111">Register a Client-Side Provider Assembly</span></span>](../../../docs/framework/ui-automation/register-a-client-side-provider-assembly.md)
