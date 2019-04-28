---
title: 1131 - InvokeMethodUseAsyncPattern
ms.date: 03/30/2017
ms.assetid: eca50fa7-5276-4759-ad1c-e490b9bd1f82
ms.openlocfilehash: 150973935d12455aa671043a619fbd6fd7e77425
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62009960"
---
# <a name="1131---invokemethoduseasyncpattern"></a><span data-ttu-id="26a6f-102">1131 - InvokeMethodUseAsyncPattern</span><span class="sxs-lookup"><span data-stu-id="26a6f-102">1131 - InvokeMethodUseAsyncPattern</span></span>
## <a name="properties"></a><span data-ttu-id="26a6f-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="26a6f-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="26a6f-104">ID</span><span class="sxs-lookup"><span data-stu-id="26a6f-104">ID</span></span>|<span data-ttu-id="26a6f-105">1131</span><span class="sxs-lookup"><span data-stu-id="26a6f-105">1131</span></span>|  
|<span data-ttu-id="26a6f-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="26a6f-106">Keywords</span></span>|<span data-ttu-id="26a6f-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="26a6f-107">WFRuntime</span></span>|  
|<span data-ttu-id="26a6f-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="26a6f-108">Level</span></span>|<span data-ttu-id="26a6f-109">Información</span><span class="sxs-lookup"><span data-stu-id="26a6f-109">Information</span></span>|  
|<span data-ttu-id="26a6f-110">Canal</span><span class="sxs-lookup"><span data-stu-id="26a6f-110">Channel</span></span>|<span data-ttu-id="26a6f-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="26a6f-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="26a6f-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="26a6f-112">Description</span></span>  
 <span data-ttu-id="26a6f-113">Durante el paso CacheMetadata, la actividad InvokeMethod indica que no está usando el patrón asincrónico al invocar el método.</span><span class="sxs-lookup"><span data-stu-id="26a6f-113">During CacheMetadata step, InvokeMethod activity indicates that it is using the async pattern when invoking the method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="26a6f-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="26a6f-114">Message</span></span>  
 <span data-ttu-id="26a6f-115">InvokeMethod '%1': el método usa el patrón asincrónico de '%2' y '%3'.</span><span class="sxs-lookup"><span data-stu-id="26a6f-115">InvokeMethod '%1' - method uses asynchronous pattern of '%2' and '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="26a6f-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="26a6f-116">Details</span></span>  
  
|<span data-ttu-id="26a6f-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="26a6f-117">Data Item Name</span></span>|<span data-ttu-id="26a6f-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="26a6f-118">Data Item Type</span></span>|<span data-ttu-id="26a6f-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="26a6f-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="26a6f-120">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="26a6f-120">InvokeMethod</span></span>|<span data-ttu-id="26a6f-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="26a6f-121">xs:string</span></span>|<span data-ttu-id="26a6f-122">Identificación y nombre para mostrar de la actividad InvokeMethod.</span><span class="sxs-lookup"><span data-stu-id="26a6f-122">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="26a6f-123">BeginMethod</span><span class="sxs-lookup"><span data-stu-id="26a6f-123">BeginMethod</span></span>|<span data-ttu-id="26a6f-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="26a6f-124">xs:string</span></span>|<span data-ttu-id="26a6f-125">Nombre del método de inicio.</span><span class="sxs-lookup"><span data-stu-id="26a6f-125">The name of the begin method.</span></span>|  
|<span data-ttu-id="26a6f-126">EndMethod</span><span class="sxs-lookup"><span data-stu-id="26a6f-126">EndMethod</span></span>|<span data-ttu-id="26a6f-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="26a6f-127">xs:string</span></span>|<span data-ttu-id="26a6f-128">Nombre del método de fin.</span><span class="sxs-lookup"><span data-stu-id="26a6f-128">The name of the end method.</span></span>|  
|<span data-ttu-id="26a6f-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="26a6f-129">AppDomain</span></span>|<span data-ttu-id="26a6f-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="26a6f-130">xs:string</span></span>|<span data-ttu-id="26a6f-131">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="26a6f-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
