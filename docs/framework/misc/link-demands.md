---
title: Peticiones de vínculos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security [.NET Framework], demands
- demanded permissions
- permissions [.NET Framework], demands
- granting permissions, demands
- code access security, demands
- user demands for permission
- caller security checks
- link demands
ms.assetid: a33fd5f9-2de9-4653-a4f0-d9df25082c4d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2ba3172b1a82c0a9f624a49eb63a193dd29faac1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61750740"
---
# <a name="link-demands"></a><span data-ttu-id="a5bb6-102">Peticiones de vínculos</span><span class="sxs-lookup"><span data-stu-id="a5bb6-102">Link Demands</span></span>
[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
 <span data-ttu-id="a5bb6-103">Una petición de vínculo hace que se produzca una comprobación de seguridad durante la compilación Just-In-Time y comprueba solo el ensamblado de llamada inmediato del código.</span><span class="sxs-lookup"><span data-stu-id="a5bb6-103">A link demand causes a security check during just-in-time compilation and checks only the immediate calling assembly of your code.</span></span> <span data-ttu-id="a5bb6-104">La vinculación se produce cuando el código se enlaza a una referencia de tipo, incluidas las referencias del puntero de función y las llamadas a métodos.</span><span class="sxs-lookup"><span data-stu-id="a5bb6-104">Linking occurs when your code is bound to a type reference, including function pointer references and method calls.</span></span> <span data-ttu-id="a5bb6-105">Si el ensamblado de llamada no tiene permisos suficientes para vincularse al código, no se permitirá el vínculo y se producirá una excepción en tiempo de ejecución cuando se cargue y ejecute el código.</span><span class="sxs-lookup"><span data-stu-id="a5bb6-105">If the calling assembly does not have sufficient permission to link to your code, the link is not allowed and a runtime exception is thrown when the code is loaded and run.</span></span> <span data-ttu-id="a5bb6-106">Las peticiones de vínculo pueden reemplazarse en las clases que heredan de su código.</span><span class="sxs-lookup"><span data-stu-id="a5bb6-106">Link demands can be overridden in classes that inherit from your code.</span></span>  
  
 <span data-ttu-id="a5bb6-107">Tenga en cuenta que no se efectúa ningún recorrido de pila completo con este tipo de petición y que el código sigue siendo vulnerable a ataques.</span><span class="sxs-lookup"><span data-stu-id="a5bb6-107">Note that a full stack walk is not performed with this type of demand and that your code is still susceptible to luring attacks.</span></span> <span data-ttu-id="a5bb6-108">Por ejemplo, si un método en el ensamblado A está protegido por una petición de vínculo, un llamador directo del ensamblado B se evalúa según los permisos del ensamblado B.  Sin embargo, la petición de vínculo no evaluará un método del ensamblado C si llama indirectamente al método del ensamblado A con el método del ensamblado B. La petición de vínculo se especifica que solo los permisos directos en el ensamblado de llamada inmediato deben poseer un vínculo al código.</span><span class="sxs-lookup"><span data-stu-id="a5bb6-108">For example, if a method in assembly A is protected by a link demand, a direct caller in assembly B is evaluated based on the permissions of Assembly B.  However, the link demand will not evaluate a method in assembly C if it indirectly calls the method in assembly A using the method in assembly B. The link demand specifies only the permissions direct callers in the immediate calling assembly must have to link to your code.</span></span> <span data-ttu-id="a5bb6-109">No especifica los permisos que deben tener todos los llamadores para ejecutar el código.</span><span class="sxs-lookup"><span data-stu-id="a5bb6-109">It does not specify the permissions all callers must have to run your code.</span></span>  
  
 <span data-ttu-id="a5bb6-110">Los modificadores de recorrido de pila <xref:System.Security.CodeAccessPermission.Assert%2A>, <xref:System.Security.CodeAccessPermission.Deny%2A> y <xref:System.Security.CodeAccessPermission.PermitOnly%2A> no afectan a la evaluación de las peticiones de vínculo.</span><span class="sxs-lookup"><span data-stu-id="a5bb6-110">The <xref:System.Security.CodeAccessPermission.Assert%2A>, <xref:System.Security.CodeAccessPermission.Deny%2A>, and <xref:System.Security.CodeAccessPermission.PermitOnly%2A> stack walk modifiers do not affect the evaluation of link demands.</span></span>  <span data-ttu-id="a5bb6-111">Dado que las peticiones de vínculo no efectúan ningún recorrido de pila, los modificadores de recorrido de pila no tienen ningún efecto sobre las peticiones de vínculo.</span><span class="sxs-lookup"><span data-stu-id="a5bb6-111">Because link demands do not perform a stack walk, the stack walk modifiers have no effect on link demands.</span></span>  
  
 <span data-ttu-id="a5bb6-112">Si se tiene acceso a un método protegido por una petición de vínculo a través de [reflexión](../../../docs/framework/reflection-and-codedom/reflection.md), a continuación, una petición de vínculo comprueba el llamador inmediato del código tiene acceso a través de reflexión.</span><span class="sxs-lookup"><span data-stu-id="a5bb6-112">If a method protected by a link demand is accessed through [Reflection](../../../docs/framework/reflection-and-codedom/reflection.md), then a link demand checks the immediate caller of the code accessed through reflection.</span></span> <span data-ttu-id="a5bb6-113">Esto es válido tanto para la detección de métodos como para la invocación de métodos efectuados por reflexión.</span><span class="sxs-lookup"><span data-stu-id="a5bb6-113">This is true both for method discovery and for method invocation performed using reflection.</span></span> <span data-ttu-id="a5bb6-114">Por ejemplo, suponga que el código usa la reflexión para devolver un <xref:System.Reflection.MethodInfo> de objeto que representa un método protegido por una petición de vínculo y, a continuación, pasa que **MethodInfo** objeto a otro código que usa el objeto para invocar el método original.</span><span class="sxs-lookup"><span data-stu-id="a5bb6-114">For example, suppose code uses reflection to return a <xref:System.Reflection.MethodInfo> object representing a method protected by a link demand and then passes that **MethodInfo** object to some other code that uses the object to invoke the original method.</span></span> <span data-ttu-id="a5bb6-115">En este caso, la comprobación de la petición de vínculo tiene lugar dos veces: una vez para el código que devuelve el **MethodInfo** objeto y una vez para el código que lo invoca.</span><span class="sxs-lookup"><span data-stu-id="a5bb6-115">In this case the link demand check occurs twice: once for the code that returns the **MethodInfo** object and once for the code that invokes it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a5bb6-116">Una petición de vínculo efectuada en un constructor de clases estáticas no protege el constructor, puesto que el sistema llama a los constructores estáticos, fuera de la ruta de acceso de ejecución del código de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a5bb6-116">A link demand performed on a static class constructor does not protect the constructor because static constructors are called by the system, outside the application's code execution path.</span></span> <span data-ttu-id="a5bb6-117">Como resultado, al aplicar una petición de vínculo a toda una clase, no puede proteger el acceso a un constructor estático, aunque proteja el resto de la clase.</span><span class="sxs-lookup"><span data-stu-id="a5bb6-117">As a result, when a link demand is applied to an entire class, it cannot protect access to a static constructor, although it does protect the rest of the class.</span></span>  
  
 <span data-ttu-id="a5bb6-118">El siguiente fragmento de código especifica de manera declarativa que cualquier código vinculado al método `ReadData` debe tener el permiso `CustomPermission`.</span><span class="sxs-lookup"><span data-stu-id="a5bb6-118">The following code fragment declaratively specifies that any code linking to the `ReadData` method must have the `CustomPermission` permission.</span></span> <span data-ttu-id="a5bb6-119">Este permiso es un permiso personalizado hipotético y no existe en .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a5bb6-119">This permission is a hypothetical custom permission and does not exist in the .NET Framework.</span></span> <span data-ttu-id="a5bb6-120">La petición se realiza pasando un **SecurityAction.LinkDemand** marca a la `CustomPermissionAttribute`.</span><span class="sxs-lookup"><span data-stu-id="a5bb6-120">The demand is made by passing a **SecurityAction.LinkDemand** flag to the `CustomPermissionAttribute`.</span></span>  
  
```vb  
<CustomPermissionAttribute(SecurityAction.LinkDemand)> _  
Public Shared Function ReadData() As String  
    ' Access a custom resource.  
End Function    
```  
  
```csharp  
[CustomPermissionAttribute(SecurityAction.LinkDemand)]  
public static string ReadData()  
{  
    // Access a custom resource.  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="a5bb6-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="a5bb6-121">See also</span></span>

- [<span data-ttu-id="a5bb6-122">Atributos</span><span class="sxs-lookup"><span data-stu-id="a5bb6-122">Attributes</span></span>](../../../docs/standard/attributes/index.md)
- [<span data-ttu-id="a5bb6-123">Seguridad de acceso del código</span><span class="sxs-lookup"><span data-stu-id="a5bb6-123">Code Access Security</span></span>](../../../docs/framework/misc/code-access-security.md)
