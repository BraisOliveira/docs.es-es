---
title: Procedimiento Diagnosticar trabajos de impresión problemáticos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- troubleshooting print job problems [WPF]
- print jobs [WPF], troubleshooting
- print jobs [WPF], diagnosing problems
ms.assetid: b081a170-84c6-48f9-a487-5766a8d58a82
ms.openlocfilehash: 181248f69684860fd43648952ef4eb3cced1c0ba
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69944631"
---
# <a name="how-to-diagnose-problematic-print-job"></a>Procedimiento Diagnosticar trabajos de impresión problemáticos
A menudo, los administradores de red reciben quejas de los usuarios sobre trabajos de impresión que no se imprimen o que se imprimen lentamente. El amplio conjunto de propiedades del trabajo de impresión expuesto en las API de Microsoft .NET Framework proporciona un medio para realizar un diagnóstico remoto rápido de los trabajos de impresión.  
  
## <a name="example"></a>Ejemplo  
 Los pasos principales para crear este tipo de utilidad son los siguientes.  
  
1. Identificar el trabajo de impresión sobre el que se queja el usuario. Los usuarios a menudo no pueden hacer esto con precisión. Puede que no conozcan los nombres de los servidores de impresión o de las impresoras. Pueden describir la ubicación de la impresora en una terminología diferente a la usada para establecer <xref:System.Printing.PrintQueue.Location%2A> la propiedad. Por lo tanto, es conveniente generar una lista de los trabajos enviados actualmente por el usuario. Si hay más de uno, la comunicación entre el usuario y el administrador del sistema de impresión puede utilizarse para identificar el trabajo que está experimentando problemas. Los pasos secundarios son los siguientes.  
  
    1. Obtener una lista de todos los servidores de impresión.  
  
    2. Recorrer los servidores para consultar sus colas de impresión.  
  
    3. En cada superación del bucle de servidor, recorrer todas las colas del servidor para consultar los trabajos.  
  
    4. En cada superación del bucle de cola, recorrer todos los trabajos y recopilar la información de identificación sobre lo enviado por el usuario que se queja.  
  
2. Cuando se haya identificado el trabajo de impresión problemático, examine las propiedades pertinentes para ver cuál puede ser el problema. Por ejemplo, ¿el trabajo está en estado de error o la impresora mantuvo la cola sin conexión antes de que se pudiera imprimir el trabajo?  
  
 El código siguiente es una serie de ejemplos de código. El primer ejemplo de código contiene el recorrido por las colas de impresión. (Paso 1c anterior). La variable `myPrintQueues` es el <xref:System.Printing.PrintQueueCollection> objeto del servidor de impresión actual.  
  
 En el ejemplo de código se empieza por actualizar el objeto de <xref:System.Printing.PrintQueue.Refresh%2A?displayProperty=nameWithType>cola de impresión actual con. Esto garantiza que las propiedades del objeto representan con precisión el estado de la impresora física a la que hace referencia. A continuación, la aplicación obtiene la colección de trabajos de impresión que <xref:System.Printing.PrintQueue.GetPrintJobInfoCollection%2A>se encuentran actualmente en la cola de impresión mediante.  
  
 Después, la aplicación recorre en <xref:System.Printing.PrintSystemJobInfo> bucle la colección y compara <xref:System.Printing.PrintSystemJobInfo.Submitter%2A> cada propiedad con el alias del usuario que se queja. Si coinciden, la aplicación agrega información de identificación sobre el trabajo a la cadena que se mostrará. (Las variables `userName` y `jobList` se inicializan anteriormente en la aplicación).  
  
 [!code-cpp[DiagnoseProblematicPrintJob#EnumerateJobsInQueues](~/samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#enumeratejobsinqueues)]
 [!code-csharp[DiagnoseProblematicPrintJob#EnumerateJobsInQueues](~/samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#enumeratejobsinqueues)]
 [!code-vb[DiagnoseProblematicPrintJob#EnumerateJobsInQueues](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#enumeratejobsinqueues)]  
  
 En el ejemplo de código siguiente se toma la aplicación en el paso 2. (Vea más arriba). Se ha identificado el trabajo problemático y la aplicación solicita la información que lo identificará. A partir de esta información <xref:System.Printing.PrintServer>, <xref:System.Printing.PrintQueue>crea objetos <xref:System.Printing.PrintSystemJobInfo> , y.  
  
 En este punto, la aplicación contiene una estructura de bifurcación correspondiente a las dos maneras de comprobar el estado de un trabajo de impresión:  
  
- Puede leer las marcas de la <xref:System.Printing.PrintSystemJobInfo.JobStatus%2A> propiedad que es del tipo. <xref:System.Printing.PrintJobStatus>  
  
- Puede leer cada propiedad pertinente como <xref:System.Printing.PrintSystemJobInfo.IsBlocked%2A> y. <xref:System.Printing.PrintSystemJobInfo.IsInError%2A>  
  
 En este ejemplo se muestran ambos métodos, por lo que al usuario se le había solicitado previamente el método para usar y respondió con "Y" si quisiera usar las marcas de la <xref:System.Printing.PrintSystemJobInfo.JobStatus%2A> propiedad. A continuación encontrará los detalles de los dos métodos. Por último, la aplicación utiliza un método denominado **ReportQueueAndJobAvailability** para informar de si el trabajo se puede imprimir a esta hora del día. Este método se trata en [Detectar si un trabajo de impresión se puede imprimir en esta hora del día](how-to-discover-whether-a-print-job-can-be-printed-at-this-time-of-day.md).  
  
 [!code-cpp[DiagnoseProblematicPrintJob#IdentifyAndDiagnoseProblematicJob](~/samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#identifyanddiagnoseproblematicjob)]
 [!code-csharp[DiagnoseProblematicPrintJob#IdentifyAndDiagnoseProblematicJob](~/samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#identifyanddiagnoseproblematicjob)]
 [!code-vb[DiagnoseProblematicPrintJob#IdentifyAndDiagnoseProblematicJob](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#identifyanddiagnoseproblematicjob)]  
  
 Para comprobar el estado del trabajo de impresión mediante las <xref:System.Printing.PrintSystemJobInfo.JobStatus%2A> marcas de la propiedad, compruebe cada marca pertinente para ver si está establecida. El modo estándar para ver si un bit se establece en un conjunto de marcadores de bits es realizar una operación AND lógica con el conjunto de marcadores como uno de los operandos y la propia marca como el otro. Puesto que el propio marcador solo tiene un bit establecido, el resultado del operador lógico AND es que, como máximo, se establezca ese mismo bit. Para averiguar si esto ocurre o no, basta con comparar el resultado del operador lógico AND y el propio marcador. Para obtener más información, <xref:System.Printing.PrintJobStatus>vea, el [operador deC# & (referencia)](../../../csharp/language-reference/operators/bitwise-and-shift-operators.md#logical-and-operator-)y. <xref:System.FlagsAttribute>  
  
 El código informa de cada atributo cuyo bit esté establecido en la pantalla de la consola y a veces sugiere una manera de responder. (A continuación se describe el método **HandlePausedJob** que se llama si el trabajo o la cola está en pausa).  
  
 [!code-cpp[DiagnoseProblematicPrintJob#SpotTroubleUsingJobAttributes](~/samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#spottroubleusingjobattributes)]
 [!code-csharp[DiagnoseProblematicPrintJob#SpotTroubleUsingJobAttributes](~/samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#spottroubleusingjobattributes)]
 [!code-vb[DiagnoseProblematicPrintJob#SpotTroubleUsingJobAttributes](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#spottroubleusingjobattributes)]  
  
 Para comprobar el estado del trabajo de impresión mediante propiedades independientes, basta con leer cada propiedad y, si la propiedad es `true`, informar a la pantalla de la consola y sugerir posiblemente una forma de responder. (A continuación se describe el método **HandlePausedJob** que se llama si el trabajo o la cola está en pausa).  
  
 [!code-cpp[DiagnoseProblematicPrintJob#SpotTroubleUsingJobProperties](~/samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#spottroubleusingjobproperties)]
 [!code-csharp[DiagnoseProblematicPrintJob#SpotTroubleUsingJobProperties](~/samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#spottroubleusingjobproperties)]
 [!code-vb[DiagnoseProblematicPrintJob#SpotTroubleUsingJobProperties](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#spottroubleusingjobproperties)]  
  
 El método **HandlePausedJob** permite que los usuarios de la aplicación reanuden remotamente los trabajos en pausa. Puesto que puede haber una buena razón de por qué se pausó la cola de impresión, el método comienza solicitando al usuario una decisión sobre la reanudación. Si la respuesta es "Y", se llama <xref:System.Printing.PrintQueue.Resume%2A?displayProperty=nameWithType> al método.  
  
 A continuación se solicita al usuario que decida si se debe reanudar el propio trabajo, en caso de que se esté en pausa independientemente de la cola de impresión. (Compare <xref:System.Printing.PrintQueue.IsPaused%2A?displayProperty=nameWithType> y <xref:System.Printing.PrintSystemJobInfo.IsPaused%2A?displayProperty=nameWithType>). Si la respuesta es "Y", se <xref:System.Printing.PrintSystemJobInfo.Resume%2A?displayProperty=nameWithType> llama a; de <xref:System.Printing.PrintSystemJobInfo.Cancel%2A> lo contrario, se llama a.  
  
 [!code-cpp[DiagnoseProblematicPrintJob#HandlePausedJob](~/samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#handlepausedjob)]
 [!code-csharp[DiagnoseProblematicPrintJob#HandlePausedJob](~/samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#handlepausedjob)]
 [!code-vb[DiagnoseProblematicPrintJob#HandlePausedJob](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#handlepausedjob)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Printing.PrintJobStatus>
- <xref:System.Printing.PrintSystemJobInfo>
- <xref:System.FlagsAttribute>
- <xref:System.Printing.PrintQueue>
- [Operador & (C# referencia)](../../../csharp/language-reference/operators/bitwise-and-shift-operators.md#logical-and-operator-)
- [Documentos en WPF](documents-in-wpf.md)
- [Información general sobre impresión](printing-overview.md)
