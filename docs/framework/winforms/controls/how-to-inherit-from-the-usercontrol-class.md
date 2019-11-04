---
title: 'Cómo: Heredar de una clase UserControl'
ms.date: 03/30/2017
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- UserControl class [Windows Forms], inheriting from
- user controls [Windows Forms], creating
- composite controls [Windows Forms], creating
ms.assetid: 67713625-e2e4-4f6a-bce7-0855ee5043d9
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 10bb807d012a130ad633b7ce06f99c5abf2cdda1
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458372"
---
# <a name="how-to-inherit-from-the-usercontrol-class"></a><span data-ttu-id="f02ad-102">Cómo: Heredar de una clase UserControl</span><span class="sxs-lookup"><span data-stu-id="f02ad-102">How to: Inherit from the UserControl Class</span></span>

<span data-ttu-id="f02ad-103">Para combinar la funcionalidad de uno o más controles de Windows Forms con código personalizado, puede crear un *control de usuario*.</span><span class="sxs-lookup"><span data-stu-id="f02ad-103">To combine the functionality of one or more Windows Forms controls with custom code, you can create a *user control*.</span></span> <span data-ttu-id="f02ad-104">Los controles de usuario combinan el desarrollo rápido de controles, la funcionalidad de los controles de Windows Forms estándar y la versatilidad de los métodos y las propiedades personalizados.</span><span class="sxs-lookup"><span data-stu-id="f02ad-104">User controls combine rapid control development, standard Windows Forms control functionality, and the versatility of custom properties and methods.</span></span> <span data-ttu-id="f02ad-105">Al comenzar a crear un control de usuario, se le presentará un diseñador visible en el que puede colocar los controles de Windows Forms estándar.</span><span class="sxs-lookup"><span data-stu-id="f02ad-105">When you begin creating a user control, you are presented with a visible designer, upon which you can place standard Windows Forms controls.</span></span> <span data-ttu-id="f02ad-106">Estos controles conservan toda su funcionalidad inherente, así como la apariencia y el comportamiento (apariencia) de los controles estándar.</span><span class="sxs-lookup"><span data-stu-id="f02ad-106">These controls retain all of their inherent functionality, as well as the appearance and behavior (look and feel) of standard controls.</span></span> <span data-ttu-id="f02ad-107">Una vez que estos controles están integrados en el control de usuario, dejan de estar disponibles en el código.</span><span class="sxs-lookup"><span data-stu-id="f02ad-107">Once these controls are built into the user control, however, they are no longer available to you through code.</span></span> <span data-ttu-id="f02ad-108">El control de usuario realiza su propio dibujo y controla también toda la funcionalidad básica asociada a los controles.</span><span class="sxs-lookup"><span data-stu-id="f02ad-108">The user control does its own painting and also handles all of the basic functionality associated with controls.</span></span>

## <a name="to-create-a-user-control"></a><span data-ttu-id="f02ad-109">Crear un control de usuario</span><span class="sxs-lookup"><span data-stu-id="f02ad-109">To create a user control</span></span>

1. <span data-ttu-id="f02ad-110">Cree un nuevo proyecto de **biblioteca de controles de Windows** en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f02ad-110">Create a new **Windows Control Library** project in Visual Studio.</span></span>

   <span data-ttu-id="f02ad-111">Se crea un nuevo proyecto con un control de usuario en blanco.</span><span class="sxs-lookup"><span data-stu-id="f02ad-111">A new project is created with a blank user control.</span></span>

2. <span data-ttu-id="f02ad-112">Arrastre controles desde la pestaña **Windows Forms** de **Cuadro de herramientas** en el diseñador.</span><span class="sxs-lookup"><span data-stu-id="f02ad-112">Drag controls from the **Windows Forms** tab of the **Toolbox** onto your designer.</span></span>

3. <span data-ttu-id="f02ad-113">Estos controles deben estar situados y diseñados como desee que aparezcan en el control de usuario final.</span><span class="sxs-lookup"><span data-stu-id="f02ad-113">These controls should be positioned and designed as you want them to appear in the final user control.</span></span> <span data-ttu-id="f02ad-114">Si desea permitir a los desarrolladores tener acceso a los controles constituyentes, deberá declararlos públicos o exponer de forma selectiva las propiedades del control constituyente.</span><span class="sxs-lookup"><span data-stu-id="f02ad-114">If you want to allow developers to access the constituent controls, you must declare them as public, or selectively expose properties of the constituent control.</span></span> <span data-ttu-id="f02ad-115">Para obtener detalles, vea [Cómo: Exponer propiedades de controles constituyentes](how-to-expose-properties-of-constituent-controls.md).</span><span class="sxs-lookup"><span data-stu-id="f02ad-115">For details, see [How to: Expose Properties of Constituent Controls](how-to-expose-properties-of-constituent-controls.md).</span></span>

4. <span data-ttu-id="f02ad-116">Implemente los métodos o propiedades personalizados que vaya a incorporar el control.</span><span class="sxs-lookup"><span data-stu-id="f02ad-116">Implement any custom methods or properties that your control will incorporate.</span></span>

5. <span data-ttu-id="f02ad-117">Presione **F5** para compilar el proyecto y ejecutar el control en **UserControl Test Container**.</span><span class="sxs-lookup"><span data-stu-id="f02ad-117">Press **F5** to build the project and run your control in the **UserControl Test Container**.</span></span> <span data-ttu-id="f02ad-118">Para más información, consulte [Cómo: Comprobar el comportamiento de un control UserControl en tiempo de ejecución](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span><span class="sxs-lookup"><span data-stu-id="f02ad-118">For more information, see [How to: Test the Run-Time Behavior of a UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f02ad-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="f02ad-119">See also</span></span>

- [<span data-ttu-id="f02ad-120">Variedades de controles personalizados</span><span class="sxs-lookup"><span data-stu-id="f02ad-120">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
- [<span data-ttu-id="f02ad-121">Cómo: Heredar de una clase de control</span><span class="sxs-lookup"><span data-stu-id="f02ad-121">How to: Inherit from the Control Class</span></span>](how-to-inherit-from-the-control-class.md)
- [<span data-ttu-id="f02ad-122">Cómo: Heredar de controles de Windows Forms existentes</span><span class="sxs-lookup"><span data-stu-id="f02ad-122">How to: Inherit from Existing Windows Forms Controls</span></span>](how-to-inherit-from-existing-windows-forms-controls.md)
- [<span data-ttu-id="f02ad-123">Cómo: Crear controles de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f02ad-123">How to: Author Controls for Windows Forms</span></span>](how-to-author-controls-for-windows-forms.md)
- [<span data-ttu-id="f02ad-124">Solucionar problemas de controladores de eventos heredados en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f02ad-124">Troubleshoot Inherited Event Handlers in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)
- [<span data-ttu-id="f02ad-125">Cómo: Comprobar el comportamiento de una clase UserControl en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="f02ad-125">How to: Test the Run-Time Behavior of a UserControl</span></span>](how-to-test-the-run-time-behavior-of-a-usercontrol.md)
