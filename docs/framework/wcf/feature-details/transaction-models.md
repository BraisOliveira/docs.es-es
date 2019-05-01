---
title: Modelos de transacción
ms.date: 03/30/2017
ms.assetid: 48a8bc1b-128b-4cf1-a421-8cc73223c340
ms.openlocfilehash: 8731b72d0657aa420dbb020e216c3af059916ce9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62050784"
---
# <a name="transaction-models"></a><span data-ttu-id="53dc8-102">Modelos de transacción</span><span class="sxs-lookup"><span data-stu-id="53dc8-102">Transaction Models</span></span>
<span data-ttu-id="53dc8-103">En este tema se describe la relación entre los modelos de programación de la transacción y los componentes de infraestructura que Microsoft proporciona.</span><span class="sxs-lookup"><span data-stu-id="53dc8-103">This topic describes the relationship between the transaction programming models and the infrastructure components Microsoft provides.</span></span>  
  
 <span data-ttu-id="53dc8-104">Cuando se usan transacciones en Windows Communication Foundation (WCF), es importante entender que no está seleccionando entre modelos transaccionales diferentes pero operando en diferentes niveles de un modelo integrado y coherente.</span><span class="sxs-lookup"><span data-stu-id="53dc8-104">When using transactions in Windows Communication Foundation (WCF), it is important to understand that you are not selecting between different transactional models, but rather operating at different layers of an integrated and consistent model.</span></span>  
  
 <span data-ttu-id="53dc8-105">Las secciones siguientes describen los tres componentes de transacción primarios.</span><span class="sxs-lookup"><span data-stu-id="53dc8-105">The following sections describe the three primary transaction components.</span></span>  
  
## <a name="windows-communication-foundation-transactions"></a><span data-ttu-id="53dc8-106">Transacciones de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="53dc8-106">Windows Communication Foundation Transactions</span></span>  
 <span data-ttu-id="53dc8-107">La compatibilidad con transacciones en WCF permite que escribir servicios transaccionales.</span><span class="sxs-lookup"><span data-stu-id="53dc8-107">The transaction support in WCF allows you write transactional services.</span></span> <span data-ttu-id="53dc8-108">Además, con su compatibilidad con el protocolo WS-AtomicTransaction (WS-AT), las aplicaciones pueden fluir transacciones a servicios Web creados mediante WCF o tecnología de otro fabricante.</span><span class="sxs-lookup"><span data-stu-id="53dc8-108">In addition, with its support for the WS-AtomicTransaction (WS-AT) protocol, applications can flow transactions to Web services built using either WCF or third-party technology.</span></span>  
  
 <span data-ttu-id="53dc8-109">En una aplicación o servicio WCF, características de la transacción de WCF proporcionan atributos y configuración para especificar mediante declaración cómo y cuándo la infraestructura debe crear, fluir y sincronizar transacciones.</span><span class="sxs-lookup"><span data-stu-id="53dc8-109">In a WCF service or application, WCF transaction features provide attributes and configuration for declaratively specifying how and when the infrastructure should create, flow, and synchronize transactions.</span></span>  
  
## <a name="systemtransactions-transactions"></a><span data-ttu-id="53dc8-110">Información general sobre las transacciones de System.Transactions</span><span class="sxs-lookup"><span data-stu-id="53dc8-110">System.Transactions Transactions</span></span>  
 <span data-ttu-id="53dc8-111">El espacio de nombres <xref:System.Transactions> proporciona un modelo de programación explícito según la clase <xref:System.Transactions.Transaction>, así como un modelo de programación implícito utilizando la clase <xref:System.Transactions.TransactionScope>, en la que la infraestructura administra automáticamente las transacciones.</span><span class="sxs-lookup"><span data-stu-id="53dc8-111">The <xref:System.Transactions> namespace provides both an explicit programming model based on the <xref:System.Transactions.Transaction> class, as well as an implicit programming model using the <xref:System.Transactions.TransactionScope> class, in which the infrastructure automatically manages transactions.</span></span>  
  
 <span data-ttu-id="53dc8-112">Para obtener más información sobre cómo crear una aplicación transaccional utilizando estos dos modelos, vea [crear una aplicación transaccional](https://go.microsoft.com/fwlink/?LinkId=94947).</span><span class="sxs-lookup"><span data-stu-id="53dc8-112">For more information about how to create a transactional application using these two models, see [Writing a Transactional Application](https://go.microsoft.com/fwlink/?LinkId=94947).</span></span>  
  
 <span data-ttu-id="53dc8-113">En una aplicación, o un servicio WCF <xref:System.Transactions> proporciona el modelo de programación para crear las transacciones dentro de una aplicación cliente y para interactuar explícitamente con una transacción, cuando sea necesario, dentro de un servicio.</span><span class="sxs-lookup"><span data-stu-id="53dc8-113">In a WCF service or application, <xref:System.Transactions> provides the programming model for creating transactions within a client application and for explicitly interacting with a transaction, when required, within a service.</span></span>  
  
## <a name="msdtc-transactions"></a><span data-ttu-id="53dc8-114">Transacciones de MSDTC</span><span class="sxs-lookup"><span data-stu-id="53dc8-114">MSDTC Transactions</span></span>  
 <span data-ttu-id="53dc8-115">Microsoft DTC (Coordinador de transacciones distribuidas) (MSDTC) es un administrador de transacciones que proporciona compatibilidad con transacciones distribuidas.</span><span class="sxs-lookup"><span data-stu-id="53dc8-115">The Microsoft Distributed Transaction Coordinator (MSDTC) is a transaction manager that provides support for distributed transactions.</span></span>  
  
 <span data-ttu-id="53dc8-116">Para obtener más información, consulte el [referencia del programador de DTC](https://go.microsoft.com/fwlink/?LinkId=94948).</span><span class="sxs-lookup"><span data-stu-id="53dc8-116">For more information, see the [DTC Programmer's Reference](https://go.microsoft.com/fwlink/?LinkId=94948).</span></span>  
  
 <span data-ttu-id="53dc8-117">En una aplicación o servicio WCF, MSDTC proporciona la infraestructura para la coordinación de transacciones creada dentro de un cliente o servicio.</span><span class="sxs-lookup"><span data-stu-id="53dc8-117">In a WCF service or application, MSDTC provides the infrastructure for the coordination of transactions created within a client or service.</span></span>
