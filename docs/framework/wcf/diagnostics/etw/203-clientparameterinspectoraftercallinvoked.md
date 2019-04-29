---
title: 203 - ClientParameterInspectorAfterCallInvoked
ms.date: 03/30/2017
ms.assetid: b9592212-07e2-43e0-8b00-affd195cf55a
ms.openlocfilehash: 57192b44a0c3babc77fcca13ad4a1433b85bfdd7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781945"
---
# <a name="203---clientparameterinspectoraftercallinvoked"></a><span data-ttu-id="d2e3c-102">203 - ClientParameterInspectorAfterCallInvoked</span><span class="sxs-lookup"><span data-stu-id="d2e3c-102">203 - ClientParameterInspectorAfterCallInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="d2e3c-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="d2e3c-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d2e3c-104">ID</span><span class="sxs-lookup"><span data-stu-id="d2e3c-104">ID</span></span>|<span data-ttu-id="d2e3c-105">203</span><span class="sxs-lookup"><span data-stu-id="d2e3c-105">203</span></span>|  
|<span data-ttu-id="d2e3c-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="d2e3c-106">Keywords</span></span>|<span data-ttu-id="d2e3c-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="d2e3c-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="d2e3c-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="d2e3c-108">Level</span></span>|<span data-ttu-id="d2e3c-109">Información</span><span class="sxs-lookup"><span data-stu-id="d2e3c-109">Information</span></span>|  
|<span data-ttu-id="d2e3c-110">Canal</span><span class="sxs-lookup"><span data-stu-id="d2e3c-110">Channel</span></span>|<span data-ttu-id="d2e3c-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="d2e3c-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="d2e3c-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="d2e3c-112">Description</span></span>  
 <span data-ttu-id="d2e3c-113">Se emite este evento cuando el modelo de servicio ha invocado el método `AfterCall` en un inspector de parámetro de cliente.</span><span class="sxs-lookup"><span data-stu-id="d2e3c-113">This event is emitted after the Service Model has invoked the `AfterCall` method on a client parameter inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="d2e3c-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="d2e3c-114">Message</span></span>  
 <span data-ttu-id="d2e3c-115">El distribuidor invocó 'AfterCall' en ClientParameterInspector de tipo '%1'.</span><span class="sxs-lookup"><span data-stu-id="d2e3c-115">The Dispatcher invoked 'AfterCall' on a ClientParameterInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="d2e3c-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="d2e3c-116">Details</span></span>  
  
|<span data-ttu-id="d2e3c-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="d2e3c-117">Data Item Name</span></span>|<span data-ttu-id="d2e3c-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="d2e3c-118">Data Item Type</span></span>|<span data-ttu-id="d2e3c-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="d2e3c-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="d2e3c-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="d2e3c-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="d2e3c-121">El nombre completo (FullName) de CLR del tipo del inspector invocado.</span><span class="sxs-lookup"><span data-stu-id="d2e3c-121">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="d2e3c-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="d2e3c-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="d2e3c-123">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="d2e3c-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="d2e3c-124">Su formato se define como ' ruta de acceso Virtual de sitio Web de nombre de la aplicación&#124;ruta de acceso Virtual del servicio&#124;ServiceName ".</span><span class="sxs-lookup"><span data-stu-id="d2e3c-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="d2e3c-125">Ejemplo: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="d2e3c-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="d2e3c-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="d2e3c-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="d2e3c-127">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="d2e3c-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
