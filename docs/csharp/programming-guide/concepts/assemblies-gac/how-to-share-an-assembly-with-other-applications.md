---
title: Procedimiento para compartir un ensamblado con otras aplicaciones (C#)
ms.date: 07/20/2015
ms.assetid: c30e972b-1693-4e05-b115-c31831fdf9f2
ms.openlocfilehash: 954db3fe139ff307386fc182dbf16c60ce86bd30
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/19/2019
ms.locfileid: "69595728"
---
# <a name="how-to-share-an-assembly-with-other-applications-c"></a><span data-ttu-id="52f75-102">Procedimiento para compartir un ensamblado con otras aplicaciones (C#)</span><span class="sxs-lookup"><span data-stu-id="52f75-102">How to: Share an Assembly with Other Applications (C#)</span></span>
<span data-ttu-id="52f75-103">Los ensamblados pueden ser privados o compartidos: de forma predeterminada, la mayoría de los programas sencillos constan de un ensamblado privado porque no se diseñaron para ser usados por otras aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="52f75-103">Assemblies can be private or shared: by default, most simple programs consist of a private assembly because they are not intended to be used by other applications.</span></span>  
  
 <span data-ttu-id="52f75-104">Para compartir un ensamblado con otras aplicaciones, debe colocarse en la [caché global de ensamblados](../../../../framework/app-domains/gac.md) (GAC).</span><span class="sxs-lookup"><span data-stu-id="52f75-104">In order to share an assembly with other applications, it must be placed in the [Global Assembly Cache](../../../../framework/app-domains/gac.md) (GAC).</span></span>  
  
### <a name="sharing-an-assembly"></a><span data-ttu-id="52f75-105">Compartir un ensamblado</span><span class="sxs-lookup"><span data-stu-id="52f75-105">Sharing an assembly</span></span>  
  
1. <span data-ttu-id="52f75-106">Cree el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="52f75-106">Create your assembly.</span></span> <span data-ttu-id="52f75-107">Para obtener más información, vea [Creating Assemblies](../../../../framework/app-domains/create-assemblies.md) (Crear ensamblados).</span><span class="sxs-lookup"><span data-stu-id="52f75-107">For more information, see [Creating Assemblies](../../../../framework/app-domains/create-assemblies.md).</span></span>  
  
2. <span data-ttu-id="52f75-108">Asigne un nombre seguro al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="52f75-108">Assign a strong name to your assembly.</span></span> <span data-ttu-id="52f75-109">Para obtener más información, vea [Cómo: Firmar un ensamblado con un nombre seguro](../../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).</span><span class="sxs-lookup"><span data-stu-id="52f75-109">For more information, see [How to: Sign an Assembly with a Strong Name](../../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).</span></span>  
  
3. <span data-ttu-id="52f75-110">Asigne la información de versión al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="52f75-110">Assign version information to your assembly.</span></span> <span data-ttu-id="52f75-111">Para obtener más información, vea [Versiones de los ensamblados](../../../../framework/app-domains/assembly-versioning.md).</span><span class="sxs-lookup"><span data-stu-id="52f75-111">For more information, see [Assembly Versioning](../../../../framework/app-domains/assembly-versioning.md).</span></span>  
  
4. <span data-ttu-id="52f75-112">Agregue el ensamblado a la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="52f75-112">Add your assembly to the Global Assembly Cache.</span></span> <span data-ttu-id="52f75-113">Para obtener más información, vea [Cómo: Instalar un ensamblado en la caché global de ensamblados](../../../../framework/app-domains/how-to-install-an-assembly-into-the-gac.md).</span><span class="sxs-lookup"><span data-stu-id="52f75-113">For more information, see [How to: Install an Assembly into the Global Assembly Cache](../../../../framework/app-domains/how-to-install-an-assembly-into-the-gac.md).</span></span>  
  
5. <span data-ttu-id="52f75-114">Obtenga acceso a los tipos contenidos en el ensamblado desde las otras aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="52f75-114">Access the types contained in the assembly from the other applications.</span></span> <span data-ttu-id="52f75-115">Para obtener más información, vea [Cómo: Hacer referencia a un ensamblado con nombre seguro](../../../../framework/app-domains/how-to-reference-a-strong-named-assembly.md).</span><span class="sxs-lookup"><span data-stu-id="52f75-115">For more information, see [How to: Reference a Strong-Named Assembly](../../../../framework/app-domains/how-to-reference-a-strong-named-assembly.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52f75-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="52f75-116">See also</span></span>

- [<span data-ttu-id="52f75-117">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="52f75-117">C# Programming Guide</span></span>](../../index.md)
- [<span data-ttu-id="52f75-118">Programar con ensamblados</span><span class="sxs-lookup"><span data-stu-id="52f75-118">Programming with Assemblies</span></span>](../../../../framework/app-domains/programming-with-assemblies.md)
