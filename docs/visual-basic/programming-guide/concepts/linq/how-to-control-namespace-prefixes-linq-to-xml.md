---
title: Procedimiento Control de los prefijos de Namespace (Visual Basic) (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: 2fcf28a5-31b6-409d-84ea-27c22f71fc9f
ms.openlocfilehash: 7e5a05d2fa93e61338f450d0a4d890fa94c04fd2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61855405"
---
# <a name="how-to-control-namespace-prefixes-visual-basic-linq-to-xml"></a><span data-ttu-id="f421f-102">Procedimiento Control de los prefijos de Namespace (Visual Basic) (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="f421f-102">How to: Control Namespace Prefixes (Visual Basic) (LINQ to XML)</span></span>
<span data-ttu-id="f421f-103">En este tema se describe cómo puede controlar prefijos de espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="f421f-103">This topic describes how you can control namespace prefixes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f421f-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f421f-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="f421f-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="f421f-105">Description</span></span>  
 <span data-ttu-id="f421f-106">Este ejemplo declara dos espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="f421f-106">This example declares two namespaces.</span></span> <span data-ttu-id="f421f-107">Especifica que el `http://www.adventure-works.com` espacio de nombres tiene el prefijo `aw`y que la `www.fourthcoffee.com` espacio de nombres tiene el prefijo `fc`.</span><span class="sxs-lookup"><span data-stu-id="f421f-107">It specifies that the `http://www.adventure-works.com` namespace has the prefix `aw`, and that the `www.fourthcoffee.com` namespace has the prefix of `fc`.</span></span>  
  
### <a name="code"></a><span data-ttu-id="f421f-108">Código</span><span class="sxs-lookup"><span data-stu-id="f421f-108">Code</span></span>  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
Imports <xmlns:fc="www.fourthcoffee.com">  
  
Module Module1  
  
    Sub Main()  
        Dim root As XElement = _  
            <aw:Root>  
                <fc:Child>  
                    <aw:DifferentChild>other content</aw:DifferentChild>  
                </fc:Child>  
                <aw:Child2>c2 content</aw:Child2>  
                <fc:Child3>c3 content</fc:Child3>  
            </aw:Root>  
        Console.WriteLine(root)  
    End Sub  
  
End Module  
```  
  
### <a name="comments"></a><span data-ttu-id="f421f-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f421f-109">Comments</span></span>  
 <span data-ttu-id="f421f-110">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="f421f-110">This example produces the following output:</span></span>  
  
```xml  
<aw:Root xmlns:fc="www.fourthcoffee.com" xmlns:aw="http://www.adventure-works.com">  
  <fc:Child>  
    <aw:DifferentChild>other content</aw:DifferentChild>  
  </fc:Child>  
  <aw:Child2>c2 content</aw:Child2>  
  <fc:Child3>c3 content</fc:Child3>  
</aw:Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f421f-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="f421f-111">See also</span></span>

- [<span data-ttu-id="f421f-112">Trabajar con espacios de nombres XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f421f-112">Working with XML Namespaces (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md)
