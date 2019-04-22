---
title: Cuándo se debe usar una enumeración (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic]
ms.assetid: e6e47b5b-3ed9-452d-a481-9c3fed88519a
ms.openlocfilehash: ff2d8c324aee8bbccef050c020e5392368b05b1c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58825110"
---
# <a name="when-to-use-an-enumeration-visual-basic"></a><span data-ttu-id="261c0-102">Cuándo se debe usar una enumeración (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="261c0-102">When to Use an Enumeration (Visual Basic)</span></span>
<span data-ttu-id="261c0-103">Las enumeraciones ofrecen una manera fácil de trabajar con conjuntos de constantes relacionadas.</span><span class="sxs-lookup"><span data-stu-id="261c0-103">Enumerations offer an easy way to work with sets of related constants.</span></span> <span data-ttu-id="261c0-104">Una enumeración, o `Enum`, es un nombre simbólico para un conjunto de valores.</span><span class="sxs-lookup"><span data-stu-id="261c0-104">An enumeration, or `Enum`, is a symbolic name for a set of values.</span></span> <span data-ttu-id="261c0-105">Las enumeraciones se tratan como tipos de datos, y puede usarlos para crear conjuntos de constantes para su uso con variables y propiedades.</span><span class="sxs-lookup"><span data-stu-id="261c0-105">Enumerations are treated as data types, and you can use them to create sets of constants for use with variables and properties.</span></span>  
  
## <a name="when-to-use-an-enumeration"></a><span data-ttu-id="261c0-106">Cuándo se debe utilizar una enumeración</span><span class="sxs-lookup"><span data-stu-id="261c0-106">When to Use an Enumeration</span></span>  
 <span data-ttu-id="261c0-107">Cada vez que un procedimiento acepta un conjunto limitado de variables, considere el uso de una enumeración.</span><span class="sxs-lookup"><span data-stu-id="261c0-107">Whenever a procedure accepts a limited set of variables, consider using an enumeration.</span></span> <span data-ttu-id="261c0-108">Asegúrese de enumeraciones para el código más claro y legible, especialmente cuando se usan nombres descriptivos.</span><span class="sxs-lookup"><span data-stu-id="261c0-108">Enumerations make for clearer and more readable code, particularly when meaningful names are used.</span></span>  
  
 <span data-ttu-id="261c0-109">Las ventajas del uso de las enumeraciones son:</span><span class="sxs-lookup"><span data-stu-id="261c0-109">The benefits of using enumerations include:</span></span>  
  
-   <span data-ttu-id="261c0-110">Reduce los errores causados por números transpuestos o.</span><span class="sxs-lookup"><span data-stu-id="261c0-110">Reduces errors caused by transposing or mistyping numbers.</span></span>  
  
-   <span data-ttu-id="261c0-111">Es fácil cambiar los valores en el futuro.</span><span class="sxs-lookup"><span data-stu-id="261c0-111">Makes it easy to change values in the future.</span></span>  
  
-   <span data-ttu-id="261c0-112">Hace el código más fácil de leer, lo que significa que es menos probable que los errores se cuelen en él.</span><span class="sxs-lookup"><span data-stu-id="261c0-112">Makes code easier to read, which means it is less likely that errors will creep into it.</span></span>  
  
-   <span data-ttu-id="261c0-113">Garantiza la compatibilidad con versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="261c0-113">Ensures forward compatibility.</span></span> <span data-ttu-id="261c0-114">Con enumeraciones, el código es menos probable que un error si en el futuro que alguien cambia los valores correspondientes a los nombres de miembro.</span><span class="sxs-lookup"><span data-stu-id="261c0-114">With enumerations, your code is less likely to fail if in the future someone changes the values corresponding to the member names.</span></span>  
  
## <a name="naming-enumerations"></a><span data-ttu-id="261c0-115">Enumeraciones de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="261c0-115">Naming Enumerations</span></span>  
 <span data-ttu-id="261c0-116">Utilice una convención de nomenclatura para los miembros de enumeración.</span><span class="sxs-lookup"><span data-stu-id="261c0-116">Use a naming convention for enumeration members.</span></span> <span data-ttu-id="261c0-117">Cuando Visual Basic encuentra un nombre de miembro de enumeración, se puede producir una excepción si otras bibliotecas de tipos que se hace referencia contienen el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="261c0-117">When Visual Basic encounters an enumeration member name, an exception may be thrown if other referenced type libraries contain the same name.</span></span> <span data-ttu-id="261c0-118">Use un prefijo único que identifica los valores de la aplicación o componente.</span><span class="sxs-lookup"><span data-stu-id="261c0-118">Use a unique prefix that identifies the values from your application or component.</span></span>  
  
 <span data-ttu-id="261c0-119">Cuando se hace referencia a un miembro de una enumeración, debe calificar el nombre de miembro con el nombre de la enumeración, o bien usar la `Imports` instrucción.</span><span class="sxs-lookup"><span data-stu-id="261c0-119">When referring to a member of an enumeration, you must qualify the member name with the enumeration name or else use the `Imports` statement.</span></span> <span data-ttu-id="261c0-120">Para obtener más información, consulte [enumeraciones y calificación de nombres](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).</span><span class="sxs-lookup"><span data-stu-id="261c0-120">For more information, see [Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).</span></span>  
  
## <a name="predefined-enumerations"></a><span data-ttu-id="261c0-121">Enumeraciones predefinidas</span><span class="sxs-lookup"><span data-stu-id="261c0-121">Predefined Enumerations</span></span>  
 <span data-ttu-id="261c0-122">Visual Basic proporciona una serie de enumeraciones predefinidas, como `FirstDayOfWeek` y `MsgBoxResult`, para facilitar el código.</span><span class="sxs-lookup"><span data-stu-id="261c0-122">Visual Basic provides a number of predefined enumerations, such as `FirstDayOfWeek` and `MsgBoxResult`, to facilitate your code.</span></span> <span data-ttu-id="261c0-123">Para obtener una lista de estos, consulte [constantes y enumeraciones](../../../../visual-basic/language-reference/constants-and-enumerations.md).</span><span class="sxs-lookup"><span data-stu-id="261c0-123">For a list of these see [Constants and Enumerations](../../../../visual-basic/language-reference/constants-and-enumerations.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="261c0-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="261c0-124">See also</span></span>

- [<span data-ttu-id="261c0-125">Cómo: Declarar una enumeración</span><span class="sxs-lookup"><span data-stu-id="261c0-125">How to: Declare an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [<span data-ttu-id="261c0-126">Cómo: Hacer referencia a un miembro de enumeración</span><span class="sxs-lookup"><span data-stu-id="261c0-126">How to: Refer to an Enumeration Member</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="261c0-127">Enumeraciones y calificación de nombres</span><span class="sxs-lookup"><span data-stu-id="261c0-127">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [<span data-ttu-id="261c0-128">Cómo: Recorrer en iteración una enumeración en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="261c0-128">How to: Iterate Through An Enumeration in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)
- [<span data-ttu-id="261c0-129">Cómo: Determinar la cadena asociada con un valor de enumeración</span><span class="sxs-lookup"><span data-stu-id="261c0-129">How to: Determine the String Associated with an Enumeration Value</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [<span data-ttu-id="261c0-130">Enum (instrucción)</span><span class="sxs-lookup"><span data-stu-id="261c0-130">Enum Statement</span></span>](../../../../visual-basic/language-reference/statements/enum-statement.md)
- [<span data-ttu-id="261c0-131">Constantes y enumeraciones</span><span class="sxs-lookup"><span data-stu-id="261c0-131">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)
