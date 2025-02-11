---
title: Depurar flujos de trabajo
ms.date: 03/30/2017
ms.assetid: b23b4814-ebb1-4c51-b7a9-469f4da7a96d
ms.openlocfilehash: 3947e61161b0e2108fa48fbc7e33fb7601645a1b
ms.sourcegitcommit: 9c3a4f2d3babca8919a1e490a159c1500ba7a844
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/12/2019
ms.locfileid: "72291490"
---
# <a name="debugging-workflows"></a>Depurar flujos de trabajo

[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] proporciona varias opciones para depurar los flujos de trabajo en ejecución del entorno de desarrollo. Los flujos de trabajo se pueden depurar en el diseñador, en XAML y en el código.

## <a name="debugging-in-the-workflow-designer"></a>Depuración en el Diseñador de flujo de trabajo

Los puntos de interrupción se pueden establecer en las actividades del diseñador de flujo de trabajo resaltando la actividad y presionando <kbd>F9</kbd> o utilizando el menú contextual de la actividad. A continuación, la ejecución del flujo de trabajo se interrumpe cuando el host del flujo de trabajo se ejecuta en modo de depuración. En la siguiente captura de pantalla, la ejecución del flujo de trabajo se para momentáneamente en un punto de interrupción. Para obtener más información, vea [Depurar flujos de trabajo con el diseñador de flujo de trabajo](/visualstudio/workflow-designer/debugging-workflows-with-the-workflow-designer).

## <a name="debugging-in-xaml"></a>Depurar en XAML

Si un flujo de trabajo se ha detenido momentáneamente en un punto de interrupción en el diseñador, el flujo de trabajo también se puede depurar en XAML. Para ver el punto de ejecución en XAML, seleccione **vista XAML** en el diseñador de flujo de trabajo cuando la ejecución del flujo de trabajo esté en pausa. La depuración se puede volver a cambiar en el diseñador mediante la reapertura del flujo de trabajo en el diseñador desde el explorador de soluciones. Para obtener más información, vea [Cómo: Depure XAML con el Diseñador de flujo de trabajo @ no__t-0.

## <a name="debugging-in-code"></a>Depurar en el código

Para establecer un punto de interrupción, haga clic en el margen izquierdo del panel de código o presione <kbd>F9</kbd> con el cursor en la línea donde desea establecerlo.

## <a name="attaching-to-a-workflow-process"></a>Adjuntar a un proceso de flujo de trabajo

La depuración del flujo de trabajo también admite el uso de la infraestructura de Visual Studio para adjuntar a un proceso. De esta forma se permite que el autor del flujo de trabajo depure un flujo de trabajo que se ejecuta en un entorno de host diferente como Internet Information Services (IIS) 7.0.

## <a name="remote-debugging"></a>Remote Debugging

La depuración remota de Windows Workflow Foundation (WF) es igual que la depuración remota de otros componentes de Visual Studio. Para obtener información sobre cómo usar la depuración remota, vea [How para: Habilite la depuración remota @ no__t-0.

> [!NOTE]
> Si la aplicación de flujo de trabajo tiene como destino la arquitectura x86 y se hospeda en un equipo que ejecuta un sistema operativo de 64 bits, la depuración remota no funcionará a menos que Visual Studio esté instalado en el equipo remoto o se cambie el destino de la aplicación de flujo de trabajo a **Cualquier CPU**.

## <a name="extending-the-workflow-debugging-service"></a>Extender el servicio de depuración del flujo de trabajo

El servicio de depurador de flujo de trabajo es público ahora y se puede usar para crear aplicaciones personalizadas como supervisión, simulación y depuración en un diseñador re-hospedado. Para obtener más información, vea el artículo <xref:System.Activities.Presentation.Debug.DebuggerService>.
