---
title: El espacio de nombres o tipo especificado en las importaciones del proyecto '<qualifiedelementname>' no tiene miembros públicos o no se encuentra
ms.date: 07/20/2015
f1_keywords:
- vbc40057
- bc40057
helpviewer_keywords:
- BC40057
ms.assetid: 4ae3506e-2ebe-4ff3-995d-14ac60db5e9f
ms.openlocfilehash: 105fa8da838938d13022c210c1f65cdafd251003
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61918312"
---
# <a name="namespace-or-type-specified-in-the-project-level-imports-qualifiedelementname-doesnt-contain-any-public-member-or-cannot-be-found"></a><span data-ttu-id="e7450-102">Namespace o tipo especificado en el nivel de proyecto Imports'\<nombrecompletoelemento >' no contiene ningún miembro público o no se encuentra</span><span class="sxs-lookup"><span data-stu-id="e7450-102">Namespace or type specified in the project-level Imports '\<qualifiedelementname>' doesn't contain any public member or cannot be found</span></span>
<span data-ttu-id="e7450-103">Namespace o tipo especificado en el nivel de proyecto Imports'\<nombrecompletoelemento >' no contiene ningún miembro público o no se encuentra.</span><span class="sxs-lookup"><span data-stu-id="e7450-103">Namespace or type specified in the project-level Imports '\<qualifiedelementname>' doesn't contain any public member or cannot be found.</span></span> <span data-ttu-id="e7450-104">Asegúrese de que el espacio de nombres o el tipo se define y contiene a al menos un miembro público.</span><span class="sxs-lookup"><span data-stu-id="e7450-104">Make sure the namespace or the type is defined and contains at least one public member.</span></span> <span data-ttu-id="e7450-105">Asegúrese de que el nombre de alias no contiene otros alias.</span><span class="sxs-lookup"><span data-stu-id="e7450-105">Make sure the alias name doesn't contain other aliases.</span></span>  
  
 <span data-ttu-id="e7450-106">Una propiedad de importación de un proyecto especifica un elemento contenedor que no se puede encontrar o no define `Public` miembros.</span><span class="sxs-lookup"><span data-stu-id="e7450-106">An import property of a project specifies a containing element that either cannot be found or does not define any `Public` members.</span></span>  
  
 <span data-ttu-id="e7450-107">Un *que contiene el elemento* puede ser el espacio de nombres, clase, estructura, módulo, interfaz o enumeración.</span><span class="sxs-lookup"><span data-stu-id="e7450-107">A *containing element* can be a namespace, class, structure, module, interface, or enumeration.</span></span> <span data-ttu-id="e7450-108">El elemento contenedor contiene a miembros, como variables, procedimientos u otros elementos que lo contiene.</span><span class="sxs-lookup"><span data-stu-id="e7450-108">The containing element contains members, such as variables, procedures, or other containing elements.</span></span>  
  
 <span data-ttu-id="e7450-109">El propósito de la importación es permitir que el código para obtener acceso a los miembros de tipo o espacio de nombres sin tener que calificarlos.</span><span class="sxs-lookup"><span data-stu-id="e7450-109">The purpose of importing is to allow your code to access namespace or type members without having to qualify them.</span></span> <span data-ttu-id="e7450-110">También podría necesitar el proyecto agregar una referencia al espacio de nombres o tipo.</span><span class="sxs-lookup"><span data-stu-id="e7450-110">Your project might also need to add a reference to the namespace or type.</span></span> <span data-ttu-id="e7450-111">Para obtener más información, vea "Importar elementos contenedores" en [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span><span class="sxs-lookup"><span data-stu-id="e7450-111">For more information, see "Importing Containing Elements" in [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
 <span data-ttu-id="e7450-112">Si el compilador no encuentra el elemento contenedor especificado, no se puede resolver las referencias que lo usan.</span><span class="sxs-lookup"><span data-stu-id="e7450-112">If the compiler cannot find the specified containing element, then it cannot resolve references that use it.</span></span> <span data-ttu-id="e7450-113">Si encuentra el elemento, pero el elemento no exponen ninguno `Public` miembros, ninguna referencia puede ser correcta.</span><span class="sxs-lookup"><span data-stu-id="e7450-113">If it finds the element but the element does not expose any `Public` members, then no reference can be successful.</span></span> <span data-ttu-id="e7450-114">En cualquier caso, tiene sentido para importar el elemento.</span><span class="sxs-lookup"><span data-stu-id="e7450-114">In either case it is meaningless to import the element.</span></span>  
  
 <span data-ttu-id="e7450-115">Usa el **Diseñador de proyectos** para especificar los elementos que se van a importar.</span><span class="sxs-lookup"><span data-stu-id="e7450-115">You use the **Project Designer** to specify elements to import.</span></span> <span data-ttu-id="e7450-116">Use la **espacios de nombres importados** sección de la **referencias** página.</span><span class="sxs-lookup"><span data-stu-id="e7450-116">Use the **Imported namespaces** section of the **References** page.</span></span> <span data-ttu-id="e7450-117">Puede tener acceso a la **Diseñador de proyectos** haciendo doble clic en el **mi proyecto** icono en **el Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="e7450-117">You can get to the **Project Designer** by double-clicking the **My Project** icon in **Solution Explorer**.</span></span>  
  
 <span data-ttu-id="e7450-118">**Identificador de error:** BC40057</span><span class="sxs-lookup"><span data-stu-id="e7450-118">**Error ID:** BC40057</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e7450-119">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="e7450-119">To correct this error</span></span>  
  
1. <span data-ttu-id="e7450-120">Abra el **Diseñador de proyectos** y cambie a la **referencia** página.</span><span class="sxs-lookup"><span data-stu-id="e7450-120">Open the **Project Designer** and switch to the **Reference** page.</span></span>  
  
2. <span data-ttu-id="e7450-121">En el **espacios de nombres importados** sección, compruebe que el elemento contenedor es accesible desde el proyecto.</span><span class="sxs-lookup"><span data-stu-id="e7450-121">In the **Imported namespaces** section, verify that the containing element is accessible from your project.</span></span>  
  
3. <span data-ttu-id="e7450-122">Compruebe que el elemento contenedor expone al menos una `Public` miembro.</span><span class="sxs-lookup"><span data-stu-id="e7450-122">Verify that the containing element exposes at least one `Public` member.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7450-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="e7450-123">See also</span></span>

- [<span data-ttu-id="e7450-124">Página Referencias, Diseñador de proyectos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e7450-124">References Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/references-page-project-designer-visual-basic)
- [<span data-ttu-id="e7450-125">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="e7450-125">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
- [<span data-ttu-id="e7450-126">Public</span><span class="sxs-lookup"><span data-stu-id="e7450-126">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="e7450-127">Espacios de nombres en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e7450-127">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)
- [<span data-ttu-id="e7450-128">Referencias a elementos declarados</span><span class="sxs-lookup"><span data-stu-id="e7450-128">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
