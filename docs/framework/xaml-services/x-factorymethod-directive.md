---
title: x:FactoryMethod (Directiva)
ms.date: 03/30/2017
helpviewer_keywords:
- XAML. x:FactoryMethod directive [XAML Services]
- FactoryMethod directive in XAML [XAML Services]
- x:FactoryMethod directive [XAML Services]
ms.assetid: 829bcbdf-5318-4afb-9a03-c310e0d2f23d
ms.openlocfilehash: 8fff4d62e07bdfd4ecc27d2692c391251afdd6d5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59190696"
---
# <a name="xfactorymethod-directive"></a><span data-ttu-id="59295-102">x:FactoryMethod (Directiva)</span><span class="sxs-lookup"><span data-stu-id="59295-102">x:FactoryMethod Directive</span></span>
<span data-ttu-id="59295-103">Especifica un método distinto de un constructor que un procesador XAML debe usar para inicializar un objeto después de resolver su tipo de respaldo.</span><span class="sxs-lookup"><span data-stu-id="59295-103">Specifies a method other than a constructor that a XAML processor should use to initialize an object after resolving its backing type.</span></span>  
  
## <a name="xaml-attribute-usage-no-xarguments"></a><span data-ttu-id="59295-104">Uso de atributos XAML, no hay x: Arguments</span><span class="sxs-lookup"><span data-stu-id="59295-104">XAML Attribute Usage, no x:Arguments</span></span>  
  
```  
<object x:FactoryMethod="methodname"...>  
  ...  
</object>  
```  
  
## <a name="xaml-attribute-usage-xarguments-as-elements"></a><span data-ttu-id="59295-105">Uso de atributos XAML, x: Arguments como elementos</span><span class="sxs-lookup"><span data-stu-id="59295-105">XAML Attribute Usage, x:Arguments as Element(s)</span></span>  
  
```  
<object x:FactoryMethod="methodname"...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="59295-106">Valores XAML</span><span class="sxs-lookup"><span data-stu-id="59295-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`methodname`|<span data-ttu-id="59295-107">El nombre del método de cadena de un método que llamen procesadores XAML para inicializar la instancia especificada como `object`.</span><span class="sxs-lookup"><span data-stu-id="59295-107">The string method name of a method that XAML processors call to initialize the instance specified as `object`.</span></span> <span data-ttu-id="59295-108">Vea la sección Comentarios.</span><span class="sxs-lookup"><span data-stu-id="59295-108">See Remarks.</span></span>|  
|`oneOrMoreObjectElements`|<span data-ttu-id="59295-109">Uno o más elementos de objeto para objetos que especifican los parámetros de método de fábrica.</span><span class="sxs-lookup"><span data-stu-id="59295-109">One or more object elements for objects that specify factory method parameters.</span></span> <span data-ttu-id="59295-110">El orden es importante; significa el orden en el que se deben pasar argumentos al método de generador.</span><span class="sxs-lookup"><span data-stu-id="59295-110">Order is significant; it signifies the order in which arguments should be passed to the factory method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="59295-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="59295-111">Remarks</span></span>  
 <span data-ttu-id="59295-112">Si `methodname` es un método de instancia, no se puede calificar.</span><span class="sxs-lookup"><span data-stu-id="59295-112">If `methodname` is an instance method, it cannot be qualified.</span></span>  
  
 <span data-ttu-id="59295-113">Se admiten métodos estáticos como métodos de generador.</span><span class="sxs-lookup"><span data-stu-id="59295-113">Static methods as factory methods are supported.</span></span> <span data-ttu-id="59295-114">Si `methodname` es un método estático, `methodname` se proporciona como un *typeName*. *methodName* combinación, donde *typeName* nombra la clase que define el método de generador estático.</span><span class="sxs-lookup"><span data-stu-id="59295-114">If `methodname` is a static method, `methodname` is provided as a *typeName*.*methodName* combination, where *typeName* names the class that defines the static factory method.</span></span> <span data-ttu-id="59295-115">*typeName* puede estar calificado con un prefijo si hace referencia a un tipo en un atributo xmlns asignado.</span><span class="sxs-lookup"><span data-stu-id="59295-115">*typeName* can be prefix-qualified if referring to a type in a mapped xmlns.</span></span> <span data-ttu-id="59295-116">*typeName* puede ser un tipo diferente al `typeof(object)`.</span><span class="sxs-lookup"><span data-stu-id="59295-116">*typeName* can be a different type than `typeof(object)`.</span></span>  
  
 <span data-ttu-id="59295-117">El método de generador debe ser un método declarado público del tipo que respalda el elemento del objeto pertinente.</span><span class="sxs-lookup"><span data-stu-id="59295-117">The factory method must be a declared public method of the type that backs the relevant object element.</span></span>  
  
 <span data-ttu-id="59295-118">El método de generador debe devolver una instancia que se puede asignar al objeto pertinente.</span><span class="sxs-lookup"><span data-stu-id="59295-118">The factory method must return an instance that is assignable to the relevant object.</span></span> <span data-ttu-id="59295-119">Métodos de generador nunca deben devolver nulos.</span><span class="sxs-lookup"><span data-stu-id="59295-119">Factory methods should never return null.</span></span>  
  
 `x:Arguments` <span data-ttu-id="59295-120">opera en un principio de la mejor coincidencia para las firmas de métodos de generador.</span><span class="sxs-lookup"><span data-stu-id="59295-120">operates on a principle of best match for signatures of factory methods.</span></span> <span data-ttu-id="59295-121">Coincidencia, el número de parámetros evalúa primero.</span><span class="sxs-lookup"><span data-stu-id="59295-121">Matching evaluates the parameter count first.</span></span> <span data-ttu-id="59295-122">Si hay más de una coincidencia posible para un número de parámetros, tipo de parámetro es, a continuación, evalúa y la mejor coincidencia vendrá determinada.</span><span class="sxs-lookup"><span data-stu-id="59295-122">If there is more than one possible match for a parameter count, parameter type is then evaluated and best match is determined.</span></span> <span data-ttu-id="59295-123">Si todavía hay ambigüedad después de esta fase de evaluación, el comportamiento del procesador XAML es indefinido.</span><span class="sxs-lookup"><span data-stu-id="59295-123">If there is still ambiguity after this phase of evaluation, XAML processor behavior is undefined.</span></span>  
  
 <span data-ttu-id="59295-124">El `x:FactoryMethod` uso del elemento no es el uso de elementos de propiedad en el sentido típico, porque el marcado de la directiva no hace referencia el tipo del elemento de objeto que contiene.</span><span class="sxs-lookup"><span data-stu-id="59295-124">The `x:FactoryMethod` element usage is not property element usage in the typical sense, because the directive markup does not reference the containing object element's type.</span></span> <span data-ttu-id="59295-125">Se espera que el uso de elemento es menos común que el uso de atributos.</span><span class="sxs-lookup"><span data-stu-id="59295-125">It is expected that element usage is less common than attribute usage.</span></span> `x:Arguments` <span data-ttu-id="59295-126">(uso del atributo o elemento) que puede usarse junto con `x:FactoryMethod` uso de elementos, pero esto no se muestren específicamente en las secciones de uso.</span><span class="sxs-lookup"><span data-stu-id="59295-126">(either attribute or element usage) can be used along with `x:FactoryMethod` element usage, but this is not specifically shown in the Usage sections.</span></span>  
  
 `x:FactoryMethod` <span data-ttu-id="59295-127">como un elemento debe preceder a cualquier otro elemento de propiedad, debe preceder a cualquier `x:Arguments` también proporcionados como elementos y deben preceder a cualquier texto de inicialización de texto o contenido interno.</span><span class="sxs-lookup"><span data-stu-id="59295-127">as an element must precede any other property elements, must precede any `x:Arguments` also provided as elements, and must precede any content/inner text/initialization text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59295-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="59295-128">See also</span></span>

- [<span data-ttu-id="59295-129">x:Arguments (Directiva)</span><span class="sxs-lookup"><span data-stu-id="59295-129">x:Arguments Directive</span></span>](x-arguments-directive.md)
