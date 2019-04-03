---
title: Error (instrucción) (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.error
helpviewer_keywords:
- Error statement [Visual Basic], syntax
- Error statement [Visual Basic]
- Error keyword [Visual Basic]
- run-time errors [Visual Basic], codes
- errors [Visual Basic], simulating
ms.assetid: 85cd5c59-5224-4f02-aaf5-fcfefab17a29
ms.openlocfilehash: 8ac7cee2f9959bc75df165d00d3a0a67e1dd9af0
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58837538"
---
# <a name="error-statement"></a><span data-ttu-id="457bd-102">Error (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="457bd-102">Error Statement</span></span>
<span data-ttu-id="457bd-103">Simula la aparición de un error.</span><span class="sxs-lookup"><span data-stu-id="457bd-103">Simulates the occurrence of an error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="457bd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="457bd-104">Syntax</span></span>  
  
```  
Error errornumber  
```  
  
## <a name="parts"></a><span data-ttu-id="457bd-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="457bd-105">Parts</span></span>  
 `errornumber`  
 <span data-ttu-id="457bd-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="457bd-106">Required.</span></span> <span data-ttu-id="457bd-107">Puede ser cualquier número de error válido.</span><span class="sxs-lookup"><span data-stu-id="457bd-107">Can be any valid error number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="457bd-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="457bd-108">Remarks</span></span>  
 <span data-ttu-id="457bd-109">El `Error` instrucción se admite por compatibilidad con versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="457bd-109">The `Error` statement is supported for backward compatibility.</span></span> <span data-ttu-id="457bd-110">En el nuevo código, especialmente al crear objetos, utilice el `Err` del objeto `Raise` método para generar errores en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="457bd-110">In new code, especially when creating objects, use the `Err` object's `Raise` method to generate run-time errors.</span></span>  
  
 <span data-ttu-id="457bd-111">Si `errornumber` está definido, el `Error` instrucción llama al controlador de errores después de las propiedades de la `Err` objeto se asignan los valores predeterminados siguientes:</span><span class="sxs-lookup"><span data-stu-id="457bd-111">If `errornumber` is defined, the `Error` statement calls the error handler after the properties of the `Err` object are assigned the following default values:</span></span>  
  
|<span data-ttu-id="457bd-112">Property</span><span class="sxs-lookup"><span data-stu-id="457bd-112">Property</span></span>|<span data-ttu-id="457bd-113">Valor</span><span class="sxs-lookup"><span data-stu-id="457bd-113">Value</span></span>|  
|--------------|-----------|  
|`Number`|<span data-ttu-id="457bd-114">Valor especificado como argumento para `Error` instrucción.</span><span class="sxs-lookup"><span data-stu-id="457bd-114">Value specified as argument to `Error` statement.</span></span> <span data-ttu-id="457bd-115">Puede ser cualquier número de error válido.</span><span class="sxs-lookup"><span data-stu-id="457bd-115">Can be any valid error number.</span></span>|  
|`Source`|<span data-ttu-id="457bd-116">Nombre del proyecto actual de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="457bd-116">Name of the current Visual Basic project.</span></span>|  
|`Description`|<span data-ttu-id="457bd-117">Corresponde al valor devuelto de una expresión de cadena del `Error` función para el elemento especificado `Number`, si esta cadena no existe.</span><span class="sxs-lookup"><span data-stu-id="457bd-117">String expression corresponding to the return value of the `Error` function for the specified `Number`, if this string exists.</span></span> <span data-ttu-id="457bd-118">Si la cadena no existe, `Description` contiene una cadena de longitud cero ("").</span><span class="sxs-lookup"><span data-stu-id="457bd-118">If the string does not exist, `Description` contains a zero-length string ("").</span></span>|  
|`HelpFile`|<span data-ttu-id="457bd-119">La unidad completa, la ruta de acceso y el nombre de archivo del archivo de Ayuda de Visual Basic apropiado.</span><span class="sxs-lookup"><span data-stu-id="457bd-119">The fully qualified drive, path, and file name of the appropriate Visual Basic Help file.</span></span>|  
|`HelpContext`|<span data-ttu-id="457bd-120">La Ayuda de Visual Basic correspondiente archivo de Id. de contexto para el error correspondiente a la `Number` propiedad.</span><span class="sxs-lookup"><span data-stu-id="457bd-120">The appropriate Visual Basic Help file context ID for the error corresponding to the `Number` property.</span></span>|  
|`LastDLLError`|<span data-ttu-id="457bd-121">Valor de cero.</span><span class="sxs-lookup"><span data-stu-id="457bd-121">Zero.</span></span>|  
  
 <span data-ttu-id="457bd-122">Si no existe ningún controlador de errores, o si ninguno está habilitado, se crea un mensaje de error y se muestra en la `Err` propiedades del objeto.</span><span class="sxs-lookup"><span data-stu-id="457bd-122">If no error handler exists, or if none is enabled, an error message is created and displayed from the `Err` object properties.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="457bd-123">Algunas aplicaciones de host de Visual Basic no pueden crear objetos.</span><span class="sxs-lookup"><span data-stu-id="457bd-123">Some Visual Basic host applications cannot create objects.</span></span> <span data-ttu-id="457bd-124">Consulte la documentación de la aplicación host para determinar si puede crear clases y objetos.</span><span class="sxs-lookup"><span data-stu-id="457bd-124">See your host application's documentation to determine whether it can create classes and objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="457bd-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="457bd-125">Example</span></span>  
 <span data-ttu-id="457bd-126">Este ejemplo se usa el `Error` instrucción para generar el error número 11.</span><span class="sxs-lookup"><span data-stu-id="457bd-126">This example uses the `Error` statement to generate error number 11.</span></span>  
  
```  
On Error Resume Next   ' Defer error handling.  
Error 11   ' Simulate the "Division by zero" error.  
```  
  
## <a name="requirements"></a><span data-ttu-id="457bd-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="457bd-127">Requirements</span></span>  
 <span data-ttu-id="457bd-128">**Espacio de nombres**: [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="457bd-128">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="457bd-129">**Ensamblado:** Biblioteca en tiempo de ejecución de Visual Basic (en Microsoft.VisualBasic.dll)</span><span class="sxs-lookup"><span data-stu-id="457bd-129">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="457bd-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="457bd-130">See also</span></span>

- <xref:Microsoft.VisualBasic.ErrObject.Clear%2A>
- <xref:Microsoft.VisualBasic.Information.Err%2A>
- <xref:Microsoft.VisualBasic.ErrObject.Raise%2A>
- [<span data-ttu-id="457bd-131">On Error (instrucción)</span><span class="sxs-lookup"><span data-stu-id="457bd-131">On Error Statement</span></span>](../../../visual-basic/language-reference/statements/on-error-statement.md)
- [<span data-ttu-id="457bd-132">Resume (instrucción)</span><span class="sxs-lookup"><span data-stu-id="457bd-132">Resume Statement</span></span>](../../../visual-basic/language-reference/statements/resume-statement.md)
- [<span data-ttu-id="457bd-133">Mensajes de error</span><span class="sxs-lookup"><span data-stu-id="457bd-133">Error Messages</span></span>](../../../visual-basic/language-reference/error-messages/index.md)
