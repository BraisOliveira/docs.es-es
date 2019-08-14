---
title: Cómo compilar aplicaciones ASP.NET con reconocimiento de mediante la autenticación basada en formularios
ms.date: 03/30/2017
ms.assetid: 98a3e029-1a9b-4e0c-b5d0-29d3f23f5b15
author: BrucePerlerMS
ms.openlocfilehash: 75db96a621d7863ef445efb24814111b34da6960
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2019
ms.locfileid: "68971834"
---
# <a name="how-to-build-claims-aware-aspnet-application-using-forms-based-authentication"></a><span data-ttu-id="42079-102">Cómo compilar aplicaciones ASP.NET con reconocimiento de mediante la autenticación basada en formularios</span><span class="sxs-lookup"><span data-stu-id="42079-102">How To: Build Claims-Aware ASP.NET Application Using Forms-Based Authentication</span></span>

## <a name="applies-to"></a><span data-ttu-id="42079-103">Se aplica a</span><span class="sxs-lookup"><span data-stu-id="42079-103">Applies To</span></span>

- <span data-ttu-id="42079-104">Microsoft® Windows® Identity Foundation (WIF)</span><span class="sxs-lookup"><span data-stu-id="42079-104">Microsoft® Windows® Identity Foundation (WIF)</span></span>

- <span data-ttu-id="42079-105">Formularios Web Forms ASP.NET®</span><span class="sxs-lookup"><span data-stu-id="42079-105">ASP.NET® Web Forms</span></span>

## <a name="summary"></a><span data-ttu-id="42079-106">Resumen</span><span class="sxs-lookup"><span data-stu-id="42079-106">Summary</span></span>

<span data-ttu-id="42079-107">Este tema de procedimientos proporciona procedimientos paso a paso para crear una sencilla aplicación de formularios Web Forms ASP.NET para notificaciones que usa la autenticación de formularios.</span><span class="sxs-lookup"><span data-stu-id="42079-107">This How-To provides detailed step-by-step procedures for creating a simple claims-aware ASP.NET Web Forms application that uses Forms authentication.</span></span> <span data-ttu-id="42079-108">También proporciona instrucciones para probar la aplicación a fin de comprobar que las notificaciones se presentan cuando un usuario inicia sesión con la autenticación de formularios.</span><span class="sxs-lookup"><span data-stu-id="42079-108">It also provides instructions for how to test the application to verify that claims are presented when a user signs in with Forms authentication.</span></span>

## <a name="contents"></a><span data-ttu-id="42079-109">Contenido</span><span class="sxs-lookup"><span data-stu-id="42079-109">Contents</span></span>

- <span data-ttu-id="42079-110">Objetivos</span><span class="sxs-lookup"><span data-stu-id="42079-110">Objectives</span></span>

- <span data-ttu-id="42079-111">Información general</span><span class="sxs-lookup"><span data-stu-id="42079-111">Overview</span></span>

- <span data-ttu-id="42079-112">Resumen de pasos</span><span class="sxs-lookup"><span data-stu-id="42079-112">Summary of Steps</span></span>

- <span data-ttu-id="42079-113">Paso 1: Crear una aplicación sencilla de formularios Web Forms ASP.NET</span><span class="sxs-lookup"><span data-stu-id="42079-113">Step 1 – Create a Simple ASP.NET Web Forms Application</span></span>

- <span data-ttu-id="42079-114">Paso 2: Configurar la aplicación de formularios Web Forms ASP.NET para notificaciones mediante la autenticación de formularios</span><span class="sxs-lookup"><span data-stu-id="42079-114">Step 2 – Configure ASP.NET Web Forms Application for Claims Using Forms Authentication</span></span>

- <span data-ttu-id="42079-115">Paso 3: Probar la solución</span><span class="sxs-lookup"><span data-stu-id="42079-115">Step 3 – Test Your Solution</span></span>

## <a name="objectives"></a><span data-ttu-id="42079-116">Objetivos</span><span class="sxs-lookup"><span data-stu-id="42079-116">Objectives</span></span>

- <span data-ttu-id="42079-117">Configurar una aplicación de formularios Web Forms ASP.NET para notificaciones mediante la autenticación de formularios</span><span class="sxs-lookup"><span data-stu-id="42079-117">Configure an ASP.NET Web Forms application for claims using Forms authentication</span></span>

- <span data-ttu-id="42079-118">Probar la aplicación de formularios Web Forms ASP.NET para ver si funciona correctamente</span><span class="sxs-lookup"><span data-stu-id="42079-118">Test the ASP.NET Web Forms application to see if it is working properly</span></span>

## <a name="overview"></a><span data-ttu-id="42079-119">Información general</span><span class="sxs-lookup"><span data-stu-id="42079-119">Overview</span></span>

<span data-ttu-id="42079-120">En .NET 4.5, WIF y su autorización basada en notificaciones se han incluido como parte integral del marco.</span><span class="sxs-lookup"><span data-stu-id="42079-120">In .NET 4.5, WIF and its claims-based authorization have been included as an integral part of the Framework.</span></span> <span data-ttu-id="42079-121">Anteriormente, si quería notificaciones de un usuario de ASP.NET, tenía que instalar WIF y, después, convertir las interfaces a objetos de entidad de seguridad como `Thread.CurrentPrincipal` o `HttpContext.Current.User`.</span><span class="sxs-lookup"><span data-stu-id="42079-121">Previously, if you wanted claims from an ASP.NET user, you were required to install WIF, and then cast interfaces to Principal objects such as `Thread.CurrentPrincipal` or `HttpContext.Current.User`.</span></span> <span data-ttu-id="42079-122">Ahora, estos objetos de entidad de seguridad sirven las notificaciones automáticamente.</span><span class="sxs-lookup"><span data-stu-id="42079-122">Now, claims are served automatically by these Principal objects.</span></span>

<span data-ttu-id="42079-123">La autenticación de formularios se ha beneficiado de la inclusión de WIF en .NET 4.5, ya que todos los usuarios autenticados mediante formularios automáticamente tienen notificaciones asociadas.</span><span class="sxs-lookup"><span data-stu-id="42079-123">Forms authentication has benefited from WIF’s inclusion in .NET 4.5 because all users authenticated by Forms automatically have claims associated with them.</span></span> <span data-ttu-id="42079-124">Puede empezar a usar estas notificaciones inmediatamente en una aplicación de ASP.NET que use la autenticación de formularios, como se muestra en este tema de procedimientos.</span><span class="sxs-lookup"><span data-stu-id="42079-124">You can begin using these claims immediately in an ASP.NET application that uses Forms authentication, as this How-To demonstrates.</span></span>

## <a name="summary-of-steps"></a><span data-ttu-id="42079-125">Resumen de pasos</span><span class="sxs-lookup"><span data-stu-id="42079-125">Summary of Steps</span></span>

- <span data-ttu-id="42079-126">Paso 1: Crear una aplicación sencilla de formularios Web Forms ASP.NET</span><span class="sxs-lookup"><span data-stu-id="42079-126">Step 1 – Create a Simple ASP.NET Web Forms Application</span></span>

- <span data-ttu-id="42079-127">Paso 2: Configurar la aplicación de formularios Web Forms ASP.NET para notificaciones mediante la autenticación de formularios</span><span class="sxs-lookup"><span data-stu-id="42079-127">Step 2 – Configure ASP.NET Web Forms Application for Claims Using Forms Authentication</span></span>

- <span data-ttu-id="42079-128">Paso 3: Probar la solución</span><span class="sxs-lookup"><span data-stu-id="42079-128">Step 3 – Test Your Solution</span></span>

## <a name="step-1--create-a-simple-aspnet-web-forms-application"></a><span data-ttu-id="42079-129">Paso 1: Crear una aplicación sencilla de formularios Web Forms ASP.NET</span><span class="sxs-lookup"><span data-stu-id="42079-129">Step 1 – Create a Simple ASP.NET Web Forms Application</span></span>

<span data-ttu-id="42079-130">En este paso creará una aplicación de formularios Web Forms ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="42079-130">In this step, you will create a new ASP.NET Web Forms application.</span></span>

### <a name="to-create-a-simple-aspnet-application"></a><span data-ttu-id="42079-131">Para crear una aplicación de ASP.NET sencilla</span><span class="sxs-lookup"><span data-stu-id="42079-131">To create a simple ASP.NET application</span></span>

1. <span data-ttu-id="42079-132">Inicie Visual Studio y haga clic en **Archivo**, **Nuevo** y, luego, en **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="42079-132">Start Visual Studio and click **File**, **New**, and then **Project**.</span></span>

2. <span data-ttu-id="42079-133">En la ventana **Nuevo proyecto**, haga clic en **Aplicación de formularios Web Forms ASP.NET**.</span><span class="sxs-lookup"><span data-stu-id="42079-133">In the **New Project** window, click **ASP.NET Web Forms Application**.</span></span>

3. <span data-ttu-id="42079-134">En **Nombre**, escriba `TestApp` y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="42079-134">In **Name**, enter `TestApp` and press **OK**.</span></span>

## <a name="step-2--configure-aspnet-web-forms-application-for-claims-using-forms-authentication"></a><span data-ttu-id="42079-135">Paso 2: Configurar la aplicación de formularios Web Forms ASP.NET para notificaciones mediante la autenticación de formularios</span><span class="sxs-lookup"><span data-stu-id="42079-135">Step 2 – Configure ASP.NET Web Forms Application for Claims Using Forms Authentication</span></span>

<span data-ttu-id="42079-136">En este paso se agrega una entrada de configuración al archivo de configuración *Web.config* y se edita el archivo *Default.aspx* para que muestre la información de notificaciones de una cuenta.</span><span class="sxs-lookup"><span data-stu-id="42079-136">In this step you will add a configuration entry to the *Web.config* configuration file and edit the *Default.aspx* file to display claims information for an account.</span></span>

### <a name="to-configure-aspnet-application-for-claims-using-forms-authentication"></a><span data-ttu-id="42079-137">Para configurar la aplicación ASP.NET para notificaciones mediante la autenticación de formularios</span><span class="sxs-lookup"><span data-stu-id="42079-137">To configure ASP.NET application for claims using Forms authentication</span></span>

1. <span data-ttu-id="42079-138">En el archivo *Default.aspx*, reemplace el marcado existente por el siguiente:</span><span class="sxs-lookup"><span data-stu-id="42079-138">In the *Default.aspx* file, replace the existing markup with the following:</span></span>

    ```aspx
    <%@ Page Title="Home Page" Language="C#" MasterPageFile="~/Site.Master" AutoEventWireup="true" CodeBehind="Default.aspx.cs" Inherits="TestApp._Default" %>

    <asp:Content runat="server" ID="BodyContent" ContentPlaceHolderID="MainContent">
        <p>
            This page displays the claims associated with a Forms authenticated user.
        </p>
        <h3>Your Claims</h3>
        <p>
            <asp:GridView ID="ClaimsGridView" runat="server" CellPadding="3">
                <AlternatingRowStyle BackColor="White" />
                <HeaderStyle BackColor="#7AC0DA" ForeColor="White" />
            </asp:GridView>
        </p>
    </asp:Content>
    ```

    <span data-ttu-id="42079-139">Este paso agrega un control GridView a la página *Default.aspx* que se va a rellenar con las notificaciones recuperadas de la autenticación de formularios.</span><span class="sxs-lookup"><span data-stu-id="42079-139">This step adds a GridView control to your *Default.aspx* page that will be populated with the claims retrieved from Forms authentication.</span></span>

2. <span data-ttu-id="42079-140">Guarde el archivo *Default.aspx* y abra su archivo de código subyacente denominado *Default.aspx.cs*.</span><span class="sxs-lookup"><span data-stu-id="42079-140">Save the *Default.aspx* file, then open its code-behind file named *Default.aspx.cs*.</span></span> <span data-ttu-id="42079-141">Reemplace el código existente por el siguiente:</span><span class="sxs-lookup"><span data-stu-id="42079-141">Replace the existing code with the following:</span></span>

    ```csharp
    using System;
    using System.Web.UI;
    using System.Security.Claims;

    namespace TestApp
    {
        public partial class _Default : Page
        {
            protected void Page_Load(object sender, EventArgs e)
            {
                ClaimsPrincipal claimsPrincipal = Page.User as ClaimsPrincipal;

                if (claimsPrincipal != null)
                {
                    this.ClaimsGridView.DataSource = claimsPrincipal.Claims;
                    this.ClaimsGridView.DataBind();
                }
            }
        }
    }
    ```

    <span data-ttu-id="42079-142">El código anterior muestra notificaciones sobre un usuario autenticado, incluidos los usuarios identificados mediante la autenticación de formularios.</span><span class="sxs-lookup"><span data-stu-id="42079-142">The above code will display claims about an authenticated user, including users identified by Forms authentication.</span></span>

## <a name="step-3--test-your-solution"></a><span data-ttu-id="42079-143">Paso 3: Probar la solución</span><span class="sxs-lookup"><span data-stu-id="42079-143">Step 3 – Test Your Solution</span></span>

<span data-ttu-id="42079-144">En este paso se prueba la aplicación de formularios Web Forms ASP.NET y se comprueba que se presentan notificaciones cuando un usuario inicia sesión con la autenticación de formularios.</span><span class="sxs-lookup"><span data-stu-id="42079-144">In this step you will test your ASP.NET Web Forms application, and verify that claims are presented when a user signs in with Forms authentication.</span></span>

### <a name="to-test-your-aspnet-web-forms-application-for-claims-using-forms-authentication"></a><span data-ttu-id="42079-145">Para probar la aplicación de formularios Web Forms ASP.NET para notificaciones mediante la autenticación de formularios</span><span class="sxs-lookup"><span data-stu-id="42079-145">To test your ASP.NET Web Forms application for claims using Forms authentication</span></span>

1. <span data-ttu-id="42079-146">Presione **F5** para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="42079-146">Press **F5** to build and run the application.</span></span> <span data-ttu-id="42079-147">Debe aparecer *Default.aspx*, que tiene los vínculos **Registrarse** e **Iniciar sesión** en la parte superior derecha de la página.</span><span class="sxs-lookup"><span data-stu-id="42079-147">You should be presented with *Default.aspx*, which has **Register** and **Log in** links in the top right of the page.</span></span> <span data-ttu-id="42079-148">Haga clic en **Registrarse**.</span><span class="sxs-lookup"><span data-stu-id="42079-148">Click **Register**.</span></span>

2. <span data-ttu-id="42079-149">En la página **Registrarse**, cree una cuenta de usuario y luego haga clic en **Registrarse**.</span><span class="sxs-lookup"><span data-stu-id="42079-149">On the **Register** page, create a user account, and then click **Register**.</span></span> <span data-ttu-id="42079-150">Se crea la cuenta mediante la autenticación de formularios y la sesión se inicia automáticamente.</span><span class="sxs-lookup"><span data-stu-id="42079-150">Your account will be created using Forms authentication, and you will be automatically signed in.</span></span>

3. <span data-ttu-id="42079-151">Después de que se le haya redirigido a la página principal, debería ver una tabla debajo del título **Sus notificaciones** con la información de notificaciones **Emisor**, **OriginalIssuer**, **Tipo**, **Valor** y **ValueType** sobre la cuenta.</span><span class="sxs-lookup"><span data-stu-id="42079-151">After you have been redirected to the home page, you should see a table beneath the **Your Claims** heading that includes the **Issuer**, **OriginalIssuer**, **Type**, **Value**, and **ValueType** claims information about your account.</span></span>
