---
title: 'Interoperabilidad: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- COM interop
- interoperability
- platform invoke, accessing APIs with C#
- C# language, interoperability
ms.assetid: 238bb95a-e962-4026-bbd5-197055bdb8ee
ms.openlocfilehash: 560218361f470266654734971a12de7862722a46
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2019
ms.locfileid: "73423176"
---
# <a name="interoperability-c-programming-guide"></a>Interoperabilidad (Guía de programación de C#)
La interoperabilidad permite conservar y aprovechar las inversiones existentes en código no administrado. El código que se ejecuta bajo el control de Common Language Runtime (CLR) se denomina *código administrado*, y el código que se ejecuta fuera de CLR se denomina *código no administrado*. COM, COM+, los componentes de C++, los componentes de ActiveX y la API Windows de Microsoft son ejemplos de código no administrado.  
  
 .NET Framework habilita la interoperabilidad con código no administrado a través de los servicios de invocación de plataforma, el espacio de nombres <xref:System.Runtime.InteropServices>, la interoperabilidad de C++ y la interoperabilidad COM.  
  
## <a name="in-this-section"></a>En esta sección  
 [Información general sobre interoperabilidad](./interoperability-overview.md)  
 Se describen métodos para habilitar la interoperabilidad entre el código administrado y el código no administrado de C#.  
  
 [Cómo: Tener acceso a objetos de interoperabilidad de Office mediante las características de Visual C#](./how-to-access-office-onterop-objects.md)  
 Describe las características introducidas en Visual C# para facilitar la programación de Office.  
  
 [Cómo: Utilizar propiedades indizadas en la programación de interoperabilidad COM](./how-to-use-indexed-properties-in-com-interop-rogramming.md)  
 Se describe cómo utilizar las propiedades indizadas para acceder a las propiedades de COM que tienen parámetros.  
  
 [Cómo: Utilizar la invocación de plataforma para reproducir un archivo de sonido](./how-to-use-platform-invoke-to-play-a-wave-file.md)  
 Se describe cómo usar los servicios de invocación de plataforma para reproducir un archivo de sonido .wav en el sistema operativo Windows.  
  
 [Tutorial: Programación de Office](./walkthrough-office-programming.md)  
 Muestra cómo crear un libro de Excel y un documento de Word que contiene un vínculo al libro.  
  
 [Clase COM de ejemplo](./example-com-class.md)  
 Muestra cómo exponer una clase de C# como un objeto COM.  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  

Para obtener más información, consulte la sección [Conceptos básicos](~/_csharplang/spec/unsafe-code.md) de [Especificación del lenguaje C#](/dotnet/csharp/language-reference/language-specification/introduction). La especificación del lenguaje es la fuente definitiva de la sintaxis y el uso de C#.
  
## <a name="see-also"></a>Vea también

- <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A?displayProperty=nameWithType>
- [Guía de programación de C#](../index.md)
- [Interoperating with Unmanaged Code](../../../framework/interop/index.md) (Interoperar con código no administrado)
- [Tutorial: Programación de Office](./walkthrough-office-programming.md)
