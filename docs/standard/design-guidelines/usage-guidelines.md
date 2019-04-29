---
title: Instrucciones de uso
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], usage guidelines
ms.assetid: 42215ffa-a099-4a26-b14e-fb2bdb6f95b7
author: KrzysztofCwalina
ms.openlocfilehash: 761570b899a2a36391eb81dc7f42e13fff1f14ef
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61778812"
---
# <a name="usage-guidelines"></a><span data-ttu-id="4d6f3-102">Instrucciones de uso</span><span class="sxs-lookup"><span data-stu-id="4d6f3-102">Usage guidelines</span></span>

<span data-ttu-id="4d6f3-103">Esta sección contiene directrices para utilizar tipos comunes en las API accesibles públicamente.</span><span class="sxs-lookup"><span data-stu-id="4d6f3-103">This section contains guidelines for using common types in publicly accessible APIs.</span></span> <span data-ttu-id="4d6f3-104">Trata de uso directo de tipos de marco (por ejemplo, los atributos de serialización) y la sobrecarga de operadores comunes integrados.</span><span class="sxs-lookup"><span data-stu-id="4d6f3-104">It deals with direct usage of built-in Framework types (e.g., serialization attributes) and overloading common operators.</span></span>
  
<span data-ttu-id="4d6f3-105">El <xref:System.IDisposable?displayProperty=nameWithType> interfaz no está cubierta en esta sección, pero se trata en el [patrón Dispose](../../../docs/standard/design-guidelines/dispose-pattern.md) sección.</span><span class="sxs-lookup"><span data-stu-id="4d6f3-105">The <xref:System.IDisposable?displayProperty=nameWithType> interface is not covered in this section, but is discussed in the [Dispose Pattern](../../../docs/standard/design-guidelines/dispose-pattern.md) section.</span></span>

> [!NOTE]
> <span data-ttu-id="4d6f3-106">Para obtener directrices e información adicional sobre otro común, tipos integrados de .NET Framework, vea los temas de referencia para los siguientes elementos: <xref:System.DateTime?displayProperty=nameWithType>, <xref:System.DateTimeOffset?displayProperty=nameWithType>, <xref:System.ICloneable?displayProperty=nameWithType>, <xref:System.IComparable%601?displayProperty=nameWithType>, <xref:System.IEquatable%601?displayProperty=nameWithType>, <xref:System.Nullable%601?displayProperty=nameWithType>, <xref:System.Object?displayProperty=nameWithType> , <xref:System.Uri?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4d6f3-106">For guidelines and additional information about other common, built-in .NET Framework types, see the reference topics for the following: <xref:System.DateTime?displayProperty=nameWithType>, <xref:System.DateTimeOffset?displayProperty=nameWithType>, <xref:System.ICloneable?displayProperty=nameWithType>, <xref:System.IComparable%601?displayProperty=nameWithType>, <xref:System.IEquatable%601?displayProperty=nameWithType>, <xref:System.Nullable%601?displayProperty=nameWithType>, <xref:System.Object?displayProperty=nameWithType>, <xref:System.Uri?displayProperty=nameWithType>.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="4d6f3-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="4d6f3-107">In this section</span></span>

[<span data-ttu-id="4d6f3-108">Matrices</span><span class="sxs-lookup"><span data-stu-id="4d6f3-108">Arrays</span></span>](arrays.md)  
[<span data-ttu-id="4d6f3-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="4d6f3-109">Attributes</span></span>](attributes.md)  
[<span data-ttu-id="4d6f3-110">Colecciones</span><span class="sxs-lookup"><span data-stu-id="4d6f3-110">Collections</span></span>](guidelines-for-collections.md)  
[<span data-ttu-id="4d6f3-111">Serialización</span><span class="sxs-lookup"><span data-stu-id="4d6f3-111">Serialization</span></span>](serialization.md)  
[<span data-ttu-id="4d6f3-112">Uso de System.Xml</span><span class="sxs-lookup"><span data-stu-id="4d6f3-112">System.Xml Usage</span></span>](system-xml-usage.md)  
[<span data-ttu-id="4d6f3-113">Operadores de igualdad</span><span class="sxs-lookup"><span data-stu-id="4d6f3-113">Equality Operators</span></span>](equality-operators.md)  

<span data-ttu-id="4d6f3-114">*Portions © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*</span><span class="sxs-lookup"><span data-stu-id="4d6f3-114">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

<span data-ttu-id="4d6f3-115">*Reimpreso con permiso de Pearson Education, Inc. de [instrucciones de diseño de Framework: Convenciones, expresiones y patrones para bibliotecas reutilizables. NET, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicada el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="4d6f3-115">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4d6f3-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="4d6f3-116">See also</span></span>

- [<span data-ttu-id="4d6f3-117">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="4d6f3-117">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
