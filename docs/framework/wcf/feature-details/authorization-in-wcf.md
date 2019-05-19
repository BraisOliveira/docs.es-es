---
title: Autorización en WCF
ms.date: 03/30/2017
helpviewer_keywords:
- authorization [WCF]
- security [WCF], authorization
ms.assetid: 8ea0b552-af65-45b0-a157-c6c111b8ce5e
ms.openlocfilehash: 8c605b310f19a05f994296d8f4268b91b408fb18
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2019
ms.locfileid: "65881202"
---
# <a name="authorization-in-wcf"></a><span data-ttu-id="e257b-102">Autorización en WCF</span><span class="sxs-lookup"><span data-stu-id="e257b-102">Authorization in WCF</span></span>
<span data-ttu-id="e257b-103">La autorización es el proceso para controlar el acceso y los derechos a los recursos, como servicios o archivos.</span><span class="sxs-lookup"><span data-stu-id="e257b-103">Authorization is the process of controlling access and rights to resources, such as services or files.</span></span> <span data-ttu-id="e257b-104">Los temas de esta sección muestran cómo realizar esta tarea básica en Windows Communication Foundation (WCF) en una variedad de formas.</span><span class="sxs-lookup"><span data-stu-id="e257b-104">The topics in this section show you how to perform this basic task in Windows Communication Foundation (WCF) in a variety of ways.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e257b-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="e257b-105">In This Section</span></span>  
 [<span data-ttu-id="e257b-106">Mecanismos de control de acceso</span><span class="sxs-lookup"><span data-stu-id="e257b-106">Access Control Mechanisms</span></span>](../../../../docs/framework/wcf/feature-details/access-control-mechanisms.md)  
 <span data-ttu-id="e257b-107">Proporciona una descripción breve de los mecanismos de autorización en WCF y usos sugeridos.</span><span class="sxs-lookup"><span data-stu-id="e257b-107">Provides a brief outline of the authorization mechanisms in WCF, and suggested uses.</span></span>  
  
 [<span data-ttu-id="e257b-108">Cómo: Restringir el acceso con la clase PrincipalPermissionAttribute</span><span class="sxs-lookup"><span data-stu-id="e257b-108">How to: Restrict Access with the PrincipalPermissionAttribute Class</span></span>](../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)  
 <span data-ttu-id="e257b-109">Muestra el proceso de restringir el acceso a un servicio con <xref:System.Security.Permissions.PrincipalPermissionAttribute>.</span><span class="sxs-lookup"><span data-stu-id="e257b-109">Shows the process of restricting access to a service with the <xref:System.Security.Permissions.PrincipalPermissionAttribute>.</span></span>  
  
 [<span data-ttu-id="e257b-110">Cómo: Usar el proveedor de funciones ASP.NET con un servicio</span><span class="sxs-lookup"><span data-stu-id="e257b-110">How to: Use the ASP.NET Role Provider with a Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)  
 <span data-ttu-id="e257b-111">Describe la configuración de un servicio para que pueda usar la característica de proveedor de roles de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="e257b-111">Walks through the configuration of a service to enable it to use the role provider feature of ASP.NET.</span></span>  
  
 [<span data-ttu-id="e257b-112">Cómo: Usar el proveedor de roles de administrador de autorización de ASP.NET con un servicio</span><span class="sxs-lookup"><span data-stu-id="e257b-112">How to: Use the ASP.NET Authorization Manager Role Provider with a Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service.md)  
 <span data-ttu-id="e257b-113">ASP.NET puede usar el Administrador de autorización para administrar la autorización para un sitio Web.</span><span class="sxs-lookup"><span data-stu-id="e257b-113">ASP.NET can use the Authorization Manager to manage authorization for a Web site.</span></span> <span data-ttu-id="e257b-114">WCF de forma similar puede aprovechar la combinación de ASP.NET/Authorization Manager para la autorización de clientes.</span><span class="sxs-lookup"><span data-stu-id="e257b-114">WCF can similarly leverage the ASP.NET/Authorization Manager combination for authorization of clients.</span></span>  
  
 [<span data-ttu-id="e257b-115">Administración de notificaciones y autorización con el modelo de identidad</span><span class="sxs-lookup"><span data-stu-id="e257b-115">Managing Claims and Authorization with the Identity Model</span></span>](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)  
 <span data-ttu-id="e257b-116">Explica los fundamentos para utilizar la infraestructura del modelo de identidad para la autorización basada en demandas.</span><span class="sxs-lookup"><span data-stu-id="e257b-116">Explains the basics of using the Identity Model infrastructure for claims-based authorization.</span></span>  
  
 [<span data-ttu-id="e257b-117">Delegación y suplantación</span><span class="sxs-lookup"><span data-stu-id="e257b-117">Delegation and Impersonation</span></span>](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md)  
 <span data-ttu-id="e257b-118">Explica la diferencia entre la delegación y la suplantación.</span><span class="sxs-lookup"><span data-stu-id="e257b-118">Explains the difference between delegation and impersonation.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="e257b-119">Referencia</span><span class="sxs-lookup"><span data-stu-id="e257b-119">Reference</span></span>  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.ServiceModel.Description.PrincipalPermissionMode>  
  
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>  
  
 <xref:System.Security.Permissions.PrincipalPermissionAttribute>  
  
## <a name="related-sections"></a><span data-ttu-id="e257b-120">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="e257b-120">Related Sections</span></span>  
 [<span data-ttu-id="e257b-121">Autenticación</span><span class="sxs-lookup"><span data-stu-id="e257b-121">Authentication</span></span>](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)  
  
## <a name="see-also"></a><span data-ttu-id="e257b-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="e257b-122">See also</span></span>

- [<span data-ttu-id="e257b-123">Información general sobre seguridad</span><span class="sxs-lookup"><span data-stu-id="e257b-123">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)
- [<span data-ttu-id="e257b-124">Modelo de seguridad de Windows Server AppFabric</span><span class="sxs-lookup"><span data-stu-id="e257b-124">Security Model for Windows Server App Fabric</span></span>](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
