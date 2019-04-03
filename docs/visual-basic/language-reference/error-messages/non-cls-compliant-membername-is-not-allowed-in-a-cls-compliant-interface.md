---
title: <membername> no compatible con CLS no se permite en una interfaz compatible con CLS
ms.date: 07/20/2015
f1_keywords:
- bc40033
- vbc40033
helpviewer_keywords:
- BC40033
ms.assetid: 060c4b08-798e-40f1-94cf-c05c524f1b8a
ms.openlocfilehash: dbffe2bd196e798b90104aebb74269387660c794
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58840463"
---
# <a name="non-cls-compliant-membername-is-not-allowed-in-a-cls-compliant-interface"></a><span data-ttu-id="ddfbf-102">No compatible con CLS \<membername > no se permite en una interfaz conforme a CLS</span><span class="sxs-lookup"><span data-stu-id="ddfbf-102">Non-CLS-compliant \<membername> is not allowed in a CLS-compliant interface</span></span>
<span data-ttu-id="ddfbf-103">Una propiedad, procedimiento o evento en una interfaz se marca como `<CLSCompliant(True)>` cuando la propia interfaz está marcada como `<CLSCompliant(False)>` o no está marcada.</span><span class="sxs-lookup"><span data-stu-id="ddfbf-103">A property, procedure, or event in an interface is marked as `<CLSCompliant(True)>` when the interface itself is marked as `<CLSCompliant(False)>` or is not marked.</span></span>  
  
 <span data-ttu-id="ddfbf-104">Para una interfaz sea compatible con la [independencia del lenguaje y componentes independientes del lenguaje](../../../standard/language-independence-and-language-independent-components.md) (CLS), deben ser compatible con todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="ddfbf-104">For an interface to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), all its members must be compliant.</span></span>  
  
 <span data-ttu-id="ddfbf-105">Al aplicar <xref:System.CLSCompliantAttribute> a un elemento de programación, establezca el parámetro `isCompliant` del atributo en `True` o `False` para indicar conformidad o disconformidad.</span><span class="sxs-lookup"><span data-stu-id="ddfbf-105">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="ddfbf-106">No hay ningún valor predeterminado para este parámetro, por lo que debe proporcionar uno.</span><span class="sxs-lookup"><span data-stu-id="ddfbf-106">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="ddfbf-107">Si no se aplica <xref:System.CLSCompliantAttribute> a un elemento, se considera que no es conforme.</span><span class="sxs-lookup"><span data-stu-id="ddfbf-107">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="ddfbf-108">De forma predeterminada, este mensaje es una advertencia.</span><span class="sxs-lookup"><span data-stu-id="ddfbf-108">By default, this message is a warning.</span></span> <span data-ttu-id="ddfbf-109">Para obtener más información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="ddfbf-109">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="ddfbf-110">**Identificador de error:** BC40033</span><span class="sxs-lookup"><span data-stu-id="ddfbf-110">**Error ID:** BC40033</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ddfbf-111">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="ddfbf-111">To correct this error</span></span>  
  
-   <span data-ttu-id="ddfbf-112">Si requiere conformidad con CLS y tiene control sobre el código fuente de interfaz, marque la interfaz como `<CLSCompliant(True)>` si todos sus miembros son conformes.</span><span class="sxs-lookup"><span data-stu-id="ddfbf-112">If you require CLS compliance and have control over the interface source code, mark the interface as `<CLSCompliant(True)>` if all its members are compliant.</span></span>  
  
-   <span data-ttu-id="ddfbf-113">Si requiere conformidad con CLS y no tiene control sobre el código fuente de interfaz, o si no cumple las condiciones ser compatible, defina a este miembro dentro de una interfaz diferente.</span><span class="sxs-lookup"><span data-stu-id="ddfbf-113">If you require CLS compliance and do not have control over the interface source code, or if it does not qualify to be compliant, define this member within a different interface.</span></span>  
  
-   <span data-ttu-id="ddfbf-114">Si necesita que este miembro permanezca dentro de su interfaz actual, quite el <xref:System.CLSCompliantAttribute> de su definición o márquelo como `<CLSCompliant(False)>`.</span><span class="sxs-lookup"><span data-stu-id="ddfbf-114">If you require that this member remain within its current interface, remove the <xref:System.CLSCompliantAttribute> from its definition or mark it as `<CLSCompliant(False)>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddfbf-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="ddfbf-115">See also</span></span>

- [<span data-ttu-id="ddfbf-116">Interface (instrucción)</span><span class="sxs-lookup"><span data-stu-id="ddfbf-116">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)
