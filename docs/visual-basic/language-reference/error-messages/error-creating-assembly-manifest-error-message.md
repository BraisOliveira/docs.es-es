---
title: 'Error al crear el manifiesto de ensamblado: <error message>'
ms.date: 07/20/2015
f1_keywords:
- bc30140
- vbc30140
helpviewer_keywords:
- BC30140
ms.assetid: 1beb5aa0-7b79-4c85-946b-5c2d0a41d1d2
ms.openlocfilehash: 0f67b772bab3104c00510954d01b200aadfa9e8a
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59296295"
---
# <a name="error-creating-assembly-manifest-error-message"></a><span data-ttu-id="58ec2-102">Error al crear el manifiesto del ensamblado: \<mensaje de error ></span><span class="sxs-lookup"><span data-stu-id="58ec2-102">Error creating assembly manifest: \<error message></span></span>
<span data-ttu-id="58ec2-103">El compilador de Visual Basic llama a la herramienta Assembly Linker (Al.exe, también denominado Alink) para generar un ensamblado con un manifiesto.</span><span class="sxs-lookup"><span data-stu-id="58ec2-103">The Visual Basic compiler calls the Assembly Linker (Al.exe, also known as Alink) to generate an assembly with a manifest.</span></span> <span data-ttu-id="58ec2-104">El vinculador ha informado de un error en una fase previa a la emisión de la creación del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="58ec2-104">The linker has reported an error in the pre-emission stage of creating the assembly.</span></span>  
  
 <span data-ttu-id="58ec2-105">Esto puede suceder si existen problemas con el archivo de clave o el contenedor de claves especificado.</span><span class="sxs-lookup"><span data-stu-id="58ec2-105">This can occur if there are problems with the key file or the key container specified.</span></span> <span data-ttu-id="58ec2-106">Para firmar completamente un ensamblado, debe proporcionar un archivo de clave válido que contenga información sobre las claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="58ec2-106">To fully sign an assembly, you must provide a valid key file that contains information about the public and private keys.</span></span> <span data-ttu-id="58ec2-107">Para retrasar la firma de un ensamblado, debe activar la casilla **Retrasar solo firma** y proporcionar un archivo de clave válido que contenga información sobre la clave pública.</span><span class="sxs-lookup"><span data-stu-id="58ec2-107">To delay sign an assembly, you must select the **Delay sign only** check box and provide a valid key file that contains information about the public key information.</span></span> <span data-ttu-id="58ec2-108">La clave privada no es necesaria cuando un ensamblado tiene la firma retrasada.</span><span class="sxs-lookup"><span data-stu-id="58ec2-108">The private key is not necessary when an assembly is delay-signed.</span></span> <span data-ttu-id="58ec2-109">Para obtener más información, vea [Cómo: Firmar un ensamblado con un nombre seguro](../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).</span><span class="sxs-lookup"><span data-stu-id="58ec2-109">For more information, see [How to: Sign an Assembly with a Strong Name](../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).</span></span>  
  
 <span data-ttu-id="58ec2-110">**Identificador de error:** BC30140</span><span class="sxs-lookup"><span data-stu-id="58ec2-110">**Error ID:** BC30140</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="58ec2-111">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="58ec2-111">To correct this error</span></span>  
  
1. <span data-ttu-id="58ec2-112">Examine el mensaje de error citado y consulte el tema [Al.exe](../../../framework/tools/al-exe-assembly-linker.md).</span><span class="sxs-lookup"><span data-stu-id="58ec2-112">Examine the quoted error message and consult the topic [Al.exe](../../../framework/tools/al-exe-assembly-linker.md).</span></span> <span data-ttu-id="58ec2-113">para el error AL1019 explicación más detallada y consejos</span><span class="sxs-lookup"><span data-stu-id="58ec2-113">for error AL1019 further explanation and advice</span></span>  
  
2. <span data-ttu-id="58ec2-114">Si el error persiste, reúna información sobre las circunstancias y notifíquelo a los Servicios de soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="58ec2-114">If the error persists, gather information about the circumstances and notify Microsoft Product Support Services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58ec2-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="58ec2-115">See also</span></span>

- [<span data-ttu-id="58ec2-116">Filtrar Firma de un ensamblado con un nombre seguro</span><span class="sxs-lookup"><span data-stu-id="58ec2-116">How to: Sign an Assembly with a Strong Name</span></span>](../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md)
- [<span data-ttu-id="58ec2-117">Página Firma, Diseñador de proyectos</span><span class="sxs-lookup"><span data-stu-id="58ec2-117">Signing Page, Project Designer</span></span>](/visualstudio/ide/reference/signing-page-project-designer)
- [<span data-ttu-id="58ec2-118">Al.exe</span><span class="sxs-lookup"><span data-stu-id="58ec2-118">Al.exe</span></span>](../../../framework/tools/al-exe-assembly-linker.md)
- [<span data-ttu-id="58ec2-119">Talk to Us</span><span class="sxs-lookup"><span data-stu-id="58ec2-119">Talk to Us</span></span>](/visualstudio/ide/talk-to-us)
