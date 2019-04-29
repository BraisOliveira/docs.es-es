---
title: Sección de configuración de Windows Forms
ms.date: 04/07/2017
ms.assetid: 6eb142d5-fc98-40e2-9d90-84733f2a27ba
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bbb2c4157ba702182056c98c959a60569e8c3d1e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61786417"
---
# <a name="windows-forms-configuration-section"></a><span data-ttu-id="28464-102">Sección de configuración de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="28464-102">Windows Forms Configuration Section</span></span>
<span data-ttu-id="28464-103">Las opciones de configuración de Windows Forms permiten a una aplicación de Windows Forms almacenar y recuperar información sobre configuraciones de aplicaciones personalizadas, como la compatibilidad multimonitor, la compatibilidad con valores altos de PPP y otras opciones de configuración predefinidos.</span><span class="sxs-lookup"><span data-stu-id="28464-103">Windows Forms configuration settings allow a Windows Forms app to store and retrieve information about customized application settings such as multi-monitor support, high DPI support, and other predefined configuration settings.</span></span>

<span data-ttu-id="28464-104">Las opciones de configuración de aplicaciones de Windows Forms se almacenan en un elemento `System.Windows.Forms.ApplicationConfigurationSection` del archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="28464-104">Windows Forms application configuration settings are stored in an application configuration file's `System.Windows.Forms.ApplicationConfigurationSection` element.</span></span>

## <a name="syntax"></a><span data-ttu-id="28464-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="28464-105">Syntax</span></span>

```xml
<configuration>
  <System.Windows.Forms.ApplicationConfigurationSection>
  ...
  </System.Windows.Forms.ApplicationConfigurationSection>
</configuration>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="28464-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="28464-106">Attributes and elements</span></span>

<span data-ttu-id="28464-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="28464-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="28464-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="28464-108">Attributes</span></span>

<span data-ttu-id="28464-109">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="28464-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="28464-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="28464-110">Child elements</span></span>

<span data-ttu-id="28464-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="28464-111">Element</span></span>  |<span data-ttu-id="28464-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="28464-112">Description</span></span> |
---------|---------|
[`<add>`](../../../../../docs/framework/configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md) | <span data-ttu-id="28464-113">Agrega una clave de valores de configuración con un valor específico.</span><span class="sxs-lookup"><span data-stu-id="28464-113">Adds a configuration setting key with a specified value</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="28464-114">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="28464-114">Parent elements</span></span>

<span data-ttu-id="28464-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="28464-115">Element</span></span>  |<span data-ttu-id="28464-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="28464-116">Description</span></span> |
---------|---------|
[<span data-ttu-id="28464-117">\<configuration></span><span class="sxs-lookup"><span data-stu-id="28464-117">\<configuration></span></span>](../configuration-element.md) | <span data-ttu-id="28464-118">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="28464-118">The root element in every configuration file used by the common language runtime and Windows Forms applications</span></span> |

## <a name="remarks"></a><span data-ttu-id="28464-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="28464-119">Remarks</span></span>

<span data-ttu-id="28464-120">A partir de .NET Framework 4.7, el elemento `<System.Windows.Forms.ApplicationConfigurationSection>` permite configurar las aplicaciones de Windows Forms para aprovechar las características agregadas en versiones recientes de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="28464-120">Starting with the .NET Framework 4.7, the `<System.Windows.Forms.ApplicationConfigurationSection>` element allows you to configure Windows Forms applications to take advantage of features added in recent releases of the .NET Framework.</span></span> 

<span data-ttu-id="28464-121">El elemento `<System.Windows.Forms.ApplicationConfigurationSection>` puede incluir uno o varios elementos [`<add>`](../../../../../docs/framework/configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md) secundarios, y cada uno de ellos define un valor de configuración específico.</span><span class="sxs-lookup"><span data-stu-id="28464-121">The `<System.Windows.Forms.ApplicationConfigurationSection>` element can include one or more child [`<add>`](../../../../../docs/framework/configure-apps/file-schema/winforms/windows-forms-add-configuration-element.md) elements, each of which defines a specific configuration setting.</span></span>

## <a name="see-also"></a><span data-ttu-id="28464-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="28464-122">See also</span></span>

- [<span data-ttu-id="28464-123">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="28464-123">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="28464-124">Compatibilidad con valores altos de PPP en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="28464-124">High DPI Support in Windows Forms</span></span>](../../../../../docs/framework/winforms/high-dpi-support-in-windows-forms.md)
