---
title: Compilación condicional en Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- conditional compilation [Visual Basic], about conditional compilation
- compilation [Visual Basic], conditional
ms.assetid: 9c35e55e-7eee-44fb-a586-dad1f1884848
ms.openlocfilehash: 828edf2e5491394f5ac802b5c9babfb3df359e59
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61758462"
---
# <a name="conditional-compilation-in-visual-basic"></a><span data-ttu-id="8cf62-102">Compilación condicional en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8cf62-102">Conditional Compilation in Visual Basic</span></span>
<span data-ttu-id="8cf62-103">En *compilación condicional*, bloques concretos de código en un programa se compilan selectivamente mientras otros se omiten.</span><span class="sxs-lookup"><span data-stu-id="8cf62-103">In *conditional compilation*, particular blocks of code in a program are compiled selectively while others are ignored.</span></span>  
  
 <span data-ttu-id="8cf62-104">Por ejemplo, puede escribir instrucciones de depuración que comparan la velocidad de enfoques diferentes para la tarea de programación misma, o que desee localizar una aplicación para varios idiomas.</span><span class="sxs-lookup"><span data-stu-id="8cf62-104">For example, you may want to write debugging statements that compare the speed of different approaches to the same programming task, or you may want to localize an application for multiple languages.</span></span> <span data-ttu-id="8cf62-105">Instrucciones de compilación condicional están diseñadas para ejecutarse durante el tiempo de compilación, no en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="8cf62-105">Conditional compilation statements are designed to run during compile time, not at run time.</span></span>  
  
 <span data-ttu-id="8cf62-106">Para indicar los bloques de código que se compilarán con la `#If...Then...#Else` directiva.</span><span class="sxs-lookup"><span data-stu-id="8cf62-106">You denote blocks of code to be conditionally compiled with the `#If...Then...#Else` directive.</span></span> <span data-ttu-id="8cf62-107">Por ejemplo, para francés y alemán de crear versiones de la misma aplicación desde el mismo código fuente, incrustar los segmentos de código específico de plataforma en `#If...Then` instrucciones mediante las constantes predefinidas `FrenchVersion` y `GermanVersion`.</span><span class="sxs-lookup"><span data-stu-id="8cf62-107">For example, to create French- and German-language versions of the same application from the same source code, you embed platform-specific code segments in `#If...Then` statements using the predefined constants `FrenchVersion` and `GermanVersion`.</span></span> <span data-ttu-id="8cf62-108">En el ejemplo siguiente se muestra cómo:</span><span class="sxs-lookup"><span data-stu-id="8cf62-108">The following example demonstrates how:</span></span>  
  
 [!code-vb[VbVbalrConditionalComp#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#5)]  
  
 <span data-ttu-id="8cf62-109">Si establece el valor de la `FrenchVersion` constante de compilación condicional para `True` en tiempo de compilación, se compila el código condicional de la versión en francés.</span><span class="sxs-lookup"><span data-stu-id="8cf62-109">If you set the value of the `FrenchVersion` conditional compilation constant to `True` at compile time, the conditional code for the French version is compiled.</span></span> <span data-ttu-id="8cf62-110">Si establece el valor de la `GermanVersion` constante a `True`, el compilador usa la versión en alemán.</span><span class="sxs-lookup"><span data-stu-id="8cf62-110">If you set the value of the `GermanVersion` constant to `True`, the compiler uses the German version.</span></span> <span data-ttu-id="8cf62-111">Si ninguno está establecido en `True`, el código en los últimos `Else` bloquear ejecuciones.</span><span class="sxs-lookup"><span data-stu-id="8cf62-111">If neither is set to `True`, the code in the last `Else` block runs.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8cf62-112">Autocompletar le no funcionará al editar código y el uso de directivas de compilación condicional si el código no forma parte de la rama actual.</span><span class="sxs-lookup"><span data-stu-id="8cf62-112">Autocompletion will not function when editing code and using conditional compilation directives if the code is not part of the current branch.</span></span>  
  
## <a name="declaring-conditional-compilation-constants"></a><span data-ttu-id="8cf62-113">Declarar constantes de compilación condicional</span><span class="sxs-lookup"><span data-stu-id="8cf62-113">Declaring Conditional Compilation Constants</span></span>  
 <span data-ttu-id="8cf62-114">Puede establecer las constantes de compilación condicional en uno de tres maneras:</span><span class="sxs-lookup"><span data-stu-id="8cf62-114">You can set conditional compilation constants in one of three ways:</span></span>  
  
- <span data-ttu-id="8cf62-115">En el **Diseñador de proyectos**</span><span class="sxs-lookup"><span data-stu-id="8cf62-115">In the **Project Designer**</span></span>  
  
- <span data-ttu-id="8cf62-116">En la línea de comandos cuando se usa el compilador de línea de comandos</span><span class="sxs-lookup"><span data-stu-id="8cf62-116">At the command line when using the command-line compiler</span></span>  
  
- <span data-ttu-id="8cf62-117">En el código</span><span class="sxs-lookup"><span data-stu-id="8cf62-117">In your code</span></span>  
  
 <span data-ttu-id="8cf62-118">Constantes de compilación condicional tienen un ámbito especial y no es accesible desde el código estándar.</span><span class="sxs-lookup"><span data-stu-id="8cf62-118">Conditional compilation constants have a special scope and cannot be accessed from standard code.</span></span> <span data-ttu-id="8cf62-119">El ámbito de una constante de compilación condicional es dependiente de la forma en que se establece.</span><span class="sxs-lookup"><span data-stu-id="8cf62-119">The scope of a conditional compilation constant is dependent on the way it is set.</span></span> <span data-ttu-id="8cf62-120">La tabla siguiente enumera el ámbito de las constantes declaradas con cada uno de los tres métodos mencionados anteriormente.</span><span class="sxs-lookup"><span data-stu-id="8cf62-120">The following table lists the scope of constants declared using each of the three ways mentioned above.</span></span>  
  
|<span data-ttu-id="8cf62-121">¿Cómo se establece (constante)</span><span class="sxs-lookup"><span data-stu-id="8cf62-121">How constant is set</span></span>|<span data-ttu-id="8cf62-122">Ámbito de constante</span><span class="sxs-lookup"><span data-stu-id="8cf62-122">Scope of constant</span></span>|  
|---|---|  
|<span data-ttu-id="8cf62-123">**Diseñador de proyectos**</span><span class="sxs-lookup"><span data-stu-id="8cf62-123">**Project Designer**</span></span>|<span data-ttu-id="8cf62-124">Public para todos los archivos del proyecto</span><span class="sxs-lookup"><span data-stu-id="8cf62-124">Public to all files in the project</span></span>|  
|<span data-ttu-id="8cf62-125">Línea de comandos</span><span class="sxs-lookup"><span data-stu-id="8cf62-125">Command line</span></span>|<span data-ttu-id="8cf62-126">Public para todos los archivos que se pasó al compilador de línea de comandos</span><span class="sxs-lookup"><span data-stu-id="8cf62-126">Public to all files passed to the command-line compiler</span></span>|  
|<span data-ttu-id="8cf62-127">`#Const` instrucción de código</span><span class="sxs-lookup"><span data-stu-id="8cf62-127">`#Const` statement in code</span></span>|<span data-ttu-id="8cf62-128">En el archivo en el que se declara private</span><span class="sxs-lookup"><span data-stu-id="8cf62-128">Private to the file in which it is declared</span></span>|  
  
|<span data-ttu-id="8cf62-129">Para definir constantes en el Diseñador de proyectos</span><span class="sxs-lookup"><span data-stu-id="8cf62-129">To set constants in the Project Designer</span></span>|  
|---|  
|<span data-ttu-id="8cf62-130">-Antes de crear el archivo ejecutable, defina las constantes en el **Diseñador de proyectos** siguiendo los pasos proporcionados en [administrar propiedades de soluciones y proyectos](/visualstudio/ide/managing-project-and-solution-properties).</span><span class="sxs-lookup"><span data-stu-id="8cf62-130">-   Before creating your executable file, set constants in the **Project Designer** by following the steps provided in [Managing Project and Solution Properties](/visualstudio/ide/managing-project-and-solution-properties).</span></span>|  
  
|<span data-ttu-id="8cf62-131">Para definir constantes en la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="8cf62-131">To set constants at the command line</span></span>|  
|---|  
|<span data-ttu-id="8cf62-132">-Use el **/d** conmutador para especificar constantes de compilación condicional, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8cf62-132">-   Use the **/d** switch to enter conditional compilation constants, as in the following example:</span></span><br />     `vbc MyProj.vb /d:conFrenchVersion=–1:conANSI=0`<br />     <span data-ttu-id="8cf62-133">No se requiere ningún espacio entre el **/d** modificador y la primera constante.</span><span class="sxs-lookup"><span data-stu-id="8cf62-133">No space is required between the **/d** switch and the first constant.</span></span> <span data-ttu-id="8cf62-134">Para obtener más información, consulte [/ define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md).</span><span class="sxs-lookup"><span data-stu-id="8cf62-134">For more information, see [/define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md).</span></span><br />     <span data-ttu-id="8cf62-135">Las declaraciones de línea de comandos reemplazan a las especificadas en el **Diseñador de proyectos**, pero no eliminarlas.</span><span class="sxs-lookup"><span data-stu-id="8cf62-135">Command-line declarations override declarations entered in the **Project Designer**, but do not erase them.</span></span> <span data-ttu-id="8cf62-136">Argumentos que se establecen **Diseñador de proyectos** siguen en vigor para las compilaciones posteriores.</span><span class="sxs-lookup"><span data-stu-id="8cf62-136">Arguments set in **Project Designer** remain in effect for subsequent compilations.</span></span><br />     <span data-ttu-id="8cf62-137">Al escribir constantes en el propio código, no hay ninguna reglas estrictas en cuanto a su ubicación, ya que su ámbito es el módulo completo en el que se declaran.</span><span class="sxs-lookup"><span data-stu-id="8cf62-137">When writing constants in the code itself, there are no strict rules as to their placement, since their scope is the entire module in which they are declared.</span></span>|  
  
|<span data-ttu-id="8cf62-138">Para definir constantes en el código</span><span class="sxs-lookup"><span data-stu-id="8cf62-138">To set constants in your code</span></span>|  
|---|  
|<span data-ttu-id="8cf62-139">-Coloque las constantes en el bloque de declaración del módulo en el que se usan.</span><span class="sxs-lookup"><span data-stu-id="8cf62-139">-   Place the constants in the declaration block of the module in which they are used.</span></span> <span data-ttu-id="8cf62-140">Esto ayuda a mantener el código organizado y más fácil de leer.</span><span class="sxs-lookup"><span data-stu-id="8cf62-140">This helps keep your code organized and easier to read.</span></span>|  
  
## <a name="related-topics"></a><span data-ttu-id="8cf62-141">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="8cf62-141">Related Topics</span></span>  
  
|<span data-ttu-id="8cf62-142">Título</span><span class="sxs-lookup"><span data-stu-id="8cf62-142">Title</span></span>|<span data-ttu-id="8cf62-143">Descripción</span><span class="sxs-lookup"><span data-stu-id="8cf62-143">Description</span></span>|  
|---|---|  
|[<span data-ttu-id="8cf62-144">Convenciones de código y estructura de programas</span><span class="sxs-lookup"><span data-stu-id="8cf62-144">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)|<span data-ttu-id="8cf62-145">Proporciona sugerencias para hacer que el código sea fácil de leer y mantener.</span><span class="sxs-lookup"><span data-stu-id="8cf62-145">Provides suggestions for making your code easy to read and maintain.</span></span>|  
  
## <a name="reference"></a><span data-ttu-id="8cf62-146">Referencia</span><span class="sxs-lookup"><span data-stu-id="8cf62-146">Reference</span></span>  
 [<span data-ttu-id="8cf62-147">#Const (directiva)</span><span class="sxs-lookup"><span data-stu-id="8cf62-147">#Const Directive</span></span>](../../../visual-basic/language-reference/directives/const-directive.md)  
  
 [<span data-ttu-id="8cf62-148">#If...Then...#Else (directivas)</span><span class="sxs-lookup"><span data-stu-id="8cf62-148">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
  
 [<span data-ttu-id="8cf62-149">/define (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8cf62-149">/define (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/define.md)
