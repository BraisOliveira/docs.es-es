---
title: Servicios de WCF y seguimiento de eventos para Windows
ms.date: 03/30/2017
ms.assetid: eda4355d-0bd0-4dc9-80a2-d2c832152272
ms.openlocfilehash: e1ee7154e2ad5b22ff0debcdd15d5809fc55df13
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2019
ms.locfileid: "70044516"
---
# <a name="wcf-services-and-event-tracing-for-windows"></a>Servicios de WCF y seguimiento de eventos para Windows
En este ejemplo se muestra cómo utilizar la traza analítica en Windows Communication Foundation (WCF) para emitir eventos en seguimiento de eventos para Windows (ETW). Los seguimientos analíticos son eventos emitidos en los puntos clave de la pila de WCF que permiten solucionar problemas de los servicios WCF en el entorno de producción.

 El seguimiento analítico en los servicios WCF es un seguimiento que se puede activar en un entorno de producción con un impacto mínimo en el rendimiento. Estos seguimientos se emiten como eventos para una sesión de ETW.

 Este ejemplo incluye un servicio WCF básico en el que los eventos se emiten desde el servicio al registro de eventos, que se puede ver mediante Visor de eventos. También es posible iniciar una sesión de ETW dedicada que realiza escuchas de eventos del servicio WCF. En el ejemplo se incluye un script para crear una sesión de ETW dedicada que almacena los eventos en un archivo binario que se puede leer utilizando el Visor de eventos.

#### <a name="to-use-this-sample"></a>Para utilizar este ejemplo

1. Con Visual Studio 2012, abra el archivo de solución EtwAnalyticTraceSample. sln.

2. Para compilar la solución, presione Ctrl+MAYÚS+B.

3. Para ejecutar la solución, presione CTRL+F5.

     En el explorador Web, haga clic en **Calculator. SVC**. El URI del documento WSDL para el servicio debería aparecer en el explorador. Copie ese URI.

     De forma predeterminada, el servicio empieza a escuchar las solicitudes en `http://localhost:1378/Calculator.svc`el puerto 1378.

4. Ejecute el cliente de prueba de WCF (WcfTestClient. exe).

     El cliente de prueba de WCF (WcfTestClient. exe) se `\<Visual Studio 2012 Install Dir>\Common7\IDE\WcfTestClient.exe`encuentra en.  El directorio de instalación predeterminado de Visual Studio `C:\Program Files\Microsoft Visual Studio 10.0`2012 es.

5. En el cliente de prueba de WCF, agregue el servicio seleccionando **archivo**y, a continuación, **Agregar servicio**.

     Agregue la dirección del punto de conexión en el cuadro de entrada. El valor predeterminado es `http://localhost:1378/Calculator.svc`.

6. Abra la aplicación Visor de eventos.

     Antes de invocar el servicio, inicie Visor de eventos y asegúrese de que el registro de eventos está escuchando los eventos de seguimiento emitidos por el servicio WCF.

7. En el menú **Inicio** , seleccione **herramientas administrativas**y, a continuación, **visor de eventos**.  Habilitar los registros analíticos y de depuración.

8. En la vista de árbol de Visor de eventos, vaya a **visor de eventos**, **registros de aplicaciones y servicios**, **Microsoft**, **Windows**y, a continuación, **aplicaciones de servidor de**aplicaciones. Haga clic con el botón derecho en **servidor de aplicaciones-aplicaciones**, seleccione **Ver**y, a continuación, **muestre los registros analíticos y de**depuración.

     Asegúrese de que la opción **Mostrar registros analíticos y** de depuración está activada.

9. Habilitación del registro **analítico** .

     En la vista de árbol de Visor de eventos, vaya a **visor de eventos**, **registros de aplicaciones y servicios**, **Microsoft**, **Windows**y, a continuación, **aplicaciones de servidor de**aplicaciones. Haga clic con el botón secundario en **analítico** y seleccione **Habilitar registro**.

#### <a name="to-test-the-service"></a>Para probar el servicio

1. Vuelva al cliente de prueba de WCF y haga doble `Divide` clic y mantenga los valores predeterminados, que especifican un denominador de 0.

     Si el denominador es 0, el servicio produce un error.

2. Observe los eventos emitidos desde el servicio.

     Vuelva a Visor de eventos y navegue a **visor de eventos**, **registros de aplicaciones y servicios**, **Microsoft**, **Windows**y, a continuación, **aplicaciones de servidor de**aplicaciones. Haga clic con el botón secundario en **analítico** y seleccione **Actualizar**.

     Los eventos de seguimiento analítico de WCF se muestran en el visor de eventos. Observe que dado que el servicio inició un error, se muestra un evento de seguimiento del error en el visor de eventos.

3. Repita los pasos 1 y 2, pero con entradas válidas. El valor del parámetro `N2` puede ser cualquier número distinto de 0.

     Actualice el canal analítico para ver los eventos de WCF que no incluyen ningún evento de error.

 En el ejemplo se muestran los eventos de seguimiento analíticos emitidos desde un servicio WCF.

#### <a name="to-cleanup-optional"></a>Para realizar la limpieza (Opcional)

1. Abra el Visor de eventos.

2. Vaya a **visor de eventos**, **registros de aplicaciones y servicios**, **Microsoft**, **Windows**y, a continuación, **aplicaciones de servidor de**aplicaciones. Haga clic con el botón secundario en **analítico** y seleccione **deshabilitar registro**.

3. Vaya a **visor de eventos**, **registros de aplicaciones y servicios**, **Microsoft**, **Windows**y, a continuación, **aplicaciones de servidor de**aplicaciones. Haga clic con el botón secundario en **analítico** y seleccione **Borrar registro**.

4. Elija la opción **Borrar** para borrar los eventos.

> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) [!INCLUDE[wf1](../../../../includes/wf1-md.md)] y ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ETWTracing`  
  
## <a name="see-also"></a>Vea también

- [Ejemplos de supervisión de AppFabric](https://go.microsoft.com/fwlink/?LinkId=193959)
