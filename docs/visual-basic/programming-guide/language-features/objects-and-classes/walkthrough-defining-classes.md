---
title: Definición de clases (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- execution [Visual Basic], ending
- objects [Visual Basic], initializing
- Initialize event [Visual Basic]
- files [Visual Basic], closing
- programs [Visual Basic], quitting
- code, exiting
- objects [Visual Basic], creating
- program termination
- classes [Visual Basic], walkthroughs
- class modules, walkthroughs
- Terminate event [Visual Basic]
- execution [Visual Basic], stopping
ms.assetid: 07018828-2d49-4cf5-a44b-19fb15d9efea
ms.openlocfilehash: 3129824f6e4047420c422503cc366a1c8d28b7e7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59326221"
---
# <a name="walkthrough-defining-classes-visual-basic"></a><span data-ttu-id="0d33f-102">Tutorial: Definición de clases (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0d33f-102">Walkthrough: Defining Classes (Visual Basic)</span></span>

<span data-ttu-id="0d33f-103">Este tutorial muestra cómo definir las clases, que, a continuación, puede usar para crear objetos.</span><span class="sxs-lookup"><span data-stu-id="0d33f-103">This walkthrough demonstrates how to define classes, which you can then use to create objects.</span></span> <span data-ttu-id="0d33f-104">También se muestra cómo agregar propiedades y métodos a la nueva clase y se muestra cómo inicializar un objeto.</span><span class="sxs-lookup"><span data-stu-id="0d33f-104">It also shows you how to add properties and methods to the new class, and demonstrates how to initialize an object.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="to-define-a-class"></a><span data-ttu-id="0d33f-105">Para definir una clase</span><span class="sxs-lookup"><span data-stu-id="0d33f-105">To define a class</span></span>
  
1. <span data-ttu-id="0d33f-106">Cree un proyecto haciendo **nuevo proyecto** en el **archivo** menú.</span><span class="sxs-lookup"><span data-stu-id="0d33f-106">Create a project by clicking **New Project** on the **File** menu.</span></span> <span data-ttu-id="0d33f-107">Aparecerá el cuadro de diálogo **Nuevo proyecto** .</span><span class="sxs-lookup"><span data-stu-id="0d33f-107">The **New Project** dialog box appears.</span></span>  
  
2. <span data-ttu-id="0d33f-108">Seleccione la aplicación de Windows en la lista de plantillas de proyecto de Visual Basic para mostrar el nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="0d33f-108">Select Windows Application from the list of Visual Basic project templates to display the new project.</span></span>  
  
3. <span data-ttu-id="0d33f-109">Agregue una nueva clase al proyecto haciendo clic en **Agregar clase** en el **proyecto** menú.</span><span class="sxs-lookup"><span data-stu-id="0d33f-109">Add a new class to the project by clicking **Add Class** on the **Project** menu.</span></span> <span data-ttu-id="0d33f-110">Aparecerá el cuadro de diálogo **Agregar nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="0d33f-110">The **Add New Item** dialog box appears.</span></span>  
  
4. <span data-ttu-id="0d33f-111">Seleccione el **clase** plantilla.</span><span class="sxs-lookup"><span data-stu-id="0d33f-111">Select the **Class** template.</span></span>  
  
5. <span data-ttu-id="0d33f-112">Nombre de la nueva clase `UserNameInfo.vb`y, a continuación, haga clic en **agregar** para mostrar el código para la nueva clase.</span><span class="sxs-lookup"><span data-stu-id="0d33f-112">Name the new class `UserNameInfo.vb`, and then click **Add** to display the code for the new class.</span></span>  
  
     [!code-vb[VbVbalrOOP#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#5)]
  
    > [!NOTE]
    >  <span data-ttu-id="0d33f-113">Puede usar Visual Basic **Editor de código** para agregar una clase al formulario de inicio escribiendo el `Class` palabra clave seguido del nombre de la nueva clase.</span><span class="sxs-lookup"><span data-stu-id="0d33f-113">You can use the Visual Basic **Code Editor** to add a class to your startup form by typing the `Class` keyword followed by the name of the new class.</span></span> <span data-ttu-id="0d33f-114">El **Editor de código** proporciona correspondiente `End Class` instrucción para usted.</span><span class="sxs-lookup"><span data-stu-id="0d33f-114">The **Code Editor** provides a corresponding `End Class` statement for you.</span></span>  
  
6. <span data-ttu-id="0d33f-115">Defina un campo privado para la clase agregando el siguiente código entre el `Class` y `End Class` instrucciones:</span><span class="sxs-lookup"><span data-stu-id="0d33f-115">Define a private field for the class by adding the following code between the `Class` and `End Class` statements:</span></span>  
  
     [!code-vb[VbVbalrOOP#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#7)]
  
     <span data-ttu-id="0d33f-116">Declara el campo como `Private` significa que se puede usar solo dentro de la clase.</span><span class="sxs-lookup"><span data-stu-id="0d33f-116">Declaring the field as `Private` means it can be used only within the class.</span></span> <span data-ttu-id="0d33f-117">Puede hacer que los campos disponibles desde fuera de una clase mediante el uso de modificadores de acceso como `Public` que proporcionan un acceso más.</span><span class="sxs-lookup"><span data-stu-id="0d33f-117">You can make fields available from outside a class by using access modifiers such as `Public` that provide more access.</span></span> <span data-ttu-id="0d33f-118">Para obtener más información, consulte [tener acceso a los niveles en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="0d33f-118">For more information, see [Access levels in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
7. <span data-ttu-id="0d33f-119">Defina una propiedad para la clase agregando el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="0d33f-119">Define a property for the class by adding the following code:</span></span>  
  
     [!code-vb[VbVbalrOOP#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#8)]
  
8. <span data-ttu-id="0d33f-120">Defina un método para la clase agregando el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="0d33f-120">Define a method for the class by adding the following code:</span></span>  
  
     [!code-vb[VbVbalrOOP#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#9)]
  
9. <span data-ttu-id="0d33f-121">Definir un constructor con parámetros para la nueva clase agregando un procedimiento denominado `Sub New`:</span><span class="sxs-lookup"><span data-stu-id="0d33f-121">Define a parameterized constructor for the new class by adding a procedure named `Sub New`:</span></span>  
  
     [!code-vb[VbVbalrOOP#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#10)]
  
     <span data-ttu-id="0d33f-122">El `Sub New` constructor se llama automáticamente cuando se crea un objeto basado en esta clase.</span><span class="sxs-lookup"><span data-stu-id="0d33f-122">The `Sub New` constructor is called automatically when an object based on this class is created.</span></span> <span data-ttu-id="0d33f-123">Este constructor establece el valor del campo que contiene el nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="0d33f-123">This constructor sets the value of the field that holds the user name.</span></span>  
  
## <a name="to-create-a-button-to-test-the-class"></a><span data-ttu-id="0d33f-124">Para crear un botón para probar la clase</span><span class="sxs-lookup"><span data-stu-id="0d33f-124">To create a button to test the class</span></span>
  
1. <span data-ttu-id="0d33f-125">Cambiar el formulario de inicio al modo de diseño haciendo clic en su nombre de **el Explorador de soluciones** y, a continuación, haga clic en **Diseñador de vistas**.</span><span class="sxs-lookup"><span data-stu-id="0d33f-125">Change the startup form to design mode by right-clicking its name in **Solution Explorer** and then clicking **View Designer**.</span></span> <span data-ttu-id="0d33f-126">De forma predeterminada, el formulario de inicio para los proyectos de aplicación de Windows se denomina Form1.vb.</span><span class="sxs-lookup"><span data-stu-id="0d33f-126">By default, the startup form for Windows Application projects is named Form1.vb.</span></span> <span data-ttu-id="0d33f-127">A continuación, aparecerá el formulario principal.</span><span class="sxs-lookup"><span data-stu-id="0d33f-127">The main form will then appear.</span></span>  
  
2. <span data-ttu-id="0d33f-128">Agregue un botón al formulario principal y haga doble clic para mostrar el código de la `Button1_Click` controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="0d33f-128">Add a button to the main form and double-click it to display the code for the `Button1_Click` event handler.</span></span> <span data-ttu-id="0d33f-129">Agregue el siguiente código para llamar al procedimiento de prueba:</span><span class="sxs-lookup"><span data-stu-id="0d33f-129">Add the following code to call the test procedure:</span></span>  
  
     [!code-vb[VbVbalrOOP#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#12)]
  
## <a name="to-run-your-application"></a><span data-ttu-id="0d33f-130">Para ejecutar la aplicación</span><span class="sxs-lookup"><span data-stu-id="0d33f-130">To run your application</span></span>
  
1. <span data-ttu-id="0d33f-131">Ejecute la aplicación presionando F5.</span><span class="sxs-lookup"><span data-stu-id="0d33f-131">Run your application by pressing F5.</span></span> <span data-ttu-id="0d33f-132">Haga clic en el botón del formulario para llamar al procedimiento de prueba.</span><span class="sxs-lookup"><span data-stu-id="0d33f-132">Click the button on the form to call the test procedure.</span></span> <span data-ttu-id="0d33f-133">Muestra un mensaje que indica que el original `UserName` es "MOORE, BOBBY", porque se llama al procedimiento el `Capitalize` método del objeto.</span><span class="sxs-lookup"><span data-stu-id="0d33f-133">It displays a message stating that the original `UserName` is "MOORE, BOBBY", because the procedure called the `Capitalize` method of the object.</span></span>  
  
2. <span data-ttu-id="0d33f-134">Haga clic en **Aceptar** para descartar el cuadro de mensaje.</span><span class="sxs-lookup"><span data-stu-id="0d33f-134">Click **OK** to dismiss the message box.</span></span> <span data-ttu-id="0d33f-135">El `Button1 Click` procedimiento cambia el valor de la `UserName` propiedad y se muestra un mensaje que indica que el nuevo valor de `UserName` es "Worden, Joe".</span><span class="sxs-lookup"><span data-stu-id="0d33f-135">The `Button1 Click` procedure changes the value of the `UserName` property and displays a message stating that the new value of `UserName` is "Worden, Joe".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d33f-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="0d33f-136">See also</span></span>

- [<span data-ttu-id="0d33f-137">Programación orientada a objetos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0d33f-137">Object-Oriented Programming (Visual Basic)</span></span>](../../concepts/object-oriented-programming.md)
- [<span data-ttu-id="0d33f-138">Objetos y clases</span><span class="sxs-lookup"><span data-stu-id="0d33f-138">Objects and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
