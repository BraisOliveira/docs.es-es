---
title: SymmetricSecurityBindingElement
ms.date: 03/30/2017
ms.assetid: b2e182b6-c041-4d80-a926-6058068d9f79
ms.openlocfilehash: f6effd533a205d0e8fd1421119e325f06b340dd1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61956720"
---
# <a name="symmetricsecuritybindingelement"></a><span data-ttu-id="1c8a3-102">SymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="1c8a3-102">SymmetricSecurityBindingElement</span></span>
<span data-ttu-id="1c8a3-103">SymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="1c8a3-103">SymmetricSecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c8a3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1c8a3-104">Syntax</span></span>  
  
```csharp
class SymmetricSecurityBindingElement : SecurityBindingElement  
{  
  string MessageProtectionOrder;  
  boolean RequireSignatureConfirmation;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="1c8a3-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="1c8a3-105">Methods</span></span>  
 <span data-ttu-id="1c8a3-106">La clase SymmetricSecurityBindingElement no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="1c8a3-106">The SymmetricSecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="1c8a3-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="1c8a3-107">Properties</span></span>  
 <span data-ttu-id="1c8a3-108">La clase SymmetricSecurityBindingElement tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="1c8a3-108">The SymmetricSecurityBindingElement class has the following properties:</span></span>  
  
### <a name="messageprotectionorder"></a><span data-ttu-id="1c8a3-109">MessageProtectionOrder</span><span class="sxs-lookup"><span data-stu-id="1c8a3-109">MessageProtectionOrder</span></span>  
 <span data-ttu-id="1c8a3-110">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="1c8a3-110">Data type: string</span></span>  
  
 <span data-ttu-id="1c8a3-111">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="1c8a3-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1c8a3-112">El orden de cifrado de mensajes y firma para este enlace.</span><span class="sxs-lookup"><span data-stu-id="1c8a3-112">The order of message encryption and signing for this binding.</span></span>  
  
### <a name="requiresignatureconfirmation"></a><span data-ttu-id="1c8a3-113">RequireSignatureConfirmation</span><span class="sxs-lookup"><span data-stu-id="1c8a3-113">RequireSignatureConfirmation</span></span>  
 <span data-ttu-id="1c8a3-114">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="1c8a3-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="1c8a3-115">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="1c8a3-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1c8a3-116">Si el enlace requiere la confirmación de la firma.</span><span class="sxs-lookup"><span data-stu-id="1c8a3-116">Whether the binding requires signature confirmation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c8a3-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1c8a3-117">Requirements</span></span>  
  
|<span data-ttu-id="1c8a3-118">MOF</span><span class="sxs-lookup"><span data-stu-id="1c8a3-118">MOF</span></span>|<span data-ttu-id="1c8a3-119">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="1c8a3-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="1c8a3-120">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="1c8a3-120">Namespace</span></span>|<span data-ttu-id="1c8a3-121">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="1c8a3-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1c8a3-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="1c8a3-122">See also</span></span>

- <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>
