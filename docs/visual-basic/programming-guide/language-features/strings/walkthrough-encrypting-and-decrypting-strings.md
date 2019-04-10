---
title: Cifrar y descifrar cadenas en Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- encryption [Visual Basic], strings
- strings [Visual Basic], encrypting
- decryption [Visual Basic], strings
- strings [Visual Basic], decrypting
ms.assetid: 1f51e40a-2f88-43e2-a83e-28a0b5c0d6fd
ms.openlocfilehash: 1d003df87327e14a6cbd65222f86c3dc4df169ff
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59334047"
---
# <a name="walkthrough-encrypting-and-decrypting-strings-in-visual-basic"></a><span data-ttu-id="57f21-102">Tutorial: Cifrar y descifrar cadenas en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="57f21-102">Walkthrough: Encrypting and Decrypting Strings in Visual Basic</span></span>
<span data-ttu-id="57f21-103">En este tutorial se muestra cómo usar el <xref:System.Security.Cryptography.DESCryptoServiceProvider> clase para cifrar y descifrar cadenas mediante la versión de servicios criptográficos (CSP) del proveedor de Triple Data Encryption Standard (<xref:System.Security.Cryptography.TripleDES>) algoritmo.</span><span class="sxs-lookup"><span data-stu-id="57f21-103">This walkthrough shows you how to use the <xref:System.Security.Cryptography.DESCryptoServiceProvider> class to encrypt and decrypt strings using the cryptographic service provider (CSP) version of the Triple Data Encryption Standard (<xref:System.Security.Cryptography.TripleDES>) algorithm.</span></span> <span data-ttu-id="57f21-104">El primer paso es crear una clase de contenedor simple que encapsula el algoritmo 3DES y almacena los datos cifrados como una cadena codificada en base 64.</span><span class="sxs-lookup"><span data-stu-id="57f21-104">The first step is to create a simple wrapper class that encapsulates the 3DES algorithm and stores the encrypted data as a base-64 encoded string.</span></span> <span data-ttu-id="57f21-105">A continuación, ese contenedor se usa para almacenar de forma segura los datos privados del usuario en un archivo de texto accesible públicamente.</span><span class="sxs-lookup"><span data-stu-id="57f21-105">Then, that wrapper is used to securely store private user data in a publicly accessible text file.</span></span>  
  
 <span data-ttu-id="57f21-106">Puede utilizar cifrado para proteger los secretos de usuario (por ejemplo, contraseñas) y hacer que las credenciales no se puede leer los usuarios no autorizados.</span><span class="sxs-lookup"><span data-stu-id="57f21-106">You can use encryption to protect user secrets (for example, passwords) and to make credentials unreadable by unauthorized users.</span></span> <span data-ttu-id="57f21-107">Esto puede proteger la identidad de un usuario autorizado desde que se lo roban, que protege los activos del usuario y proporciona el no rechazo.</span><span class="sxs-lookup"><span data-stu-id="57f21-107">This can protect an authorized user's identity from being stolen, which protects the user's assets and provides non-repudiation.</span></span> <span data-ttu-id="57f21-108">Cifrado también puede proteger datos de un usuario está accediendo a los usuarios no autorizados.</span><span class="sxs-lookup"><span data-stu-id="57f21-108">Encryption can also protect a user's data from being accessed by unauthorized users.</span></span>  
  
 <span data-ttu-id="57f21-109">Para más información, vea [Servicios criptográficos](../../../../standard/security/cryptographic-services.md).</span><span class="sxs-lookup"><span data-stu-id="57f21-109">For more information, see [Cryptographic Services](../../../../standard/security/cryptographic-services.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="57f21-110">Los algoritmos de Triple Data Encryption Standard (3DES) y Rijndael (conocido ahora como estándar de cifrado avanzado [AES]) proporcionan mayor seguridad que DES porque son más intensivas.</span><span class="sxs-lookup"><span data-stu-id="57f21-110">The Rijndael (now referred to as Advanced Encryption Standard [AES]) and Triple Data Encryption Standard (3DES) algorithms provide greater security than DES because they are more computationally intensive.</span></span> <span data-ttu-id="57f21-111">Para obtener más información, vea <xref:System.Security.Cryptography.DES> y <xref:System.Security.Cryptography.Rijndael>.</span><span class="sxs-lookup"><span data-stu-id="57f21-111">For more information, see <xref:System.Security.Cryptography.DES> and <xref:System.Security.Cryptography.Rijndael>.</span></span>  
  
### <a name="to-create-the-encryption-wrapper"></a><span data-ttu-id="57f21-112">Para crear el contenedor de cifrado</span><span class="sxs-lookup"><span data-stu-id="57f21-112">To create the encryption wrapper</span></span>  
  
1. <span data-ttu-id="57f21-113">Crear el `Simple3Des` clase para encapsular los métodos de cifrado y descifrado.</span><span class="sxs-lookup"><span data-stu-id="57f21-113">Create the `Simple3Des` class to encapsulate the encryption and decryption methods.</span></span>  
  
     [!code-vb[VbVbalrStrings#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#38)]  
  
2. <span data-ttu-id="57f21-114">Agregue una importación del espacio de nombres de criptografía al principio del archivo que contiene el `Simple3Des` clase.</span><span class="sxs-lookup"><span data-stu-id="57f21-114">Add an import of the cryptography namespace to the start of the file that contains the `Simple3Des` class.</span></span>  
  
     [!code-vb[VbVbalrStrings#77](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#77)]  
  
3. <span data-ttu-id="57f21-115">En el `Simple3Des` clase, agregue un campo privado para almacenar el proveedor de servicios de cifrado 3DES.</span><span class="sxs-lookup"><span data-stu-id="57f21-115">In the `Simple3Des` class, add a private field to store the 3DES cryptographic service provider.</span></span>  
  
     [!code-vb[VbVbalrStrings#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#39)]  
  
4. <span data-ttu-id="57f21-116">Agregue un método privado que crea una matriz de bytes de una longitud especificada del código hash de la clave especificada.</span><span class="sxs-lookup"><span data-stu-id="57f21-116">Add a private method that creates a byte array of a specified length from the hash of the specified key.</span></span>  
  
     [!code-vb[VbVbalrStrings#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#41)]  
  
5. <span data-ttu-id="57f21-117">Agregue un constructor para inicializar el proveedor de servicios de cifrado 3DES.</span><span class="sxs-lookup"><span data-stu-id="57f21-117">Add a constructor to initialize the 3DES cryptographic service provider.</span></span>  
  
     <span data-ttu-id="57f21-118">El `key` parámetro controla el `EncryptData` y `DecryptData` métodos.</span><span class="sxs-lookup"><span data-stu-id="57f21-118">The `key` parameter controls the `EncryptData` and `DecryptData` methods.</span></span>  
  
     [!code-vb[VbVbalrStrings#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#40)]  
  
6. <span data-ttu-id="57f21-119">Agregue un método público que cifre una cadena.</span><span class="sxs-lookup"><span data-stu-id="57f21-119">Add a public method that encrypts a string.</span></span>  
  
     [!code-vb[VbVbalrStrings#42](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#42)]  
  
7. <span data-ttu-id="57f21-120">Agregue un método público que descifra una cadena.</span><span class="sxs-lookup"><span data-stu-id="57f21-120">Add a public method that decrypts a string.</span></span>  
  
     [!code-vb[VbVbalrStrings#43](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#43)]  
  
     <span data-ttu-id="57f21-121">Ahora se puede usar la clase contenedora para proteger los activos de usuario.</span><span class="sxs-lookup"><span data-stu-id="57f21-121">The wrapper class can now be used to protect user assets.</span></span> <span data-ttu-id="57f21-122">En este ejemplo, sirve para almacenar de forma segura los datos privados del usuario en un archivo de texto accesible públicamente.</span><span class="sxs-lookup"><span data-stu-id="57f21-122">In this example, it is used to securely store private user data in a publicly accessible text file.</span></span>  
  
### <a name="to-test-the-encryption-wrapper"></a><span data-ttu-id="57f21-123">Para probar el contenedor de cifrado</span><span class="sxs-lookup"><span data-stu-id="57f21-123">To test the encryption wrapper</span></span>  
  
1. <span data-ttu-id="57f21-124">En una clase independiente, agregue un método que utiliza el contenedor `EncryptData` método para cifrar una cadena y escribirla en el usuario de la carpeta Mis documentos.</span><span class="sxs-lookup"><span data-stu-id="57f21-124">In a separate class, add a method that uses the wrapper's `EncryptData` method to encrypt a string and write it to the user's My Documents folder.</span></span>  
  
     [!code-vb[VbVbalrStrings#78](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#78)]  
  
2. <span data-ttu-id="57f21-125">Agregar un método que lee la cadena cifrada del usuario de la carpeta Mis documentos y descifra la cadena con el contenedor `DecryptData` método.</span><span class="sxs-lookup"><span data-stu-id="57f21-125">Add a method that reads the encrypted string from the user's My Documents folder and decrypts the string with the wrapper's `DecryptData` method.</span></span>  
  
     [!code-vb[VbVbalrStrings#79](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#79)]  
  
3. <span data-ttu-id="57f21-126">Agregar código de interfaz de usuario para llamar a la `TestEncoding` y `TestDecoding` métodos.</span><span class="sxs-lookup"><span data-stu-id="57f21-126">Add user interface code to call the `TestEncoding` and `TestDecoding` methods.</span></span>  
  
4. <span data-ttu-id="57f21-127">Ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="57f21-127">Run the application.</span></span>  
  
     <span data-ttu-id="57f21-128">Al probar la aplicación, tenga en cuenta que no descifrará los datos si se proporciona una contraseña incorrecta.</span><span class="sxs-lookup"><span data-stu-id="57f21-128">When you test the application, notice that it will not decrypt the data if you provide the wrong password.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57f21-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="57f21-129">See also</span></span>

- <xref:System.Security.Cryptography>
- <xref:System.Security.Cryptography.DESCryptoServiceProvider>
- <xref:System.Security.Cryptography.DES>
- <xref:System.Security.Cryptography.TripleDES>
- <xref:System.Security.Cryptography.Rijndael>
- [<span data-ttu-id="57f21-130">servicios criptográficos</span><span class="sxs-lookup"><span data-stu-id="57f21-130">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
