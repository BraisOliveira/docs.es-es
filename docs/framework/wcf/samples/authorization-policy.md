---
title: Directiva de autorización
ms.date: 03/30/2017
ms.assetid: 1db325ec-85be-47d0-8b6e-3ba2fdf3dda0
ms.openlocfilehash: 50e868645d7e7ccbcf4be697f8bdb1814dd90e9c
ms.sourcegitcommit: 89fcad7e816c12eb1299128481183f01c73f2c07
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/24/2019
ms.locfileid: "63807972"
---
# <a name="authorization-policy"></a><span data-ttu-id="1ec44-102">Directiva de autorización</span><span class="sxs-lookup"><span data-stu-id="1ec44-102">Authorization Policy</span></span>

<span data-ttu-id="1ec44-103">Este ejemplo muestra cómo implementar una directiva de autorización de notificación personalizada y un administrador de autorización de servicio personalizado asociado.</span><span class="sxs-lookup"><span data-stu-id="1ec44-103">This sample demonstrates how to implement a custom claim authorization policy and an associated custom service authorization manager.</span></span> <span data-ttu-id="1ec44-104">Esto es útil cuando el servicio realiza las comprobaciones de acceso basadas en las notificaciones para operaciones de servicio y antes de las comprobaciones de acceso, concede ciertos derechos al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="1ec44-104">This is useful when the service makes claim-based access checks to service operations and prior to the access checks, grants the caller certain rights.</span></span> <span data-ttu-id="1ec44-105">Este ejemplo muestra el proceso de agregar las notificaciones así como el proceso para hacer una comprobación de acceso con el conjunto finalizado de notificaciones.</span><span class="sxs-lookup"><span data-stu-id="1ec44-105">This sample shows both the process of adding claims as well as the process for doing an access check against the finalized set of claims.</span></span> <span data-ttu-id="1ec44-106">Todos los mensajes de la aplicación entre el cliente y el servidor se firman y se cifran.</span><span class="sxs-lookup"><span data-stu-id="1ec44-106">All application messages between the client and server are signed and encrypted.</span></span> <span data-ttu-id="1ec44-107">De forma predeterminada, con el enlace `wsHttpBinding`, se utiliza un nombre de usuario y una contraseña proporcionadas por el cliente para iniciar sesión con una cuenta válida de Windows NT.</span><span class="sxs-lookup"><span data-stu-id="1ec44-107">By default with the `wsHttpBinding` binding, a username and password supplied by the client are used to logon to a valid Windows NT account.</span></span> <span data-ttu-id="1ec44-108">Este ejemplo muestra cómo utilizar un <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> personalizado para autenticar el cliente.</span><span class="sxs-lookup"><span data-stu-id="1ec44-108">This sample demonstrates how to utilize a custom <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> to authenticate the client.</span></span> <span data-ttu-id="1ec44-109">Además, este ejemplo muestra el cliente que se autentica con el servicio utilizando un certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="1ec44-109">In addition this sample shows the client authenticating to the service using an X.509 certificate.</span></span> <span data-ttu-id="1ec44-110">Este ejemplo muestra una implementación de <xref:System.IdentityModel.Policy.IAuthorizationPolicy> y <xref:System.ServiceModel.ServiceAuthorizationManager>, que entre ellos conceden acceso a métodos concretos del servicio para usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="1ec44-110">This sample shows an implementation of <xref:System.IdentityModel.Policy.IAuthorizationPolicy> and <xref:System.ServiceModel.ServiceAuthorizationManager>, which between them grant access to specific methods of the service for specific users.</span></span> <span data-ttu-id="1ec44-111">En este ejemplo se basa en el [nombre de usuario de seguridad de mensaje](../../../../docs/framework/wcf/samples/message-security-user-name.md), pero se muestra cómo realizar una transformación de notificaciones anteriores a la <xref:System.ServiceModel.ServiceAuthorizationManager> que se llama.</span><span class="sxs-lookup"><span data-stu-id="1ec44-111">This sample is based on the [Message Security User Name](../../../../docs/framework/wcf/samples/message-security-user-name.md), but demonstrates how to perform a claim transformation prior to the <xref:System.ServiceModel.ServiceAuthorizationManager> being called.</span></span>

> [!NOTE]
> <span data-ttu-id="1ec44-112">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="1ec44-112">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

 <span data-ttu-id="1ec44-113">En resumen, este ejemplo muestra cómo:</span><span class="sxs-lookup"><span data-stu-id="1ec44-113">In summary, this sample demonstrates how:</span></span>

- <span data-ttu-id="1ec44-114">El cliente se puede autenticar utilizando una contraseña de nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="1ec44-114">The client can be authenticated using a user name-password.</span></span>

- <span data-ttu-id="1ec44-115">El cliente se puede autenticar utilizando un certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="1ec44-115">The client can be authenticated using an X.509 certificate.</span></span>

- <span data-ttu-id="1ec44-116">El servidor valida las credenciales del cliente contra un validador `UsernamePassword` personalizado.</span><span class="sxs-lookup"><span data-stu-id="1ec44-116">The server validates the client credentials against a custom `UsernamePassword` validator.</span></span>

- <span data-ttu-id="1ec44-117">El servidor se autentica utilizando el certificado X.509 del servidor.</span><span class="sxs-lookup"><span data-stu-id="1ec44-117">The server is authenticated using the server's X.509 certificate.</span></span>

- <span data-ttu-id="1ec44-118">El servidor puede utilizar <xref:System.ServiceModel.ServiceAuthorizationManager> para controlar el acceso a ciertos métodos en el servicio.</span><span class="sxs-lookup"><span data-stu-id="1ec44-118">The server can use <xref:System.ServiceModel.ServiceAuthorizationManager> to control access to certain methods in the service.</span></span>

- <span data-ttu-id="1ec44-119">Cómo implementar <xref:System.IdentityModel.Policy.IAuthorizationPolicy>.</span><span class="sxs-lookup"><span data-stu-id="1ec44-119">How to implement <xref:System.IdentityModel.Policy.IAuthorizationPolicy>.</span></span>

<span data-ttu-id="1ec44-120">El servicio expone dos puntos de conexión para comunicarse con el servicio, definidos mediante el archivo de configuración App.config. Cada extremo está compuesto por una dirección, un enlace y un contrato.</span><span class="sxs-lookup"><span data-stu-id="1ec44-120">The service exposes two endpoints for communicating with the service, defined using the configuration file App.config. Each endpoint consists of an address, a binding, and a contract.</span></span> <span data-ttu-id="1ec44-121">Un enlace se configura con un enlace `wsHttpBinding` estándar que utiliza la autenticación de WS-Security y del nombre de usuario del cliente.</span><span class="sxs-lookup"><span data-stu-id="1ec44-121">One binding is configured with a standard `wsHttpBinding` binding that uses WS-Security and client username authentication.</span></span> <span data-ttu-id="1ec44-122">El otro enlace se configura con un enlace `wsHttpBinding` estándar que utiliza la autenticación de WS-Security y del certificado de cliente.</span><span class="sxs-lookup"><span data-stu-id="1ec44-122">The other binding is configured with a standard `wsHttpBinding` binding that uses WS-Security and client certificate authentication.</span></span> <span data-ttu-id="1ec44-123">El [ \<comportamiento >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) especifica que las credenciales de usuario que se usará para la autenticación de servicio.</span><span class="sxs-lookup"><span data-stu-id="1ec44-123">The [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) specifies that the user credentials are to be used for service authentication.</span></span> <span data-ttu-id="1ec44-124">El certificado de servidor debe contener el mismo valor para el `SubjectName` propiedad como el `findValue` atributo en el [ \<serviceCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md).</span><span class="sxs-lookup"><span data-stu-id="1ec44-124">The server certificate must contain the same value for the `SubjectName` property as the `findValue` attribute in the [\<serviceCertificate>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md).</span></span>

```xml
<system.serviceModel>
  <services>
    <service name="Microsoft.ServiceModel.Samples.CalculatorService"
             behaviorConfiguration="CalculatorServiceBehavior">
      <host>
        <baseAddresses>
          <!-- configure base address provided by host -->
          <add baseAddress ="http://localhost:8001/servicemodelsamples/service"/>
        </baseAddresses>
      </host>
      <!-- use base address provided by host, provide two endpoints -->
      <endpoint address="username"
                binding="wsHttpBinding"
                bindingConfiguration="Binding1"
                contract="Microsoft.ServiceModel.Samples.ICalculator" />
      <endpoint address="certificate"
                binding="wsHttpBinding"
                bindingConfiguration="Binding2"
                contract="Microsoft.ServiceModel.Samples.ICalculator" />
    </service>
  </services>

  <bindings>
    <wsHttpBinding>
      <!-- Username binding -->
      <binding name="Binding1">
        <security mode="Message">
    <message clientCredentialType="UserName" />
        </security>
      </binding>
      <!-- X509 certificate binding -->
      <binding name="Binding2">
        <security mode="Message">
          <message clientCredentialType="Certificate" />
        </security>
      </binding>
    </wsHttpBinding>
  </bindings>

  <behaviors>
    <serviceBehaviors>
      <behavior name="CalculatorServiceBehavior" >
        <serviceDebug includeExceptionDetailInFaults ="true" />
        <serviceCredentials>
          <!--
          The serviceCredentials behavior allows one to specify a custom validator for username/password combinations.
          -->
          <userNameAuthentication userNamePasswordValidationMode="Custom" customUserNamePasswordValidatorType="Microsoft.ServiceModel.Samples.MyCustomUserNameValidator, service" />
          <!--
          The serviceCredentials behavior allows one to specify authentication constraints on client certificates.
          -->
          <clientCertificate>
            <!--
            Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate
            is in the user's Trusted People store, then it will be trusted without performing a
            validation of the certificate's issuer chain. This setting is used here for convenience so that the
            sample can be run without having to have certificates issued by a certification authority (CA).
            This setting is less secure than the default, ChainTrust. The security implications of this
            setting should be carefully considered before using PeerOrChainTrust in production code.
            -->
            <authentication certificateValidationMode="PeerOrChainTrust" />
          </clientCertificate>
          <!--
          The serviceCredentials behavior allows one to define a service certificate.
          A service certificate is used by a client to authenticate the service and provide message protection.
          This configuration references the "localhost" certificate installed during the setup instructions.
          -->
          <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName" />
        </serviceCredentials>
        <serviceAuthorization serviceAuthorizationManagerType="Microsoft.ServiceModel.Samples.MyServiceAuthorizationManager, service">
          <!--
          The serviceAuthorization behavior allows one to specify custom authorization policies.
          -->
          <authorizationPolicies>
            <add policyType="Microsoft.ServiceModel.Samples.CustomAuthorizationPolicy.MyAuthorizationPolicy, PolicyLibrary" />
          </authorizationPolicies>
        </serviceAuthorization>
      </behavior>
    </serviceBehaviors>
  </behaviors>

</system.serviceModel>
```

<span data-ttu-id="1ec44-125">Cada configuración de extremo de cliente está compuesta de un nombre de configuración, una dirección absoluta para el extremo de servicio, el enlace y el contrato.</span><span class="sxs-lookup"><span data-stu-id="1ec44-125">Each client endpoint configuration consists of a configuration name, an absolute address for the service endpoint, the binding, and the contract.</span></span> <span data-ttu-id="1ec44-126">El enlace del cliente se configura con el modo de seguridad adecuados según lo especificado en este caso en el [ \<seguridad >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md) y `clientCredentialType` según lo especificado en el [ \<mensaje >](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="1ec44-126">The client binding is configured with the appropriate security mode as specified in this case in the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md) and `clientCredentialType` as specified in the [\<message>](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md).</span></span>

```xml
<system.serviceModel>

    <client>
      <!-- Username based endpoint -->
      <endpoint name="Username"
            address="http://localhost:8001/servicemodelsamples/service/username"
    binding="wsHttpBinding"
    bindingConfiguration="Binding1"
                behaviorConfiguration="ClientCertificateBehavior"
                contract="Microsoft.ServiceModel.Samples.ICalculator" >
      </endpoint>
      <!-- X509 certificate based endpoint -->
      <endpoint name="Certificate"
                        address="http://localhost:8001/servicemodelsamples/service/certificate"
                binding="wsHttpBinding"
            bindingConfiguration="Binding2"
                behaviorConfiguration="ClientCertificateBehavior"
                contract="Microsoft.ServiceModel.Samples.ICalculator">
      </endpoint>
    </client>

    <bindings>
      <wsHttpBinding>
        <!-- Username binding -->
      <binding name="Binding1">
        <security mode="Message">
          <message clientCredentialType="UserName" />
        </security>
      </binding>
        <!-- X509 certificate binding -->
        <binding name="Binding2">
          <security mode="Message">
            <message clientCredentialType="Certificate" />
          </security>
        </binding>
    </wsHttpBinding>
    </bindings>

    <behaviors>
      <behavior name="ClientCertificateBehavior">
        <clientCredentials>
          <serviceCertificate>
            <!--
            Setting the certificateValidationMode to PeerOrChainTrust
            means that if the certificate
            is in the user's Trusted People store, then it will be
            trusted without performing a
            validation of the certificate's issuer chain. This setting
            is used here for convenience so that the
            sample can be run without having to have certificates
            issued by a certification authority (CA).
            This setting is less secure than the default, ChainTrust.
            The security implications of this
            setting should be carefully considered before using
            PeerOrChainTrust in production code.
            -->
            <authentication certificateValidationMode = "PeerOrChainTrust" />
          </serviceCertificate>
        </clientCredentials>
      </behavior>
    </behaviors>

  </system.serviceModel>
```

<span data-ttu-id="1ec44-127">Para el punto de conexión basado en el nombre de usuario, la implementación del cliente establece el nombre de usuario y la contraseña que se van a utilizar.</span><span class="sxs-lookup"><span data-stu-id="1ec44-127">For the user name-based endpoint, the client implementation sets the user name and password to use.</span></span>

```csharp
// Create a client with Username endpoint configuration
CalculatorClient client1 = new CalculatorClient("Username");

client1.ClientCredentials.UserName.UserName = "test1";
client1.ClientCredentials.UserName.Password = "1tset";

try
{
    // Call the Add service operation.
    double value1 = 100.00D;
    double value2 = 15.99D;
    double result = client1.Add(value1, value2);
    Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);
    ...
}
catch (Exception e)
{
    Console.WriteLine("Call failed : {0}", e.Message);
}

client1.Close();
```

<span data-ttu-id="1ec44-128">Para el punto de conexión basado en el certificado, la implementación del cliente establece el certificado de cliente que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="1ec44-128">For the certificate-based endpoint, the client implementation sets the client certificate to use.</span></span>

```csharp
// Create a client with Certificate endpoint configuration
CalculatorClient client2 = new CalculatorClient("Certificate");

client2.ClientCredentials.ClientCertificate.SetCertificate(StoreLocation.CurrentUser, StoreName.My, X509FindType.FindBySubjectName, "test1");

try
{
    // Call the Add service operation.
    double value1 = 100.00D;
    double value2 = 15.99D;
    double result = client2.Add(value1, value2);
    Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);
    ...
}
catch (Exception e)
{
    Console.WriteLine("Call failed : {0}", e.Message);
}

client2.Close();
```

<span data-ttu-id="1ec44-129">Este ejemplo utiliza un <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> personalizado para validar nombres de usuario y contraseñas.</span><span class="sxs-lookup"><span data-stu-id="1ec44-129">This sample uses a custom <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> to validate user names and passwords.</span></span> <span data-ttu-id="1ec44-130">El ejemplo implementa `MyCustomUserNamePasswordValidator`, derivado de <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>.</span><span class="sxs-lookup"><span data-stu-id="1ec44-130">The sample implements `MyCustomUserNamePasswordValidator`, derived from <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>.</span></span> <span data-ttu-id="1ec44-131">Consulte la documentación sobre <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="1ec44-131">See the documentation about <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> for more information.</span></span> <span data-ttu-id="1ec44-132">Con el fin de mostrar la integración con <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>, este ejemplo de validador personalizado implementa el método <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> para aceptar pares de nombre de usuario/contraseña donde el primero coincide con la contraseña tal y como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="1ec44-132">For the purposes of demonstrating the integration with the <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>, this custom validator sample implements the <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> method to accept user name/password pairs where the user name matches the password as shown in the following code.</span></span>

```csharp
public class MyCustomUserNamePasswordValidator : UserNamePasswordValidator
{
  // This method validates users. It allows in two users,
  // test1 and test2 with passwords 1tset and 2tset respectively.
  // This code is for illustration purposes only and
  // MUST NOT be used in a production environment because it
  // is NOT secure.
  public override void Validate(string userName, string password)
  {
    if (null == userName || null == password)
    {
      throw new ArgumentNullException();
    }

    if (!(userName == "test1" && password == "1tset") && !(userName == "test2" && password == "2tset"))
    {
      throw new SecurityTokenException("Unknown Username or Password");
    }
  }
}
```

<span data-ttu-id="1ec44-133">Una vez que se implementa el validador en el código de servicio, se debe informar al host de servicio sobre la instancia del validador que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="1ec44-133">Once the validator is implemented in service code, the service host must be informed about the validator instance to use.</span></span> <span data-ttu-id="1ec44-134">Esto se realiza mediante el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="1ec44-134">This is done using the following code:</span></span>

```csharp
Servicehost.Credentials.UserNameAuthentication.UserNamePasswordValidationMode = UserNamePasswordValidationMode.Custom;
serviceHost.Credentials.UserNameAuthentication.CustomUserNamePasswordValidator = new MyCustomUserNamePasswordValidatorProvider();
```

<span data-ttu-id="1ec44-135">O bien, puede hacer lo mismo en la configuración:</span><span class="sxs-lookup"><span data-stu-id="1ec44-135">Or you can do the same thing in configuration:</span></span>

```xml
<behavior ...>
    <serviceCredentials>
      <!--
      The serviceCredentials behavior allows one to specify a custom validator for username/password combinations.
      -->
      <userNameAuthentication userNamePasswordValidationMode="Custom" customUserNamePasswordValidatorType="Microsoft.ServiceModel.Samples.MyCustomUserNameValidator, service" />
    ...
    </serviceCredentials>
</behavior>
```

<span data-ttu-id="1ec44-136">Windows Communication Foundation (WCF) proporciona un modelo enriquecido basado en notificaciones para realizar comprobaciones de acceso.</span><span class="sxs-lookup"><span data-stu-id="1ec44-136">Windows Communication Foundation (WCF) provides a rich claims-based model for performing access checks.</span></span> <span data-ttu-id="1ec44-137">El objeto <xref:System.ServiceModel.ServiceAuthorizationManager> se utiliza para realizar la comprobación de acceso y determinar si las notificaciones asociadas con el cliente satisfacen los requisitos necesarios para tener acceso al método de servicio.</span><span class="sxs-lookup"><span data-stu-id="1ec44-137">The <xref:System.ServiceModel.ServiceAuthorizationManager> object is used to perform the access check and determine whether the claims associated with the client satisfy the requirements necessary to access the service method.</span></span>

<span data-ttu-id="1ec44-138">Para los fines de demostración, este ejemplo muestra una implementación de <xref:System.ServiceModel.ServiceAuthorizationManager> que implementa el <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> método para permitir el acceso de un usuario a los métodos en función de las notificaciones de tipo `http://example.com/claims/allowedoperation` cuyo valor es el URI de acción de la operación permite que se llame.</span><span class="sxs-lookup"><span data-stu-id="1ec44-138">For the purposes of demonstration, this sample shows an implementation of <xref:System.ServiceModel.ServiceAuthorizationManager> that implements the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> method to allow a user's access to methods based on claims of type `http://example.com/claims/allowedoperation` whose value is the Action URI of the operation that is allowed to be called.</span></span>

```csharp
public class MyServiceAuthorizationManager : ServiceAuthorizationManager
{
  protected override bool CheckAccessCore(OperationContext operationContext)
  {
    string action = operationContext.RequestContext.RequestMessage.Headers.Action;
    Console.WriteLine("action: {0}", action);
    foreach(ClaimSet cs in operationContext.ServiceSecurityContext.AuthorizationContext.ClaimSets)
    {
      if ( cs.Issuer == ClaimSet.System )
      {
        foreach (Claim c in cs.FindClaims("http://example.com/claims/allowedoperation", Rights.PossessProperty))
        {
          Console.WriteLine("resource: {0}", c.Resource.ToString());
          if (action == c.Resource.ToString())
            return true;
        }
      }
    }
    return false;
  }
}
```

<span data-ttu-id="1ec44-139">Una vez implementado el <xref:System.ServiceModel.ServiceAuthorizationManager> personalizado, se debe informar al host de servicio sobre el <xref:System.ServiceModel.ServiceAuthorizationManager> que se va a utilizar.</span><span class="sxs-lookup"><span data-stu-id="1ec44-139">Once the custom <xref:System.ServiceModel.ServiceAuthorizationManager> is implemented, the service host must be informed about the <xref:System.ServiceModel.ServiceAuthorizationManager> to use.</span></span> <span data-ttu-id="1ec44-140">Esto se hace tal y como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="1ec44-140">This is done as shown in the following code.</span></span>

```xml
<behavior ...>
    ...
    <serviceAuthorization serviceAuthorizationManagerType="Microsoft.ServiceModel.Samples.MyServiceAuthorizationManager, service">
        ...
    </serviceAuthorization>
</behavior>
```

<span data-ttu-id="1ec44-141">El método <xref:System.IdentityModel.Policy.IAuthorizationPolicy> principal que implementar es el método <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%28System.IdentityModel.Policy.EvaluationContext%2CSystem.Object%40%29>.</span><span class="sxs-lookup"><span data-stu-id="1ec44-141">The primary <xref:System.IdentityModel.Policy.IAuthorizationPolicy> method to implement is the <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%28System.IdentityModel.Policy.EvaluationContext%2CSystem.Object%40%29> method.</span></span>

```csharp
public class MyAuthorizationPolicy : IAuthorizationPolicy
{
    string id;

    public MyAuthorizationPolicy()
    {
    id =  Guid.NewGuid().ToString();
    }

    public bool Evaluate(EvaluationContext evaluationContext,
                                            ref object state)
    {
        bool bRet = false;
        CustomAuthState customstate = null;

        if (state == null)
        {
            customstate = new CustomAuthState();
            state = customstate;
        }
        else
            customstate = (CustomAuthState)state;
        Console.WriteLine("In Evaluate");
        if (!customstate.ClaimsAdded)
        {
           IList<Claim> claims = new List<Claim>();

           foreach (ClaimSet cs in evaluationContext.ClaimSets)
              foreach (Claim c in cs.FindClaims(ClaimTypes.Name,
                                         Rights.PossessProperty))
                  foreach (string s in
                        GetAllowedOpList(c.Resource.ToString()))
                  {
                       claims.Add(new
               Claim("http://example.com/claims/allowedoperation",
                                    s, Rights.PossessProperty));
                            Console.WriteLine("Claim added {0}", s);
                      }
                   evaluationContext.AddClaimSet(this,
                           new DefaultClaimSet(this.Issuer,claims));
                   customstate.ClaimsAdded = true;
                   bRet = true;
                }
         else
         {
              bRet = true;
         }
         return bRet;
     }
...
}
```

<span data-ttu-id="1ec44-142">El código anterior muestra cómo el método <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%28System.IdentityModel.Policy.EvaluationContext%2CSystem.Object%40%29> comprueba que no se ha añadido ninguna notificación que afecte al procesamiento y añade notificaciones específicas.</span><span class="sxs-lookup"><span data-stu-id="1ec44-142">The previous code shows how the <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%28System.IdentityModel.Policy.EvaluationContext%2CSystem.Object%40%29> method checks that no new claims have been added that affect the processing and adds specific claims.</span></span> <span data-ttu-id="1ec44-143">Las notificaciones que se permiten se obtienen del método `GetAllowedOpList`, que se implementa para devolver una lista concreta de operaciones que el usuario puede realizar.</span><span class="sxs-lookup"><span data-stu-id="1ec44-143">The claims that are allowed are obtained from the `GetAllowedOpList` method, which is implemented to return a specific list of operations that the user is allowed to perform.</span></span> <span data-ttu-id="1ec44-144">La directiva de autorización agrega notificaciones para tener acceso a la operación determinada.</span><span class="sxs-lookup"><span data-stu-id="1ec44-144">The authorization policy adds claims for accessing the particular operation.</span></span> <span data-ttu-id="1ec44-145"><xref:System.ServiceModel.ServiceAuthorizationManager> lo utiliza después para realizar decisiones de comprobación de acceso.</span><span class="sxs-lookup"><span data-stu-id="1ec44-145">This is later used by the <xref:System.ServiceModel.ServiceAuthorizationManager> to perform access check decisions.</span></span>

<span data-ttu-id="1ec44-146">Una vez implementado el <xref:System.IdentityModel.Policy.IAuthorizationPolicy> personalizado, se debe informar al host de servicio sobre las directivas de autorización que desee utilizar.</span><span class="sxs-lookup"><span data-stu-id="1ec44-146">Once the custom <xref:System.IdentityModel.Policy.IAuthorizationPolicy> is implemented, the service host must be informed about the authorization policies to use.</span></span>

```xml
<serviceAuthorization ...>
       <authorizationPolicies>
            <add policyType='Microsoft.ServiceModel.Samples.CustomAuthorizationPolicy.MyAuthorizationPolicy, PolicyLibrary' />
       </authorizationPolicies>
</serviceAuthorization>
```

<span data-ttu-id="1ec44-147">Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente.</span><span class="sxs-lookup"><span data-stu-id="1ec44-147">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="1ec44-148">El cliente llama correctamente a los métodos Sumar, Restar y Multiplicar y obtiene un mensaje de acceso denegado al intentar llamar al método Dividir.</span><span class="sxs-lookup"><span data-stu-id="1ec44-148">The client successfully calls the Add, Subtract and Multiple methods and gets an "Access is denied" message when trying to call the Divide method.</span></span> <span data-ttu-id="1ec44-149">Presione ENTRAR en la ventana de cliente para cerrar el cliente.</span><span class="sxs-lookup"><span data-stu-id="1ec44-149">Press ENTER in the client window to shut down the client.</span></span>

## <a name="setup-batch-file"></a><span data-ttu-id="1ec44-150">Instalar el archivo por lotes</span><span class="sxs-lookup"><span data-stu-id="1ec44-150">Setup Batch File</span></span>

<span data-ttu-id="1ec44-151">El archivo por lotes Setup.bat incluido con este ejemplo permite configurar el servidor con los certificados pertinentes para ejecutar una aplicación autohospedada que requiera seguridad basada en el certificado del servidor.</span><span class="sxs-lookup"><span data-stu-id="1ec44-151">The Setup.bat batch file included with this sample allows you to configure the server with relevant certificates to run a self-hosted application that requires server certificate-based security.</span></span>

<span data-ttu-id="1ec44-152">A continuación, se proporciona información general breve de las diferentes secciones de los archivos por lotes para que se puedan modificar para su ejecución en la configuración adecuada:</span><span class="sxs-lookup"><span data-stu-id="1ec44-152">The following provides a brief overview of the different sections of the batch files so that they can be modified to run in the appropriate configuration:</span></span>

- <span data-ttu-id="1ec44-153">Crear el certificado de servidor.</span><span class="sxs-lookup"><span data-stu-id="1ec44-153">Creating the server certificate.</span></span>

    <span data-ttu-id="1ec44-154">Las líneas siguientes del archivo por lotes Setup.bat crean el certificado de servidor que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="1ec44-154">The following lines from the Setup.bat batch file create the server certificate to be used.</span></span> <span data-ttu-id="1ec44-155">La variable %SERVER_NAME% especifica el nombre del servidor.</span><span class="sxs-lookup"><span data-stu-id="1ec44-155">The %SERVER_NAME% variable specifies the server name.</span></span> <span data-ttu-id="1ec44-156">Cambie esta variable para especificar su propio nombre de servidor.</span><span class="sxs-lookup"><span data-stu-id="1ec44-156">Change this variable to specify your own server name.</span></span> <span data-ttu-id="1ec44-157">El valor predeterminado es el host local.</span><span class="sxs-lookup"><span data-stu-id="1ec44-157">The default value is localhost.</span></span>

    ```
    echo ************
    echo Server cert setup starting
    echo %SERVER_NAME%
    echo ************
    echo making server cert
    echo ************
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe
    ```

- <span data-ttu-id="1ec44-158">Instalar el certificado del servidor en el almacén de certificados de confianza del cliente.</span><span class="sxs-lookup"><span data-stu-id="1ec44-158">Installing the server certificate into client's trusted certificate store.</span></span>

    <span data-ttu-id="1ec44-159">Las líneas siguientes del archivo por lotes Setup.bat copian el certificado de servidor en el almacén de los usuarios de confianza del cliente.</span><span class="sxs-lookup"><span data-stu-id="1ec44-159">The following lines in the Setup.bat batch file copy the server certificate into the client trusted people store.</span></span> <span data-ttu-id="1ec44-160">Se requiere este paso porque el sistema cliente no confía implícitamente en los certificados generados por Makecert.exe.</span><span class="sxs-lookup"><span data-stu-id="1ec44-160">This step is required because certificates that are generated by Makecert.exe are not implicitly trusted by the client system.</span></span> <span data-ttu-id="1ec44-161">Si ya tiene un certificado que se basa en un certificado raíz de confianza del cliente (por ejemplo, un certificado emitido por Microsoft), no es necesario el paso de rellenar el almacén de certificados del cliente con el certificado de servidor.</span><span class="sxs-lookup"><span data-stu-id="1ec44-161">If you already have a certificate that is rooted in a client trusted root certificate—for example, a Microsoft issued certificate—this step of populating the client certificate store with the server certificate is not required.</span></span>

    ```
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople
    ```

- <span data-ttu-id="1ec44-162">Crear el certificado del cliente.</span><span class="sxs-lookup"><span data-stu-id="1ec44-162">Creating the client certificate.</span></span>

    <span data-ttu-id="1ec44-163">Las líneas siguientes del archivo por lotes Setup.bat crean el certificado de cliente que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="1ec44-163">The following lines from the Setup.bat batch file create the client certificate to be used.</span></span> <span data-ttu-id="1ec44-164">La variable %USER_NAME% especifica el nombre del servidor.</span><span class="sxs-lookup"><span data-stu-id="1ec44-164">The %USER_NAME% variable specifies the server name.</span></span> <span data-ttu-id="1ec44-165">Este valor está establecido en "test1" porque se trata del nombre que `IAuthorizationPolicy` busca.</span><span class="sxs-lookup"><span data-stu-id="1ec44-165">This value is set to "test1" because this is the name the `IAuthorizationPolicy` looks for.</span></span> <span data-ttu-id="1ec44-166">Si cambia el valor de %USER_NAME%, debe cambiar el valor correspondiente en el método `IAuthorizationPolicy.Evaluate`.</span><span class="sxs-lookup"><span data-stu-id="1ec44-166">If you change the value of %USER_NAME% you must change the corresponding value in the `IAuthorizationPolicy.Evaluate` method.</span></span>

    <span data-ttu-id="1ec44-167">El certificado está almacenado en Mi almacén (Personal) debajo de la ubicación de almacén CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="1ec44-167">The certificate is stored in My (Personal) store under the CurrentUser store location.</span></span>

    ```
    echo ************
    echo making client cert
    echo ************
    makecert.exe -sr CurrentUser -ss MY -a sha1 -n CN=%CLIENT_NAME% -sky exchange -pe
    ```

- <span data-ttu-id="1ec44-168">Instalar el certificado del cliente en el almacén de certificados de confianza del servidor.</span><span class="sxs-lookup"><span data-stu-id="1ec44-168">Installing the client certificate into server's trusted certificate store.</span></span>

    <span data-ttu-id="1ec44-169">Las líneas siguientes del archivo por lotes Setup.bat copian el certificado del cliente en el almacén de los usuarios de confianza.</span><span class="sxs-lookup"><span data-stu-id="1ec44-169">The following lines in the Setup.bat batch file copy the client certificate into the trusted people store.</span></span> <span data-ttu-id="1ec44-170">Se requiere este paso porque el sistema servidor no confía implícitamente en los certificados generados por Makecert.exe.</span><span class="sxs-lookup"><span data-stu-id="1ec44-170">This step is required because certificates that are generated by Makecert.exe are not implicitly trusted by the server system.</span></span> <span data-ttu-id="1ec44-171">Si ya tiene un certificado que se basa en un certificado raíz de confianza del cliente, por ejemplo, un certificado emitido por Microsoft, no es necesario el paso de rellenar el almacén del certificado del servidor con el certificado del cliente.</span><span class="sxs-lookup"><span data-stu-id="1ec44-171">If you already have a certificate that is rooted in a trusted root certificate—for example, a Microsoft issued certificate—this step of populating the server certificate store with the client certificate is not required.</span></span>

    ```
    certmgr.exe -add -r CurrentUser -s My -c -n %CLIENT_NAME% -r LocalMachine -s TrustedPeople
    ```

### <a name="to-set-up-and-build-the-sample"></a><span data-ttu-id="1ec44-172">Para configurar y compilar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="1ec44-172">To set up and build the sample</span></span>

1. <span data-ttu-id="1ec44-173">Para compilar la solución, siga las instrucciones de [compilar los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="1ec44-173">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>

2. <span data-ttu-id="1ec44-174">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, utilice las instrucciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="1ec44-174">To run the sample in a single- or cross-computer configuration, use the following instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="1ec44-175">Si usa Svcutil.exe para regenerar la configuración de este ejemplo, asegúrese de que modifica el nombre del extremo en la configuración del cliente para que coincida con el código de cliente.</span><span class="sxs-lookup"><span data-stu-id="1ec44-175">If you use Svcutil.exe to regenerate the configuration for this sample, be sure to modify the endpoint name in the client configuration to match the client code.</span></span>

### <a name="to-run-the-sample-on-the-same-computer"></a><span data-ttu-id="1ec44-176">Para ejecutar el ejemplo en el mismo equipo</span><span class="sxs-lookup"><span data-stu-id="1ec44-176">To run the sample on the same computer</span></span>

1. <span data-ttu-id="1ec44-177">Abra el símbolo del sistema para desarrolladores de Visual Studio con privilegios de administrador y ejecute *Setup.bat* desde la carpeta de instalación del ejemplo.</span><span class="sxs-lookup"><span data-stu-id="1ec44-177">Open Developer Command Prompt for Visual Studio with administrator privileges and run *Setup.bat* from the sample install folder.</span></span> <span data-ttu-id="1ec44-178">De esta forma, se instalan todos los certificados necesarios para ejecutar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="1ec44-178">This installs all the certificates required for running the sample.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1ec44-179">El archivo por lotes Setup.bat está diseñado para ejecutarse en línea de comandos para desarrolladores de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="1ec44-179">The Setup.bat batch file is designed to be run from Developer Command Prompt for Visual Studio.</span></span> <span data-ttu-id="1ec44-180">La variable de entorno PATH establece dentro de símbolo para desarrolladores de Visual Studio de los puntos en el directorio que contiene los archivos ejecutables requeridos por la *Setup.bat* secuencia de comandos.</span><span class="sxs-lookup"><span data-stu-id="1ec44-180">The PATH environment variable set within Developer Command Prompt for Visual Studio points to the directory that contains executables required by the *Setup.bat* script.</span></span>

1. <span data-ttu-id="1ec44-181">Inicie Service.exe desde *service\bin*.</span><span class="sxs-lookup"><span data-stu-id="1ec44-181">Launch Service.exe from *service\bin*.</span></span>

1. <span data-ttu-id="1ec44-182">Inicie Client.exe desde *\client\bin*.</span><span class="sxs-lookup"><span data-stu-id="1ec44-182">Launch Client.exe from *\client\bin*.</span></span> <span data-ttu-id="1ec44-183">La actividad del cliente se muestra en la aplicación de consola del cliente.</span><span class="sxs-lookup"><span data-stu-id="1ec44-183">Client activity is displayed on the client console application.</span></span>

<span data-ttu-id="1ec44-184">Si el cliente y el servicio no se pueden comunicar, vea [sugerencias de solución de problemas para obtener ejemplos de WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="1ec44-184">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>

### <a name="to-run-the-sample-across-computers"></a><span data-ttu-id="1ec44-185">Para ejecutar el ejemplo en varios equipos</span><span class="sxs-lookup"><span data-stu-id="1ec44-185">To run the sample across computers</span></span>

1. <span data-ttu-id="1ec44-186">Cree un directorio en el equipo del servicio.</span><span class="sxs-lookup"><span data-stu-id="1ec44-186">Create a directory on the service computer.</span></span>

2. <span data-ttu-id="1ec44-187">Copie los archivos de programa de servicio de *\service\bin* en el directorio en el equipo del servicio.</span><span class="sxs-lookup"><span data-stu-id="1ec44-187">Copy the service program files from *\service\bin* to the directory on the service computer.</span></span> <span data-ttu-id="1ec44-188">Copie también los archivos Setup.bat, Cleanup.bat, GetComputerName.vbs e ImportClientCert.bat en el equipo de servicio.</span><span class="sxs-lookup"><span data-stu-id="1ec44-188">Also copy the Setup.bat, Cleanup.bat, GetComputerName.vbs and ImportClientCert.bat files to the service computer.</span></span>

3. <span data-ttu-id="1ec44-189">Cree un directorio en el equipo cliente para los archivos binarios del cliente.</span><span class="sxs-lookup"><span data-stu-id="1ec44-189">Create a directory on the client computer for the client binaries.</span></span>

4. <span data-ttu-id="1ec44-190">Copie los archivos de programa del cliente en el directorio del cliente en el equipo cliente.</span><span class="sxs-lookup"><span data-stu-id="1ec44-190">Copy the client program files to the client directory on the client computer.</span></span> <span data-ttu-id="1ec44-191">Copie también los archivos Setup.bat, Cleanup.bat e ImportServiceCert.bat en el cliente.</span><span class="sxs-lookup"><span data-stu-id="1ec44-191">Also copy the Setup.bat, Cleanup.bat, and ImportServiceCert.bat files to the client.</span></span>

5. <span data-ttu-id="1ec44-192">En el servidor, ejecute `setup.bat service` en línea de comandos de desarrollador para Visual Studio abierto con privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="1ec44-192">On the server, run `setup.bat service` in Developer Command Prompt for Visual Studio opened with administrator privileges.</span></span>

    <span data-ttu-id="1ec44-193">Ejecutando `setup.bat` con el `service` argumento crea un certificado de servicio con el nombre de dominio completo del equipo y exporta el certificado de servicio a un archivo denominado *Service.cer*.</span><span class="sxs-lookup"><span data-stu-id="1ec44-193">Running `setup.bat` with the `service` argument creates a service certificate with the fully qualified domain name of the computer, and exports the service certificate to a file named *Service.cer*.</span></span>

6. <span data-ttu-id="1ec44-194">Editar *Service.exe.config* para reflejar el nuevo nombre del certificado (en el `findValue` atributo en el [ \<serviceCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)) que es el mismo que el nombre de dominio completo del equipo.</span><span class="sxs-lookup"><span data-stu-id="1ec44-194">Edit *Service.exe.config* to reflect the new certificate name (in the `findValue` attribute in the [\<serviceCertificate>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)) which is the same as the fully qualified domain name of the computer.</span></span> <span data-ttu-id="1ec44-195">Cambie también el **computername** en el \<servicio > /\<baseAddresses > elemento desde el host local para el nombre completo de su equipo de servicio.</span><span class="sxs-lookup"><span data-stu-id="1ec44-195">Also change the **computername** in the \<service>/\<baseAddresses> element from localhost to the fully qualified name of your service computer.</span></span>

7. <span data-ttu-id="1ec44-196">Copia el *Service.cer* archivo desde el directorio de servicio al directorio del cliente en el equipo cliente.</span><span class="sxs-lookup"><span data-stu-id="1ec44-196">Copy the *Service.cer* file from the service directory to the client directory on the client computer.</span></span>

8. <span data-ttu-id="1ec44-197">En el cliente, ejecute `setup.bat client` en línea de comandos de desarrollador para Visual Studio abierto con privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="1ec44-197">On the client, run `setup.bat client` in Developer Command Prompt for Visual Studio opened with administrator privileges.</span></span>

    <span data-ttu-id="1ec44-198">Ejecutando `setup.bat` con el `client` argumento crea un certificado de cliente denominado **test1** y exporta el certificado de cliente a un archivo denominado *Client.cer*.</span><span class="sxs-lookup"><span data-stu-id="1ec44-198">Running `setup.bat` with the `client` argument creates a client certificate named **test1** and exports the client certificate to a file named *Client.cer*.</span></span>

9. <span data-ttu-id="1ec44-199">En el *Client.exe.config* de archivos en el equipo cliente, cambie el valor de la dirección del punto de conexión para que coincida con la nueva dirección de su servicio.</span><span class="sxs-lookup"><span data-stu-id="1ec44-199">In the *Client.exe.config* file on the client computer, change the address value of the endpoint to match the new address of your service.</span></span> <span data-ttu-id="1ec44-200">Realizar esto reemplazando **localhost** con el nombre de dominio completo del servidor.</span><span class="sxs-lookup"><span data-stu-id="1ec44-200">Do this by replacing **localhost** with the fully qualified domain name of the server.</span></span>

10. <span data-ttu-id="1ec44-201">Copie el archivo Client.cer del directorio del cliente en el directorio del servicio en el servidor.</span><span class="sxs-lookup"><span data-stu-id="1ec44-201">Copy the Client.cer file from the client directory to the service directory on the server.</span></span>

11. <span data-ttu-id="1ec44-202">En el cliente, ejecute *ImportServiceCert.bat* en línea de comandos de desarrollador para Visual Studio abierto con privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="1ec44-202">On the client, run *ImportServiceCert.bat* in Developer Command Prompt for Visual Studio opened with administrator privileges.</span></span>

    <span data-ttu-id="1ec44-203">Esto importa el certificado de servicio desde el archivo Service.cer en el **CurrentUser - TrustedPeople** almacenar.</span><span class="sxs-lookup"><span data-stu-id="1ec44-203">This imports the service certificate from the Service.cer file into the **CurrentUser - TrustedPeople** store.</span></span>

12. <span data-ttu-id="1ec44-204">En el servidor, ejecute *ImportClientCert.bat* en línea de comandos de desarrollador para Visual Studio abierto con privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="1ec44-204">On the server, run *ImportClientCert.bat* in Developer Command Prompt for Visual Studio opened with administrator privileges.</span></span>

    <span data-ttu-id="1ec44-205">Esto importa el certificado de cliente desde el archivo Client.cer en el **LocalMachine - TrustedPeople** almacenar.</span><span class="sxs-lookup"><span data-stu-id="1ec44-205">This imports the client certificate from the Client.cer file into the **LocalMachine - TrustedPeople** store.</span></span>

13. <span data-ttu-id="1ec44-206">En el equipo servidor, inicie Service.exe desde la ventana de símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="1ec44-206">On the server computer, launch Service.exe from the command prompt window.</span></span>

14. <span data-ttu-id="1ec44-207">En el equipo cliente, inicie Client.exe desde una ventana de símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="1ec44-207">On the client computer, launch Client.exe from a command prompt window.</span></span>

    <span data-ttu-id="1ec44-208">Si el cliente y el servicio no se pueden comunicar, vea [sugerencias de solución de problemas para obtener ejemplos de WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="1ec44-208">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>

### <a name="clean-up-after-the-sample"></a><span data-ttu-id="1ec44-209">Limpiar después de la muestra</span><span class="sxs-lookup"><span data-stu-id="1ec44-209">Clean up after the sample</span></span>

<span data-ttu-id="1ec44-210">Para limpiar después de la muestra, ejecute *Cleanup.bat* en la carpeta de ejemplos cuando haya terminado de ejecutar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="1ec44-210">To clean up after the sample, run *Cleanup.bat* in the samples folder when you have finished running the sample.</span></span> <span data-ttu-id="1ec44-211">Esto quita los certificados de cliente y servidor del almacén de certificados.</span><span class="sxs-lookup"><span data-stu-id="1ec44-211">This removes the server and client certificates from the certificate store.</span></span>

> [!NOTE]
> <span data-ttu-id="1ec44-212">Este script no quita los certificados del servicio en un cliente cuando el ejemplo se ejecuta en varios equipos.</span><span class="sxs-lookup"><span data-stu-id="1ec44-212">This script does not remove service certificates on a client when running this sample across computers.</span></span> <span data-ttu-id="1ec44-213">Si ha ejecutado los ejemplos de WCF que usan certificados en varios equipos, asegúrese de borrar los certificados de servicio que se han instalado en el almacén CurrentUser - TrustedPeople almacenar.</span><span class="sxs-lookup"><span data-stu-id="1ec44-213">If you have run WCF samples that use certificates across computers, be sure to clear the service certificates that have been installed in the CurrentUser - TrustedPeople store.</span></span> <span data-ttu-id="1ec44-214">Para ello, use el siguiente comando: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` Por ejemplo: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span><span class="sxs-lookup"><span data-stu-id="1ec44-214">To do this, use the following command: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` For example: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span></span>