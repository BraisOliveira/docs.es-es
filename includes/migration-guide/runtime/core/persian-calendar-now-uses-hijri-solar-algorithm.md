---
ms.openlocfilehash: 130c26b7d135db232eb40a2c466aa3bdb2481ace
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/11/2019
ms.locfileid: "67858413"
---
### <a name="persian-calendar-now-uses-the-hijri-solar-algorithm"></a>En el calendario persa ahora se usa el algoritmo Hijri solar

|   |   |
|---|---|
|Detalles|A partir de .NET Framework 4.6, en la clase <xref:System.Globalization.PersianCalendar?displayProperty=name> se usa el algoritmo Hijri solar. La conversión de fechas entre <xref:System.Globalization.PersianCalendar?displayProperty=name> y otros calendarios puede producir un resultado ligeramente diferente a partir de .NET Framework 4.6 para las fechas anteriores a 1800 o posteriores a 2023 (del calendario gregoriano). Además, <xref:System.Globalization.PersianCalendar.MinSupportedDateTime?displayProperty=nameWithType> ahora es <code>March 22, 0622</code> en lugar de <code>March 21, 0622</code>.|
|Sugerencia|Tenga en cuenta que algunas fechas tempranas o tardías pueden ser ligeramente diferentes cuando se usa PersianCalendar en .NET Framework 4.6. Además, al serializar fechas entre procesos que puedan ejecutarse en diferentes versiones de .NET Framework, no las guarde como cadenas de fecha de PersianCalendar (ya que estos valores pueden ser diferentes).|
|Ámbito|Secundaria|
|Versión|4.6|
|Tipo|Tiempo de ejecución|
|API afectadas|<ul><li><xref:System.Globalization.PersianCalendar?displayProperty=nameWithType></li></ul>|

