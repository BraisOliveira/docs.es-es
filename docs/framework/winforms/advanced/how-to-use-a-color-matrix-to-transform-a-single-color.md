---
title: Filtrar para usar una matriz de colores para transformar un color único
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- image colors [Windows Forms], transforming
- color matrices [Windows Forms], using
ms.assetid: 44df4556-a433-49c0-ac0f-9a12063a5860
ms.openlocfilehash: 78fc498b0689026fb74ec0c422948c1879495560
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59342861"
---
# <a name="how-to-use-a-color-matrix-to-transform-a-single-color"></a><span data-ttu-id="481ee-102">Filtrar para usar una matriz de colores para transformar un color único</span><span class="sxs-lookup"><span data-stu-id="481ee-102">How to: Use a Color Matrix to Transform a Single Color</span></span>
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="481ee-103">proporciona el <xref:System.Drawing.Image> y <xref:System.Drawing.Bitmap> clases para almacenar y manipular imágenes.</span><span class="sxs-lookup"><span data-stu-id="481ee-103">provides the <xref:System.Drawing.Image> and <xref:System.Drawing.Bitmap> classes for storing and manipulating images.</span></span> <xref:System.Drawing.Image> <span data-ttu-id="481ee-104">y <xref:System.Drawing.Bitmap> objetos almacenan el color de cada píxel como un número de 32 bits: 8 bits para cada color rojo, verde, azul y alfa.</span><span class="sxs-lookup"><span data-stu-id="481ee-104">and <xref:System.Drawing.Bitmap> objects store the color of each pixel as a 32-bit number: 8 bits each for red, green, blue, and alpha.</span></span> <span data-ttu-id="481ee-105">Cada uno de los cuatro componentes es un número comprendido entre 0 y 255, donde 0 representa ninguna intensidad y que representa la intensidad máxima de 255.</span><span class="sxs-lookup"><span data-stu-id="481ee-105">Each of the four components is a number from 0 through 255, with 0 representing no intensity and 255 representing full intensity.</span></span> <span data-ttu-id="481ee-106">El componente alfa especifica la transparencia del color: 0 es completamente transparente y 255 es completamente opaco.</span><span class="sxs-lookup"><span data-stu-id="481ee-106">The alpha component specifies the transparency of the color: 0 is fully transparent, and 255 is fully opaque.</span></span>  
  
 <span data-ttu-id="481ee-107">Un vector de color es una tupla de 4 del formulario (rojo, verde, azul, alfa).</span><span class="sxs-lookup"><span data-stu-id="481ee-107">A color vector is a 4-tuple of the form (red, green, blue, alpha).</span></span> <span data-ttu-id="481ee-108">Por ejemplo, el vector de color (0, 255, 0, 255) representa un color opaco que no tenga ningún rojo o azul, verde intensidad máxima.</span><span class="sxs-lookup"><span data-stu-id="481ee-108">For example, the color vector (0, 255, 0, 255) represents an opaque color that has no red or blue, but has green at full intensity.</span></span>  
  
 <span data-ttu-id="481ee-109">Otra convención para representar los colores utiliza el número 1 de máxima intensidad.</span><span class="sxs-lookup"><span data-stu-id="481ee-109">Another convention for representing colors uses the number 1 for full intensity.</span></span> <span data-ttu-id="481ee-110">Mediante esta convención, el color que se describe en el párrafo anterior podría representarse mediante el vector (0, 1, 0, 1).</span><span class="sxs-lookup"><span data-stu-id="481ee-110">Using that convention, the color described in the preceding paragraph would be represented by the vector (0, 1, 0, 1).</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="481ee-111">utiliza la convención 1 como intensidad total cuando realiza las transformaciones de color.</span><span class="sxs-lookup"><span data-stu-id="481ee-111">uses the convention of 1 as full intensity when it performs color transformations.</span></span>  
  
 <span data-ttu-id="481ee-112">Puede aplicar transformaciones lineales (rotación, escala y similares) a los vectores de color multiplicando los vectores de color por una matriz de 4 x 4.</span><span class="sxs-lookup"><span data-stu-id="481ee-112">You can apply linear transformations (rotation, scaling, and the like) to color vectors by multiplying the color vectors by a 4×4 matrix.</span></span> <span data-ttu-id="481ee-113">Sin embargo, no se puede utilizar una matriz de 4 x 4 para realizar una conversión (no lineal).</span><span class="sxs-lookup"><span data-stu-id="481ee-113">However, you cannot use a 4×4 matrix to perform a translation (nonlinear).</span></span> <span data-ttu-id="481ee-114">Si agrega una quinta coordenada ficticia (por ejemplo, el número 1) a cada uno de los vectores de color, puede usar una matriz de 5 × 5 para aplicar cualquier combinación de conversiones y transformaciones lineales.</span><span class="sxs-lookup"><span data-stu-id="481ee-114">If you add a dummy fifth coordinate (for example, the number 1) to each of the color vectors, you can use a 5×5 matrix to apply any combination of linear transformations and translations.</span></span> <span data-ttu-id="481ee-115">Una transformación que consta de una transformación lineal seguida de una traducción se denomina una transformación afín.</span><span class="sxs-lookup"><span data-stu-id="481ee-115">A transformation consisting of a linear transformation followed by a translation is called an affine transformation.</span></span>  
  
 <span data-ttu-id="481ee-116">Por ejemplo, suponga que desea empezar con el color (0.2, 0.0, 0.4, 1.0) y aplicar las transformaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="481ee-116">For example, suppose you want to start with the color (0.2, 0.0, 0.4, 1.0) and apply the following transformations:</span></span>  
  
1. <span data-ttu-id="481ee-117">Duplique el componente rojo</span><span class="sxs-lookup"><span data-stu-id="481ee-117">Double the red component</span></span>  
  
2. <span data-ttu-id="481ee-118">Agregue 0.2 a los componentes rojos, verde y azules</span><span class="sxs-lookup"><span data-stu-id="481ee-118">Add 0.2 to the red, green, and blue components</span></span>  
  
 <span data-ttu-id="481ee-119">La multiplicación de matriz siguientes llevará a cabo el par de transformaciones en el orden mostrado.</span><span class="sxs-lookup"><span data-stu-id="481ee-119">The following matrix multiplication will perform the pair of transformations in the order listed.</span></span>  
  
 <span data-ttu-id="481ee-120">![Cambiar el color de](./media/recoloring01.gif "recoloring01")</span><span class="sxs-lookup"><span data-stu-id="481ee-120">![Recoloring](./media/recoloring01.gif "recoloring01")</span></span>  
  
 <span data-ttu-id="481ee-121">Los elementos de una matriz de colores se indizan (basado en cero) por fila y, a continuación, la columna.</span><span class="sxs-lookup"><span data-stu-id="481ee-121">The elements of a color matrix are indexed (zero-based) by row and then column.</span></span> <span data-ttu-id="481ee-122">Por ejemplo, la entrada en la quinta fila y la tercera columna de matriz M está indicada por M [4] [2].</span><span class="sxs-lookup"><span data-stu-id="481ee-122">For example, the entry in the fifth row and third column of matrix M is denoted by M[4][2].</span></span>  
  
 <span data-ttu-id="481ee-123">La matriz de identidad de 5 × 5 (se muestra en la siguiente ilustración) tiene 1s en la diagonal y 0s en los demás.</span><span class="sxs-lookup"><span data-stu-id="481ee-123">The 5×5 identity matrix (shown in the following illustration) has 1s on the diagonal and 0s everywhere else.</span></span> <span data-ttu-id="481ee-124">Si se multiplica un vector de color por la matriz de identidad, el vector de color no cambia.</span><span class="sxs-lookup"><span data-stu-id="481ee-124">If you multiply a color vector by the identity matrix, the color vector does not change.</span></span> <span data-ttu-id="481ee-125">Una manera cómoda para formar la matriz de transformación de un color es empezar con la matriz de identidad y realice un pequeño cambio que produce la transformación deseada.</span><span class="sxs-lookup"><span data-stu-id="481ee-125">A convenient way to form the matrix of a color transformation is to start with the identity matrix and make a small change that produces the desired transformation.</span></span>  
  
 <span data-ttu-id="481ee-126">![Cambiar el color de](./media/recoloring02.gif "recoloring02")</span><span class="sxs-lookup"><span data-stu-id="481ee-126">![Recoloring](./media/recoloring02.gif "recoloring02")</span></span>  
  
 <span data-ttu-id="481ee-127">Para obtener una explicación más detallada de las matrices y las transformaciones, vea [sistemas de coordenadas y transformaciones](coordinate-systems-and-transformations.md).</span><span class="sxs-lookup"><span data-stu-id="481ee-127">For a more detailed discussion of matrices and transformations, see [Coordinate Systems and Transformations](coordinate-systems-and-transformations.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="481ee-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="481ee-128">Example</span></span>  
 <span data-ttu-id="481ee-129">El siguiente ejemplo toma una imagen que es un color (0.2, 0.0, 0.4, 1.0) y se aplica la transformación descrita en los párrafos anteriores.</span><span class="sxs-lookup"><span data-stu-id="481ee-129">The following example takes an image that is all one color (0.2, 0.0, 0.4, 1.0) and applies the transformation described in the preceding paragraphs.</span></span>  
  
 <span data-ttu-id="481ee-130">La siguiente ilustración muestra la imagen original a la izquierda y la imagen transformada de la derecha.</span><span class="sxs-lookup"><span data-stu-id="481ee-130">The following illustration shows the original image on the left and the transformed image on the right.</span></span>  
  
 <span data-ttu-id="481ee-131">![Colores](./media/colortrans1.png "colortrans1")</span><span class="sxs-lookup"><span data-stu-id="481ee-131">![Colors](./media/colortrans1.png "colortrans1")</span></span>  
  
 <span data-ttu-id="481ee-132">El código en el ejemplo siguiente utiliza los siguientes pasos para realizar el cambio de color:</span><span class="sxs-lookup"><span data-stu-id="481ee-132">The code in the following example uses the following steps to perform the recoloring:</span></span>  
  
1. <span data-ttu-id="481ee-133">Inicializar un <xref:System.Drawing.Imaging.ColorMatrix> objeto.</span><span class="sxs-lookup"><span data-stu-id="481ee-133">Initialize a <xref:System.Drawing.Imaging.ColorMatrix> object.</span></span>  
  
2. <span data-ttu-id="481ee-134">Crear un <xref:System.Drawing.Imaging.ImageAttributes> objeto y pase el <xref:System.Drawing.Imaging.ColorMatrix> de objeto para el <xref:System.Drawing.Imaging.ImageAttributes.SetColorMatrix%2A> método de la <xref:System.Drawing.Imaging.ImageAttributes> objeto.</span><span class="sxs-lookup"><span data-stu-id="481ee-134">Create an <xref:System.Drawing.Imaging.ImageAttributes> object and pass the <xref:System.Drawing.Imaging.ColorMatrix> object to the <xref:System.Drawing.Imaging.ImageAttributes.SetColorMatrix%2A> method of the <xref:System.Drawing.Imaging.ImageAttributes> object.</span></span>  
  
3. <span data-ttu-id="481ee-135">Pase el <xref:System.Drawing.Imaging.ImageAttributes> de objeto para el <xref:System.Drawing.Graphics.DrawImage%2A> método de un <xref:System.Drawing.Graphics> objeto.</span><span class="sxs-lookup"><span data-stu-id="481ee-135">Pass the <xref:System.Drawing.Imaging.ImageAttributes> object to the <xref:System.Drawing.Graphics.DrawImage%2A> method of a <xref:System.Drawing.Graphics> object.</span></span>  
  
 [!code-csharp[System.Drawing.RecoloringImages#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.RecoloringImages#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="481ee-136">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="481ee-136">Compiling the Code</span></span>  
 <span data-ttu-id="481ee-137">El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de la <xref:System.Windows.Forms.Control.Paint> controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="481ee-137">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="481ee-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="481ee-138">See also</span></span>

- [<span data-ttu-id="481ee-139">Cambiar el color de las imágenes</span><span class="sxs-lookup"><span data-stu-id="481ee-139">Recoloring Images</span></span>](recoloring-images.md)
- [<span data-ttu-id="481ee-140">Sistemas de coordenadas y transformaciones</span><span class="sxs-lookup"><span data-stu-id="481ee-140">Coordinate Systems and Transformations</span></span>](coordinate-systems-and-transformations.md)
