---
title: Procedimiento Usar claves de fuentes del sistema
ms.date: 03/30/2017
helpviewer_keywords:
- resource keys [WPF], SystemFonts class
ms.assetid: 036ebea7-5677-4f60-8ba4-56c9f9d9b8bd
ms.openlocfilehash: 7283e4225b75909322fa312583e9f1a0679762e2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918387"
---
# <a name="how-to-use-system-fonts-keys"></a><span data-ttu-id="37845-102">Procedimiento Usar claves de fuentes del sistema</span><span class="sxs-lookup"><span data-stu-id="37845-102">How to: Use System Fonts Keys</span></span>
<span data-ttu-id="37845-103">Los recursos del sistema exponen varias métricas del sistema como recursos para ayudar a los desarrolladores a crear efectos visuales coherentes con la configuración del sistema.</span><span class="sxs-lookup"><span data-stu-id="37845-103">System resources expose a number of system metrics as resources to help developers create visuals that are consistent with system settings.</span></span> <span data-ttu-id="37845-104"><xref:System.Windows.SystemFonts>es una clase que contiene los valores de fuente del sistema y los recursos de fuente del sistema que se enlazan <xref:System.Windows.SystemFonts.CaptionFontFamily%2A> a <xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A>los valores; por ejemplo, y.</span><span class="sxs-lookup"><span data-stu-id="37845-104"><xref:System.Windows.SystemFonts> is a class that contains both system font values and system font resources that bind to the values—for example, <xref:System.Windows.SystemFonts.CaptionFontFamily%2A> and <xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A>.</span></span>  
  
 <span data-ttu-id="37845-105">La métricas de fuentes del sistema se pueden usar como recursos estáticos o dinámicos.</span><span class="sxs-lookup"><span data-stu-id="37845-105">System font metrics can be used as either static or dynamic resources.</span></span> <span data-ttu-id="37845-106">Use un recurso dinámico si quiere que la métrica de fuentes se actualice automáticamente mientras se ejecuta la aplicación. De lo contrario, use un recurso estático.</span><span class="sxs-lookup"><span data-stu-id="37845-106">Use a dynamic resource if you want the font metric to update automatically while the application runs; otherwise use a static resource.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="37845-107">Los recursos dinámicos tienen la palabra *clave* keyword anexada al nombre de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="37845-107">Dynamic resources have the keyword *Key* appended to the property name.</span></span>  
  
 <span data-ttu-id="37845-108">En el ejemplo siguiente se muestra cómo obtener acceso y usar los recursos dinámicos de fuentes del sistema para aplicar estilo a un botón o personalizarlo.</span><span class="sxs-lookup"><span data-stu-id="37845-108">The following example shows how to access and use system font dynamic resources to style or customize a button.</span></span> <span data-ttu-id="37845-109">En [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] este ejemplo se crea un estilo de botón que <xref:System.Windows.SystemFonts> asigna valores a un botón.</span><span class="sxs-lookup"><span data-stu-id="37845-109">This [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] example creates a button style that assigns <xref:System.Windows.SystemFonts> values to a button.</span></span>  
  
## <a name="example"></a><span data-ttu-id="37845-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="37845-110">Example</span></span>  
 [!code-xaml[SystemRes_snip#FontDynamicResources](~/samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/MyApp.xaml#fontdynamicresources)]  
  
## <a name="see-also"></a><span data-ttu-id="37845-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="37845-111">See also</span></span>

- [<span data-ttu-id="37845-112">Pintar un área con un pincel del sistema</span><span class="sxs-lookup"><span data-stu-id="37845-112">Paint an Area with a System Brush</span></span>](../graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)
- [<span data-ttu-id="37845-113">Usar SystemParameters</span><span class="sxs-lookup"><span data-stu-id="37845-113">Use SystemParameters</span></span>](how-to-use-systemparameters.md)
- [<span data-ttu-id="37845-114">Usar SystemFonts</span><span class="sxs-lookup"><span data-stu-id="37845-114">Use SystemFonts</span></span>](how-to-use-systemfonts.md)
