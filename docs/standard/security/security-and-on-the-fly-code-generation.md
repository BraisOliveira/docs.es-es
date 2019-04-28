---
title: Seguridad y generación de código inmediata
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- code security, on-the-fly code generation
- on-the-fly code generation
- security [.NET Framework], on-the-fly code generation
- secure coding, on-the-fly code generation
ms.assetid: 6d221724-bb21-4d76-90c3-0ee2a2e69be2
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ffb1081c80c31353ad38080ae16ef9f8a74b5481
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61860547"
---
# <a name="security-and-on-the-fly-code-generation"></a><span data-ttu-id="5532a-102">Seguridad y generación de código inmediata</span><span class="sxs-lookup"><span data-stu-id="5532a-102">Security and On-the-Fly Code Generation</span></span>
<span data-ttu-id="5532a-103">Algunas bibliotecas funcionan generando código y ejecutándolo para realizar algunas operaciones para el llamador.</span><span class="sxs-lookup"><span data-stu-id="5532a-103">Some libraries operate by generating code and running it to perform some operation for the caller.</span></span> <span data-ttu-id="5532a-104">El problema fundamental es generar código en nombre de código de menor confianza y ejecutarlo con una confianza superior.</span><span class="sxs-lookup"><span data-stu-id="5532a-104">The basic problem is generating code on behalf of lesser-trust code and running it at a higher trust.</span></span> <span data-ttu-id="5532a-105">El problema empeora cuando el llamador puede influir en la generación de código, por lo que debe asegurarse de generar solo código que considere seguro.</span><span class="sxs-lookup"><span data-stu-id="5532a-105">The problem worsens when the caller can influence code generation, so you must ensure that only code you consider safe is generated.</span></span>  
  
 <span data-ttu-id="5532a-106">Necesitará saber exactamente qué código genera en todo momento.</span><span class="sxs-lookup"><span data-stu-id="5532a-106">You need to know exactly what code you are generating at all times.</span></span> <span data-ttu-id="5532a-107">Esto significa que debe tener controles estrictos sobre los valores que obtiene de un usuario, ya sean cadenas entre comillas (que se deben escribir entre caracteres de escape para que no puedan incluir elementos de código imprevistos), identificadores (que se deben comprobar para verificar que son identificadores válidos), o cualquier otra cosa.</span><span class="sxs-lookup"><span data-stu-id="5532a-107">This means that you must have strict controls on any values that you get from a user, be they quote-enclosed strings (which should be escaped so they cannot include unexpected code elements), identifiers (which should be checked to verify that they are valid identifiers), or anything else.</span></span> <span data-ttu-id="5532a-108">Los identificadores pueden ser peligrosos porque un ensamblado compilado puede modificarse para que sus identificadores contengan caracteres extraños que probablemente lo interrumpirán (aunque esta es una vulnerabilidad de seguridad muy poco frecuente).</span><span class="sxs-lookup"><span data-stu-id="5532a-108">Identifiers can be dangerous because a compiled assembly can be modified so that its identifiers contain strange characters, which will probably break it (although this is rarely a security vulnerability).</span></span>  
  
 <span data-ttu-id="5532a-109">Es conveniente generar código con emisión de la reflexión porque suele ayudar a evitar muchos de estos problemas.</span><span class="sxs-lookup"><span data-stu-id="5532a-109">It is recommended that you generate code with reflection emit, which often helps you avoid many of these problems.</span></span>  
  
 <span data-ttu-id="5532a-110">Al compilar el código, tenga en cuenta si hay alguna manera de que un programa malintencionado lo modifique.</span><span class="sxs-lookup"><span data-stu-id="5532a-110">When you compile the code, consider whether there is some way a malicious program could modify it.</span></span> <span data-ttu-id="5532a-111">¿Existe algún momento, por breve que sea, durante el cual un código malintencionado puede cambiar el código fuente en el disco antes de que el compilador lo lea o antes de que el código cargue el archivo .dll?</span><span class="sxs-lookup"><span data-stu-id="5532a-111">Is there a small window of time during which malicious code can change source code on disk before the compiler reads it or before your code loads the .dll file?</span></span> <span data-ttu-id="5532a-112">Si es así, debe proteger el directorio que contiene estos archivos usando una lista de control de acceso en el sistema de archivos, según corresponda.</span><span class="sxs-lookup"><span data-stu-id="5532a-112">If so, you must protect the directory containing these files, using an Access Control List in the file system, as appropriate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5532a-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="5532a-113">See also</span></span>

- [<span data-ttu-id="5532a-114">Instrucciones de codificación segura</span><span class="sxs-lookup"><span data-stu-id="5532a-114">Secure Coding Guidelines</span></span>](../../../docs/standard/security/secure-coding-guidelines.md)
