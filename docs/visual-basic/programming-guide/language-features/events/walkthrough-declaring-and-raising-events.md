---
title: Declarar y generar eventos (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], events
- events [Visual Basic], walkthroughs
- declaring events [Visual Basic], walkthroughs
- events [Visual Basic], declaring
- events [Visual Basic], raising
- raising events [Visual Basic], walkthroughs
ms.assetid: 8ffb3be8-097d-4d3c-b71e-04555ebda2a2
ms.openlocfilehash: 20e2b0efbf40597049c515134f408927f18d5603
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69956329"
---
# <a name="walkthrough-declaring-and-raising-events-visual-basic"></a>Tutorial: Declarar y generar eventos (Visual Basic)
En este tutorial se muestra cómo declarar y generar eventos para una clase `Widget`denominada. Después de completar los pasos, es posible que desee leer el tema [complementario: Control de](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md)eventos, que muestra cómo utilizar los eventos `Widget` de los objetos para proporcionar información de estado en una aplicación.  
  
## <a name="the-widget-class"></a>La clase widget  
 Supongamos por el momento que tiene `Widget` una clase. La `Widget` clase tiene un método que puede tardar mucho tiempo en ejecutarse y desea que la aplicación pueda incluir algún tipo de indicador de finalización.  
  
 Por supuesto, puede hacer que el `Widget` objeto muestre un cuadro de diálogo porcentaje de finalización, pero a continuación se bloqueará este cuadro de diálogo en todos los proyectos en los `Widget` que se haya utilizado la clase. Un buen principio de diseño de objetos es permitir que la aplicación que usa un objeto controle la interfaz de usuario, a menos que el propósito completo del objeto sea administrar un formulario o un cuadro de diálogo.  
  
 El propósito de `Widget` es realizar otras tareas, por lo que es mejor agregar un `PercentDone` evento y dejar que el procedimiento que llama `Widget`a los métodos de llame a ese evento y muestre las actualizaciones de estado. El `PercentDone` evento también puede proporcionar un mecanismo para cancelar la tarea.  
  
#### <a name="to-build-the-code-example-for-this-topic"></a>Para compilar el ejemplo de código de este tema  
  
1. Abra un nuevo proyecto de aplicación de Windows Visual Basic y cree un `Form1`formulario denominado.  
  
2. Agregue dos botones y una etiqueta a `Form1`.  
  
3. Asigne nombre a los objetos tal y como se muestra en la tabla siguiente.  
  
    |Objeto|Propiedad|Parámetro|  
    |------------|--------------|-------------|  
    |`Button1`|`Text`|Tarea de inicio|  
    |`Button2`|`Text`|Cancelar|  
    |`Label`|`(Name)`, `Text`|lblPercentDone, 0|  
  
4. En el menú **proyecto** , elija **Agregar clase** para agregar una clase denominada `Widget.vb` al proyecto.  
  
#### <a name="to-declare-an-event-for-the-widget-class"></a>Para declarar un evento para la clase widget  
  
- Use la `Event` palabra clave para declarar un evento en `Widget` la clase. Tenga en cuenta que un evento `ByVal` puede `ByRef` tener argumentos y `Widget`, `PercentDone` como se muestra en el evento:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#1)]  
  
 Cuando el objeto que realiza la `PercentDone` llamada recibe un `Percent` evento, el argumento contiene el porcentaje de la tarea que ha finalizado. El `Cancel` argumento se puede establecer en `True` para cancelar el método que provocó el evento.  
  
> [!NOTE]
> Puede declarar argumentos de evento del mismo modo que los argumentos de procedimientos, con las siguientes excepciones: Los eventos no `Optional` pueden `ParamArray` tener argumentos o, y los eventos no tienen valores devueltos.  
  
 El evento es desencadenado por `LongTask` el método de `Widget` la clase. `PercentDone` `LongTask`toma dos argumentos: la cantidad de tiempo que el método está realizando el trabajo y el intervalo de tiempo mínimo antes `LongTask` de que se ponga en pausa para generar el `PercentDone` evento.  
  
#### <a name="to-raise-the-percentdone-event"></a>Para generar el evento PercentDone  
  
1. Para simplificar el acceso `Timer` a la propiedad utilizada por esta clase, `Imports` agregue una instrucción al principio de la sección de declaraciones del módulo de clase, encima `Class Widget` de la instrucción.  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#2)]  
  
2. Agregue el código siguiente a la clase `Widget`:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#3)]  
  
 Cuando la aplicación llama al `LongTask` método, la `Widget` clase genera el `PercentDone` evento cada `MinimumInterval` segundos. Cuando el evento vuelve, `LongTask` comprueba si el `Cancel` argumento se estableció en `True`.  
  
 Aquí se necesitan algunas renuncias. Para simplificar, `LongTask` el procedimiento presupone que sabe de antemano cuánto tiempo tardará la tarea en realizarse. Esto casi nunca es el caso. Dividir las tareas en fragmentos de tamaño uniforme puede ser difícil y, a menudo, lo más importante para los usuarios es simplemente la cantidad de tiempo que pasa antes de que obtengan una indicación de que se está produciendo algo.  
  
 Es posible que haya detectado otro problema en este ejemplo. La `Timer` propiedad devuelve el número de segundos transcurridos desde la medianoche; por lo tanto, la aplicación se bloquea si se inicia justo antes de medianoche. Un enfoque más cuidadoso para medir el tiempo tomaría condiciones de límite, como esto, o evitar que se consuman por completo `Now`, mediante propiedades como.  
  
 Ahora que la `Widget` clase puede generar eventos, puede pasar al siguiente tutorial. [Tutorial: El `WithEvents` ](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md) controlde`PercentDone` eventos muestra cómo utilizar para asociar un controlador de eventos al evento.  
  
## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.DateAndTime.Timer%2A>
- <xref:Microsoft.VisualBasic.DateAndTime.Now%2A>
- [Tutorial: Controlar eventos](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md)
- [Eventos](../../../../visual-basic/programming-guide/language-features/events/index.md)
