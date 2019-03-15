---
title: Cadenas de conexión de ADO.NET
ms.date: 10/10/2018
ms.assetid: 745c5f95-2f02-4674-b378-6d51a7ec2490
ms.openlocfilehash: 1197335f3ba2a09b6e7303d31bc32383d1fd3436
ms.sourcegitcommit: 69bf8b719d4c289eec7b45336d0b933dd7927841
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2019
ms.locfileid: "57844877"
---
# <a name="connection-strings-in-adonet"></a><span data-ttu-id="29559-102">Cadenas de conexión de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="29559-102">Connection Strings in ADO.NET</span></span>

<span data-ttu-id="29559-103">Una cadena de conexión contiene información de inicialización que se transfiere como un parámetro desde un proveedor de datos a un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="29559-103">A connection string contains initialization information that is passed as a parameter from a data provider to a data source.</span></span> <span data-ttu-id="29559-104">El proveedor de datos recibe la cadena de conexión como el valor de la <xref:System.Data.Common.DbConnection.ConnectionString?displayProperty=nameWithType> propiedad.</span><span class="sxs-lookup"><span data-stu-id="29559-104">The data provider receives the connection string as the value of the <xref:System.Data.Common.DbConnection.ConnectionString?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="29559-105">El proveedor analiza la cadena de conexión y se garantiza que la sintaxis es correcta y que se admiten las palabras clave.</span><span class="sxs-lookup"><span data-stu-id="29559-105">The provider parses the connection string and ensures that the syntax is correct and that the keywords are supported.</span></span> <span data-ttu-id="29559-106">El <xref:System.Data.Common.DbConnection.Open?displayProperty=nameWithType> método pasa los parámetros de conexión analizado al origen de datos.</span><span class="sxs-lookup"><span data-stu-id="29559-106">Then the <xref:System.Data.Common.DbConnection.Open?displayProperty=nameWithType> method passes the parsed connection parameters to the data source.</span></span> <span data-ttu-id="29559-107">El origen de datos realiza la validación y establece una conexión.</span><span class="sxs-lookup"><span data-stu-id="29559-107">The data source performs further validation and establishes a connection.</span></span>

## <a name="connection-string-syntax"></a><span data-ttu-id="29559-108">Sintaxis de la cadena de conexión</span><span class="sxs-lookup"><span data-stu-id="29559-108">Connection string syntax</span></span>

<span data-ttu-id="29559-109">Una cadena de conexión es una lista delimitada por punto y coma de pares de parámetro de clave/valor:</span><span class="sxs-lookup"><span data-stu-id="29559-109">A connection string is a semicolon-delimited list of key/value parameter pairs:</span></span>

    keyword1=value; keyword2=value;

<span data-ttu-id="29559-110">Palabras clave no distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="29559-110">Keywords are not case-sensitive.</span></span> <span data-ttu-id="29559-111">Sin embargo, los valores, pueden ser entre mayúsculas y minúsculas, según el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="29559-111">Values, however, may be case-sensitive, depending on the data source.</span></span> <span data-ttu-id="29559-112">Pueden contener las palabras clave y valores [caracteres de espacio en blanco](https://en.wikipedia.org/wiki/Whitespace_character#Unicode).</span><span class="sxs-lookup"><span data-stu-id="29559-112">Both keywords and values may contain [whitespace characters](https://en.wikipedia.org/wiki/Whitespace_character#Unicode).</span></span> <span data-ttu-id="29559-113">Espacio en blanco inicial y final se omite en las palabras clave y sin comillas los valores.</span><span class="sxs-lookup"><span data-stu-id="29559-113">Leading and trailing white space is ignored in keywords and unquoted values.</span></span>

<span data-ttu-id="29559-114">Si el valor contiene el punto y coma, [caracteres de control Unicode](https://en.wikipedia.org/wiki/Unicode_control_characters), o iniciales o finales de espacio en blanco, debe encerrarse entre comillas simples o dobles.</span><span class="sxs-lookup"><span data-stu-id="29559-114">If a value contains the semicolon, [Unicode control characters](https://en.wikipedia.org/wiki/Unicode_control_characters), or leading or trailing white space, it must be enclosed in single or double quotation marks.</span></span> <span data-ttu-id="29559-115">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="29559-115">For example:</span></span>

    Keyword=" whitespace  ";
    Keyword='special;character';

<span data-ttu-id="29559-116">El carácter envolvente no puede producirse dentro del valor que se agrega.</span><span class="sxs-lookup"><span data-stu-id="29559-116">The enclosing character may not occur within the value it encloses.</span></span> <span data-ttu-id="29559-117">Por lo tanto, un valor que contiene comillas simples puede incluirse únicamente en las comillas dobles y viceversa:</span><span class="sxs-lookup"><span data-stu-id="29559-117">Therefore, a value containing single quotation marks can be enclosed only in double quotation marks, and vice versa:</span></span>

    Keyword='double"quotation;mark';
    Keyword="single'quotation;mark";

<span data-ttu-id="29559-118">Las comillas a sí mismos, así como el signo igual, no requiere la adición, por lo que las siguientes cadenas de conexión son válidas:</span><span class="sxs-lookup"><span data-stu-id="29559-118">The quotation marks themselves, as well as the equals sign, do not require escaping, so the following connection strings are valid:</span></span>

    Keyword=no "escaping" 'required';
    Keyword=a=b=c

<span data-ttu-id="29559-119">Dado que cada valor se lee hasta el punto y coma siguiente o al final de cadena, el valor en el último ejemplo es `a=b=c`, y el punto y coma final es opcional.</span><span class="sxs-lookup"><span data-stu-id="29559-119">Since each value is read till the next semicolon or the end of string, the value in the latter example is `a=b=c`, and the final semicolon is optional.</span></span>

<span data-ttu-id="29559-120">Todas las cadenas de conexión comparten la misma sintaxis básica que se ha descrito anteriormente.</span><span class="sxs-lookup"><span data-stu-id="29559-120">All connection strings share the same basic syntax described above.</span></span> <span data-ttu-id="29559-121">El conjunto de palabras clave reconocidos depende del proveedor, sin embargo y ha evolucionado durante los años desde las primeras API como *ODBC*.</span><span class="sxs-lookup"><span data-stu-id="29559-121">The set of recognized keywords depends on the provider, however, and has evolved over the years from earlier APIs such as *ODBC*.</span></span> <span data-ttu-id="29559-122">El *.NET Framework* proveedor de datos para *SQL Server* (`SqlClient`) es compatible con muchas palabras clave de API anteriores, pero es generalmente más flexible y acepta sinónimos para muchos de la cadena de conexión comunes palabras clave.</span><span class="sxs-lookup"><span data-stu-id="29559-122">The *.NET Framework* data provider for *SQL Server* (`SqlClient`) supports many keywords from older APIs, but is generally more flexible and accepts synonyms for many of the common connection string keywords.</span></span>

<span data-ttu-id="29559-123">Errores de escritura pueden provocar errores.</span><span class="sxs-lookup"><span data-stu-id="29559-123">Typing mistakes can cause errors.</span></span> <span data-ttu-id="29559-124">Por ejemplo, `Integrated Security=true` es válido, pero `IntegratedSecurity=true` produce un error.</span><span class="sxs-lookup"><span data-stu-id="29559-124">For example, `Integrated Security=true` is valid, but `IntegratedSecurity=true` causes an error.</span></span>

<span data-ttu-id="29559-125">Las cadenas de conexión creadas manualmente en tiempo de ejecución desde una entrada de usuario son vulnerables a ataques por inyección de cadenas y poner en peligro la seguridad en el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="29559-125">Connection strings constructed manually at run time from unvalidated user input are vulnerable to string-injection attacks and jeopardize security at the data source.</span></span> <span data-ttu-id="29559-126">Para abordar estos problemas, *ADO.NET* 2.0 introducidas [generadores de cadenas de conexión](../../../../docs/framework/data/adonet/connection-string-builders.md) para cada *.NET Framework* proveedor de datos.</span><span class="sxs-lookup"><span data-stu-id="29559-126">To address these problems, *ADO.NET* 2.0 introduced [connection string builders](../../../../docs/framework/data/adonet/connection-string-builders.md) for each *.NET Framework* data provider.</span></span> <span data-ttu-id="29559-127">Estos generadores de cadenas de conexión exponen parámetros como propiedades fuertemente tipadas y hacen posible validar la cadena de conexión antes de enviarla al origen de datos.</span><span class="sxs-lookup"><span data-stu-id="29559-127">These connection string builders expose parameters as strongly-typed properties, and make it possible to validate the connection string before it's sent to the data source.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="29559-128">En esta sección</span><span class="sxs-lookup"><span data-stu-id="29559-128">In This Section</span></span>

<span data-ttu-id="29559-129">[Generadores de cadenas de conexión](../../../../docs/framework/data/adonet/connection-string-builders.md)\\</span><span class="sxs-lookup"><span data-stu-id="29559-129">[Connection String Builders](../../../../docs/framework/data/adonet/connection-string-builders.md)\\</span></span>
<span data-ttu-id="29559-130">Muestra cómo usar las clases `ConnectionStringBuilder` para construir cadenas de conexión válidas en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="29559-130">Demonstrates how to use the `ConnectionStringBuilder` classes to construct valid connection strings at run time.</span></span>

<span data-ttu-id="29559-131">[Las cadenas de conexión y archivos de configuración](../../../../docs/framework/data/adonet/connection-strings-and-configuration-files.md)\\</span><span class="sxs-lookup"><span data-stu-id="29559-131">[Connection Strings and Configuration Files](../../../../docs/framework/data/adonet/connection-strings-and-configuration-files.md)\\</span></span>
<span data-ttu-id="29559-132">Muestra cómo almacenar y recuperar cadenas de conexión en archivos de configuración.</span><span class="sxs-lookup"><span data-stu-id="29559-132">Demonstrates how to store and retrieve connection strings in configuration files.</span></span>

<span data-ttu-id="29559-133">[Sintaxis de la cadena de conexión](../../../../docs/framework/data/adonet/connection-string-syntax.md)\\</span><span class="sxs-lookup"><span data-stu-id="29559-133">[Connection String Syntax](../../../../docs/framework/data/adonet/connection-string-syntax.md)\\</span></span>
<span data-ttu-id="29559-134">Describe cómo configurar cadenas de conexión específicas de proveedor para `SqlClient`, `OracleClient`, `OleDb` y `Odbc`.</span><span class="sxs-lookup"><span data-stu-id="29559-134">Describes how to configure provider-specific connection strings for `SqlClient`, `OracleClient`, `OleDb`, and `Odbc`.</span></span>

<span data-ttu-id="29559-135">[Protección de la información de conexión](../../../../docs/framework/data/adonet/protecting-connection-information.md)\\</span><span class="sxs-lookup"><span data-stu-id="29559-135">[Protecting Connection Information](../../../../docs/framework/data/adonet/protecting-connection-information.md)\\</span></span>
<span data-ttu-id="29559-136">Muestra técnicas de protección de la información utilizada para conectarse a un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="29559-136">Demonstrates techniques for protecting information used to connect to a data source.</span></span>

## <a name="see-also"></a><span data-ttu-id="29559-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="29559-137">See also</span></span>

- [<span data-ttu-id="29559-138">Conexión a un origen de datos</span><span class="sxs-lookup"><span data-stu-id="29559-138">Connecting to a Data Source</span></span>](/cpp/data/odbc/connecting-to-a-data-source)
- [<span data-ttu-id="29559-139">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="29559-139">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
