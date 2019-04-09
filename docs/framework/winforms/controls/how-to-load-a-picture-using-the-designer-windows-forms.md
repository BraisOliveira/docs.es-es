---
title: Filtrar Cargar una imagen mediante el diseñador (formularios Windows Forms)
ms.date: 03/30/2017
helpviewer_keywords:
- picture formats
- images [Windows Forms], displaying on Windows Forms
- pictures [Windows Forms], displaying
- forms [Windows Forms], displaying images
- PictureBox control [Windows Forms], adding pictures
ms.assetid: 4dc7b973-afb1-4276-8322-20825af96655
ms.openlocfilehash: 5aa8ff1efa045d52382cc5c24a0cae1f0f1bb510
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59127145"
---
# <a name="how-to-load-a-picture-using-the-designer-windows-forms"></a><span data-ttu-id="10078-102">Filtrar Cargar una imagen mediante el diseñador (formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="10078-102">How to: Load a Picture Using the Designer (Windows Forms)</span></span>
<span data-ttu-id="10078-103">Con los formularios de Windows <xref:System.Windows.Forms.PictureBox> control, puede cargar y mostrar una imagen en un formulario en tiempo de diseño estableciendo el <xref:System.Windows.Forms.PictureBox.Image%2A> propiedad en una imagen válida.</span><span class="sxs-lookup"><span data-stu-id="10078-103">With the Windows Forms <xref:System.Windows.Forms.PictureBox> control, you can load and display a picture on a form at design time by setting the <xref:System.Windows.Forms.PictureBox.Image%2A> property to a valid picture.</span></span> <span data-ttu-id="10078-104">En la tabla siguiente se muestra los tipos de archivo aceptables.</span><span class="sxs-lookup"><span data-stu-id="10078-104">The following table shows the acceptable file types.</span></span>  
  
|<span data-ttu-id="10078-105">Tipo</span><span class="sxs-lookup"><span data-stu-id="10078-105">Type</span></span>|<span data-ttu-id="10078-106">Extensión de nombre de archivo</span><span class="sxs-lookup"><span data-stu-id="10078-106">File name extension</span></span>|  
|----------|-------------------------|  
|<span data-ttu-id="10078-107">Bitmap</span><span class="sxs-lookup"><span data-stu-id="10078-107">Bitmap</span></span>|<span data-ttu-id="10078-108">.bmp</span><span class="sxs-lookup"><span data-stu-id="10078-108">.bmp</span></span>|  
|<span data-ttu-id="10078-109">Iconos</span><span class="sxs-lookup"><span data-stu-id="10078-109">Icon</span></span>|<span data-ttu-id="10078-110">.ico</span><span class="sxs-lookup"><span data-stu-id="10078-110">.ico</span></span>|  
|<span data-ttu-id="10078-111">GIF</span><span class="sxs-lookup"><span data-stu-id="10078-111">GIF</span></span>|<span data-ttu-id="10078-112">.gif</span><span class="sxs-lookup"><span data-stu-id="10078-112">.gif</span></span>|  
|<span data-ttu-id="10078-113">Metarchivo</span><span class="sxs-lookup"><span data-stu-id="10078-113">Metafile</span></span>|<span data-ttu-id="10078-114">.wmf</span><span class="sxs-lookup"><span data-stu-id="10078-114">.wmf</span></span>|  
|<span data-ttu-id="10078-115">JPEG</span><span class="sxs-lookup"><span data-stu-id="10078-115">JPEG</span></span>|<span data-ttu-id="10078-116">.jpg</span><span class="sxs-lookup"><span data-stu-id="10078-116">.jpg</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="10078-117">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="10078-117">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="10078-118">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="10078-118">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="10078-119">Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="10078-119">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-display-a-picture-at-design-time"></a><span data-ttu-id="10078-120">Para mostrar una imagen en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="10078-120">To display a picture at design time</span></span>  
  
1.  <span data-ttu-id="10078-121">Dibujar un <xref:System.Windows.Forms.PictureBox> control en un formulario.</span><span class="sxs-lookup"><span data-stu-id="10078-121">Draw a <xref:System.Windows.Forms.PictureBox> control on a form.</span></span>  
  
2.  <span data-ttu-id="10078-122">En la ventana Propiedades, seleccione la <xref:System.Windows.Forms.PictureBox.Image%2A> propiedad y, a continuación, haga clic en botón de puntos suspensivos para mostrar el **abierto** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="10078-122">On the Properties window, select the <xref:System.Windows.Forms.PictureBox.Image%2A> property, then click the ellipsis button to display the **Open** dialog box.</span></span>  
  
3.  <span data-ttu-id="10078-123">Si busca un tipo de archivo específico (por ejemplo, archivos .gif), selecciónelo en la **archivos de tipo** cuadro.</span><span class="sxs-lookup"><span data-stu-id="10078-123">If you are looking for a specific file type (for example, .gif files), select it in the **Files of type** box.</span></span>  
  
4.  <span data-ttu-id="10078-124">Seleccione el archivo que desea mostrar.</span><span class="sxs-lookup"><span data-stu-id="10078-124">Select the file you want to display.</span></span>  
  
### <a name="to-clear-the-picture-at-design-time"></a><span data-ttu-id="10078-125">Para borrar la imagen en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="10078-125">To clear the picture at design time</span></span>  
  
1.  <span data-ttu-id="10078-126">En el **propiedades** ventana, seleccione el <xref:System.Windows.Forms.PictureBox.Image%2A> propiedad y con el botón secundario en la imagen en miniatura que aparece a la izquierda del nombre del objeto de imagen.</span><span class="sxs-lookup"><span data-stu-id="10078-126">On the **Properties** window, select the <xref:System.Windows.Forms.PictureBox.Image%2A> property and right-click the small thumbnail image that appears to the left of the name of the image object.</span></span> <span data-ttu-id="10078-127">Elija **restablecer**.</span><span class="sxs-lookup"><span data-stu-id="10078-127">Choose **Reset**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10078-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="10078-128">See also</span></span>

- <xref:System.Windows.Forms.PictureBox>
- [<span data-ttu-id="10078-129">Información general sobre el control PictureBox</span><span class="sxs-lookup"><span data-stu-id="10078-129">PictureBox Control Overview</span></span>](picturebox-control-overview-windows-forms.md)
- [<span data-ttu-id="10078-130">Filtrar para modificar el tamaño o la situación de una imagen en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="10078-130">How to: Modify the Size or Placement of a Picture at Run Time</span></span>](how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)
- [<span data-ttu-id="10078-131">Filtrar para establecer imágenes en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="10078-131">How to: Set Pictures at Run Time</span></span>](how-to-set-pictures-at-run-time-windows-forms.md)
- [<span data-ttu-id="10078-132">Control PictureBox</span><span class="sxs-lookup"><span data-stu-id="10078-132">PictureBox Control</span></span>](picturebox-control-windows-forms.md)
