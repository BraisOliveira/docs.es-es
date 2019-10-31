---
title: Referencia de LINQ to XML propiedades dinámicas
ms.date: 10/22/2019
ms.topic: reference
ms.openlocfilehash: 48b51e92eb78786b2cc189e3e7daa00875b41585
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2019
ms.locfileid: "73197056"
---
# <a name="linq-to-xml-dynamic-properties"></a><span data-ttu-id="a0df4-102">Propiedades dinámicas de LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="a0df4-102">LINQ to XML dynamic properties</span></span>

<span data-ttu-id="a0df4-103">En esta sección se proporciona información de referencia acerca de las propiedades dinámicas en LINQ to XML.</span><span class="sxs-lookup"><span data-stu-id="a0df4-103">This section provides reference information about the dynamic properties in LINQ to XML.</span></span> <span data-ttu-id="a0df4-104">Específicamente, esas propiedades son expuestas por las clases <xref:System.Xml.Linq.XAttribute> y <xref:System.Xml.Linq.XElement>, que están en el espacio de nombres <xref:System.Xml.Linq>.</span><span class="sxs-lookup"><span data-stu-id="a0df4-104">Specifically, these properties are exposed by the <xref:System.Xml.Linq.XAttribute> and <xref:System.Xml.Linq.XElement> classes, which are in the <xref:System.Xml.Linq> namespace.</span></span>

<span data-ttu-id="a0df4-105">Tal y como se explica en el tema [Información general de enlace de datos WPF con LINQ to XML](wpf-data-binding-with-linq-to-xml-overview.md), cada una de las propiedades dinámicas es equivalente a un método o una propiedad estándar pública de la misma clase.</span><span class="sxs-lookup"><span data-stu-id="a0df4-105">As explained in the topic [Overview of WPF data binding with LINQ to XML](wpf-data-binding-with-linq-to-xml-overview.md), each of the dynamic properties is equivalent to a standard public property or method in the same class.</span></span> <span data-ttu-id="a0df4-106">Esos miembros estándar deben usarse para la mayoría de propósitos; las propiedades dinámicas se proporcionan específicamente para los casos de enlace de datos de LINQ to XML.</span><span class="sxs-lookup"><span data-stu-id="a0df4-106">These standard members should be used for most purposes; dynamic properties are provided specifically for LINQ to XML data binding scenarios.</span></span> <span data-ttu-id="a0df4-107">Para obtener más información acerca de los miembros estándar de esas clases, vea los temas de referencia <xref:System.Xml.Linq.XAttribute> y <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="a0df4-107">For more information about the standard members of these classes, see the <xref:System.Xml.Linq.XAttribute> and <xref:System.Xml.Linq.XElement> reference topics.</span></span>

<span data-ttu-id="a0df4-108">Con respecto a sus valores resueltos, las propiedades dinámicas de esa sección se dividen en dos categorías:</span><span class="sxs-lookup"><span data-stu-id="a0df4-108">With respect to their resolved values, the dynamic properties in this section fall into two categories:</span></span>

- <span data-ttu-id="a0df4-109">Sencillas, como las propiedades `Value` de las clases <xref:System.Xml.Linq.XAttribute> y <xref:System.Xml.Linq.XElement>, que se resuelven en un valor único.</span><span class="sxs-lookup"><span data-stu-id="a0df4-109">Simple ones, such as the `Value` properties in the <xref:System.Xml.Linq.XAttribute> and <xref:System.Xml.Linq.XElement> classes, that resolve to a single value.</span></span>

- <span data-ttu-id="a0df4-110">Valores indexados, como las propiedades [Elements](elements-xelement-dynamic-property.md) y [Descendants](descendants-xelement-dynamic-property.md) de <xref:System.Xml.Linq.XElement>, que se resuelven en un tipo de indizador.</span><span class="sxs-lookup"><span data-stu-id="a0df4-110">Indexed values, such as the [Elements](elements-xelement-dynamic-property.md) and [Descendants](descendants-xelement-dynamic-property.md) properties of <xref:System.Xml.Linq.XElement>, that resolve into an indexer type.</span></span> <span data-ttu-id="a0df4-111">Para que los tipos de indizador se resuelvan en el valor o la recopilación que se desea, se les debe pasar un parámetro de nombre expandido.</span><span class="sxs-lookup"><span data-stu-id="a0df4-111">For indexer types to be resolved to the desired value or collection, an expanded name parameter must be passed to them.</span></span>

<span data-ttu-id="a0df4-112">Todas las propiedades dinámicas que devuelven un valor indizado del tipo <xref:System.Collections.Generic.IEnumerable%601> utilizan la ejecución aplazada.</span><span class="sxs-lookup"><span data-stu-id="a0df4-112">All the dynamic properties that return an indexed value of type <xref:System.Collections.Generic.IEnumerable%601> use deferred execution.</span></span> <span data-ttu-id="a0df4-113">Para obtener más información sobre la ejecución aplazada, vea [Introducción a las consultas LINQ (C#)](../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span><span class="sxs-lookup"><span data-stu-id="a0df4-113">For more information about deferred execution, see [Introduction to LINQ queries (C#)](../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>

## <a name="reference"></a><span data-ttu-id="a0df4-114">Referencia</span><span class="sxs-lookup"><span data-stu-id="a0df4-114">Reference</span></span>

- <xref:System.Xml.Linq>
- <xref:System.Xml.Linq.XElement?displayProperty=fullName>
- <xref:System.Xml.Linq.XAttribute?displayProperty=fullName>

## <a name="see-also"></a><span data-ttu-id="a0df4-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="a0df4-115">See also</span></span>

- [<span data-ttu-id="a0df4-116">Enlace de datos de WPF con LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="a0df4-116">WPF data binding with LINQ to XML</span></span>](wpf-data-binding-with-linq-to-xml-overview.md)
- [<span data-ttu-id="a0df4-117">Información general de enlace de datos WPF con LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="a0df4-117">WPF data binding with LINQ to XML overview</span></span>](wpf-data-binding-with-linq-to-xml-overview.md)
- [<span data-ttu-id="a0df4-118">Introducción a las consultas LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="a0df4-118">Introduction to LINQ queries (C#)</span></span>](../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)
