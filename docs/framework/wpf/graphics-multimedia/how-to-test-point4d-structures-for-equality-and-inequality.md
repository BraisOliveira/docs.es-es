---
title: Filtrar Comprobar la igualdad y la desigualdad de estructuras Point4D
ms.date: 03/30/2017
helpviewer_keywords:
- inequality [WPF], testing Point4D structures for
- equality [WPF], testing Point4D structures for
- testing [WPF], Point4D structures for equality
- Point4D structures [WPF], testing for inequality
- testing [WPF], Point4D structures for inequality
- Point4D structures [WPF], testing for equality
ms.assetid: e004a67e-db7f-4af8-a31f-e6b2a44ccf34
ms.openlocfilehash: ce1188e99ef2b0682427cc2e227aaccd27f7c4f4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59198444"
---
# <a name="how-to-test-point4d-structures-for-equality-and-inequality"></a><span data-ttu-id="ca0d6-102">Filtrar Comprobar la igualdad y la desigualdad de estructuras Point4D</span><span class="sxs-lookup"><span data-stu-id="ca0d6-102">How to: Test Point4D structures for equality and inequality</span></span>
<span data-ttu-id="ca0d6-103">En este ejemplo se muestra cómo probar <xref:System.Windows.Media.Media3D.Point4D> estructuras de igualdad y desigualdad.</span><span class="sxs-lookup"><span data-stu-id="ca0d6-103">This example shows how to test <xref:System.Windows.Media.Media3D.Point4D> structures for equality and inequality.</span></span>  
  
 <span data-ttu-id="ca0d6-104">El código siguiente muestra cómo probar <xref:System.Windows.Media.Media3D.Point4D> estructuras de igualdad y desigualdad mediante el <xref:System.Windows.Media.Media3D.Point4D> métodos de igualdad.</span><span class="sxs-lookup"><span data-stu-id="ca0d6-104">The following code illustrates how to test <xref:System.Windows.Media.Media3D.Point4D> structures for equality and inequality using the <xref:System.Windows.Media.Media3D.Point4D> equality methods.</span></span>  <span data-ttu-id="ca0d6-105">El <xref:System.Windows.Media.Media3D.Point4D> estructuras se comprueban si son iguales mediante la igualdad sobrecargado (`==`) operador, a continuación, para desigualdad utilizando la desigualdad sobrecargado (`!=`) (operador) y, finalmente, un <xref:System.Windows.Media.Media3D.Point3D> estructura y un <xref:System.Windows.Media.Media3D.Point4D> estructura se comprueban para la igualdad con estático <xref:System.Windows.Media.Media3D.Point4D.Equals%2A> método.</span><span class="sxs-lookup"><span data-stu-id="ca0d6-105">The <xref:System.Windows.Media.Media3D.Point4D> structures are tested for equality using the overloaded equality (`==`) operator, then for inequality using the overloaded inequality (`!=`) operator, and finally a <xref:System.Windows.Media.Media3D.Point3D> structure and a <xref:System.Windows.Media.Media3D.Point4D> structure are checked for equality using the static <xref:System.Windows.Media.Media3D.Point4D.Equals%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ca0d6-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ca0d6-106">Example</span></span>  
 [!code-csharp[3DGallery_procedural_snip#Point4DEqualityExample_csharp](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/Misc3DOperationsExample.cs#point4dequalityexample_csharp)]  
  
## <a name="see-also"></a><span data-ttu-id="ca0d6-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="ca0d6-107">See also</span></span>

- <xref:System.Windows.Media.Media3D.Point4D.op_Equality%2A>
- <xref:System.Windows.Media.Media3D.Point4D.op_Inequality%2A>
- <xref:System.Windows.Media.Media3D.Point4D.Equals%2A>
