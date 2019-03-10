---
title: Proceso de aprobación de un documento
ms.date: 03/30/2017
ms.assetid: 9b240937-76a7-45cd-8823-7f82c34d03bd
ms.openlocfilehash: d1e37dcbc21239822937c57d9779a52357aac518
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57717718"
---
# <a name="document-approval-process"></a><span data-ttu-id="ac427-102">Proceso de aprobación de un documento</span><span class="sxs-lookup"><span data-stu-id="ac427-102">Document Approval Process</span></span>
<span data-ttu-id="ac427-103">Este ejemplo muestra el uso de muchas características de Windows Workflow Foundation (WF) y Windows Communication Foundation (WCF) juntos.</span><span class="sxs-lookup"><span data-stu-id="ac427-103">This sample demonstrates the use of many Windows Workflow Foundation (WF) and Windows Communication Foundation (WCF) features together.</span></span> <span data-ttu-id="ac427-104">Juntas implementan un escenario de proceso de aprobación de un documento.</span><span class="sxs-lookup"><span data-stu-id="ac427-104">Together they implement a document approval process scenario.</span></span> <span data-ttu-id="ac427-105">Una aplicación cliente puede enviar documentos para su aprobación y aprobar documentos.</span><span class="sxs-lookup"><span data-stu-id="ac427-105">A client application can submit documents for approval and approve documents.</span></span> <span data-ttu-id="ac427-106">Existe una aplicación de administrador de aprobaciones para facilitar las comunicaciones entre los clientes y aplicar las reglas del proceso de aprobación.</span><span class="sxs-lookup"><span data-stu-id="ac427-106">An approval manager application exists to facilitate communications between clients and to enforce the rules of the approval process.</span></span> <span data-ttu-id="ac427-107">El proceso de aprobación es un flujo de trabajo que puede ejecutar varios tipos de aprobación.</span><span class="sxs-lookup"><span data-stu-id="ac427-107">The approval process is a workflow that can execute several types of approval.</span></span> <span data-ttu-id="ac427-108">Existen actividades para obtener una aprobación única, una aprobación de quórum (un porcentaje de un conjunto de aprobadores) y un proceso de aprobación compleja que consta de una aprobación de quórum y una aprobación única en una secuencia.</span><span class="sxs-lookup"><span data-stu-id="ac427-108">Activities exist to get a single approval, a quorum approval (a percentage of set of approvers), and a complex approval process that consists of a quorum and single approval in a sequence.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="ac427-109">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="ac427-109">The samples may already be installed on your machine.</span></span> <span data-ttu-id="ac427-110">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="ac427-110">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="ac427-111">Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="ac427-111">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ac427-112">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="ac427-112">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Application\DocumentApprovalProcess`  
  
## <a name="sample-details"></a><span data-ttu-id="ac427-113">Detalles del ejemplo</span><span class="sxs-lookup"><span data-stu-id="ac427-113">Sample Details</span></span>  
 <span data-ttu-id="ac427-114">El siguiente gráfico muestra el flujo de trabajo del proceso de aprobación de un documento.</span><span class="sxs-lookup"><span data-stu-id="ac427-114">The following graphic demonstrates the document approval process workflow.</span></span>  
  
 <span data-ttu-id="ac427-115">![Un flujo de trabajo de proceso de aprobación de documentos](./media/approvalprocess.jpg "ApprovalProcess")</span><span class="sxs-lookup"><span data-stu-id="ac427-115">![A document approval process workflow](./media/approvalprocess.jpg "ApprovalProcess")</span></span>  
  
 <span data-ttu-id="ac427-116">Desde la perspectiva del cliente, el proceso de aprobación funciona del siguiente modo:</span><span class="sxs-lookup"><span data-stu-id="ac427-116">From the client's perspective, the approval process functions as follows:</span></span>  
  
1.  <span data-ttu-id="ac427-117">Un cliente realiza una suscripción para convertirse en usuario en el sistema del proceso de aprobación.</span><span class="sxs-lookup"><span data-stu-id="ac427-117">A client subscribes to be a user in the approval process system.</span></span>  
  
2.  <span data-ttu-id="ac427-118">Un cliente WCF envía a un servicio WCF hospedado por la aplicación de administrador de aprobaciones.</span><span class="sxs-lookup"><span data-stu-id="ac427-118">A WCF client sends to a WCF service hosted by the approval manager application.</span></span>  
  
3.  <span data-ttu-id="ac427-119">Se devuelve un Id. de usuario único al cliente.</span><span class="sxs-lookup"><span data-stu-id="ac427-119">A unique user ID is returned to the client.</span></span> <span data-ttu-id="ac427-120">El cliente puede participar ahora en los procesos de aprobación.</span><span class="sxs-lookup"><span data-stu-id="ac427-120">The client can now participate in approval processes.</span></span>  
  
4.  <span data-ttu-id="ac427-121">Una vez admitido, un cliente puede enviar un documento para su aprobación mediante un proceso de aprobación única, de quórum o compleja.</span><span class="sxs-lookup"><span data-stu-id="ac427-121">Once joined, a client can send a document for approval using single, quorum or complex approval processes.</span></span>  
  
5.  <span data-ttu-id="ac427-122">Al hacer clic en un botón de la interfaz del cliente, se inicia una instancia de flujo de trabajo en un host de servicio de flujo de trabajo del cliente.</span><span class="sxs-lookup"><span data-stu-id="ac427-122">A button in the client’s interface is clicked, starting a workflow instance in a client Workflow Service Host.</span></span>  
  
6.  <span data-ttu-id="ac427-123">El flujo de trabajo envía una solicitud de aprobación a la aplicación de administrador de aprobaciones.</span><span class="sxs-lookup"><span data-stu-id="ac427-123">The workflow sends an approval request to the approval manager application.</span></span>  
  
7.  <span data-ttu-id="ac427-124">El administrador del flujo de trabajo inicia un flujo de trabajo por su parte para representar un proceso de aprobación.</span><span class="sxs-lookup"><span data-stu-id="ac427-124">The workflow manager starts a workflow on its own side to represent an approval process.</span></span>  
  
8.  <span data-ttu-id="ac427-125">Una vez ejecutado el flujo de trabajo de aprobación del administrador, los resultados se devuelven al cliente.</span><span class="sxs-lookup"><span data-stu-id="ac427-125">Once the manager approval workflow executes, the results are sent back to the client.</span></span>  
  
9. <span data-ttu-id="ac427-126">El cliente muestra los resultados.</span><span class="sxs-lookup"><span data-stu-id="ac427-126">The client displays the results.</span></span>  
  
10. <span data-ttu-id="ac427-127">Un cliente puede recibir una solicitud de aprobación y responder a la solicitud en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="ac427-127">A client may receive an approval request and respond to the request at any point in time.</span></span>  
  
11. <span data-ttu-id="ac427-128">Un servicio WCF hospedado en el cliente puede recibir una solicitud de aprobación de la aplicación de administrador de aprobaciones.</span><span class="sxs-lookup"><span data-stu-id="ac427-128">A WCF service hosted on the client can receive an approval request from the approval manager application.</span></span>  
  
12. <span data-ttu-id="ac427-129">La información del documento se presenta en el cliente para revisión.</span><span class="sxs-lookup"><span data-stu-id="ac427-129">The document information is presented on the client for review.</span></span>  
  
13. <span data-ttu-id="ac427-130">El usuario puede aprobar o rechazar el documento.</span><span class="sxs-lookup"><span data-stu-id="ac427-130">The user can approve or reject the document.</span></span>  
  
14. <span data-ttu-id="ac427-131">Se utiliza un cliente WCF para enviar una respuesta de aprobación a la aplicación de administrador de autorización.</span><span class="sxs-lookup"><span data-stu-id="ac427-131">A WCF client is used to send an approval response back to the approval manager application.</span></span>  
  
 <span data-ttu-id="ac427-132">Desde el punto de vista de la aplicación de administrador de aprobaciones, el proceso de aprobación funciona del siguiente modo:</span><span class="sxs-lookup"><span data-stu-id="ac427-132">From the approval manager application’s point of view, the approval process functions as follows:</span></span>  
  
1.  <span data-ttu-id="ac427-133">Un cliente solicita al sistema del proceso de aprobación participar.</span><span class="sxs-lookup"><span data-stu-id="ac427-133">A client requests to participate to the approval process system.</span></span>  
  
2.  <span data-ttu-id="ac427-134">Un servicio WCF en el Administrador de aprobaciones recibe una solicitud para formar parte del sistema del proceso de aprobación.</span><span class="sxs-lookup"><span data-stu-id="ac427-134">A WCF service on the approval manager receives a request to be part of the approval process system.</span></span>  
  
3.  <span data-ttu-id="ac427-135">Se genera un identificador único para el cliente.</span><span class="sxs-lookup"><span data-stu-id="ac427-135">A unique ID is generated for the client.</span></span> <span data-ttu-id="ac427-136">La información sobre el usuario se almacena en una base de datos.</span><span class="sxs-lookup"><span data-stu-id="ac427-136">The user information is stored in a database.</span></span>  
  
4.  <span data-ttu-id="ac427-137">El identificador único se envía al usuario.</span><span class="sxs-lookup"><span data-stu-id="ac427-137">The unique ID is sent back to the user.</span></span>  
  
5.  <span data-ttu-id="ac427-138">Se recibe una solicitud de aprobación.</span><span class="sxs-lookup"><span data-stu-id="ac427-138">An approval request is receive.</span></span> <span data-ttu-id="ac427-139">El administrador de aprobaciones ejecuta un proceso de aprobación.</span><span class="sxs-lookup"><span data-stu-id="ac427-139">The approval manager executes an approval process.</span></span>  
  
6.  <span data-ttu-id="ac427-140">El administrador de aprobaciones recibe una solicitud de aprobación, lo que inicia un nuevo flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ac427-140">An approval request is received by the approval manager, starting a new workflow.</span></span>  
  
7.  <span data-ttu-id="ac427-141">Según el tipo de solicitud (simple, quórum o compleja), se ejecuta una actividad diferente.</span><span class="sxs-lookup"><span data-stu-id="ac427-141">Depending on the type of request (simple, quorum, or complex) a different activity is executed.</span></span>  
  
8.  <span data-ttu-id="ac427-142">Las actividades Send y Receive con correlación se utilizan para enviar la solicitud de aprobación al cliente para su revisión y recibir la respuesta.</span><span class="sxs-lookup"><span data-stu-id="ac427-142">Send and Receive activities with correlation are used to send the approval request to the client for review and receive the response.</span></span>  
  
9. <span data-ttu-id="ac427-143">El resultado del flujo de trabajo del proceso de aprobación se envía al cliente.</span><span class="sxs-lookup"><span data-stu-id="ac427-143">The result of the approval process workflow is sent to the client.</span></span>  
  
## <a name="using-the-sample"></a><span data-ttu-id="ac427-144">Utilizar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="ac427-144">Using the Sample</span></span>  
  
##### <a name="to-set-up-the-database"></a><span data-ttu-id="ac427-145">Para configurar la base de datos</span><span class="sxs-lookup"><span data-stu-id="ac427-145">To set up the database</span></span>  
  
1.  <span data-ttu-id="ac427-146">Desde una línea de comandos de Visual Studio 2010 abierta con privilegios de administrador, vaya a la carpeta DocumentApprovalProcess y ejecute Setup.cmd.</span><span class="sxs-lookup"><span data-stu-id="ac427-146">From a Visual Studio 2010 command prompt opened with Administrator privileges, navigate to this DocumentApprovalProcess folder and run Setup.cmd.</span></span>  
  
##### <a name="to-set-up-the-application"></a><span data-ttu-id="ac427-147">Para configurar la aplicación</span><span class="sxs-lookup"><span data-stu-id="ac427-147">To set up the application</span></span>  
  
1.  <span data-ttu-id="ac427-148">Con Visual Studio 2010, abra el archivo de solución de DocumentApprovalProcess.sln.</span><span class="sxs-lookup"><span data-stu-id="ac427-148">Using Visual Studio 2010, open the DocumentApprovalProcess.sln solution file.</span></span>  
  
2.  <span data-ttu-id="ac427-149">Para compilar la solución, presione Ctrl+MAYÚS+B.</span><span class="sxs-lookup"><span data-stu-id="ac427-149">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="ac427-150">Para ejecutar la solución, inicie la aplicación Administrador de aprobaciones haciendo clic con el proyecto ApprovalManager en el **el Explorador de soluciones** y haga clic en **depurar**->**iniciar**  nueva instancia en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="ac427-150">To run the solution, launch the Approval Manager Application by right-clicking the ApprovalManager project in the **Solution Explorer** and clicking **Debug**->**Start** new instance from the right-click menu.</span></span>  
  
     <span data-ttu-id="ac427-151">Espere a que el resultado del administrador le indique que está listo.</span><span class="sxs-lookup"><span data-stu-id="ac427-151">Wait for the manager’s output to let you know that it is ready.</span></span>  
  
##### <a name="to-run-the-single-approval-scenario"></a><span data-ttu-id="ac427-152">Para ejecutar el escenario de aprobación única</span><span class="sxs-lookup"><span data-stu-id="ac427-152">To run the single approval scenario</span></span>  
  
1.  <span data-ttu-id="ac427-153">Abra un símbolo del sistema con permisos de administrador.</span><span class="sxs-lookup"><span data-stu-id="ac427-153">Open a command prompt with administrator permission.</span></span>  
  
2.  <span data-ttu-id="ac427-154">Navegue al directorio que contiene la solución.</span><span class="sxs-lookup"><span data-stu-id="ac427-154">Navigate to the directory that contains the solution.</span></span>  
  
3.  <span data-ttu-id="ac427-155">Navegue a la carpeta ApprovalClient\Bin\Debug y ejecute dos instancias de ApprovalClient.exe.</span><span class="sxs-lookup"><span data-stu-id="ac427-155">Navigate to the ApprovalClient\Bin\Debug folder and execute two instances of ApprovalClient.exe.</span></span>  
  
4.  <span data-ttu-id="ac427-156">Haga clic en **detectar**, espere hasta que el **suscribirse** botón está habilitado.</span><span class="sxs-lookup"><span data-stu-id="ac427-156">Click **discover**, wait until the **subscribe** button is enabled.</span></span>  
  
5.  <span data-ttu-id="ac427-157">Escriba cualquier nombre de usuario y haga clic en **suscribirse**.</span><span class="sxs-lookup"><span data-stu-id="ac427-157">Type any user name and click **subscribe**.</span></span> <span data-ttu-id="ac427-158">Para un cliente, use `UserType1` y para el otro, escriba `UserType2`.</span><span class="sxs-lookup"><span data-stu-id="ac427-158">For one client, use `UserType1` and the other type `UserType2`.</span></span>  
  
6.  <span data-ttu-id="ac427-159">En el cliente `UserType1`, seleccione el tipo de aprobación única en el menú desplegable y escriba un nombre de documento y su contenido.</span><span class="sxs-lookup"><span data-stu-id="ac427-159">In the `UserType1` client, select the single approval type from the drop down menu and type a document name and content.</span></span> <span data-ttu-id="ac427-160">Haga clic en **solicitar aprobación**.</span><span class="sxs-lookup"><span data-stu-id="ac427-160">Click **Request Approval**.</span></span>  
  
7.  <span data-ttu-id="ac427-161">En el cliente `UserType2`, aparecerá un documento a la espera de aprobación.</span><span class="sxs-lookup"><span data-stu-id="ac427-161">In the `UserType2` client, a document awaiting approval appears.</span></span> <span data-ttu-id="ac427-162">Selecciónelo y presione **aprobar** o **rechazar**.</span><span class="sxs-lookup"><span data-stu-id="ac427-162">Select it and press **approve** or **reject**.</span></span> <span data-ttu-id="ac427-163">Los resultados deberían mostrarse en el cliente `UserType1`.</span><span class="sxs-lookup"><span data-stu-id="ac427-163">The results should show in the `UserType1` client.</span></span>  
  
##### <a name="to-run-the-quorum-approval-scenario"></a><span data-ttu-id="ac427-164">Para ejecutar el escenario de aprobación de quórum</span><span class="sxs-lookup"><span data-stu-id="ac427-164">To run the quorum approval scenario</span></span>  
  
1.  <span data-ttu-id="ac427-165">Abra un símbolo del sistema con permisos de administrador.</span><span class="sxs-lookup"><span data-stu-id="ac427-165">Open a command prompt with administrator permission.</span></span>  
  
2.  <span data-ttu-id="ac427-166">Navegue al directorio que contiene la solución.</span><span class="sxs-lookup"><span data-stu-id="ac427-166">Navigate to the directory that contains the solution.</span></span>  
  
3.  <span data-ttu-id="ac427-167">Navegue a la carpeta ApprovalClient\Bin\Debug y ejecute tres instancias de ApprovalClient.exe.</span><span class="sxs-lookup"><span data-stu-id="ac427-167">Navigate to the ApprovalClient\Bin\Debug folder and execute three instances of ApprovalClient.exe.</span></span>  
  
4.  <span data-ttu-id="ac427-168">Haga clic en **detectar**, espere hasta que el **suscribirse** botón está habilitado.</span><span class="sxs-lookup"><span data-stu-id="ac427-168">Click **discover**, wait until the **subscribe** button is enabled.</span></span>  
  
5.  <span data-ttu-id="ac427-169">Escriba cualquier nombre de usuario y haga clic en **suscribirse**.</span><span class="sxs-lookup"><span data-stu-id="ac427-169">Type any user name and click **subscribe**.</span></span> <span data-ttu-id="ac427-170">Para un cliente, use `UserType1` y para los otros dos, escriba `UserType2`.</span><span class="sxs-lookup"><span data-stu-id="ac427-170">For one client use `UserType1` and the other two type `UserType2`.</span></span>  
  
6.  <span data-ttu-id="ac427-171">En el cliente `UserType1`, seleccione el tipo de aprobación de quórum en el menú desplegable y escriba un nombre de documento y su contenido.</span><span class="sxs-lookup"><span data-stu-id="ac427-171">In the `UserType1` client, select the quorum approval type from the drop down menu and type a document name and content.</span></span> <span data-ttu-id="ac427-172">Haga clic en **solicitar aprobación**.</span><span class="sxs-lookup"><span data-stu-id="ac427-172">Click **Request Approval**.</span></span> <span data-ttu-id="ac427-173">Este tipo de aprobación requieres que los dos clientes `UserType2` aprueben o rechacen el documento.</span><span class="sxs-lookup"><span data-stu-id="ac427-173">This requests that the two `UserType2` clients approve or reject the document.</span></span> <span data-ttu-id="ac427-174">Aunque los dos clientes `UserType2` deben responder, solo uno de ellos necesita aprobar el documento para que se considere aprobado.</span><span class="sxs-lookup"><span data-stu-id="ac427-174">While both `UserType2` clients must respond, only one client must approve the document for it to be approved.</span></span>  
  
7.  <span data-ttu-id="ac427-175">En los clientes `UserType2`, aparecerá un documento a la espera de aprobación.</span><span class="sxs-lookup"><span data-stu-id="ac427-175">In the `UserType2` clients, a document awaiting approval appears.</span></span> <span data-ttu-id="ac427-176">Selecciónelo y presione **aprobar** o **rechazar**.</span><span class="sxs-lookup"><span data-stu-id="ac427-176">Select it and press **approve** or **reject**.</span></span> <span data-ttu-id="ac427-177">Los resultados deberían mostrarse en el cliente `UserType1`.</span><span class="sxs-lookup"><span data-stu-id="ac427-177">The results should show in the `UserType1` client.</span></span>  
  
##### <a name="to-run-the-complex-approval-scenario"></a><span data-ttu-id="ac427-178">Para ejecutar el escenario de aprobación compleja</span><span class="sxs-lookup"><span data-stu-id="ac427-178">To run the complex approval scenario</span></span>  
  
1.  <span data-ttu-id="ac427-179">Abra un símbolo del sistema con permisos de administrador.</span><span class="sxs-lookup"><span data-stu-id="ac427-179">Open a command prompt with administrator permission.</span></span>  
  
2.  <span data-ttu-id="ac427-180">Navegue al directorio que contiene la solución.</span><span class="sxs-lookup"><span data-stu-id="ac427-180">Navigate to the directory that contains the solution.</span></span>  
  
3.  <span data-ttu-id="ac427-181">Navegue a la carpeta ApprovalClient\Bin\Debug y ejecute cuatro instancias de ApprovalClient.exe.</span><span class="sxs-lookup"><span data-stu-id="ac427-181">Navigate to the ApprovalClient\Bin\Debug folder and execute four instances of ApprovalClient.exe.</span></span>  
  
4.  <span data-ttu-id="ac427-182">Haga clic en **detectar**, espere hasta que el **suscribirse** botón está habilitado.</span><span class="sxs-lookup"><span data-stu-id="ac427-182">Click **discover**, wait until the **subscribe** button is enabled.</span></span>  
  
5.  <span data-ttu-id="ac427-183">Escriba cualquier nombre de usuario y haga clic en **suscribirse**.</span><span class="sxs-lookup"><span data-stu-id="ac427-183">Type any user name and click **subscribe**.</span></span> <span data-ttu-id="ac427-184">Para un cliente, use `UserType1`, para los otros dos, escriba `UserType2` y en el último, use `UserType3`.</span><span class="sxs-lookup"><span data-stu-id="ac427-184">For one client use `UserType1`, in two uses type `UserType2`, and in the last use `UserType3`.</span></span>  
  
6.  <span data-ttu-id="ac427-185">En el cliente `UserType1`, seleccione el tipo de aprobación única en el menú desplegable y escriba un nombre de documento y su contenido.</span><span class="sxs-lookup"><span data-stu-id="ac427-185">In the `UserType1` client, select the single approval type from the drop down menu and type a document name and content.</span></span> <span data-ttu-id="ac427-186">Haga clic en **solicitar aprobación**.</span><span class="sxs-lookup"><span data-stu-id="ac427-186">Click **Request Approval**.</span></span>  
  
7.  <span data-ttu-id="ac427-187">En los clientes `UserType2`, aparecerá un documento a la espera de aprobación.</span><span class="sxs-lookup"><span data-stu-id="ac427-187">In the `UserType2` clients, a document awaiting approval appears.</span></span> <span data-ttu-id="ac427-188">Selecciónelo y presione **aprobar**, el documento se pasa a la `UserType3` cliente.</span><span class="sxs-lookup"><span data-stu-id="ac427-188">Select it and press **approve**, the document is passed to the `UserType3` client.</span></span>  
  
     <span data-ttu-id="ac427-189">Si el primer quórum `UserType2` aprueba el documento, el documento se pasa al cliente `UserType3`.</span><span class="sxs-lookup"><span data-stu-id="ac427-189">If the document is approved by the first `UserType2` quorum, the document is passed to the `UserType3` client.</span></span>  
  
8.  <span data-ttu-id="ac427-190">Apruebe o rechace el documento en el cliente `UserType3`.</span><span class="sxs-lookup"><span data-stu-id="ac427-190">Approve or reject the document from the `UserType3` client.</span></span> <span data-ttu-id="ac427-191">Los resultados deberían mostrarse en el cliente `UserType1`.</span><span class="sxs-lookup"><span data-stu-id="ac427-191">The results should show in the `UserType1` client.</span></span>  
  
##### <a name="to-clean-up"></a><span data-ttu-id="ac427-192">Para realizar una limpieza</span><span class="sxs-lookup"><span data-stu-id="ac427-192">To clean up</span></span>  
  
1.  <span data-ttu-id="ac427-193">Desde un símbolo del sistema de Visual Studio 2010, vaya a la carpeta DocumentApprovalProcess y ejecute Cleanup.cmd.</span><span class="sxs-lookup"><span data-stu-id="ac427-193">From a Visual Studio 2010 command prompt, navigate to the DocumentApprovalProcess folder and run Cleanup.cmd.</span></span>
