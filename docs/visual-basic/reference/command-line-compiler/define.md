---
title: -Definir (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- -d compiler option [Visual Basic]
- /d compiler option [Visual Basic]
- -define compiler option [Visual Basic]
- d compiler option [Visual Basic]
- /define compiler option [Visual Basic]
- define compiler option [Visual Basic]
ms.assetid: f735c57d-1cf9-4f2f-a26f-0de630fd4077
ms.openlocfilehash: d0a483e7a3c9e9863db39e89d655cf172c1e8c81
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58834314"
---
# <a name="-define-visual-basic"></a><span data-ttu-id="e6ebb-102">-Definir (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e6ebb-102">-define (Visual Basic)</span></span>
<span data-ttu-id="e6ebb-103">Permite definir constantes condicionales para el compilador.</span><span class="sxs-lookup"><span data-stu-id="e6ebb-103">Defines conditional compiler constants.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6ebb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e6ebb-104">Syntax</span></span>  
  
```  
-define:["]symbol[=value][,symbol[=value]]["]  
' -or-  
-d:["]symbol[=value][,symbol[=value]]["]  
```  
  
## <a name="arguments"></a><span data-ttu-id="e6ebb-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="e6ebb-105">Arguments</span></span>  
  
|<span data-ttu-id="e6ebb-106">Término</span><span class="sxs-lookup"><span data-stu-id="e6ebb-106">Term</span></span>|<span data-ttu-id="e6ebb-107">de esquema JSON</span><span class="sxs-lookup"><span data-stu-id="e6ebb-107">Definition</span></span>|  
|---|---|  
|`symbol`|<span data-ttu-id="e6ebb-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="e6ebb-108">Required.</span></span> <span data-ttu-id="e6ebb-109">Símbolo que se va a definir.</span><span class="sxs-lookup"><span data-stu-id="e6ebb-109">The symbol to define.</span></span>|  
|`value`|<span data-ttu-id="e6ebb-110">Opcional.</span><span class="sxs-lookup"><span data-stu-id="e6ebb-110">Optional.</span></span> <span data-ttu-id="e6ebb-111">Valor que se va a asignar a `symbol`.</span><span class="sxs-lookup"><span data-stu-id="e6ebb-111">The value to assign `symbol`.</span></span> <span data-ttu-id="e6ebb-112">Si `value` es una cadena, se debe entrecomillar las secuencias de barra diagonal inversa/comillas (\\") en lugar de comillas.</span><span class="sxs-lookup"><span data-stu-id="e6ebb-112">If `value` is a string, it must be surrounded by backslash/quotation-mark sequences (\\") instead of quotation marks.</span></span> <span data-ttu-id="e6ebb-113">Si no se especifica ningún valor, se considera como verdadero.</span><span class="sxs-lookup"><span data-stu-id="e6ebb-113">If no value is specified, then it is taken to be True.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e6ebb-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e6ebb-114">Remarks</span></span>  
 <span data-ttu-id="e6ebb-115">El `-define` opción tiene un efecto similar al uso de un `#Const` directiva de preprocesador en el archivo de origen, excepto que las constantes definidas con `-define` son públicos y se aplican a todos los archivos del proyecto.</span><span class="sxs-lookup"><span data-stu-id="e6ebb-115">The `-define` option has an effect similar to using a `#Const` preprocessor directive in your source file, except that constants defined with `-define` are public and apply to all files in the project.</span></span>  
  
 <span data-ttu-id="e6ebb-116">Los símbolos creados por esta opción se pueden usar con la directiva `#If`...`Then`...`#Else` para compilar archivos de origen condicionalmente.</span><span class="sxs-lookup"><span data-stu-id="e6ebb-116">You can use symbols created by this option with the `#If`...`Then`...`#Else` directive to compile source files conditionally.</span></span>  
  
 <span data-ttu-id="e6ebb-117">`-d` es la forma abreviada de `-define`.</span><span class="sxs-lookup"><span data-stu-id="e6ebb-117">`-d` is the short form of `-define`.</span></span>  
  
 <span data-ttu-id="e6ebb-118">Se pueden definir varios símbolos con `-define`; use una coma para separar las definiciones de símbolos.</span><span class="sxs-lookup"><span data-stu-id="e6ebb-118">You can define multiple symbols with `-define` by using a comma to separate symbol definitions.</span></span>  
  
|<span data-ttu-id="e6ebb-119">Para definir/establecer en el entorno de desarrollo integrado de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e6ebb-119">To set /define in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="e6ebb-120">1.  Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="e6ebb-120">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="e6ebb-121">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="e6ebb-121">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="e6ebb-122">2.  Haga clic en la pestaña **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="e6ebb-122">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="e6ebb-123">3.  Haga clic en **Avanzado**.</span><span class="sxs-lookup"><span data-stu-id="e6ebb-123">3.  Click **Advanced**.</span></span><br /><span data-ttu-id="e6ebb-124">4.  Modifique el valor en el **constantes personalizadas** cuadro.</span><span class="sxs-lookup"><span data-stu-id="e6ebb-124">4.  Modify the value in the **Custom Constants** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e6ebb-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e6ebb-125">Example</span></span>  
 <span data-ttu-id="e6ebb-126">En el siguiente código se definen y usan dos constantes de compilador condicionales.</span><span class="sxs-lookup"><span data-stu-id="e6ebb-126">The following code defines and then uses two conditional compiler constants.</span></span>  
  
 [!code-vb[VbVbalrCompiler#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/Class1.vb#45)]  
  
## <a name="see-also"></a><span data-ttu-id="e6ebb-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="e6ebb-127">See also</span></span>

- [<span data-ttu-id="e6ebb-128">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e6ebb-128">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="e6ebb-129">#If...Then...#Else (directivas)</span><span class="sxs-lookup"><span data-stu-id="e6ebb-129">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [<span data-ttu-id="e6ebb-130">#Const (directiva)</span><span class="sxs-lookup"><span data-stu-id="e6ebb-130">#Const Directive</span></span>](../../../visual-basic/language-reference/directives/const-directive.md)
- [<span data-ttu-id="e6ebb-131">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="e6ebb-131">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
