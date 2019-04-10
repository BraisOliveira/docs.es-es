---
title: Filtrar para crear objetos gráficos para dibujar
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- graphics [Windows Forms], creating
- images [Windows Forms], creating
- GDI+, creating images
ms.assetid: 162861f9-f050-445e-8abb-b2c43a918b8b
ms.openlocfilehash: 79eae4d37c056fc95ac73c78e00dd1a2b68bcd24
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59324206"
---
# <a name="how-to-create-graphics-objects-for-drawing"></a><span data-ttu-id="b1dbb-102">Filtrar para crear objetos gráficos para dibujar</span><span class="sxs-lookup"><span data-stu-id="b1dbb-102">How to: Create Graphics Objects for Drawing</span></span>
<span data-ttu-id="b1dbb-103">Antes de poder dibujar líneas y formas, representar texto o mostrar y manipular imágenes con [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], deberá crear un <xref:System.Drawing.Graphics> objeto.</span><span class="sxs-lookup"><span data-stu-id="b1dbb-103">Before you can draw lines and shapes, render text, or display and manipulate images with [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], you need to create a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="b1dbb-104">El <xref:System.Drawing.Graphics> objeto representa un [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] superficie de dibujo, y es el objeto que se usa para crear imágenes gráficas.</span><span class="sxs-lookup"><span data-stu-id="b1dbb-104">The <xref:System.Drawing.Graphics> object represents a [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] drawing surface, and is the object that is used to create graphical images.</span></span>  
  
 <span data-ttu-id="b1dbb-105">Trabajar con gráficos, hay dos pasos:</span><span class="sxs-lookup"><span data-stu-id="b1dbb-105">There are two steps in working with graphics:</span></span>  
  
1. <span data-ttu-id="b1dbb-106">Creación de un <xref:System.Drawing.Graphics> objeto.</span><span class="sxs-lookup"><span data-stu-id="b1dbb-106">Creating a <xref:System.Drawing.Graphics> object.</span></span>  
  
2. <span data-ttu-id="b1dbb-107">Mediante el <xref:System.Drawing.Graphics> objeto para dibujar líneas y formas, representar texto o mostrar y manipular imágenes.</span><span class="sxs-lookup"><span data-stu-id="b1dbb-107">Using the <xref:System.Drawing.Graphics> object to draw lines and shapes, render text, or display and manipulate images.</span></span>  
  
## <a name="creating-a-graphics-object"></a><span data-ttu-id="b1dbb-108">Creación de un objeto Graphics</span><span class="sxs-lookup"><span data-stu-id="b1dbb-108">Creating a Graphics Object</span></span>  
 <span data-ttu-id="b1dbb-109">Un objeto graphics puede crearse en una variedad de formas.</span><span class="sxs-lookup"><span data-stu-id="b1dbb-109">A graphics object can be created in a variety of ways.</span></span>  
  
#### <a name="to-create-a-graphics-object"></a><span data-ttu-id="b1dbb-110">Para crear un objeto graphics</span><span class="sxs-lookup"><span data-stu-id="b1dbb-110">To create a graphics object</span></span>  
  
-   <span data-ttu-id="b1dbb-111">Reciba una referencia a un objeto graphics como parte de la <xref:System.Windows.Forms.PaintEventArgs> en el <xref:System.Windows.Forms.Control.Paint> eventos de un formulario o control.</span><span class="sxs-lookup"><span data-stu-id="b1dbb-111">Receive a reference to a graphics object as part of the <xref:System.Windows.Forms.PaintEventArgs> in the <xref:System.Windows.Forms.Control.Paint> event of a form or control.</span></span> <span data-ttu-id="b1dbb-112">Normalmente, esto es cómo obtener una referencia a un objeto graphics al crear el código de dibujo de un control.</span><span class="sxs-lookup"><span data-stu-id="b1dbb-112">This is usually how you obtain a reference to a graphics object when creating painting code for a control.</span></span> <span data-ttu-id="b1dbb-113">De forma similar, también se puede obtener un objeto graphics como una propiedad de la <xref:System.Drawing.Printing.PrintPageEventArgs> al controlar la <xref:System.Drawing.Printing.PrintDocument.PrintPage> eventos para un <xref:System.Drawing.Printing.PrintDocument>.</span><span class="sxs-lookup"><span data-stu-id="b1dbb-113">Similarly, you can also obtain a graphics object as a property of the <xref:System.Drawing.Printing.PrintPageEventArgs> when handling the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event for a <xref:System.Drawing.Printing.PrintDocument>.</span></span>  
  
     <span data-ttu-id="b1dbb-114">-o bien-</span><span class="sxs-lookup"><span data-stu-id="b1dbb-114">-or-</span></span>  
  
-   <span data-ttu-id="b1dbb-115">Llame a la <xref:System.Windows.Forms.Control.CreateGraphics%2A> método de un control o formulario para obtener una referencia a un <xref:System.Drawing.Graphics> objeto que representa la superficie de dibujo de dicho control o formulario.</span><span class="sxs-lookup"><span data-stu-id="b1dbb-115">Call the <xref:System.Windows.Forms.Control.CreateGraphics%2A> method of a control or form to obtain a reference to a <xref:System.Drawing.Graphics> object that represents the drawing surface of that control or form.</span></span> <span data-ttu-id="b1dbb-116">Utilice este método si desea que se va a dibujar en un formulario o control que ya existe.</span><span class="sxs-lookup"><span data-stu-id="b1dbb-116">Use this method if you want to draw on a form or control that already exists.</span></span>  
  
     <span data-ttu-id="b1dbb-117">-o bien-</span><span class="sxs-lookup"><span data-stu-id="b1dbb-117">-or-</span></span>  
  
-   <span data-ttu-id="b1dbb-118">Crear un <xref:System.Drawing.Graphics> objeto de cualquier objeto que hereda de <xref:System.Drawing.Image>.</span><span class="sxs-lookup"><span data-stu-id="b1dbb-118">Create a <xref:System.Drawing.Graphics> object from any object that inherits from <xref:System.Drawing.Image>.</span></span> <span data-ttu-id="b1dbb-119">Este enfoque es útil cuando desea modificar una imagen ya existente.</span><span class="sxs-lookup"><span data-stu-id="b1dbb-119">This approach is useful when you want to alter an already existing image.</span></span>  
  
     <span data-ttu-id="b1dbb-120">Las secciones siguientes proporcionan detalles sobre cada uno de estos procesos.</span><span class="sxs-lookup"><span data-stu-id="b1dbb-120">The following sections give details about each of these processes.</span></span>  
  
## <a name="painteventargs-in-the-paint-event-handler"></a><span data-ttu-id="b1dbb-121">PaintEventArgs en el controlador de eventos Paint</span><span class="sxs-lookup"><span data-stu-id="b1dbb-121">PaintEventArgs in the Paint Event Handler</span></span>  
 <span data-ttu-id="b1dbb-122">Al programar el <xref:System.Windows.Forms.PaintEventHandler> para los controles o el <xref:System.Drawing.Printing.PrintDocument.PrintPage> para un <xref:System.Drawing.Printing.PrintDocument>, un objeto graphics se proporciona como una de las propiedades de <xref:System.Windows.Forms.PaintEventArgs> o <xref:System.Drawing.Printing.PrintPageEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="b1dbb-122">When programming the <xref:System.Windows.Forms.PaintEventHandler> for controls or the <xref:System.Drawing.Printing.PrintDocument.PrintPage> for a <xref:System.Drawing.Printing.PrintDocument>, a graphics object is provided as one of the properties of <xref:System.Windows.Forms.PaintEventArgs> or <xref:System.Drawing.Printing.PrintPageEventArgs>.</span></span>  
  
#### <a name="to-obtain-a-reference-to-a-graphics-object-from-the-painteventargs-in-the-paint-event"></a><span data-ttu-id="b1dbb-123">Para obtener una referencia a un objeto Graphics desde PaintEventArgs en el evento Paint</span><span class="sxs-lookup"><span data-stu-id="b1dbb-123">To obtain a reference to a Graphics object from the PaintEventArgs in the Paint event</span></span>  
  
1. <span data-ttu-id="b1dbb-124">Declare el <xref:System.Drawing.Graphics> objeto.</span><span class="sxs-lookup"><span data-stu-id="b1dbb-124">Declare the <xref:System.Drawing.Graphics> object.</span></span>  
  
2. <span data-ttu-id="b1dbb-125">Asigne la variable para hacer referencia a la <xref:System.Drawing.Graphics> objeto pasado como parte de la <xref:System.Windows.Forms.PaintEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="b1dbb-125">Assign the variable to refer to the <xref:System.Drawing.Graphics> object passed as part of the <xref:System.Windows.Forms.PaintEventArgs>.</span></span>  
  
3. <span data-ttu-id="b1dbb-126">Inserte código para dibujar el formulario o control.</span><span class="sxs-lookup"><span data-stu-id="b1dbb-126">Insert code to paint the form or control.</span></span>  
  
     <span data-ttu-id="b1dbb-127">El ejemplo siguiente muestra cómo hacer referencia a un <xref:System.Drawing.Graphics> objeto desde el <xref:System.Windows.Forms.PaintEventArgs> en el <xref:System.Windows.Forms.Control.Paint> eventos:</span><span class="sxs-lookup"><span data-stu-id="b1dbb-127">The following example shows how to reference a <xref:System.Drawing.Graphics> object from the <xref:System.Windows.Forms.PaintEventArgs> in the <xref:System.Windows.Forms.Control.Paint> event:</span></span>  
  
    ```vb  
    Private Sub Form1_Paint(sender As Object, pe As PaintEventArgs) Handles _  
       MyBase.Paint  
       ' Declares the Graphics object and sets it to the Graphics object  
       ' supplied in the PaintEventArgs.  
       Dim g As Graphics = pe.Graphics  
       ' Insert code to paint the form here.  
    End Sub  
    ```  
  
    ```csharp  
    private void Form1_Paint(object sender,   
       System.Windows.Forms.PaintEventArgs pe)   
    {  
       // Declares the Graphics object and sets it to the Graphics object  
       // supplied in the PaintEventArgs.  
       Graphics g = pe.Graphics;  
       // Insert code to paint the form here.  
    }  
    ```  
  
    ```cpp  
    private:  
       void Form1_Paint(System::Object ^ sender,  
          System::Windows::Forms::PaintEventArgs ^ pe)  
       {  
          // Declares the Graphics object and sets it to the Graphics object  
          // supplied in the PaintEventArgs.  
          Graphics ^ g = pe->Graphics;  
          // Insert code to paint the form here.  
       }  
    ```  
  
## <a name="creategraphics-method"></a><span data-ttu-id="b1dbb-128">Método CreateGraphics</span><span class="sxs-lookup"><span data-stu-id="b1dbb-128">CreateGraphics Method</span></span>  
 <span data-ttu-id="b1dbb-129">También puede usar el <xref:System.Windows.Forms.Control.CreateGraphics%2A> método de un control o formulario para obtener una referencia a un <xref:System.Drawing.Graphics> objeto que representa la superficie de dibujo de dicho control o formulario.</span><span class="sxs-lookup"><span data-stu-id="b1dbb-129">You can also use the <xref:System.Windows.Forms.Control.CreateGraphics%2A> method of a control or form to obtain a reference to a <xref:System.Drawing.Graphics> object that represents the drawing surface of that control or form.</span></span>  
  
#### <a name="to-create-a-graphics-object-with-the-creategraphics-method"></a><span data-ttu-id="b1dbb-130">Para crear un objeto de gráficos con el método CreateGraphics</span><span class="sxs-lookup"><span data-stu-id="b1dbb-130">To create a Graphics object with the CreateGraphics method</span></span>  
  
-   <span data-ttu-id="b1dbb-131">Llame a la <xref:System.Windows.Forms.Control.CreateGraphics%2A> método del formulario o control en el que desea representar gráficos.</span><span class="sxs-lookup"><span data-stu-id="b1dbb-131">Call the <xref:System.Windows.Forms.Control.CreateGraphics%2A> method of the form or control upon which you want to render graphics.</span></span>  
  
    ```vb  
    Dim g as Graphics  
    ' Sets g to a Graphics object representing the drawing surface of the  
    ' control or form g is a member of.  
    g = Me.CreateGraphics  
    ```  
  
    ```csharp  
    Graphics g;  
    // Sets g to a graphics object representing the drawing surface of the  
    // control or form g is a member of.  
    g = this.CreateGraphics();  
    ```  
  
    ```cpp  
    Graphics ^ g;  
    // Sets g to a graphics object representing the drawing surface of the  
    // control or form g is a member of.  
    g = this->CreateGraphics();  
    ```  
  
## <a name="create-from-an-image-object"></a><span data-ttu-id="b1dbb-132">Crear a partir de un objeto de imagen</span><span class="sxs-lookup"><span data-stu-id="b1dbb-132">Create from an Image Object</span></span>  
 <span data-ttu-id="b1dbb-133">Además, puede crear un objeto graphics de cualquier objeto que se deriva el <xref:System.Drawing.Image> clase.</span><span class="sxs-lookup"><span data-stu-id="b1dbb-133">Additionally, you can create a graphics object from any object that derives from the <xref:System.Drawing.Image> class.</span></span>  
  
#### <a name="to-create-a-graphics-object-from-an-image"></a><span data-ttu-id="b1dbb-134">Para crear un objeto de gráficos desde una imagen</span><span class="sxs-lookup"><span data-stu-id="b1dbb-134">To create a Graphics object from an Image</span></span>  
  
-   <span data-ttu-id="b1dbb-135">Llame a la <xref:System.Drawing.Graphics.FromImage%2A?displayProperty=nameWithType> método, proporcionando el nombre de la variable de la imagen desde el que desea crear un <xref:System.Drawing.Graphics> objeto.</span><span class="sxs-lookup"><span data-stu-id="b1dbb-135">Call the <xref:System.Drawing.Graphics.FromImage%2A?displayProperty=nameWithType> method, supplying the name of the Image variable from which you want to create a <xref:System.Drawing.Graphics> object.</span></span>  
  
     <span data-ttu-id="b1dbb-136">El ejemplo siguiente muestra cómo usar un <xref:System.Drawing.Bitmap> objeto:</span><span class="sxs-lookup"><span data-stu-id="b1dbb-136">The following example shows how to use a <xref:System.Drawing.Bitmap> object:</span></span>  
  
    ```vb  
    Dim myBitmap as New Bitmap("C:\Documents and Settings\Joe\Pics\myPic.bmp")  
    Dim g as Graphics = Graphics.FromImage(myBitmap)  
    ```  
  
    ```csharp  
    Bitmap myBitmap = new Bitmap(@"C:\Documents and   
       Settings\Joe\Pics\myPic.bmp");  
    Graphics g = Graphics.FromImage(myBitmap);  
    ```  
  
    ```cpp  
    Bitmap ^ myBitmap = gcnew  
       Bitmap("D:\\Documents and Settings\\Joe\\Pics\\myPic.bmp");  
    Graphics ^ g = Graphics::FromImage(myBitmap);  
    ```  
  
> [!NOTE]
>  <span data-ttu-id="b1dbb-137">Solo se puede crear <xref:System.Drawing.Graphics> objetos desde los archivos .bmp no indizados, como los archivos .bmp 16, 24 y 32 bits.</span><span class="sxs-lookup"><span data-stu-id="b1dbb-137">You can only create <xref:System.Drawing.Graphics> objects from nonindexed .bmp files, such as 16-bit, 24-bit, and 32-bit .bmp files.</span></span> <span data-ttu-id="b1dbb-138">Cada píxel de archivos .bmp no indizada contiene un color, a diferencia de píxeles de los archivos .bmp indizados, que contienen un índice a una tabla de colores.</span><span class="sxs-lookup"><span data-stu-id="b1dbb-138">Each pixel of nonindexed .bmp files holds a color, in contrast to pixels of indexed .bmp files, which hold an index to a color table.</span></span>  
  
## <a name="drawing-and-manipulating-shapes-and-images"></a><span data-ttu-id="b1dbb-139">Dibujar y manipular formas e imágenes</span><span class="sxs-lookup"><span data-stu-id="b1dbb-139">Drawing and Manipulating Shapes and Images</span></span>  
 <span data-ttu-id="b1dbb-140">Después de crearlo, un <xref:System.Drawing.Graphics> objeto puede utilizarse para dibujar líneas y formas, representar texto o mostrar y manipular imágenes.</span><span class="sxs-lookup"><span data-stu-id="b1dbb-140">After it is created, a <xref:System.Drawing.Graphics> object may be used to draw lines and shapes, render text, or display and manipulate images.</span></span> <span data-ttu-id="b1dbb-141">Los objetos principales que se usan con el <xref:System.Drawing.Graphics> objeto son:</span><span class="sxs-lookup"><span data-stu-id="b1dbb-141">The principal objects that are used with the <xref:System.Drawing.Graphics> object are:</span></span>  
  
-   <span data-ttu-id="b1dbb-142">La <xref:System.Drawing.Pen> clase, utilizado para dibujar líneas, formas de esquematización o representar otros elementos geométricos.</span><span class="sxs-lookup"><span data-stu-id="b1dbb-142">The <xref:System.Drawing.Pen> class—Used for drawing lines, outlining shapes, or rendering other geometric representations.</span></span>  
  
-   <span data-ttu-id="b1dbb-143">La <xref:System.Drawing.Brush> clase, utiliza para rellenar las áreas de gráficos, como formas rellenas, imágenes o texto.</span><span class="sxs-lookup"><span data-stu-id="b1dbb-143">The <xref:System.Drawing.Brush> class—Used for filling areas of graphics, such as filled shapes, images, or text.</span></span>  
  
-   <span data-ttu-id="b1dbb-144">La <xref:System.Drawing.Font> clase, proporciona una descripción de las formas que se utilizan al representar texto.</span><span class="sxs-lookup"><span data-stu-id="b1dbb-144">The <xref:System.Drawing.Font> class—Provides a description of what shapes to use when rendering text.</span></span>  
  
-   <span data-ttu-id="b1dbb-145">El <xref:System.Drawing.Color> estructura, representa los distintos colores para mostrar.</span><span class="sxs-lookup"><span data-stu-id="b1dbb-145">The <xref:System.Drawing.Color> structure—Represents the different colors to display.</span></span>  
  
#### <a name="to-use-the-graphics-object-you-have-created"></a><span data-ttu-id="b1dbb-146">Para usar el objeto Graphics que ha creado</span><span class="sxs-lookup"><span data-stu-id="b1dbb-146">To use the Graphics object you have created</span></span>  
  
-   <span data-ttu-id="b1dbb-147">Trabajar con el objeto apropiado enumerado anteriormente para dibujar lo que necesita.</span><span class="sxs-lookup"><span data-stu-id="b1dbb-147">Work with the appropriate object listed above to draw what you need.</span></span>  
  
     <span data-ttu-id="b1dbb-148">Para obtener más información, vea los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="b1dbb-148">For more information, see the following topics:</span></span>  
  
    |<span data-ttu-id="b1dbb-149">Para representar</span><span class="sxs-lookup"><span data-stu-id="b1dbb-149">To render</span></span>|<span data-ttu-id="b1dbb-150">Vea</span><span class="sxs-lookup"><span data-stu-id="b1dbb-150">See</span></span>|  
    |---------------|---------|  
    |<span data-ttu-id="b1dbb-151">Líneas</span><span class="sxs-lookup"><span data-stu-id="b1dbb-151">Lines</span></span>|[<span data-ttu-id="b1dbb-152">Filtrar para dibujar una línea en un formulario Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b1dbb-152">How to: Draw a Line on a Windows Form</span></span>](how-to-draw-a-line-on-a-windows-form.md)|  
    |<span data-ttu-id="b1dbb-153">Formas</span><span class="sxs-lookup"><span data-stu-id="b1dbb-153">Shapes</span></span>|[<span data-ttu-id="b1dbb-154">Filtrar para dibujar una forma con contorno</span><span class="sxs-lookup"><span data-stu-id="b1dbb-154">How to: Draw an Outlined Shape</span></span>](how-to-draw-an-outlined-shape.md)|  
    |<span data-ttu-id="b1dbb-155">Texto</span><span class="sxs-lookup"><span data-stu-id="b1dbb-155">Text</span></span>|[<span data-ttu-id="b1dbb-156">Filtrar para dibujar texto en un formulario Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b1dbb-156">How to: Draw Text on a Windows Form</span></span>](how-to-draw-text-on-a-windows-form.md)|  
    |<span data-ttu-id="b1dbb-157">Imágenes</span><span class="sxs-lookup"><span data-stu-id="b1dbb-157">Images</span></span>|[<span data-ttu-id="b1dbb-158">Filtrar para representar imágenes con GDI+</span><span class="sxs-lookup"><span data-stu-id="b1dbb-158">How to: Render Images with GDI+</span></span>](how-to-render-images-with-gdi.md)|  
  
## <a name="see-also"></a><span data-ttu-id="b1dbb-159">Vea también</span><span class="sxs-lookup"><span data-stu-id="b1dbb-159">See also</span></span>

- [<span data-ttu-id="b1dbb-160">Introducción a la programación de gráficos</span><span class="sxs-lookup"><span data-stu-id="b1dbb-160">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="b1dbb-161">Gráficos y dibujos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b1dbb-161">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="b1dbb-162">Líneas, curvas y formas</span><span class="sxs-lookup"><span data-stu-id="b1dbb-162">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="b1dbb-163">Filtrar para representar imágenes con GDI+</span><span class="sxs-lookup"><span data-stu-id="b1dbb-163">How to: Render Images with GDI+</span></span>](how-to-render-images-with-gdi.md)
