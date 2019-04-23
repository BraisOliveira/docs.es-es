---
title: Utilizar valores de configuración de aplicación y de usuario
ms.date: 03/30/2017
helpviewer_keywords:
- user settings [Windows Forms]
- application settings [Windows Forms], how-to topics
ms.assetid: 54682d3b-1cbf-4683-9351-012b8b4286b5
ms.openlocfilehash: ea6994e653b3a06239634f5a0fddea84a07086e2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59107268"
---
# <a name="using-application-settings-and-user-settings"></a><span data-ttu-id="5001e-102">Utilizar valores de configuración de aplicación y de usuario</span><span class="sxs-lookup"><span data-stu-id="5001e-102">Using Application Settings and User Settings</span></span>
<span data-ttu-id="5001e-103">A partir de .NET Framework 2.0, puede crear y tener acceso a los valores que se conservan entre sesiones de ejecución de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5001e-103">Starting with the .NET Framework 2.0, you can create and access values that are persisted between application execution sessions.</span></span> <span data-ttu-id="5001e-104">Estos valores se denominan *configuración*.</span><span class="sxs-lookup"><span data-stu-id="5001e-104">These values are called *settings*.</span></span> <span data-ttu-id="5001e-105">Puede representa las preferencias del usuario o información valiosa de la aplicación debe usar.</span><span class="sxs-lookup"><span data-stu-id="5001e-105">Settings can represent user preferences, or valuable information the application needs to use.</span></span> <span data-ttu-id="5001e-106">Por ejemplo, podría crear una serie de valores que almacenan las preferencias del usuario para la combinación de colores de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="5001e-106">For example, you might create a series of settings that store user preferences for the color scheme of an application.</span></span> <span data-ttu-id="5001e-107">O bien, podría almacenar la cadena de conexión que especifica una base de datos que usa su aplicación.</span><span class="sxs-lookup"><span data-stu-id="5001e-107">Or you might store the connection string that specifies a database that your application uses.</span></span> <span data-ttu-id="5001e-108">La configuración permite que conservar la información que es fundamental para la aplicación fuera del código y creación de perfiles que almacenan las preferencias de usuarios individuales.</span><span class="sxs-lookup"><span data-stu-id="5001e-108">Settings allow you to both persist information that is critical to the application outside the code, and to create profiles that store the preferences of individual users.</span></span>  
  
 <span data-ttu-id="5001e-109">Los temas de esta sección describen cómo usar la configuración en tiempo de diseño y tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="5001e-109">The topics in this section describe how to use settings at design time and run time.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5001e-110">En esta sección</span><span class="sxs-lookup"><span data-stu-id="5001e-110">In This Section</span></span>  
 [<span data-ttu-id="5001e-111">Cómo: Crear una nueva configuración en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="5001e-111">How To: Create a New Setting at Design Time</span></span>](how-to-create-a-new-setting-at-design-time.md)  
  
 <span data-ttu-id="5001e-112">Explica cómo utilizar Visual Studio para crear una nueva configuración para una aplicación.</span><span class="sxs-lookup"><span data-stu-id="5001e-112">Explains how to use Visual Studio to create a new setting for an application.</span></span>  
  
 [<span data-ttu-id="5001e-113">Cómo: Cambie el valor de una configuración existente en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="5001e-113">How To: Change the Value of an Existing Setting at Design Time</span></span>](how-to-change-the-value-of-an-existing-setting-at-design-time.md)  
  
 <span data-ttu-id="5001e-114">Describe cómo usar Visual Studio para cambiar el valor de una configuración existente.</span><span class="sxs-lookup"><span data-stu-id="5001e-114">Describes how to use Visual Studio to change the value of an existing setting.</span></span>  
  
 [<span data-ttu-id="5001e-115">Cómo: Cambie el valor de una configuración entre sesiones de aplicación</span><span class="sxs-lookup"><span data-stu-id="5001e-115">How To: Change the Value of a Setting Between Application Sessions</span></span>](how-to-change-the-value-of-a-setting-between-application-sessions.md)  
  
 <span data-ttu-id="5001e-116">Detalla cómo cambiar el valor de una configuración en una aplicación compilada entre sesiones de aplicación.</span><span class="sxs-lookup"><span data-stu-id="5001e-116">Details how to change the value of a setting in a compiled application between application sessions.</span></span>  
  
 [<span data-ttu-id="5001e-117">Cómo: Leer la configuración en tiempo de ejecución conC#</span><span class="sxs-lookup"><span data-stu-id="5001e-117">How To: Read Settings at Run Time With C#</span></span>](how-to-read-settings-at-run-time-with-csharp.md)  
  
 <span data-ttu-id="5001e-118">Describe cómo usar código para leer la configuración con C#.</span><span class="sxs-lookup"><span data-stu-id="5001e-118">Describes how to use code to read settings with C#.</span></span>  
  
 [<span data-ttu-id="5001e-119">Cómo: Escribir la configuración de usuario en tiempo de ejecución conC#</span><span class="sxs-lookup"><span data-stu-id="5001e-119">How To: Write User Settings at Run Time with C#</span></span>](how-to-write-user-settings-at-run-time-with-csharp.md)  
  
 <span data-ttu-id="5001e-120">Se explica cómo usar código para escribir y guardar los valores de configuración de usuario con C#.</span><span class="sxs-lookup"><span data-stu-id="5001e-120">Explains how to use code to write and save the values of user settings with C#.</span></span>  
  
 [<span data-ttu-id="5001e-121">Cómo: Agregar varios conjuntos de configuración a la aplicación enC#</span><span class="sxs-lookup"><span data-stu-id="5001e-121">How To: Add Multiple Sets of Settings To Your Application in C#</span></span>](how-to-add-multiple-sets-of-settings-to-your-application-in-csharp.md)  
  
 <span data-ttu-id="5001e-122">Detalla cómo agregar varios conjuntos de configuración a una aplicación con C#.</span><span class="sxs-lookup"><span data-stu-id="5001e-122">Details how to add multiple sets of settings to an application with C#.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5001e-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="5001e-123">See also</span></span>

- [<span data-ttu-id="5001e-124">Configuración de la aplicación en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5001e-124">Application Settings for Windows Forms</span></span>](application-settings-for-windows-forms.md)
