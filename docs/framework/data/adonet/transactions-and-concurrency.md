---
title: Transacciones y simultaneidad
ms.date: 03/30/2017
ms.assetid: f46570de-9e50-4fe6-8710-a8c31fa8569b
ms.openlocfilehash: 837fe6c42d64f7416dbd895e56a38d1a409e567a
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70791317"
---
# <a name="transactions-and-concurrency"></a><span data-ttu-id="2570e-102">Transacciones y simultaneidad</span><span class="sxs-lookup"><span data-stu-id="2570e-102">Transactions and Concurrency</span></span>
<span data-ttu-id="2570e-103">Una transacción consiste en un comando único o en un grupo de comandos que se ejecutan como un paquete.</span><span class="sxs-lookup"><span data-stu-id="2570e-103">A transaction consists of a single command or a group of commands that execute as a package.</span></span> <span data-ttu-id="2570e-104">Las transacciones permiten combinar varias operaciones en una sola unidad de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2570e-104">Transactions allow you to combine multiple operations into a single unit of work.</span></span> <span data-ttu-id="2570e-105">Si en un punto de la transacción se produjera un error, todas las actualizaciones podrían revertirse y devolverse al estado que tenían antes de la transacción.</span><span class="sxs-lookup"><span data-stu-id="2570e-105">If a failure occurs at one point in the transaction, all of the updates can be rolled back to their pre-transaction state.</span></span>  
  
 <span data-ttu-id="2570e-106">Una transacción debe ajustarse a las propiedades ACID (atomicidad, coherencia, aislamiento y durabilidad) para poder garantizar la coherencia de datos.</span><span class="sxs-lookup"><span data-stu-id="2570e-106">A transaction must conform to the ACID properties—atomicity, consistency, isolation, and durability—in order to guarantee data consistency.</span></span> <span data-ttu-id="2570e-107">La mayoría de los sistemas de bases de datos relacionales, como Microsoft SQL Server, admiten transacciones, al proporcionar funciones de bloqueo, registro y administración de transacciones cada vez que una aplicación cliente realiza una operación de actualización, inserción o eliminación.</span><span class="sxs-lookup"><span data-stu-id="2570e-107">Most relational database systems, such as Microsoft SQL Server, support transactions by providing locking, logging, and transaction management facilities whenever a client application performs an update, insert, or delete operation.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2570e-108">Las transacciones que requieren varios recursos pueden reducir la simultaneidad si la duración del bloqueo es demasiado larga.</span><span class="sxs-lookup"><span data-stu-id="2570e-108">Transactions that involve multiple resources can lower concurrency if locks are held too long.</span></span> <span data-ttu-id="2570e-109">Por ello, haga la transacción lo más corta posible.</span><span class="sxs-lookup"><span data-stu-id="2570e-109">Therefore, keep transactions as short as possible.</span></span>  
  
 <span data-ttu-id="2570e-110">Las transacciones explícitas en procedimientos almacenados suelen dar mejores resultados cuando una transacción implica el uso de varias tablas en la misma base de datos o servidor.</span><span class="sxs-lookup"><span data-stu-id="2570e-110">If a transaction involves multiple tables in the same database or server, then explicit transactions in stored procedures often perform better.</span></span> <span data-ttu-id="2570e-111">Se pueden crear transacciones en procedimientos almacenados de SQL Server mediante las instrucciones `BEGIN TRANSACTION`, `COMMIT TRANSACTION` o `ROLLBACK TRANSACTION` de Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="2570e-111">You can create transactions in SQL Server stored procedures by using the Transact-SQL `BEGIN TRANSACTION`, `COMMIT TRANSACTION`, and `ROLLBACK TRANSACTION` statements.</span></span> <span data-ttu-id="2570e-112">Para obtener más información, vea los Libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2570e-112">For more information, see SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="2570e-113">Las transacciones que implican diferentes administradores de recursos, como una transacción entre SQL Server y Oracle, requieren una transacción distribuida.</span><span class="sxs-lookup"><span data-stu-id="2570e-113">Transactions involving different resource managers, such as a transaction between SQL Server and Oracle, require a distributed transaction.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2570e-114">En esta sección</span><span class="sxs-lookup"><span data-stu-id="2570e-114">In This Section</span></span>  
 [<span data-ttu-id="2570e-115">Transacciones locales</span><span class="sxs-lookup"><span data-stu-id="2570e-115">Local Transactions</span></span>](local-transactions.md)  
 <span data-ttu-id="2570e-116">Muestra cómo realizar transacciones en una base de datos.</span><span class="sxs-lookup"><span data-stu-id="2570e-116">Demonstrates how to perform transactions against a database.</span></span>  
  
 [<span data-ttu-id="2570e-117">Transacciones distribuidas</span><span class="sxs-lookup"><span data-stu-id="2570e-117">Distributed Transactions</span></span>](distributed-transactions.md)  
 <span data-ttu-id="2570e-118">Describe cómo realizar transacciones distribuidas en ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="2570e-118">Describes how to perform distributed transactions in ADO.NET.</span></span>  
  
 [<span data-ttu-id="2570e-119">Integración de System.Transactions con SQL Server</span><span class="sxs-lookup"><span data-stu-id="2570e-119">System.Transactions Integration with SQL Server</span></span>](system-transactions-integration-with-sql-server.md)  
 <span data-ttu-id="2570e-120">Describe <xref:System.Transactions> la integración con SQL Server para trabajar con transacciones distribuidas.</span><span class="sxs-lookup"><span data-stu-id="2570e-120">Describes <xref:System.Transactions> integration with SQL Server for working with distributed transactions.</span></span>  
  
 [<span data-ttu-id="2570e-121">Simultaneidad optimista</span><span class="sxs-lookup"><span data-stu-id="2570e-121">Optimistic Concurrency</span></span>](optimistic-concurrency.md)  
 <span data-ttu-id="2570e-122">Describe la simultaneidad optimista y pesimista, y cómo puede probar las infracciones de simultaneidad.</span><span class="sxs-lookup"><span data-stu-id="2570e-122">Describes optimistic and pessimistic concurrency, and how you can test for concurrency violations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2570e-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="2570e-123">See also</span></span>

- [<span data-ttu-id="2570e-124">Principios de la transacción</span><span class="sxs-lookup"><span data-stu-id="2570e-124">Transaction Fundamentals</span></span>](../transactions/transaction-fundamentals.md)
- [<span data-ttu-id="2570e-125">Conexión a un origen de datos</span><span class="sxs-lookup"><span data-stu-id="2570e-125">Connecting to a Data Source</span></span>](connecting-to-a-data-source.md)
- [<span data-ttu-id="2570e-126">Comandos y parámetros</span><span class="sxs-lookup"><span data-stu-id="2570e-126">Commands and Parameters</span></span>](commands-and-parameters.md)
- [<span data-ttu-id="2570e-127">Objetos DataAdapter y DataReader</span><span class="sxs-lookup"><span data-stu-id="2570e-127">DataAdapters and DataReaders</span></span>](dataadapters-and-datareaders.md)
- [<span data-ttu-id="2570e-128">Objetos DbProviderFactory</span><span class="sxs-lookup"><span data-stu-id="2570e-128">DbProviderFactories</span></span>](dbproviderfactories.md)
- [<span data-ttu-id="2570e-129">Información general sobre ADO.NET</span><span class="sxs-lookup"><span data-stu-id="2570e-129">ADO.NET Overview</span></span>](ado-net-overview.md)
