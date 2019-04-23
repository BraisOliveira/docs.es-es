---
title: System.ServiceModel.Activation.WebHostServiceCloseFailed
ms.date: 03/30/2017
ms.assetid: 3cab9856-a5cf-4f0e-a0cb-89425e368f8e
ms.openlocfilehash: afe84db3d4df8914ff1ed001b064439d581ead89
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59085400"
---
# <a name="systemservicemodelactivationwebhostserviceclosefailed"></a><span data-ttu-id="64f0d-102">System.ServiceModel.Activation.WebHostServiceCloseFailed</span><span class="sxs-lookup"><span data-stu-id="64f0d-102">System.ServiceModel.Activation.WebHostServiceCloseFailed</span></span>
<span data-ttu-id="64f0d-103">Sucede cuando un servicio no se puede cerrar correctamente y se anula.</span><span class="sxs-lookup"><span data-stu-id="64f0d-103">Occurs when a service cannot be closed gracefully and is aborted.</span></span>  
  
## <a name="description"></a><span data-ttu-id="64f0d-104">Descripción</span><span class="sxs-lookup"><span data-stu-id="64f0d-104">Description</span></span>  
 <span data-ttu-id="64f0d-105">Este código de error solo aparece en el archivo de registro.</span><span class="sxs-lookup"><span data-stu-id="64f0d-105">This error code only appears in the log file.</span></span> <span data-ttu-id="64f0d-106">Suele indicar un error de programación, por ejemplo, cuando se intenta cerrar un servicio después de haber llamado ya a Abort.</span><span class="sxs-lookup"><span data-stu-id="64f0d-106">It usually indicates a programming error, for example, when you try to close a service after Abort has already been called.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="64f0d-107">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="64f0d-107">Troubleshooting</span></span>  
 <span data-ttu-id="64f0d-108">Compruebe el código fuente de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="64f0d-108">Check the application source code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64f0d-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="64f0d-109">See also</span></span>

- [<span data-ttu-id="64f0d-110">Traza</span><span class="sxs-lookup"><span data-stu-id="64f0d-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="64f0d-111">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="64f0d-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="64f0d-112">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="64f0d-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
