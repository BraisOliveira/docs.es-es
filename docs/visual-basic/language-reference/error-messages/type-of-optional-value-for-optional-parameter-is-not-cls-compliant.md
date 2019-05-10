---
title: El tipo de valor opcional para el parámetro opcional <parametername> no es compatible con CLS
ms.date: 07/20/2015
f1_keywords:
- BC40042
- vbc40042
helpviewer_keywords:
- BC40042
ms.assetid: 1d6eae29-4ad3-4434-bde4-a53b6051adf5
ms.openlocfilehash: ee7d208f7a579f81690ffbda265bde29316e4ec3
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64664299"
---
# <a name="type-of-optional-value-for-optional-parameter-parametername-is-not-cls-compliant"></a><span data-ttu-id="a704a-102">Tipo de valor opcional para el parámetro opcional \<parametername > no es conforme a CLS</span><span class="sxs-lookup"><span data-stu-id="a704a-102">Type of optional value for optional parameter \<parametername> is not CLS-compliant</span></span>
<span data-ttu-id="a704a-103">Un procedimiento se marca como `<CLSCompliant(True)>`, pero declara un parámetro [opcional](../../../visual-basic/language-reference/modifiers/optional.md) con valor predeterminado de un tipo no conforme.</span><span class="sxs-lookup"><span data-stu-id="a704a-103">A procedure is marked as `<CLSCompliant(True)>` but declares an [Optional](../../../visual-basic/language-reference/modifiers/optional.md) parameter with default value of a noncompliant type.</span></span>  
  
 <span data-ttu-id="a704a-104">Para que un procedimiento sea conforme a la [Independencia del lenguaje y componentes independientes del lenguaje](../../../standard/language-independence-and-language-independent-components.md) (CLS), solo debe usar tipos conformes a CLS.</span><span class="sxs-lookup"><span data-stu-id="a704a-104">For a procedure to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), it must use only CLS-compliant types.</span></span> <span data-ttu-id="a704a-105">Esto se aplica a los tipos de los parámetros, el tipo de valor devuelto y los tipos de todas sus variables locales.</span><span class="sxs-lookup"><span data-stu-id="a704a-105">This applies to the types of the parameters, the return type, and the types of all its local variables.</span></span> <span data-ttu-id="a704a-106">También se aplica a los valores predeterminados de parámetros opcionales.</span><span class="sxs-lookup"><span data-stu-id="a704a-106">It also applies to the default values of optional parameters.</span></span>  
  
 <span data-ttu-id="a704a-107">Los siguientes tipos de datos de Visual Basic no son conformes a CLS:</span><span class="sxs-lookup"><span data-stu-id="a704a-107">The following Visual Basic data types are not CLS-compliant:</span></span>  
  
- [<span data-ttu-id="a704a-108">SByte (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="a704a-108">SByte Data Type</span></span>](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
- [<span data-ttu-id="a704a-109">UInteger (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="a704a-109">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
- [<span data-ttu-id="a704a-110">ULong (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="a704a-110">ULong Data Type</span></span>](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
- [<span data-ttu-id="a704a-111">UShort (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="a704a-111">UShort Data Type</span></span>](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 <span data-ttu-id="a704a-112">Al aplicar el atributo <xref:System.CLSCompliantAttribute> a un elemento de programación, establezca el parámetro `isCompliant` del atributo como `True` o `False` para indicar compatibilidad o incompatibilidad.</span><span class="sxs-lookup"><span data-stu-id="a704a-112">When you apply the <xref:System.CLSCompliantAttribute> attribute to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="a704a-113">No hay ningún valor predeterminado para este parámetro, por lo que debe proporcionar uno.</span><span class="sxs-lookup"><span data-stu-id="a704a-113">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="a704a-114">Si no aplica <xref:System.CLSCompliantAttribute> a un elemento, se considera que no es conforme.</span><span class="sxs-lookup"><span data-stu-id="a704a-114">If you do not apply <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="a704a-115">De forma predeterminada, este mensaje es una advertencia.</span><span class="sxs-lookup"><span data-stu-id="a704a-115">By default, this message is a warning.</span></span> <span data-ttu-id="a704a-116">Para obtener más información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="a704a-116">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="a704a-117">**Identificador de error:** BC40042</span><span class="sxs-lookup"><span data-stu-id="a704a-117">**Error ID:** BC40042</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a704a-118">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="a704a-118">To correct this error</span></span>  
  
- <span data-ttu-id="a704a-119">Si el parámetro opcional debe tener un valor predeterminado de este tipo particular, quite <xref:System.CLSCompliantAttribute>.</span><span class="sxs-lookup"><span data-stu-id="a704a-119">If the optional parameter must have a default value of this particular type, remove <xref:System.CLSCompliantAttribute>.</span></span> <span data-ttu-id="a704a-120">El procedimiento no puede ser conforme a CLS.</span><span class="sxs-lookup"><span data-stu-id="a704a-120">The procedure cannot be CLS-compliant.</span></span>  
  
- <span data-ttu-id="a704a-121">Si el procedimiento debe ser conforme a CLS, cambie el tipo de este valor predeterminado al tipo conforme a CLS más próximo.</span><span class="sxs-lookup"><span data-stu-id="a704a-121">If the procedure must be CLS-compliant, change the type of this default value to the closest CLS-compliant type.</span></span> <span data-ttu-id="a704a-122">Por ejemplo, en lugar de `UInteger` , quizá pueda usar `Integer` si no necesita que el intervalo de valores esté por encima de 2.147.483.647.</span><span class="sxs-lookup"><span data-stu-id="a704a-122">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="a704a-123">Si necesita el intervalo extendido, puede reemplazar `UInteger` por `Long`.</span><span class="sxs-lookup"><span data-stu-id="a704a-123">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>  
  
- <span data-ttu-id="a704a-124">Si trabaja con objetos de automatización o COM, tenga en cuenta que algunos tipos tienen anchos de datos distintos que en [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a704a-124">If you are interfacing with Automation or COM objects, keep in mind that some types have different data widths than in the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="a704a-125">Por ejemplo, `int` suele ser de 16 bits en otros entornos.</span><span class="sxs-lookup"><span data-stu-id="a704a-125">For example, `int` is often 16 bits in other environments.</span></span> <span data-ttu-id="a704a-126">Si se acepta un entero de 16 bits de esos componentes, declárelo como `Short` en lugar de `Integer` en el código administrado de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="a704a-126">If you are accepting a 16-bit integer from such a component, declare it as `Short` instead of `Integer` in your managed Visual Basic code.</span></span>