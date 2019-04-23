---
title: OperationBehaviorAttribute
ms.date: 03/30/2017
ms.assetid: 8c9b0755-9e83-411f-bdcb-61a586022797
ms.openlocfilehash: 79601308c66abe43dd5a7f72bd2a05b9d2346c2b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2019
ms.locfileid: "59975161"
---
# <a name="operationbehaviorattribute"></a><span data-ttu-id="97d50-102">OperationBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="97d50-102">OperationBehaviorAttribute</span></span>
<span data-ttu-id="97d50-103">OperationBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="97d50-103">OperationBehaviorAttribute</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97d50-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="97d50-104">Syntax</span></span>  
  
```csharp
class OperationBehaviorAttribute : Behavior  
{  
  boolean AutoDisposeParameters;  
  string Impersonation;  
  string ReleaseInstanceMode;  
  boolean TransactionAutoComplete;  
  boolean TransactionScopeRequired;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="97d50-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="97d50-105">Methods</span></span>  
 <span data-ttu-id="97d50-106">La clase OperationBehaviorAttribute no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="97d50-106">The OperationBehaviorAttribute class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="97d50-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="97d50-107">Properties</span></span>  
 <span data-ttu-id="97d50-108">La clase OperationBehaviorAttribute tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="97d50-108">The OperationBehaviorAttribute class has the following properties:</span></span>  
  
### <a name="autodisposeparameters"></a><span data-ttu-id="97d50-109">AutoDisposeParameters</span><span class="sxs-lookup"><span data-stu-id="97d50-109">AutoDisposeParameters</span></span>  
 <span data-ttu-id="97d50-110">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="97d50-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="97d50-111">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="97d50-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="97d50-112">El estado de la característica de eliminación automática para parámetros.</span><span class="sxs-lookup"><span data-stu-id="97d50-112">The state of the auto-dispose feature for parameters.</span></span>  
  
### <a name="impersonation"></a><span data-ttu-id="97d50-113">Suplantación</span><span class="sxs-lookup"><span data-stu-id="97d50-113">Impersonation</span></span>  
 <span data-ttu-id="97d50-114">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="97d50-114">Data type: string</span></span>  
  
 <span data-ttu-id="97d50-115">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="97d50-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="97d50-116">Indica el nivel de suplantación del llamador que la operación admite.</span><span class="sxs-lookup"><span data-stu-id="97d50-116">Indicates the level of caller impersonation that the operation supports.</span></span>  
  
### <a name="releaseinstancemode"></a><span data-ttu-id="97d50-117">ReleaseInstanceMode</span><span class="sxs-lookup"><span data-stu-id="97d50-117">ReleaseInstanceMode</span></span>  
 <span data-ttu-id="97d50-118">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="97d50-118">Data type: string</span></span>  
  
 <span data-ttu-id="97d50-119">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="97d50-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="97d50-120">Indica cuándo durante el curso de una invocación de la operación debe reciclarse el objeto.</span><span class="sxs-lookup"><span data-stu-id="97d50-120">Indicates when in the course of an operation invocation to recycle the object.</span></span>  
  
### <a name="transactionautocomplete"></a><span data-ttu-id="97d50-121">TransactionAutoComplete</span><span class="sxs-lookup"><span data-stu-id="97d50-121">TransactionAutoComplete</span></span>  
 <span data-ttu-id="97d50-122">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="97d50-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="97d50-123">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="97d50-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="97d50-124">Indica si confirmar automáticamente la transacción actual si no se produce ninguna excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="97d50-124">Indicates whether to automatically commit the current transaction if no unhandled exceptions occur.</span></span>  
  
### <a name="transactionscoperequired"></a><span data-ttu-id="97d50-125">TransactionScopeRequired</span><span class="sxs-lookup"><span data-stu-id="97d50-125">TransactionScopeRequired</span></span>  
 <span data-ttu-id="97d50-126">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="97d50-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="97d50-127">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="97d50-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="97d50-128">Indica si la operación requiere una transacción.</span><span class="sxs-lookup"><span data-stu-id="97d50-128">Indicates whether the operation requires a transaction.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97d50-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="97d50-129">Requirements</span></span>  
  
|<span data-ttu-id="97d50-130">MOF</span><span class="sxs-lookup"><span data-stu-id="97d50-130">MOF</span></span>|<span data-ttu-id="97d50-131">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="97d50-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="97d50-132">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="97d50-132">Namespace</span></span>|<span data-ttu-id="97d50-133">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="97d50-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="97d50-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="97d50-134">See also</span></span>

- <xref:System.ServiceModel.OperationBehaviorAttribute>
