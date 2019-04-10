---
title: Ejemplo de tecnología de serialización básica
ms.date: 03/30/2017
ms.assetid: 9d824e16-08d1-4a36-bc7f-2388c1f75f34
ms.openlocfilehash: dc190a93e45bf2b682aff0158ccd42bc09762d9a
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59315015"
---
# <a name="basic-serialization-technology-sample"></a><span data-ttu-id="f2ed8-102">Ejemplo de tecnología de serialización básica</span><span class="sxs-lookup"><span data-stu-id="f2ed8-102">Basic Serialization Technology Sample</span></span>
[<span data-ttu-id="f2ed8-103">Descargar ejemplo</span><span class="sxs-lookup"><span data-stu-id="f2ed8-103">Download sample</span></span>](https://download.microsoft.com/download/4/7/B/47B2164C-E780-4B10-8DE4-2CB5B886E0A6/Technologies/Serialization/Runtime%20Serialization/Basic.zip.exe)  
  
 <span data-ttu-id="f2ed8-104">En este ejemplo se demuestra la capacidad de Common Language Runtime para serializar un gráfico de objetos de la memoria en una secuencia.</span><span class="sxs-lookup"><span data-stu-id="f2ed8-104">This sample demonstrates the common language runtime's ability to serialize an object graph in memory to a stream.</span></span> <span data-ttu-id="f2ed8-105">En este ejemplo se puede utilizar <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> o <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> para la serialización.</span><span class="sxs-lookup"><span data-stu-id="f2ed8-105">This sample can use either the <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> or the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> for serialization.</span></span> <span data-ttu-id="f2ed8-106">Se serializa o deserializa una lista vinculada, llena de datos, desde o hacia una secuencia del archivo.</span><span class="sxs-lookup"><span data-stu-id="f2ed8-106">A linked list, filled with data, is serialized or deserialized to or from a file stream.</span></span> <span data-ttu-id="f2ed8-107">En cualquier caso, se muestra la lista para que pueda ver los resultados.</span><span class="sxs-lookup"><span data-stu-id="f2ed8-107">In either case the list is displayed so that you can see the results.</span></span> <span data-ttu-id="f2ed8-108">La lista vinculada es de tipo `LinkedList`, un tipo definido por este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="f2ed8-108">The linked list is of type `LinkedList`, a type defined by this sample.</span></span>  
  
 <span data-ttu-id="f2ed8-109">Para obtener más información sobre la serialización, revise los comentarios de los archivos de código fuente y de build.proj.</span><span class="sxs-lookup"><span data-stu-id="f2ed8-109">Review comments in the source code and build.proj files for more information on serialization.</span></span>  
  
### <a name="to-build-the-sample-using-the-command-prompt"></a><span data-ttu-id="f2ed8-110">Para generar el ejemplo desde el símbolo del sistema</span><span class="sxs-lookup"><span data-stu-id="f2ed8-110">To build the sample using the Command Prompt</span></span>  
  
1. <span data-ttu-id="f2ed8-111">Navegue hasta uno de los subdirectorios específicos de lenguaje bajo el directorio Technologies\Serialization\Runtime Serialization\Basic, utilizando el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="f2ed8-111">Navigate to one of the language-specific subdirectories under the Technologies\Serialization\Runtime Serialization\Basic directory, using the command prompt.</span></span>  
  
2. <span data-ttu-id="f2ed8-112">Escriba **msbuild SerializationCS.sln**, **msbuild SerializationJSL.sln** o **msbuild SerializationVB.sln**, según el lenguaje de programación que prefiera, en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="f2ed8-112">Type **msbuild SerializationCS.sln**, **msbuild SerializationJSL.sln** or **msbuild SerializationVB.sln**, depending on your choice of programming language, at the command line.</span></span>  
  
### <a name="to-build-the-sample-using-visual-studio"></a><span data-ttu-id="f2ed8-113">Para compilar el ejemplo con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f2ed8-113">To build the sample using Visual Studio</span></span>  
  
1. <span data-ttu-id="f2ed8-114">Abra [!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)] y navegue hasta uno de los subdirectorios específicos del lenguaje del ejemplo.</span><span class="sxs-lookup"><span data-stu-id="f2ed8-114">Open [!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)] and navigate to one of the language-specific subdirectories for the sample.</span></span>  
  
2. <span data-ttu-id="f2ed8-115">Haga doble clic en el icono del archivo SerializationCS.sln, SerializationJSL.sln o SerializationVB.sln, dependiendo del lenguaje de programación elegido, para abrir el archivo en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f2ed8-115">Double-click the icon for the SerializationCS.sln, SerializationJSL.sln or SerializationVB.sln file, depending on your choice of programming language, to open the file in Visual Studio.</span></span>  
  
3. <span data-ttu-id="f2ed8-116">En el menú **Compilar**, seleccione **Compilar solución**.</span><span class="sxs-lookup"><span data-stu-id="f2ed8-116">In the **Build** menu, select **Build Solution**.</span></span>  
  
 <span data-ttu-id="f2ed8-117">La aplicación de ejemplo se generará en el subdirectorio predeterminado \bin o \bin\Debug.</span><span class="sxs-lookup"><span data-stu-id="f2ed8-117">The sample application will be built in the default \bin or \bin\Debug subdirectory.</span></span>  
  
### <a name="to-run-the-sample"></a><span data-ttu-id="f2ed8-118">Para ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="f2ed8-118">To run the sample</span></span>  
  
1. <span data-ttu-id="f2ed8-119">Navegue hasta el directorio que contiene el ejecutable generado.</span><span class="sxs-lookup"><span data-stu-id="f2ed8-119">Navigate to the directory containing the built executable.</span></span>  
  
2. <span data-ttu-id="f2ed8-120">Escriba **Serialization.exe**, junto con los valores de parámetro que quiera, en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="f2ed8-120">Type **Serialization.exe**, along with the parameter values you desire, at the command line.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f2ed8-121">En este ejemplo se genera una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="f2ed8-121">This sample builds a console application.</span></span> <span data-ttu-id="f2ed8-122">Para poder ver el resultado, debe iniciarla desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="f2ed8-122">You must launch it using the command prompt in order to view its output.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f2ed8-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f2ed8-123">Remarks</span></span>  
 <span data-ttu-id="f2ed8-124">La aplicación de ejemplo acepta parámetros de línea de comandos que indican qué comprobación desea ejecutar.</span><span class="sxs-lookup"><span data-stu-id="f2ed8-124">The sample application accepts command line parameters indicating which test you would like to execute.</span></span> <span data-ttu-id="f2ed8-125">Para serializar una lista de 10 nodos en un archivo denominado **Test.xml** mediante el formateador SOAP, use los parámetros **sx Test.xml 10**.</span><span class="sxs-lookup"><span data-stu-id="f2ed8-125">To serialize a 10-node list to a file named **Test.xml** using the SOAP formatter, use the parameters **sx Test.xml 10**.</span></span>  
  
 <span data-ttu-id="f2ed8-126">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f2ed8-126">For Example:</span></span>  
  
 **<span data-ttu-id="f2ed8-127">Serialize.exe - sx Test.xml 10</span><span class="sxs-lookup"><span data-stu-id="f2ed8-127">Serialize.exe -sx Test.xml 10</span></span>**  
  
 <span data-ttu-id="f2ed8-128">Para deserializar el archivo **Test.xml** del ejemplo anterior, use los parámetros **dx Test.xml**.</span><span class="sxs-lookup"><span data-stu-id="f2ed8-128">To deserialize the **Test.xml** file from the previous example, use the parameters **dx Test.xml**.</span></span>  
  
 <span data-ttu-id="f2ed8-129">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f2ed8-129">For Example:</span></span>  
  
 **<span data-ttu-id="f2ed8-130">Serialize.exe - dx Test.xml</span><span class="sxs-lookup"><span data-stu-id="f2ed8-130">Serialize.exe -dx Test.xml</span></span>**  
  
 <span data-ttu-id="f2ed8-131">En los dos ejemplos anteriores, la "x" en el modificador de la línea de comandos indica que desea realizar una serialización de XML SOAP.</span><span class="sxs-lookup"><span data-stu-id="f2ed8-131">In the two examples above, the "x" in the command line switch indicates that you want XML SOAP serialization.</span></span> <span data-ttu-id="f2ed8-132">Puede utilizar "b" en su lugar para utilizar la serialización binaria.</span><span class="sxs-lookup"><span data-stu-id="f2ed8-132">You can use "b" in its place to use binary serialization.</span></span> <span data-ttu-id="f2ed8-133">Si desea realizar la serialización con un gran número de nodos, puede que prefiera redirigir el resultado de la consola a un archivo.</span><span class="sxs-lookup"><span data-stu-id="f2ed8-133">If you wish to try serialization with a very large number of nodes, you might want to redirect the console output to a file.</span></span>  
  
 <span data-ttu-id="f2ed8-134">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f2ed8-134">For Example:</span></span>  
  
 **<span data-ttu-id="f2ed8-135">Serialize.exe -sb Test.bin 10000 >somefile.txt</span><span class="sxs-lookup"><span data-stu-id="f2ed8-135">Serialize.exe -sb Test.bin 10000 >somefile.txt</span></span>**  
  
 <span data-ttu-id="f2ed8-136">Las viñetas siguientes describen brevemente las clases y las tecnologías que se utilizan en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="f2ed8-136">The following bullets briefly describe the classes and technologies used by this sample.</span></span>  
  
-   <span data-ttu-id="f2ed8-137">Serialización en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="f2ed8-137">Runtime Serialization</span></span>  
  
    -   <xref:System.Runtime.Serialization.IFormatter> <span data-ttu-id="f2ed8-138">Usar para hacer referencia a un <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> o un <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> objeto.</span><span class="sxs-lookup"><span data-stu-id="f2ed8-138">Used to refer to either a <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> or a <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> object.</span></span>  
  
    -   <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> <span data-ttu-id="f2ed8-139">Usado para serializar una lista vinculada a una secuencia en un formato binario.</span><span class="sxs-lookup"><span data-stu-id="f2ed8-139">Used to serialize a linked list to a stream in a binary format.</span></span> <span data-ttu-id="f2ed8-140">El formateador binario utiliza un formato que solo entiende el tipo <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>.</span><span class="sxs-lookup"><span data-stu-id="f2ed8-140">The binary formatter uses a format that only the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> type understands.</span></span> <span data-ttu-id="f2ed8-141">Sin embargo, los datos son concisos.</span><span class="sxs-lookup"><span data-stu-id="f2ed8-141">However, the data is concise.</span></span>  
  
    -   <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> <span data-ttu-id="f2ed8-142">Usado para serializar una lista vinculada a una secuencia en formato SOAP.</span><span class="sxs-lookup"><span data-stu-id="f2ed8-142">Used to serialize a linked list to a stream in the SOAP format.</span></span> <span data-ttu-id="f2ed8-143">SOAP es un formato estándar.</span><span class="sxs-lookup"><span data-stu-id="f2ed8-143">SOAP is a standard format.</span></span>  
  
-   <span data-ttu-id="f2ed8-144">E/S de secuencia</span><span class="sxs-lookup"><span data-stu-id="f2ed8-144">Stream I/O</span></span>  
  
    -   <xref:System.IO.Stream> <span data-ttu-id="f2ed8-145">Se utiliza para serializar y deserializar.</span><span class="sxs-lookup"><span data-stu-id="f2ed8-145">Used to serialize and deserialize.</span></span> <span data-ttu-id="f2ed8-146">El tipo de secuencia concreto utilizado en este ejemplo es el tipo <xref:System.IO.FileStream>.</span><span class="sxs-lookup"><span data-stu-id="f2ed8-146">The specific stream type used in this sample is the <xref:System.IO.FileStream> type.</span></span> <span data-ttu-id="f2ed8-147">Sin embargo, la serialización se puede utilizar con cualquier tipo derivado de <xref:System.IO.Stream>.</span><span class="sxs-lookup"><span data-stu-id="f2ed8-147">However, serialization can be used with any type derived from <xref:System.IO.Stream>.</span></span>  
  
    -   <xref:System.IO.File> <span data-ttu-id="f2ed8-148">Utilizado para crear <xref:System.IO.FileStream> objetos para leer y crear archivos en disco.</span><span class="sxs-lookup"><span data-stu-id="f2ed8-148">Used to create <xref:System.IO.FileStream> objects for reading and creating files on disk.</span></span>  
  
    -   <xref:System.IO.FileStream> <span data-ttu-id="f2ed8-149">Se utiliza para serializar y deserializar las listas vinculadas.</span><span class="sxs-lookup"><span data-stu-id="f2ed8-149">Used to serialize and deserialize linked lists.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2ed8-150">Vea también</span><span class="sxs-lookup"><span data-stu-id="f2ed8-150">See also</span></span>

- <xref:System.IO>
- <xref:System.IO.File>
- <xref:System.IO.FileStream>
- <xref:System.IO.Stream>
- <xref:System.Random>
- <xref:System.Runtime.Serialization>
- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>
- <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>
- <xref:System.Runtime.Serialization.IFormatter>
- <xref:System.SerializableAttribute>
- <xref:System.Xml.Serialization>
- [<span data-ttu-id="f2ed8-151">Serialización básica</span><span class="sxs-lookup"><span data-stu-id="f2ed8-151">Basic Serialization</span></span>](../../../docs/standard/serialization/basic-serialization.md)
- [<span data-ttu-id="f2ed8-152">Serialización binaria</span><span class="sxs-lookup"><span data-stu-id="f2ed8-152">Binary Serialization</span></span>](../../../docs/standard/serialization/binary-serialization.md)
- [<span data-ttu-id="f2ed8-153">Controlar la serialización XML mediante atributos</span><span class="sxs-lookup"><span data-stu-id="f2ed8-153">Controlling XML Serialization Using Attributes</span></span>](../../../docs/standard/serialization/controlling-xml-serialization-using-attributes.md)
- [<span data-ttu-id="f2ed8-154">Introducir la serialización XML</span><span class="sxs-lookup"><span data-stu-id="f2ed8-154">Introducing XML Serialization</span></span>](../../../docs/standard/serialization/introducing-xml-serialization.md)
- [<span data-ttu-id="f2ed8-155">Serialización</span><span class="sxs-lookup"><span data-stu-id="f2ed8-155">Serialization</span></span>](../../../docs/standard/serialization/index.md)
- [<span data-ttu-id="f2ed8-156">Serialización de SOAP y XML</span><span class="sxs-lookup"><span data-stu-id="f2ed8-156">XML and SOAP Serialization</span></span>](../../../docs/standard/serialization/xml-and-soap-serialization.md)
