---
title: 1005 - WorkflowApplicationIdled
ms.date: 03/30/2017
ms.assetid: 74d77dfa-f20d-4fe9-a6ae-e6d1b5fe4182
ms.openlocfilehash: 6bbd12e8025b6a127dbfec8e5d3690825c188c4d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62008608"
---
# <a name="1005---workflowapplicationidled"></a><span data-ttu-id="de162-102">1005 - WorkflowApplicationIdled</span><span class="sxs-lookup"><span data-stu-id="de162-102">1005 - WorkflowApplicationIdled</span></span>
## <a name="properties"></a><span data-ttu-id="de162-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="de162-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="de162-104">ID</span><span class="sxs-lookup"><span data-stu-id="de162-104">ID</span></span>|<span data-ttu-id="de162-105">1005</span><span class="sxs-lookup"><span data-stu-id="de162-105">1005</span></span>|  
|<span data-ttu-id="de162-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="de162-106">Keywords</span></span>|<span data-ttu-id="de162-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="de162-107">WFRuntime</span></span>|  
|<span data-ttu-id="de162-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="de162-108">Level</span></span>|<span data-ttu-id="de162-109">Información</span><span class="sxs-lookup"><span data-stu-id="de162-109">Information</span></span>|  
|<span data-ttu-id="de162-110">Canal</span><span class="sxs-lookup"><span data-stu-id="de162-110">Channel</span></span>|<span data-ttu-id="de162-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="de162-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="de162-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="de162-112">Description</span></span>  
 <span data-ttu-id="de162-113">Indica que una aplicación de flujo de trabajo ha estado inactiva.</span><span class="sxs-lookup"><span data-stu-id="de162-113">Indicates a workflow application has idled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="de162-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="de162-114">Message</span></span>  
 <span data-ttu-id="de162-115">WorkflowApplication Id: '%1' se desactivó.</span><span class="sxs-lookup"><span data-stu-id="de162-115">WorkflowApplication Id: '%1' went idle.</span></span>  
  
## <a name="details"></a><span data-ttu-id="de162-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="de162-116">Details</span></span>  
  
|<span data-ttu-id="de162-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="de162-117">Data Item Name</span></span>|<span data-ttu-id="de162-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="de162-118">Data Item Type</span></span>|<span data-ttu-id="de162-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="de162-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="de162-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="de162-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="de162-121">Identificador de la aplicación del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="de162-121">The workflow application id</span></span>|  
|<span data-ttu-id="de162-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="de162-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="de162-123">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="de162-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
