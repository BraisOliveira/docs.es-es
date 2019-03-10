---
title: Filtrar Agregar o quitar imágenes con el componente ImageList de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- images [Windows Forms], removing from ImageList component
- images [Windows Forms], storing for controls
- ImageList component [Windows Forms], adding images
- ImageList component [Windows Forms], removing images
- images [Windows Forms], adding to ImageList component
- images [Windows Forms], displaying with controls
ms.assetid: c5eacc56-f769-4e2e-bfb7-f756620913db
ms.openlocfilehash: 81c85186d2f15917a6aa1067814a0119edf3f460
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57705173"
---
# <a name="how-to-add-or-remove-images-with-the-windows-forms-imagelist-component"></a><span data-ttu-id="2d4bc-102">Procedimiento Agregar o quitar imágenes con el componente ImageList de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2d4bc-102">How to: Add or Remove Images with the Windows Forms ImageList Component</span></span>
<span data-ttu-id="2d4bc-103">Los formularios de Windows <xref:System.Windows.Forms.ImageList> componente normalmente se rellena con las imágenes antes de asociarlo con un control.</span><span class="sxs-lookup"><span data-stu-id="2d4bc-103">The Windows Forms <xref:System.Windows.Forms.ImageList> component is typically populated with images before it is associated with a control.</span></span> <span data-ttu-id="2d4bc-104">Sin embargo, puede agregar y quitar imágenes después de asociar la lista de imágenes con un control.</span><span class="sxs-lookup"><span data-stu-id="2d4bc-104">However, you can add and remove images after associating the image list with a control.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2d4bc-105">Al quitar las imágenes, compruebe que la <xref:System.Windows.Forms.ButtonBase.ImageIndex%2A> sigue siendo válida la propiedad de los controles asociados.</span><span class="sxs-lookup"><span data-stu-id="2d4bc-105">When you remove images, verify that the <xref:System.Windows.Forms.ButtonBase.ImageIndex%2A> property of any associated controls is still valid.</span></span>  
  
### <a name="to-add-images-programmatically"></a><span data-ttu-id="2d4bc-106">Para agregar imágenes mediante programación</span><span class="sxs-lookup"><span data-stu-id="2d4bc-106">To add images programmatically</span></span>  
  
-   <span data-ttu-id="2d4bc-107">Use la <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> método de la lista de imágenes <xref:System.Windows.Forms.ImageList.Images%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="2d4bc-107">Use the <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> method of the image list's <xref:System.Windows.Forms.ImageList.Images%2A> property.</span></span>  
  
     <span data-ttu-id="2d4bc-108">En el ejemplo de código siguiente establece la ruta de acceso para la ubicación de la imagen es la **Mis documentos** carpeta.</span><span class="sxs-lookup"><span data-stu-id="2d4bc-108">In the following code example, the path set for the location of the image is the **My Documents** folder.</span></span> <span data-ttu-id="2d4bc-109">Se utiliza esta ubicación porque se puede suponer que la mayoría de los equipos que ejecuta el sistema operativo Windows incluirá esta carpeta.</span><span class="sxs-lookup"><span data-stu-id="2d4bc-109">This location is used because you can assume that most computers that are running the Windows operating system will include this folder.</span></span> <span data-ttu-id="2d4bc-110">Al elegir esta ubicación también permite a los usuarios que tienen acceso niveles mínimos más ejecutar de forma segura la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2d4bc-110">Choosing this location also lets users who have minimal system access levels more safely run the application.</span></span> <span data-ttu-id="2d4bc-111">El siguiente ejemplo de código requiere que tenga un formulario con un <xref:System.Windows.Forms.ImageList> control ya se ha agregado.</span><span class="sxs-lookup"><span data-stu-id="2d4bc-111">The following code example requires that you have a form with an <xref:System.Windows.Forms.ImageList> control already added.</span></span>  
  
    ```vb  
    Public Sub LoadImage()  
       Dim myImage As System.Drawing.Image = _  
         Image.FromFile _  
       (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Image.gif")  
       ImageList1.Images.Add(myImage)  
    End Sub  
    ```  
  
    ```csharp  
    public void addImage()  
    {  
    // Be sure that you use an appropriate escape sequence (such as the   
    // @) when specifying the location of the file.  
       System.Drawing.Image myImage =   
         Image.FromFile  
       (System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.Personal)  
       + @"\Image.gif");  
       imageList1.Images.Add(myImage);  
    }  
    ```  
  
    ```cpp  
    public:  
       void addImage()  
       {  
       // Replace the bold image in the following sample   
       // with your own icon.  
       // Be sure that you use an appropriate escape sequence (such as   
       // \\) when specifying the location of the file.  
          System::Drawing::Image ^ myImage =   
             Image::FromFile(String::Concat(  
             System::Environment::GetFolderPath(  
             System::Environment::SpecialFolder::Personal),  
             "\\Image.gif"));  
          imageList1->Images->Add(myImage);  
       }  
    ```  
  
### <a name="to-add-images-with-a-key-value"></a><span data-ttu-id="2d4bc-112">Para agregar las imágenes con un valor de clave.</span><span class="sxs-lookup"><span data-stu-id="2d4bc-112">To add images with a key value.</span></span>  
  
-   <span data-ttu-id="2d4bc-113">Utilice uno de los <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> métodos de la lista de imágenes <xref:System.Windows.Forms.ImageList.Images%2A> propiedad que toma un valor de clave.</span><span class="sxs-lookup"><span data-stu-id="2d4bc-113">Use one of the <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> methods of the image list's <xref:System.Windows.Forms.ImageList.Images%2A> property that takes a key value.</span></span>  
  
     <span data-ttu-id="2d4bc-114">En el ejemplo de código siguiente establece la ruta de acceso para la ubicación de la imagen es la **Mis documentos** carpeta.</span><span class="sxs-lookup"><span data-stu-id="2d4bc-114">In the following code example, the path set for the location of the image is the **My Documents** folder.</span></span> <span data-ttu-id="2d4bc-115">Se utiliza esta ubicación porque se puede suponer que la mayoría de los equipos que ejecuta el sistema operativo Windows incluirá esta carpeta.</span><span class="sxs-lookup"><span data-stu-id="2d4bc-115">This location is used because you can assume that most computers that are running the Windows operating system will include this folder.</span></span> <span data-ttu-id="2d4bc-116">Al elegir esta ubicación también permite a los usuarios que tienen acceso niveles mínimos más ejecutar de forma segura la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2d4bc-116">Choosing this location also lets users who have minimal system access levels more safely run the application.</span></span> <span data-ttu-id="2d4bc-117">El siguiente ejemplo de código requiere que tenga un formulario con un <xref:System.Windows.Forms.ImageList> control ya se ha agregado.</span><span class="sxs-lookup"><span data-stu-id="2d4bc-117">The following code example requires that you have a form with an <xref:System.Windows.Forms.ImageList> control already added.</span></span>  
  
    ```vb  
    Public Sub LoadImage()  
       Dim myImage As System.Drawing.Image = _  
         Image.FromFile _  
       (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Image.gif")  
       ImageList1.Images.Add("myPhoto", myImage)  
    End Sub  
    ```  
  
```csharp  
public void addImage()  
{  
// Be sure that you use an appropriate escape sequence (such as the   
// @) when specifying the location of the file.  
   System.Drawing.Image myImage =   
     Image.FromFile  
   (System.Environment.GetFolderPath  
   (System.Environment.SpecialFolder.Personal)  
   + @"\Image.gif");  
   imageList1.Images.Add("myPhoto", myImage);  
}  
```  
  
### <a name="to-remove-all-images-programmatically"></a><span data-ttu-id="2d4bc-118">Para quitar todas las imágenes mediante programación</span><span class="sxs-lookup"><span data-stu-id="2d4bc-118">To remove all images programmatically</span></span>  
  
-   <span data-ttu-id="2d4bc-119">Use el <xref:System.Windows.Forms.ImageList.ImageCollection.Remove%2A> método para quitar una sola imagen</span><span class="sxs-lookup"><span data-stu-id="2d4bc-119">Use the <xref:System.Windows.Forms.ImageList.ImageCollection.Remove%2A> method to remove a single image</span></span>  
  
     <span data-ttu-id="2d4bc-120">, - o -</span><span class="sxs-lookup"><span data-stu-id="2d4bc-120">,-or-</span></span>  
  
     <span data-ttu-id="2d4bc-121">Use el <xref:System.Windows.Forms.ImageList.ImageCollection.Clear%2A> método para borrar todas las imágenes en la lista de imágenes.</span><span class="sxs-lookup"><span data-stu-id="2d4bc-121">Use the <xref:System.Windows.Forms.ImageList.ImageCollection.Clear%2A> method to clear all images in the image list.</span></span>  
  
    ```vb  
    ' Removes the first image in the image list  
    ImageList1.Images.Remove(myImage)  
    ' Clears all images in the image list  
    ImageList1.Images.Clear()  
    ```  
  
```csharp  
// Removes the first image in the image list.  
imageList1.Images.Remove(myImage);  
// Clears all images in the image list.  
imageList1.Images.Clear();  
```  
  
### <a name="to-remove-images-by-key"></a><span data-ttu-id="2d4bc-122">Para quitar las imágenes por clave</span><span class="sxs-lookup"><span data-stu-id="2d4bc-122">To remove images by key</span></span>  
  
-   <span data-ttu-id="2d4bc-123">Use el <xref:System.Windows.Forms.ImageList.ImageCollection.RemoveByKey%2A> método para quitar una sola imagen por su clave.</span><span class="sxs-lookup"><span data-stu-id="2d4bc-123">Use the <xref:System.Windows.Forms.ImageList.ImageCollection.RemoveByKey%2A> method to remove a single image by its key.</span></span>  
  
    ```vb  
    ' Removes the image named "myPhoto" from the list.  
    ImageList1.Images.RemoveByKey("myPhoto")  
    ```  
  
```csharp  
// Removes the image named "myPhoto" from the list.  
imageList1.Images.RemoveByKey("myPhoto");  
```  
  
## <a name="see-also"></a><span data-ttu-id="2d4bc-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="2d4bc-124">See also</span></span>
- [<span data-ttu-id="2d4bc-125">ImageList (componente)</span><span class="sxs-lookup"><span data-stu-id="2d4bc-125">ImageList Component</span></span>](imagelist-component-windows-forms.md)
- [<span data-ttu-id="2d4bc-126">Información general sobre el componente ImageList</span><span class="sxs-lookup"><span data-stu-id="2d4bc-126">ImageList Component Overview</span></span>](imagelist-component-overview-windows-forms.md)
- [<span data-ttu-id="2d4bc-127">Imágenes, mapas de bits y metarchivos</span><span class="sxs-lookup"><span data-stu-id="2d4bc-127">Images, Bitmaps, and Metafiles</span></span>](../advanced/images-bitmaps-and-metafiles.md)
