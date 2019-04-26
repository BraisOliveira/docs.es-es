---
title: Seguridad en los formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- designer access security [Windows Forms]
- permissions [Windows Forms], Windows Forms
- Windows Forms, security
- security [Windows Forms]
- access control [Windows Forms], Windows Forms
- security policy [Windows Forms], Windows Forms
ms.assetid: 932d438a-5285-46d8-a958-8c93d0ad6cae
ms.openlocfilehash: f64d5ef2e9bb0e977b4c007e8c5109ac0c331a84
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61799377"
---
# <a name="windows-forms-security"></a><span data-ttu-id="a9fc9-102">Seguridad en los formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a9fc9-102">Windows Forms Security</span></span>
<span data-ttu-id="a9fc9-103">Windows Forms incluye un modelo de seguridad que está basado en código (niveles de seguridad se establecen para el código, independientemente del usuario que ejecuta el código).</span><span class="sxs-lookup"><span data-stu-id="a9fc9-103">Windows Forms features a security model that is code-based (security levels are set for code, regardless of the user running the code).</span></span> <span data-ttu-id="a9fc9-104">Esto es además de cualquier esquema de seguridad que pueda estar aplicada ya en el equipo.</span><span class="sxs-lookup"><span data-stu-id="a9fc9-104">This is in addition to any security schemas that may be in place already on your computer system.</span></span> <span data-ttu-id="a9fc9-105">Estos pueden incluir en el explorador (por ejemplo, la seguridad basada en la zona de Internet Explorer) o el sistema operativo (por ejemplo, la seguridad basada en credenciales de Windows NT).</span><span class="sxs-lookup"><span data-stu-id="a9fc9-105">These can include those in the browser (such as the zone-based security available in Internet Explorer) or the operating system (such as the credential-based security of Windows NT).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a9fc9-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="a9fc9-106">In This Section</span></span>  
 [<span data-ttu-id="a9fc9-107">Información general sobre la seguridad en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a9fc9-107">Security in Windows Forms Overview</span></span>](security-in-windows-forms-overview.md)  
 <span data-ttu-id="a9fc9-108">Explica brevemente el modelo de seguridad de .NET Framework y los pasos básicos necesarios para asegurarse de los formularios de Windows en la aplicación son seguros.</span><span class="sxs-lookup"><span data-stu-id="a9fc9-108">Briefly explains the .NET Framework security model and the basic steps necessary to ensure the Windows Forms in your application are secure.</span></span>  
  
 [<span data-ttu-id="a9fc9-109">Acceso más seguro a archivos y datos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a9fc9-109">More Secure File and Data Access in Windows Forms</span></span>](more-secure-file-and-data-access-in-windows-forms.md)  
 <span data-ttu-id="a9fc9-110">Describe cómo tener acceso a archivos y datos en un entorno de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="a9fc9-110">Describes how to access files and data in a semi-trusted environment.</span></span>  
  
 [<span data-ttu-id="a9fc9-111">Impresión más segura en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a9fc9-111">More Secure Printing in Windows Forms</span></span>](more-secure-printing-in-windows-forms.md)  
 <span data-ttu-id="a9fc9-112">Describe cómo tener acceso a características de impresión en un entorno de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="a9fc9-112">Describes how to access printing features in a semi-trusted environment.</span></span>  
  
 [<span data-ttu-id="a9fc9-113">Consideraciones de seguridad adicionales en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a9fc9-113">Additional Security Considerations in Windows Forms</span></span>](additional-security-considerations-in-windows-forms.md)  
 <span data-ttu-id="a9fc9-114">Describe cómo manipular ventanas, usando el Portapapeles y realizar llamadas a código no administrado en un entorno de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="a9fc9-114">Describes performing window manipulation, using the Clipboard, and making calls to unmanaged code in a semi-trusted environment.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="a9fc9-115">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="a9fc9-115">Related Sections</span></span>  
 <span data-ttu-id="a9fc9-116">[Directiva de seguridad predeterminada](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/03kwzyfc(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="a9fc9-116">[Default Security Policy](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/03kwzyfc(v=vs.100))</span></span>  
 <span data-ttu-id="a9fc9-117">Enumera los permisos concedidos en los conjuntos de permisos de plena confianza, Intranet Local e Internet.</span><span class="sxs-lookup"><span data-stu-id="a9fc9-117">Lists the default permissions granted in the Full Trust, Local Intranet, and Internet permission sets.</span></span>  
  
 <span data-ttu-id="a9fc9-118">[Administración general de directivas de seguridad](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ed5htz45(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="a9fc9-118">[General Security Policy Administration](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ed5htz45(v=vs.100))</span></span>  
 <span data-ttu-id="a9fc9-119">Proporciona información sobre la administración de la directiva de seguridad de .NET Framework y la concesión de permisos.</span><span class="sxs-lookup"><span data-stu-id="a9fc9-119">Gives information about the administering the .NET Framework security policy and elevating permissions.</span></span>  
  
 [<span data-ttu-id="a9fc9-120">Permisos peligrosos y administración de directivas</span><span class="sxs-lookup"><span data-stu-id="a9fc9-120">Dangerous Permissions and Policy Administration</span></span>](../misc/dangerous-permissions-and-policy-administration.md)  
 <span data-ttu-id="a9fc9-121">Se describen algunos de los permisos de.NET Framework que pueden permitir potencialmente burlar el sistema de seguridad.</span><span class="sxs-lookup"><span data-stu-id="a9fc9-121">Discusses some of the.NET Framework permissions that can potentially allow the security system to be circumvented.</span></span>  
  
 [<span data-ttu-id="a9fc9-122">Instrucciones de codificación segura</span><span class="sxs-lookup"><span data-stu-id="a9fc9-122">Secure Coding Guidelines</span></span>](../../standard/security/secure-coding-guidelines.md)  
 <span data-ttu-id="a9fc9-123">Vínculos a temas que explican los procedimientos recomendados para escribir código seguro para .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a9fc9-123">Links to topics that explain the best practices for securely writing code against the .NET Framework.</span></span>  
  
 <span data-ttu-id="a9fc9-124">[Solicitar permisos](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/yd267cce(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="a9fc9-124">[Requesting Permissions](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/yd267cce(v=vs.100))</span></span>  
 <span data-ttu-id="a9fc9-125">Describe el uso de atributos para que el tiempo de ejecución sepa qué permisos necesita ejecutar su código.</span><span class="sxs-lookup"><span data-stu-id="a9fc9-125">Discusses the use of attributes to let the runtime know what permissions your code needs to run.</span></span>  
  
 [<span data-ttu-id="a9fc9-126">Conceptos clave de seguridad</span><span class="sxs-lookup"><span data-stu-id="a9fc9-126">Key Security Concepts</span></span>](../../standard/security/key-security-concepts.md)  
 <span data-ttu-id="a9fc9-127">Vínculos a temas que tratan los aspectos básicos de seguridad del código.</span><span class="sxs-lookup"><span data-stu-id="a9fc9-127">Links to topics that cover the basic aspects of code security.</span></span>  
  
 <span data-ttu-id="a9fc9-128">[Code Access Security Basics](../misc/code-access-security-basics.md) (Conceptos básicos sobre la seguridad de acceso del código)</span><span class="sxs-lookup"><span data-stu-id="a9fc9-128">[Code Access Security Basics](../misc/code-access-security-basics.md)</span></span>  
 <span data-ttu-id="a9fc9-129">Explica los fundamentos de trabajar con la directiva de seguridad de tiempo de ejecución de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a9fc9-129">Discusses the basics of working with the .NET Framework run time security policy.</span></span>  
  
 <span data-ttu-id="a9fc9-130">[Determinar cuándo se debe modificar la directiva de seguridad](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/xky659fc(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="a9fc9-130">[Determining When to Modify Security Policy](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/xky659fc(v=vs.100))</span></span>  
 <span data-ttu-id="a9fc9-131">Explica cómo determinar cuándo las aplicaciones necesitan desviarse de la directiva de seguridad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="a9fc9-131">Explains how to determine when your applications need to diverge from the default security policy.</span></span>  
  
 <span data-ttu-id="a9fc9-132">[Implementación de la directiva de seguridad](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/13wcxx6y(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="a9fc9-132">[Deploying Security Policy](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/13wcxx6y(v=vs.100))</span></span>  
 <span data-ttu-id="a9fc9-133">Describe la mejor manera de implementar cambios de directiva de seguridad.</span><span class="sxs-lookup"><span data-stu-id="a9fc9-133">Discusses the best manner for deploying security policy changes.</span></span>
