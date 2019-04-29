---
title: 211 - ParameterInspectorAfterCallInvoked
ms.date: 03/30/2017
ms.assetid: c0e21297-10b8-4456-a0e1-e019145cd5ac
ms.openlocfilehash: ada3ced31def2bb821b975e09f50ad83f28d56bf
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781867"
---
# <a name="211---parameterinspectoraftercallinvoked"></a><span data-ttu-id="d032b-102">211 - ParameterInspectorAfterCallInvoked</span><span class="sxs-lookup"><span data-stu-id="d032b-102">211 - ParameterInspectorAfterCallInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="d032b-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="d032b-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d032b-104">ID</span><span class="sxs-lookup"><span data-stu-id="d032b-104">ID</span></span>|<span data-ttu-id="d032b-105">211</span><span class="sxs-lookup"><span data-stu-id="d032b-105">211</span></span>|  
|<span data-ttu-id="d032b-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="d032b-106">Keywords</span></span>|<span data-ttu-id="d032b-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="d032b-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="d032b-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="d032b-108">Level</span></span>|<span data-ttu-id="d032b-109">Información</span><span class="sxs-lookup"><span data-stu-id="d032b-109">Information</span></span>|  
|<span data-ttu-id="d032b-110">Canal</span><span class="sxs-lookup"><span data-stu-id="d032b-110">Channel</span></span>|<span data-ttu-id="d032b-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="d032b-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="d032b-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="d032b-112">Description</span></span>  
 <span data-ttu-id="d032b-113">Se emite este evento cuando el modelo de servicio ha invocado el método `AfterCall` en `ParameterInspector`.</span><span class="sxs-lookup"><span data-stu-id="d032b-113">This event is emitted after the Service Model has invoked the `AfterCall` method on a `ParameterInspector`.</span></span>  
  
## <a name="message"></a><span data-ttu-id="d032b-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="d032b-114">Message</span></span>  
 <span data-ttu-id="d032b-115">El distribuidor invocó 'AfterCall' en un ParameterInspector de tipo '%1'.</span><span class="sxs-lookup"><span data-stu-id="d032b-115">The Dispatcher invoked 'AfterCall' on a ParameterInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="d032b-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="d032b-116">Details</span></span>  
  
|<span data-ttu-id="d032b-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="d032b-117">Data Item Name</span></span>|<span data-ttu-id="d032b-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="d032b-118">Data Item Type</span></span>|<span data-ttu-id="d032b-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="d032b-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="d032b-120">Nombre de tipo</span><span class="sxs-lookup"><span data-stu-id="d032b-120">Type Name</span></span>|`xs:string`|<span data-ttu-id="d032b-121">Nombre completo (FullName) de CLR del tipo del `ParameterInspector` invocado.</span><span class="sxs-lookup"><span data-stu-id="d032b-121">The CLR FullName of the type of the invoked `ParameterInspector`.</span></span>|  
|<span data-ttu-id="d032b-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="d032b-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="d032b-123">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="d032b-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="d032b-124">Su formato se define como ' ruta de acceso Virtual de sitio Web de nombre de la aplicación&#124;ruta de acceso Virtual del servicio&#124;ServiceName ".</span><span class="sxs-lookup"><span data-stu-id="d032b-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="d032b-125">Ejemplo: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="d032b-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="d032b-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="d032b-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="d032b-127">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="d032b-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
