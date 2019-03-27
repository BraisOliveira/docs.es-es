---
title: Predicción de precios mediante un aprendiz de regresión con ML.NET
description: Prediga precios mediante un aprendiz de regresión con ML.NET.
author: aditidugar
ms.author: johalex
ms.date: 03/20/2019
ms.topic: tutorial
ms.custom: mvc, seodec18
ms.openlocfilehash: 0a027b3b4930f7dda48d884faf0484cf33856c8d
ms.sourcegitcommit: 77854e8704b9689b73103d691db34d71c2bf1dad
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/21/2019
ms.locfileid: "58307985"
---
# <a name="tutorial-predict-prices-using-a-regression-learner-with-mlnet"></a><span data-ttu-id="acecc-103">Tutorial: Predicción de precios mediante un aprendiz de regresión con ML.NET</span><span class="sxs-lookup"><span data-stu-id="acecc-103">Tutorial: Predict prices using a regression learner with ML.NET</span></span>

<span data-ttu-id="acecc-104">En este tutorial se muestra cómo usar ML.NET para generar un [modelo de regresión](../resources/glossary.md#regression) para predecir precios, en concreto las tarifas de taxi de Nueva York.</span><span class="sxs-lookup"><span data-stu-id="acecc-104">This tutorial illustrates how to use ML.NET to build a [regression model](../resources/glossary.md#regression) for predicting prices, specifically, New York City taxi fares.</span></span>

> [!NOTE]
> <span data-ttu-id="acecc-105">Este tema hace referencia a ML.NET, que se encuentra actualmente en versión preliminar, por lo que el material está sujeto a cambios.</span><span class="sxs-lookup"><span data-stu-id="acecc-105">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="acecc-106">Para obtener más información, vea [la introducción de ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="acecc-106">For more information, see the [ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="acecc-107">Este tutorial y el ejemplo relacionado usan actualmente **ML.NET en su versión 0.11**.</span><span class="sxs-lookup"><span data-stu-id="acecc-107">This tutorial and related sample are currently using **ML.NET version 0.11**.</span></span> <span data-ttu-id="acecc-108">Para obtener más información, consulte las notas de la versión en el [repositorio de GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span><span class="sxs-lookup"><span data-stu-id="acecc-108">For more information, see the release notes at the [dotnet/machinelearning GitHub repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

<span data-ttu-id="acecc-109">En este tutorial aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="acecc-109">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="acecc-110">Entender el problema</span><span class="sxs-lookup"><span data-stu-id="acecc-110">Understand the problem</span></span>
> * <span data-ttu-id="acecc-111">Seleccionar la tarea de aprendizaje automático adecuada</span><span class="sxs-lookup"><span data-stu-id="acecc-111">Select the appropriate machine learning task</span></span>
> * <span data-ttu-id="acecc-112">Preparar y entender los datos</span><span class="sxs-lookup"><span data-stu-id="acecc-112">Prepare and understand the data</span></span>
> * <span data-ttu-id="acecc-113">Crear una canalización de aprendizaje</span><span class="sxs-lookup"><span data-stu-id="acecc-113">Create a learning pipeline</span></span>
> * <span data-ttu-id="acecc-114">Cargar y transformar los datos</span><span class="sxs-lookup"><span data-stu-id="acecc-114">Load and transform the data</span></span>
> * <span data-ttu-id="acecc-115">Elegir un algoritmo de aprendizaje</span><span class="sxs-lookup"><span data-stu-id="acecc-115">Choose a learning algorithm</span></span>
> * <span data-ttu-id="acecc-116">Entrenar el modelo</span><span class="sxs-lookup"><span data-stu-id="acecc-116">Train the model</span></span>
> * <span data-ttu-id="acecc-117">Evaluar el modelo</span><span class="sxs-lookup"><span data-stu-id="acecc-117">Evaluate the model</span></span>
> * <span data-ttu-id="acecc-118">Usar el modelo para las predicciones</span><span class="sxs-lookup"><span data-stu-id="acecc-118">Use the model for predictions</span></span>

## <a name="prerequisites"></a><span data-ttu-id="acecc-119">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="acecc-119">Prerequisites</span></span>

* <span data-ttu-id="acecc-120">[Visual Studio 2017 15.6 o posterior](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) con la carga de trabajo "Desarrollo multiplataforma de .NET Core" instalada.</span><span class="sxs-lookup"><span data-stu-id="acecc-120">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

## <a name="understand-the-problem"></a><span data-ttu-id="acecc-121">Entender el problema</span><span class="sxs-lookup"><span data-stu-id="acecc-121">Understand the problem</span></span>

<span data-ttu-id="acecc-122">Este problema trata sobre la predicción de la tarifa de una carrera de taxi en Nueva York.</span><span class="sxs-lookup"><span data-stu-id="acecc-122">This problem is about predicting the fare of a taxi trip in New York City.</span></span> <span data-ttu-id="acecc-123">A primera vista, puede parecer que simplemente depende de la distancia recorrida.</span><span class="sxs-lookup"><span data-stu-id="acecc-123">At first glance, it may seem to depend simply on the distance traveled.</span></span> <span data-ttu-id="acecc-124">Sin embargo, los taxistas de Nueva York cobran distintas cantidades por otros factores, como llevar pasajeros adicionales o pagar con tarjeta de crédito en lugar de efectivo.</span><span class="sxs-lookup"><span data-stu-id="acecc-124">However, taxi vendors in New York charge varying amounts for other factors such as additional passengers or paying with a credit card instead of cash.</span></span>

## <a name="select-the-appropriate-machine-learning-task"></a><span data-ttu-id="acecc-125">Seleccionar la tarea de aprendizaje automático adecuada</span><span class="sxs-lookup"><span data-stu-id="acecc-125">Select the appropriate machine learning task</span></span>

<span data-ttu-id="acecc-126">Se quiere predecir el precio, que es un valor real, en función de los demás factores del conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="acecc-126">You want to predict the price value, which is a real value, based on the other factors in the data set.</span></span> <span data-ttu-id="acecc-127">Para ello, elija una tarea de aprendizaje automático de [regresión](../resources/glossary.md#regression).</span><span class="sxs-lookup"><span data-stu-id="acecc-127">To do that you choose a [regression](../resources/glossary.md#regression) machine learning task.</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="acecc-128">Creación de una aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="acecc-128">Create a console application</span></span>

1. <span data-ttu-id="acecc-129">Abra Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="acecc-129">Open Visual Studio 2017.</span></span> <span data-ttu-id="acecc-130">Seleccione **Archivo** > **Nuevo** > **Proyecto** de la barra de menús.</span><span class="sxs-lookup"><span data-stu-id="acecc-130">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="acecc-131">En el cuadro de diálogo **Nuevo proyecto**, seleccione el nodo **Visual C#** seguido del nodo **.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="acecc-131">In the **New Project** dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="acecc-132">Después, seleccione la plantilla del proyecto **Aplicación de consola (.NET Core)**.</span><span class="sxs-lookup"><span data-stu-id="acecc-132">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="acecc-133">En el cuadro de texto **Nombre**, escriba "TaxiFarePrediction" y después haga clic en el botón **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="acecc-133">In the **Name** text box, type "TaxiFarePrediction" and then select the **OK** button.</span></span>

1. <span data-ttu-id="acecc-134">Cree un directorio denominado *Datos* en el proyecto para almacenar el conjunto de datos y los archivos del modelo:</span><span class="sxs-lookup"><span data-stu-id="acecc-134">Create a directory named *Data* in your project to store the data set and model files:</span></span>

    <span data-ttu-id="acecc-135">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y seleccione **Agregar** > **Nueva carpeta**.</span><span class="sxs-lookup"><span data-stu-id="acecc-135">In **Solution Explorer**, right-click the project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="acecc-136">Escriba "Datos" y presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="acecc-136">Type "Data" and hit Enter.</span></span>

1. <span data-ttu-id="acecc-137">Instale el paquete NuGet **Microsoft.ML**:</span><span class="sxs-lookup"><span data-stu-id="acecc-137">Install the **Microsoft.ML** NuGet Package:</span></span>

    <span data-ttu-id="acecc-138">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y seleccione **Administrar paquetes NuGet**.</span><span class="sxs-lookup"><span data-stu-id="acecc-138">In **Solution Explorer**, right-click the project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="acecc-139">Elija "nuget.org" como origen del paquete, seleccione la pestaña **Examinar**, busque **Microsoft.ML**, seleccione ese paquete en la lista y haga clic en el botón **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="acecc-139">Choose "nuget.org" as the Package source, select the **Browse** tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="acecc-140">Seleccione el botón **Aceptar** en el cuadro de diálogo **Vista previa de cambios** y, a continuación, seleccione el botón **Acepto** del cuadro de diálogo **Aceptación de la licencia** en caso de que esté de acuerdo con los términos de licencia de los paquetes mostrados.</span><span class="sxs-lookup"><span data-stu-id="acecc-140">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

## <a name="prepare-and-understand-the-data"></a><span data-ttu-id="acecc-141">Preparar y entender los datos</span><span class="sxs-lookup"><span data-stu-id="acecc-141">Prepare and understand the data</span></span>

1. <span data-ttu-id="acecc-142">Descargue los conjuntos de datos [taxi-fare-train.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-train.csv) y [taxi-fare-test.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-test.csv) y guárdelos en la carpeta *Datos* que ha creado en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="acecc-142">Download the [taxi-fare-train.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-train.csv) and the [taxi-fare-test.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-test.csv) data sets and save them to the *Data* folder you've created at the previous step.</span></span> <span data-ttu-id="acecc-143">Usaremos estos conjuntos de datos para entrenar el modelo de aprendizaje automático y, después, evaluar su precisión.</span><span class="sxs-lookup"><span data-stu-id="acecc-143">We use these data sets to train the machine learning model and then evaluate how accurate the model is.</span></span> <span data-ttu-id="acecc-144">Estos conjuntos de datos proceden originalmente del [conjunto de datos NYC TLC Taxi Trip](http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml).</span><span class="sxs-lookup"><span data-stu-id="acecc-144">These data sets are originally from the [NYC TLC Taxi Trip data set](http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml).</span></span>

1. <span data-ttu-id="acecc-145">En el **Explorador de soluciones**, haga clic con el botón derecho en cada uno de los archivos \*.csv y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="acecc-145">In **Solution Explorer**, right-click each of the \*.csv files and select **Properties**.</span></span> <span data-ttu-id="acecc-146">En **Avanzadas**, cambie el valor de **Copiar en el directorio de salida** por **Copiar si es posterior**.</span><span class="sxs-lookup"><span data-stu-id="acecc-146">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

1. <span data-ttu-id="acecc-147">Abra el conjunto de datos **taxi-fare-train.csv** y consulte los encabezados de columna de la primera fila.</span><span class="sxs-lookup"><span data-stu-id="acecc-147">Open the **taxi-fare-train.csv** data set and look at column headers in the first row.</span></span> <span data-ttu-id="acecc-148">Eche un vistazo a cada una de las columnas.</span><span class="sxs-lookup"><span data-stu-id="acecc-148">Take a look at each of the columns.</span></span> <span data-ttu-id="acecc-149">Estudie los datos y decida qué columnas son **características** y cuál es la **etiqueta**.</span><span class="sxs-lookup"><span data-stu-id="acecc-149">Understand the data and decide which columns are **features** and which one is the **label**.</span></span>

<span data-ttu-id="acecc-150">La **etiqueta** es el identificador de la columna que quiere predecir.</span><span class="sxs-lookup"><span data-stu-id="acecc-150">The **label** is the identifier of the column you want to predict.</span></span> <span data-ttu-id="acecc-151">Las **características** identificadas se usan para predecir la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="acecc-151">The identified **features** are used to predict the label.</span></span>

<span data-ttu-id="acecc-152">El conjunto de datos proporcionado contiene las columnas siguientes:</span><span class="sxs-lookup"><span data-stu-id="acecc-152">The provided data set contains the following columns:</span></span>

* <span data-ttu-id="acecc-153">**vendor_id:** el identificador del taxista es una característica.</span><span class="sxs-lookup"><span data-stu-id="acecc-153">**vendor_id:** The ID of the taxi vendor is a feature.</span></span>
* <span data-ttu-id="acecc-154">**rate_code:** el tipo de tarifa del viaje en taxi es una característica.</span><span class="sxs-lookup"><span data-stu-id="acecc-154">**rate_code:** The rate type of the taxi trip is a feature.</span></span>
* <span data-ttu-id="acecc-155">**passenger_count:** el número de pasajeros en el recorrido es una característica.</span><span class="sxs-lookup"><span data-stu-id="acecc-155">**passenger_count:** The number of passengers on the trip is a feature.</span></span>
* <span data-ttu-id="acecc-156">**trip_time_in_secs:** la cantidad de tiempo que tardó el viaje.</span><span class="sxs-lookup"><span data-stu-id="acecc-156">**trip_time_in_secs:** The amount of time the trip took.</span></span> <span data-ttu-id="acecc-157">Por ejemplo, si quiere calcular la tarifa del viaje antes de que termine</span><span class="sxs-lookup"><span data-stu-id="acecc-157">You want to predict the fare of the trip before the trip is completed.</span></span> <span data-ttu-id="acecc-158">y aún no conoce la duración del viaje,</span><span class="sxs-lookup"><span data-stu-id="acecc-158">At that moment you don't know how long the trip would take.</span></span> <span data-ttu-id="acecc-159">el tiempo del viaje no es una característica, por lo que deberá excluir esta columna del modelo.</span><span class="sxs-lookup"><span data-stu-id="acecc-159">Thus, the trip time is not a feature and you'll exclude this column from the model.</span></span>
* <span data-ttu-id="acecc-160">**trip_distance:** la distancia del viaje es una característica.</span><span class="sxs-lookup"><span data-stu-id="acecc-160">**trip_distance:** The distance of the trip is a feature.</span></span>
* <span data-ttu-id="acecc-161">**payment_type:** el método de pago (efectivo o tarjeta de crédito) es una característica.</span><span class="sxs-lookup"><span data-stu-id="acecc-161">**payment_type:** The payment method (cash or credit card) is a feature.</span></span>
* <span data-ttu-id="acecc-162">**fare_amount:** la tarifa de taxi total pagada es la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="acecc-162">**fare_amount:** The total taxi fare paid is the label.</span></span>

## <a name="create-data-classes"></a><span data-ttu-id="acecc-163">Crear clases de datos</span><span class="sxs-lookup"><span data-stu-id="acecc-163">Create data classes</span></span>

<span data-ttu-id="acecc-164">Cree clases para los datos de entrada y las predicciones:</span><span class="sxs-lookup"><span data-stu-id="acecc-164">Create classes for the input data and the predictions:</span></span>

1. <span data-ttu-id="acecc-165">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto y, a continuación, seleccione **Agregar** > **Nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="acecc-165">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="acecc-166">En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Clase** y cambie el campo **Nombre** a *TaxiTrip.cs*.</span><span class="sxs-lookup"><span data-stu-id="acecc-166">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *TaxiTrip.cs*.</span></span> <span data-ttu-id="acecc-167">A continuación, seleccione el botón **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="acecc-167">Then, select the **Add** button.</span></span>
1. <span data-ttu-id="acecc-168">Agregue las siguientes directivas `using` al nuevo archivo:</span><span class="sxs-lookup"><span data-stu-id="acecc-168">Add the following `using` directives to the new file:</span></span>

   [!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TaxiTrip.cs#1 "Add necessary usings")]

<span data-ttu-id="acecc-169">Quite la definición de clase existente y agregue el código siguiente, que tiene dos clases `TaxiTrip` y `TaxiTripFarePrediction`, al archivo *TaxiTrip.cs*:</span><span class="sxs-lookup"><span data-stu-id="acecc-169">Remove the existing class definition and add the following code, which has two classes `TaxiTrip` and `TaxiTripFarePrediction`, to the *TaxiTrip.cs* file:</span></span>

[!code-csharp[DefineTaxiTrip](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TaxiTrip.cs#2 "Define the taxi trip and fare predictions classes")]

<span data-ttu-id="acecc-170">`TaxiTrip` es la clase de datos de entrada y tiene definiciones para cada una de las columnas del conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="acecc-170">`TaxiTrip` is the input data class and has definitions for each of the data set columns.</span></span> <span data-ttu-id="acecc-171">Use el atributo <xref:Microsoft.ML.Data.LoadColumnAttribute> para especificar los índices de las columnas de origen en el conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="acecc-171">Use the <xref:Microsoft.ML.Data.LoadColumnAttribute> attribute to specify the indices of the source columns in the data set.</span></span>

<span data-ttu-id="acecc-172">La clase `TaxiTripFarePrediction` representa los resultados predichos.</span><span class="sxs-lookup"><span data-stu-id="acecc-172">The `TaxiTripFarePrediction` class represents predicted results.</span></span> <span data-ttu-id="acecc-173">Tiene un único campo flotante, `FareAmount`, con un atributo `Score` <xref:Microsoft.ML.Data.ColumnNameAttribute> aplicado.</span><span class="sxs-lookup"><span data-stu-id="acecc-173">It has a single float field, `FareAmount`, with a `Score` <xref:Microsoft.ML.Data.ColumnNameAttribute> attribute applied.</span></span> <span data-ttu-id="acecc-174">En el caso de la tarea de regresión, la columna **Score** contiene valores de etiqueta predichos.</span><span class="sxs-lookup"><span data-stu-id="acecc-174">In case of the regression task the **Score** column contains predicted label values.</span></span>

> [!NOTE]
> <span data-ttu-id="acecc-175">Use el tipo `float` para representar los valores de punto flotante en las clases de entrada y predicción de datos.</span><span class="sxs-lookup"><span data-stu-id="acecc-175">Use the `float` type to represent floating-point values in the input and prediction data classes.</span></span>

## <a name="define-data-and-model-paths"></a><span data-ttu-id="acecc-176">Definir rutas de acceso de datos y modelos</span><span class="sxs-lookup"><span data-stu-id="acecc-176">Define data and model paths</span></span>

<span data-ttu-id="acecc-177">Agregue las siguientes instrucciones `using` adicionales a la parte superior del archivo *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="acecc-177">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#1 "Add necessary usings")]

<span data-ttu-id="acecc-178">Deberá crear tres campos que contengan las rutas de acceso a los archivos con los conjuntos de datos y el archivo para guardar el modelo:</span><span class="sxs-lookup"><span data-stu-id="acecc-178">You need to create three fields to hold the paths to the files with data sets and the file to save the model:</span></span>

* <span data-ttu-id="acecc-179">`_trainDataPath` contiene la ruta de acceso al archivo con el conjunto de datos utilizado para entrenar el modelo.</span><span class="sxs-lookup"><span data-stu-id="acecc-179">`_trainDataPath` contains the path to the file with the data set used to train the model.</span></span>
* <span data-ttu-id="acecc-180">`_testDataPath` contiene la ruta de acceso al archivo con el conjunto de datos utilizado para evaluar el modelo.</span><span class="sxs-lookup"><span data-stu-id="acecc-180">`_testDataPath` contains the path to the file with the data set used to evaluate the model.</span></span>
* <span data-ttu-id="acecc-181">`_modelPath` contiene la ruta de acceso al archivo en el que se almacena el modelo entrenado.</span><span class="sxs-lookup"><span data-stu-id="acecc-181">`_modelPath` contains the path to the file where the trained model is stored.</span></span>

<span data-ttu-id="acecc-182">Agregue el código siguiente justo encima del método `Main` para especificar esas rutas de acceso y la variable `_textLoader`:</span><span class="sxs-lookup"><span data-stu-id="acecc-182">Add the following code right above the `Main` method to specify those paths and for the `_textLoader` variable:</span></span>

[!code-csharp[InitializePaths](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#2 "Define variables to store the data file paths")]

<span data-ttu-id="acecc-183">Cuando se crea un modelo con ML.NET se empieza creando un contexto de ML.</span><span class="sxs-lookup"><span data-stu-id="acecc-183">When building a model with ML.NET you start by creating an ML Context.</span></span> <span data-ttu-id="acecc-184">Esto es comparable conceptualmente a usar `DbContext` en Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="acecc-184">This is comparable conceptually to using `DbContext` in Entity Framework.</span></span> <span data-ttu-id="acecc-185">El entorno proporciona un contexto para el trabajo de aprendizaje automático que puede usarse para el seguimiento y registro de excepciones.</span><span class="sxs-lookup"><span data-stu-id="acecc-185">The environment provides a context for your machine learning job that can be used for exception tracking and logging.</span></span>

### <a name="initialize-variables-in-main"></a><span data-ttu-id="acecc-186">Inicializar variables en Main</span><span class="sxs-lookup"><span data-stu-id="acecc-186">Initialize variables in Main</span></span>

<span data-ttu-id="acecc-187">Cree una variable denominada `mlContext` e inicialícela con una nueva instancia de `MLContext`.</span><span class="sxs-lookup"><span data-stu-id="acecc-187">Create a variable called `mlContext` and initialize it with a new instance of `MLContext`.</span></span>  <span data-ttu-id="acecc-188">Reemplace la línea `Console.WriteLine("Hello World!")` por el código siguiente en el método `Main`:</span><span class="sxs-lookup"><span data-stu-id="acecc-188">Replace the `Console.WriteLine("Hello World!")` line with the following code in the `Main` method:</span></span>

[!code-csharp[CreateMLContext](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#3 "Create the ML Context")]

<span data-ttu-id="acecc-189">Agregue lo siguiente como la siguiente línea de código en el método `Main` para llamar al método `Train`:</span><span class="sxs-lookup"><span data-stu-id="acecc-189">Add the following as the next line of code in the `Main` method to call the `Train` method:</span></span>

[!code-csharp[Train](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#5 "Train your model")]

<span data-ttu-id="acecc-190">El método `Train` ejecuta las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="acecc-190">The `Train` method executes the following tasks:</span></span>

* <span data-ttu-id="acecc-191">Carga los datos.</span><span class="sxs-lookup"><span data-stu-id="acecc-191">Loads the data.</span></span>
* <span data-ttu-id="acecc-192">Extrae y transforma los datos.</span><span class="sxs-lookup"><span data-stu-id="acecc-192">Extracts and transforms the data.</span></span>
* <span data-ttu-id="acecc-193">Entrena el modelo.</span><span class="sxs-lookup"><span data-stu-id="acecc-193">Trains the model.</span></span>
* <span data-ttu-id="acecc-194">Guarda el modelo como un archivo ZIP.</span><span class="sxs-lookup"><span data-stu-id="acecc-194">Saves the model as .zip file.</span></span>
* <span data-ttu-id="acecc-195">Devuelve el modelo.</span><span class="sxs-lookup"><span data-stu-id="acecc-195">Returns the model.</span></span>

<span data-ttu-id="acecc-196">El método `Train` entrena el modelo.</span><span class="sxs-lookup"><span data-stu-id="acecc-196">The `Train` method trains the model.</span></span> <span data-ttu-id="acecc-197">Cree ese método justo debajo de `Main` utilizando el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="acecc-197">Create that method just below `Main`, using the following code:</span></span>

```csharp
public static ITransformer Train(MLContext mlContext, string dataPath)
{

}
```

<span data-ttu-id="acecc-198">Pasamos dos parámetros al método `Train`; `MLContext` para el contexto (`mlContext`) y una cadena para la ruta de acceso al conjunto de datos (`dataPath`).</span><span class="sxs-lookup"><span data-stu-id="acecc-198">We are passing two parameters into the `Train` method; an `MLContext` for the context (`mlContext`), and a string for the dataset path (`dataPath`).</span></span> <span data-ttu-id="acecc-199">Vamos a volver a usar este método para cargar los conjuntos de datos.</span><span class="sxs-lookup"><span data-stu-id="acecc-199">We're going to reuse this method for loading datasets.</span></span>

## <a name="load-and-transform-data"></a><span data-ttu-id="acecc-200">Cargar y transformar datos</span><span class="sxs-lookup"><span data-stu-id="acecc-200">Load and transform data</span></span>

<span data-ttu-id="acecc-201">Cargue los datos mediante el contenedor `MLContext.Data.LoadFromTextFile` para el [método LoadFromTextFile](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29).</span><span class="sxs-lookup"><span data-stu-id="acecc-201">Load the data using the `MLContext.Data.LoadFromTextFile` wrapper for the [LoadFromTextFile method](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29).</span></span> <span data-ttu-id="acecc-202">Devuelve <xref:Microsoft.Data.DataView.IDataView>.</span><span class="sxs-lookup"><span data-stu-id="acecc-202">It returns a <xref:Microsoft.Data.DataView.IDataView>.</span></span> 

<span data-ttu-id="acecc-203">Como la entrada y salida de `Transforms`, `DataView` es el tipo de canalización de datos fundamentales, comparable con `IEnumerable` para `LINQ`.</span><span class="sxs-lookup"><span data-stu-id="acecc-203">As the input and output of `Transforms`, a `DataView` is the fundamental data pipeline type, comparable to `IEnumerable` for `LINQ`.</span></span>

<span data-ttu-id="acecc-204">En ML.NET, los datos son similares a una vista SQL.</span><span class="sxs-lookup"><span data-stu-id="acecc-204">In ML.NET, data is similar to a SQL view.</span></span> <span data-ttu-id="acecc-205">Se evalúan lentamente, se esquematizan y son heterogéneos.</span><span class="sxs-lookup"><span data-stu-id="acecc-205">It is lazily evaluated, schematized, and heterogenous.</span></span> <span data-ttu-id="acecc-206">El objeto es la primera parte de la canalización y carga los datos.</span><span class="sxs-lookup"><span data-stu-id="acecc-206">The object is the first part of the pipeline, and loads the data.</span></span> <span data-ttu-id="acecc-207">Para este tutorial, carga un conjunto de datos con información sobre los precios de los viajes en taxi.</span><span class="sxs-lookup"><span data-stu-id="acecc-207">For this tutorial, it loads a dataset with taxi trip pricing information.</span></span> <span data-ttu-id="acecc-208">Esto se usa para crear el modelo y entrenarlo.</span><span class="sxs-lookup"><span data-stu-id="acecc-208">This is used to create the model, and train it.</span></span>

<span data-ttu-id="acecc-209">Agregue el código siguiente a la primera línea del método `Train`:</span><span class="sxs-lookup"><span data-stu-id="acecc-209">Add the following code as the first line of the `Train` method:</span></span>

[!code-csharp[LoadTrainData](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#6 "loading training dataset")]

<span data-ttu-id="acecc-210">En los pasos siguientes se hace referencia a las columnas con los nombres definidos en la clase `TaxiTrip`.</span><span class="sxs-lookup"><span data-stu-id="acecc-210">In the next steps we refer to the columns by the names defined in the `TaxiTrip` class.</span></span>

<span data-ttu-id="acecc-211">Si el modelo se ha entrenado y evaluado, de forma predeterminada, los valores de la columna **Label** se consideran valores correctos para predecir.</span><span class="sxs-lookup"><span data-stu-id="acecc-211">When the model is trained and evaluated, by default, the values in the **Label** column are considered as correct values to be predicted.</span></span> <span data-ttu-id="acecc-212">Para predecir la tarifa del viaje en taxi, debe copiar la columna `FareAmount` en la columna **Etiqueta**.</span><span class="sxs-lookup"><span data-stu-id="acecc-212">As we want to predict the taxi trip fare, copy the `FareAmount` column into the **Label** column.</span></span> <span data-ttu-id="acecc-213">Para ello, use la clase de transformación `CopyColumnsEstimator` y agregue el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="acecc-213">To do that, use the `CopyColumnsEstimator` transformation class, and add the following code:</span></span>

[!code-csharp[CopyColumnsEstimator](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#7 "Use the CopyColumnsEstimator")]

<span data-ttu-id="acecc-214">El algoritmo que entrena el modelo requiere características **numéricas**, por lo que debe transformar los datos de categorías (`VendorId`, `RateCode` y `PaymentType`) en números (`VendorIdEncoded`, `RateCodeEncoded` y `PaymentTypeEncoded`).</span><span class="sxs-lookup"><span data-stu-id="acecc-214">The algorithm that trains the model requires **numeric** features, so you have to transform the categorical data (`VendorId`, `RateCode`, and `PaymentType`) values into numbers (`VendorIdEncoded`, `RateCodeEncoded`, and `PaymentTypeEncoded`).</span></span> <span data-ttu-id="acecc-215">Para ello, use la clase de transformación Microsoft.ML.Transforms.OneHotEncodingTransformer>, que asigna valores clave numéricos diferentes a los distintos valores de cada una de las columnas, y agregue el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="acecc-215">To do that, use the Microsoft.ML.Transforms.OneHotEncodingTransformer> transformation class, which assigns different numeric key values to the different values in each of the columns, and add the following code:</span></span>

[!code-csharp[OneHotEncodingEstimator](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#8 "Use the OneHotEncodingEstimator")]

<span data-ttu-id="acecc-216">En el último paso para la preparación de los datos, se combinan todas las columnas de característica en la columna **Características** mediante la clase de transformación `mlContext.Transforms.Concatenate`.</span><span class="sxs-lookup"><span data-stu-id="acecc-216">The last step in data preparation combines all of the feature columns into the **Features** column using the `mlContext.Transforms.Concatenate` transformation class.</span></span> <span data-ttu-id="acecc-217">De forma predeterminada, un algoritmo de aprendizaje solo procesa las características de la columna **Features**.</span><span class="sxs-lookup"><span data-stu-id="acecc-217">By default, a learning algorithm processes only features from the **Features** column.</span></span> <span data-ttu-id="acecc-218">Agregue el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="acecc-218">Add the following code:</span></span>

[!code-csharp[ColumnConcatenatingEstimator](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#9 "Use the ColumnConcatenatingEstimator")]

## <a name="choose-a-learning-algorithm"></a><span data-ttu-id="acecc-219">Elegir un algoritmo de aprendizaje</span><span class="sxs-lookup"><span data-stu-id="acecc-219">Choose a learning algorithm</span></span>

<span data-ttu-id="acecc-220">Después de agregar los datos a la canalización y transformarlos en el formato de entrada correcto, se selecciona un algoritmo de aprendizaje (**aprendiz**).</span><span class="sxs-lookup"><span data-stu-id="acecc-220">After adding the data to the pipeline and transforming it into the correct input format, we select a learning algorithm (**learner**).</span></span> <span data-ttu-id="acecc-221">El aprendiz entrena el modelo.</span><span class="sxs-lookup"><span data-stu-id="acecc-221">The learner trains the model.</span></span> <span data-ttu-id="acecc-222">Elegimos una tarea de **regresión** para este problema, por lo que usamos un aprendiz de `FastTreeRegressionTrainer`, que es uno de los aprendices de regresión que proporciona ML.NET.</span><span class="sxs-lookup"><span data-stu-id="acecc-222">We chose a **regression** task for this problem, so we use a `FastTreeRegressionTrainer` learner, which is one of the regression learners provided by ML.NET.</span></span>

<span data-ttu-id="acecc-223">El algoritmo de entrenamiento `FastTreeRegressionTrainer` usa la potenciación del gradiente.</span><span class="sxs-lookup"><span data-stu-id="acecc-223">The `FastTreeRegressionTrainer` training algorithm utilizes gradient boosting.</span></span> <span data-ttu-id="acecc-224">La potenciación de gradiente es una técnica para los problemas de regresión de aprendizaje automático.</span><span class="sxs-lookup"><span data-stu-id="acecc-224">Gradient boosting is a machine learning technique for regression problems.</span></span> <span data-ttu-id="acecc-225">Crea cada árbol de regresión de forma escalonada.</span><span class="sxs-lookup"><span data-stu-id="acecc-225">It builds each regression tree in a step-wise fashion.</span></span> <span data-ttu-id="acecc-226">Utiliza una función de pérdida predefinida para medir el error en cada paso y corregirlo en el siguiente.</span><span class="sxs-lookup"><span data-stu-id="acecc-226">It uses a pre-defined loss function to measure the error in each step and correct for it in the next.</span></span> <span data-ttu-id="acecc-227">El resultado es un modelo de predicción que es realmente un conjunto de modelos de predicción más débiles.</span><span class="sxs-lookup"><span data-stu-id="acecc-227">The result is a prediction model that is actually an ensemble of weaker prediction models.</span></span> <span data-ttu-id="acecc-228">Para obtener más información sobre la potenciación de gradiente, consulte [Boosted Decision Tree Regression](/azure/machine-learning/studio-module-reference/boosted-decision-tree-regression) (Regresión de árbol de decisión potenciado).</span><span class="sxs-lookup"><span data-stu-id="acecc-228">For more information about gradient boosting, see [Boosted Decision Tree Regression](/azure/machine-learning/studio-module-reference/boosted-decision-tree-regression).</span></span>

<span data-ttu-id="acecc-229">Agregue el código siguiente al método `Train` para agregar `FastTreeRegressionTrainer` al código de procesamiento de datos que se agregó en el paso anterior:</span><span class="sxs-lookup"><span data-stu-id="acecc-229">Add the following code into the `Train` method to add the `FastTreeRegressionTrainer` to the data processing code added in the previous step:</span></span>

[!code-csharp[FastTreeRegressionTrainer](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#10 "Add the FastTreeRegressionTrainer")]

## <a name="train-the-model"></a><span data-ttu-id="acecc-230">Entrenar el modelo</span><span class="sxs-lookup"><span data-stu-id="acecc-230">Train the model</span></span>

<span data-ttu-id="acecc-231">El último paso es entrenar el modelo.</span><span class="sxs-lookup"><span data-stu-id="acecc-231">The final step is to train the model.</span></span> <span data-ttu-id="acecc-232">Se entrena el modelo, <xref:Microsoft.ML.Data.TransformerChain>, en función del conjunto de datos que se haya cargado y transformado.</span><span class="sxs-lookup"><span data-stu-id="acecc-232">We train the model, <xref:Microsoft.ML.Data.TransformerChain>, based on the dataset that has been loaded and transformed.</span></span> <span data-ttu-id="acecc-233">Una vez que se ha definido el estimador, se entrena el modelo mediante <xref:Microsoft.ML.Data.EstimatorChain%601.Fit%2A> y, al mismo tiempo, se proporcionan los datos de entrenamiento ya cargados.</span><span class="sxs-lookup"><span data-stu-id="acecc-233">Once the estimator has been defined, we train the model using the <xref:Microsoft.ML.Data.EstimatorChain%601.Fit%2A> while providing the already loaded training data.</span></span> <span data-ttu-id="acecc-234">Esto devuelve un modelo que se usa para las predicciones.</span><span class="sxs-lookup"><span data-stu-id="acecc-234">This returns a model to use for predictions.</span></span> <span data-ttu-id="acecc-235">`pipeline.Fit()` entrena la canalización y devuelve `Transformer` según la `DataView` que se pasa.</span><span class="sxs-lookup"><span data-stu-id="acecc-235">`pipeline.Fit()` trains the pipeline and returns a `Transformer` based on the `DataView` passed in.</span></span> <span data-ttu-id="acecc-236">El experimento no se ejecuta hasta que esto suceda.</span><span class="sxs-lookup"><span data-stu-id="acecc-236">The experiment is not executed until this happens.</span></span>

[!code-csharp[TrainModel](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#11 "Train the model")]

### <a name="save-the-model"></a><span data-ttu-id="acecc-237">Guardado del modelo</span><span class="sxs-lookup"><span data-stu-id="acecc-237">Save the model</span></span>

<span data-ttu-id="acecc-238">En este punto, tiene un modelo de tipo <xref:Microsoft.ML.Data.TransformerChain> que se puede integrar en cualquiera de las aplicaciones de .NET nuevas o existentes.</span><span class="sxs-lookup"><span data-stu-id="acecc-238">At this point, you have a model of type <xref:Microsoft.ML.Data.TransformerChain> that can be integrated into any of your existing or new .NET applications.</span></span> <span data-ttu-id="acecc-239">Para guardar el modelo en un archivo .zip, agregue el código siguiente al final del método `Train`:</span><span class="sxs-lookup"><span data-stu-id="acecc-239">To save the model to a .zip file, add the following code at the end of the `Train` method:</span></span>

[!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#12 "Save the model as a .zip file and return the model")]

## <a name="save-the-model-as-a-zip-file"></a><span data-ttu-id="acecc-240">Almacenamiento del modelo como un archivo ZIP</span><span class="sxs-lookup"><span data-stu-id="acecc-240">Save the model as a .zip file</span></span>

<span data-ttu-id="acecc-241">Cree el método `SaveModelAsFile`, justo después del método `Train`, mediante el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="acecc-241">Create the `SaveModelAsFile` method, just after the `Train` method, using the following code:</span></span>

```csharp
private static void SaveModelAsFile(MLContext mlContext, ITransformer model)
{

}
```

<span data-ttu-id="acecc-242">El método `SaveModelAsFile` ejecuta las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="acecc-242">The `SaveModelAsFile` method executes the following tasks:</span></span>

* <span data-ttu-id="acecc-243">Guarda el modelo como un archivo ZIP.</span><span class="sxs-lookup"><span data-stu-id="acecc-243">Saves the model as a .zip file.</span></span>

<span data-ttu-id="acecc-244">Es necesario crear un método para guardar el modelo para que se pueda volver a usar y consumir en otras aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="acecc-244">We need to create a method to save the model so that it can be reused and consumed in other applications.</span></span> <span data-ttu-id="acecc-245">`ITransformer` tiene un método <xref:Microsoft.ML.Data.TransformerChain%601.SaveTo(Microsoft.ML.IHostEnvironment,System.IO.Stream)> que toma el campo global `_modelPath` y <xref:System.IO.Stream>.</span><span class="sxs-lookup"><span data-stu-id="acecc-245">The `ITransformer` has a <xref:Microsoft.ML.Data.TransformerChain%601.SaveTo(Microsoft.ML.IHostEnvironment,System.IO.Stream)> method that takes in the `_modelPath` global field, and a <xref:System.IO.Stream>.</span></span> <span data-ttu-id="acecc-246">Como queremos guardar esto como archivo ZIP, vamos a crear `FileStream` inmediatamente antes de llamar al método `SaveTo`.</span><span class="sxs-lookup"><span data-stu-id="acecc-246">Since we want to save this as a zip file, we'll create the `FileStream` immediately before calling the `SaveTo` method.</span></span> <span data-ttu-id="acecc-247">Agregue el siguiente código al método `SaveModelAsFile` como la siguiente línea:</span><span class="sxs-lookup"><span data-stu-id="acecc-247">Add the following code to the `SaveModelAsFile` method as the next line:</span></span>

[!code-csharp[SaveToMethod](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#13 "Add the SaveTo Method")]

<span data-ttu-id="acecc-248">También podríamos mostrar dónde se escribió el archivo mediante la escritura de un mensaje de consola con `_modelPath`, utilizando el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="acecc-248">We could also display where the file was written by writing a console message with the `_modelPath`, using the following code:</span></span>

```csharp
Console.WriteLine("The model is saved to {0}", _modelPath);
```

## <a name="evaluate-the-model"></a><span data-ttu-id="acecc-249">Evaluar el modelo</span><span class="sxs-lookup"><span data-stu-id="acecc-249">Evaluate the model</span></span>

<span data-ttu-id="acecc-250">La evaluación es el proceso que sirve para comprobar cómo predice valores de etiqueta el modelo.</span><span class="sxs-lookup"><span data-stu-id="acecc-250">Evaluation is the process of checking how well the model predicts label values.</span></span> <span data-ttu-id="acecc-251">Es importante que el modelo haga buenas predicciones sobre los datos que no se han usado para entrenarlo.</span><span class="sxs-lookup"><span data-stu-id="acecc-251">It's important that the model makes good predictions on data that was not used to train the model.</span></span> <span data-ttu-id="acecc-252">Una forma de hacerlo es dividir los datos en conjuntos de datos de entrenamiento y prueba, como se ha hecho en este tutorial.</span><span class="sxs-lookup"><span data-stu-id="acecc-252">One way to do this is to split the data into training and test data sets, as it's done in this tutorial.</span></span> <span data-ttu-id="acecc-253">Ahora que ha entrenado el modelo en los datos de aprendizaje, puede ver qué tal funciona en los datos de prueba.</span><span class="sxs-lookup"><span data-stu-id="acecc-253">Now that you've trained the model on the training data, you can see how well it performs on the test data.</span></span>

<span data-ttu-id="acecc-254">El método `Evaluate` evaluará el modelo.</span><span class="sxs-lookup"><span data-stu-id="acecc-254">The `Evaluate` method evaluates the model.</span></span> <span data-ttu-id="acecc-255">Para crear este método, agregue el código siguiente debajo del método `Train`:</span><span class="sxs-lookup"><span data-stu-id="acecc-255">To create that method, add the following code below the `Train` method:</span></span>

```csharp
private static void Evaluate(MLContext mlContext, ITransformer model)
{

}
```
<span data-ttu-id="acecc-256">El método `Evaluate` ejecuta las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="acecc-256">The `Evaluate` method executes the following tasks:</span></span>

* <span data-ttu-id="acecc-257">Carga el conjunto de datos de prueba.</span><span class="sxs-lookup"><span data-stu-id="acecc-257">Loads the test dataset.</span></span>
* <span data-ttu-id="acecc-258">Crea el evaluador de regresión.</span><span class="sxs-lookup"><span data-stu-id="acecc-258">Creates the regression evaluator.</span></span>
* <span data-ttu-id="acecc-259">Evalúa el modelo y crea las métricas.</span><span class="sxs-lookup"><span data-stu-id="acecc-259">Evaluates the model and creates metrics.</span></span>
* <span data-ttu-id="acecc-260">Muestra las métricas.</span><span class="sxs-lookup"><span data-stu-id="acecc-260">Displays the metrics.</span></span>

<span data-ttu-id="acecc-261">Agregue una llamada al método nuevo desde el método `Main`, justo debajo de la llamada al método `Train`, utilizando el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="acecc-261">Add a call to the new method from the `Main` method, right under the `Train` method call, using the following code:</span></span>

[!code-csharp[CallEvaluate](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#14 "Call the Evaluate method")]

<span data-ttu-id="acecc-262">Cargue el conjunto de datos de prueba con el contenedor `MLContext.Data.LoadFromTextFile`.</span><span class="sxs-lookup"><span data-stu-id="acecc-262">Load the test dataset using the `MLContext.Data.LoadFromTextFile` wrapper.</span></span> <span data-ttu-id="acecc-263">Puede evaluar el modelo utilizando este conjunto de datos como una comprobación de calidad.</span><span class="sxs-lookup"><span data-stu-id="acecc-263">You can evaluate the model using this dataset as a quality check.</span></span> <span data-ttu-id="acecc-264">Agregue el código siguiente al método `Evaluate`:</span><span class="sxs-lookup"><span data-stu-id="acecc-264">Add the following code to the `Evaluate` method:</span></span>

[!code-csharp[LoadTestDataset](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#15 "Load the test dataset")]

<span data-ttu-id="acecc-265">A continuación, use el parámetro `model` de aprendizaje automático (un transformador) para introducir las características y devolver las predicciones.</span><span class="sxs-lookup"><span data-stu-id="acecc-265">Next, use the machine learning `model` parameter (a transformer) to input the features and return predictions.</span></span> <span data-ttu-id="acecc-266">Agregue el código siguiente al método `Evaluate` como la siguiente línea:</span><span class="sxs-lookup"><span data-stu-id="acecc-266">Add the following code to the `Evaluate` method as the next line:</span></span>

[!code-csharp[PredictWithTransformer](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#16 "Predict using the Transformer")]

<span data-ttu-id="acecc-267">El método `RegressionContext.Evaluate` calcula las métricas de calidad para `PredictionModel` mediante el conjunto de datos especificado.</span><span class="sxs-lookup"><span data-stu-id="acecc-267">The `RegressionContext.Evaluate` method computes the quality metrics for the `PredictionModel` using the specified dataset.</span></span> <span data-ttu-id="acecc-268">Devuelve un objeto <xref:Microsoft.ML.Data.RegressionMetrics> que contiene las métricas totales calculadas por evaluadores de regresión.</span><span class="sxs-lookup"><span data-stu-id="acecc-268">It returns a <xref:Microsoft.ML.Data.RegressionMetrics> object that contains the overall metrics computed by regression evaluators.</span></span> <span data-ttu-id="acecc-269">Para mostrar estos elementos a fin de determinar la calidad del modelo, debe obtener primero las métricas.</span><span class="sxs-lookup"><span data-stu-id="acecc-269">To display these to determine the quality of the model, you need to get the metrics first.</span></span> <span data-ttu-id="acecc-270">Agregue el siguiente código como la siguiente línea en el método `Evaluate`:</span><span class="sxs-lookup"><span data-stu-id="acecc-270">Add the following code as the next line in the `Evaluate` method:</span></span>

[!code-csharp[ComputeMetrics](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#17 "Compute Metrics")]

<span data-ttu-id="acecc-271">Agregue el código siguiente para evaluar el modelo y generar las métricas de evaluación:</span><span class="sxs-lookup"><span data-stu-id="acecc-271">Add the following code to evaluate the model and produce the evaluation metrics:</span></span>

```csharp
Console.WriteLine();
Console.WriteLine($"*************************************************");
Console.WriteLine($"*       Model quality metrics evaluation         ");
Console.WriteLine($"*------------------------------------------------");
```

<span data-ttu-id="acecc-272">[RSquared](../resources/glossary.md#coefficient-of-determination) es otra métrica de evaluación de modelos de regresión.</span><span class="sxs-lookup"><span data-stu-id="acecc-272">[RSquared](../resources/glossary.md#coefficient-of-determination) is another evaluation metric of the regression models.</span></span> <span data-ttu-id="acecc-273">RSquared muestra valores comprendidos entre 0 y 1.</span><span class="sxs-lookup"><span data-stu-id="acecc-273">RSquared takes values between 0 and 1.</span></span> <span data-ttu-id="acecc-274">Cuanto más se acerque el valor a 1, mejor será el modelo.</span><span class="sxs-lookup"><span data-stu-id="acecc-274">The closer its value is to 1, the better the model is.</span></span> <span data-ttu-id="acecc-275">Agregue el código siguiente al método `Evaluate` para mostrar el valor de RSquared:</span><span class="sxs-lookup"><span data-stu-id="acecc-275">Add the following code into the `Evaluate` method to display the RSquared value:</span></span>

[!code-csharp[DisplayRSquared](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#18 "Display the RSquared metric.")]

<span data-ttu-id="acecc-276">[RMS](../resources/glossary.md##root-of-mean-squared-error-rmse) es una de las métricas de evaluación del modelo de regresión.</span><span class="sxs-lookup"><span data-stu-id="acecc-276">[RMS](../resources/glossary.md##root-of-mean-squared-error-rmse) is one of the evaluation metrics of the regression model.</span></span> <span data-ttu-id="acecc-277">Cuanto menor sea su valor, mejor será el modelo.</span><span class="sxs-lookup"><span data-stu-id="acecc-277">The lower it is, the better the model is.</span></span> <span data-ttu-id="acecc-278">Agregue el código siguiente al método `Evaluate` para mostrar el valor de RMS:</span><span class="sxs-lookup"><span data-stu-id="acecc-278">Add the following code into the `Evaluate` method to display the RMS value:</span></span>

[!code-csharp[DisplayRMS](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#19 "Display the RMS metric.")]

## <a name="use-the-model-for-predictions"></a><span data-ttu-id="acecc-279">Usar el modelo para las predicciones</span><span class="sxs-lookup"><span data-stu-id="acecc-279">Use the model for predictions</span></span>


## <a name="predict-the-test-data-outcome-with-the-model-and-a-single-comment"></a><span data-ttu-id="acecc-280">Predicción del resultado de los datos de prueba con el modelo y un único comentario</span><span class="sxs-lookup"><span data-stu-id="acecc-280">Predict the test data outcome with the model and a single comment</span></span>

<span data-ttu-id="acecc-281">Cree el método `TestSinglePrediction`, justo después del método `Evaluate`, mediante el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="acecc-281">Create the `TestSinglePrediction` method, just after the `Evaluate` method, using the following code:</span></span>

```csharp
private static void TestSinglePrediction(MLContext mlContext)
{

}
```

<span data-ttu-id="acecc-282">El método `TestSinglePrediction` ejecuta las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="acecc-282">The `TestSinglePrediction` method executes the following tasks:</span></span>

* <span data-ttu-id="acecc-283">Crea un único comentario de datos de prueba.</span><span class="sxs-lookup"><span data-stu-id="acecc-283">Creates a single comment of test data.</span></span>
* <span data-ttu-id="acecc-284">Predice la tarifa según los datos de prueba.</span><span class="sxs-lookup"><span data-stu-id="acecc-284">Predicts fare amount based on test data.</span></span>
* <span data-ttu-id="acecc-285">Combina datos de prueba y predicciones para la generación de informes.</span><span class="sxs-lookup"><span data-stu-id="acecc-285">Combines test data and predictions for reporting.</span></span>
* <span data-ttu-id="acecc-286">Muestra los resultados de la predicción.</span><span class="sxs-lookup"><span data-stu-id="acecc-286">Displays the predicted results.</span></span>

<span data-ttu-id="acecc-287">Agregue una llamada al método nuevo desde el método `Main`, justo debajo de la llamada al método `Evaluate`, utilizando el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="acecc-287">Add a call to the new method from the `Main` method, right under the `Evaluate` method call, using the following code:</span></span>

[!code-csharp[CallTestSinglePrediction](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#20 "Call the TestSinglePrediction method")]

<span data-ttu-id="acecc-288">Como queremos cargar el modelo desde el archivo ZIP que guardamos, crearemos `FileStream` inmediatamente antes de llamar al método `Load`.</span><span class="sxs-lookup"><span data-stu-id="acecc-288">Since we want to load the model from the zip file we saved, we'll create the `FileStream` immediately before calling the `Load` method.</span></span> <span data-ttu-id="acecc-289">Agregue el código siguiente al método `TestSinglePrediction` como la siguiente línea:</span><span class="sxs-lookup"><span data-stu-id="acecc-289">Add the following code to the `TestSinglePrediction` method as the next line:</span></span>

[!code-csharp[LoadTheModel](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#21 "Load the model")]

<span data-ttu-id="acecc-290">Mientras `model` es `transformer` que opera en muchas filas de datos, un escenario muy común de producción es necesario para las predicciones con los ejemplos individuales.</span><span class="sxs-lookup"><span data-stu-id="acecc-290">While the `model` is a `transformer` that operates on many rows of data, a very common production scenario is a need for predictions on individual examples.</span></span> <span data-ttu-id="acecc-291"><xref:Microsoft.ML.PredictionEngine%602> es un contenedor que se devuelve del método `CreatePredictionEngine`.</span><span class="sxs-lookup"><span data-stu-id="acecc-291">The <xref:Microsoft.ML.PredictionEngine%602> is a wrapper that is returned from the `CreatePredictionEngine` method.</span></span> <span data-ttu-id="acecc-292">Vamos a agregar el código siguiente para crear `PredictionEngine` como la línea siguiente en el método `TestSinglePrediction`:</span><span class="sxs-lookup"><span data-stu-id="acecc-292">Let's add the following code to create the `PredictionEngine` as the next line in the `TestSinglePrediction` Method:</span></span>

[!code-csharp[MakePredictionEngine](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#22 "Create the PredictionFunction")]
  
<span data-ttu-id="acecc-293">En este tutorial se utiliza un viaje de prueba en esta clase.</span><span class="sxs-lookup"><span data-stu-id="acecc-293">This tutorial uses one test trip within this class.</span></span> <span data-ttu-id="acecc-294">Más adelante, puede agregar otros escenarios para experimentar con el modelo.</span><span class="sxs-lookup"><span data-stu-id="acecc-294">Later you can add other scenarios to experiment with the model.</span></span> <span data-ttu-id="acecc-295">Agregue un viaje para probar la predicción de costo del modelo entrenado en el método `TestSinglePrediction` mediante la creación de una instancia de `TaxiTrip`:</span><span class="sxs-lookup"><span data-stu-id="acecc-295">Add a trip to test the trained model's prediction of cost in the `TestSinglePrediction` method by creating an instance of `TaxiTrip`:</span></span>

[!code-csharp[PredictionData](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#23 "Create test data for single prediction")]

 <span data-ttu-id="acecc-296">Podemos usarlo para predecir la tarifa en función de una instancia única de los datos del viaje en taxi.</span><span class="sxs-lookup"><span data-stu-id="acecc-296">We can use that to predict the fare based on a single instance of the taxi trip data.</span></span> <span data-ttu-id="acecc-297">Para obtener una predicción, use <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> en los datos.</span><span class="sxs-lookup"><span data-stu-id="acecc-297">To get a prediction, use <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> on the data.</span></span> <span data-ttu-id="acecc-298">Tenga en cuenta que los datos de entrada son una cadena y el modelo incluye la caracterización.</span><span class="sxs-lookup"><span data-stu-id="acecc-298">Note that the input data is a string and the model includes the featurization.</span></span> <span data-ttu-id="acecc-299">La canalización está sincronizada durante el entrenamiento y la predicción.</span><span class="sxs-lookup"><span data-stu-id="acecc-299">Your pipeline is in sync during training and prediction.</span></span> <span data-ttu-id="acecc-300">No fue necesario escribir el código de preprocesamiento o caracterización específicamente para las predicciones, y la misma API se encarga de las predicciones por lotes y puntuales.</span><span class="sxs-lookup"><span data-stu-id="acecc-300">You didn’t have to write preprocessing/featurization code specifically for predictions, and the same API takes care of both batch and one-time predictions.</span></span>

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#24 "Create a prediction of taxi fare")]

<span data-ttu-id="acecc-301">Para mostrar la tarifa prevista del viaje especificado, agregue el código siguiente al método `TestSinglePrediction`:</span><span class="sxs-lookup"><span data-stu-id="acecc-301">To display the predicted fare of the specified trip, add the following code into the `TestSinglePrediction` method:</span></span>

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#25 "Display the prediction.")]

<span data-ttu-id="acecc-302">Ejecute el programa para ver la tarifa de taxi predicha para su caso de prueba.</span><span class="sxs-lookup"><span data-stu-id="acecc-302">Run the program to see the predicted taxi fare for your test case.</span></span>

<span data-ttu-id="acecc-303">¡Enhorabuena!</span><span class="sxs-lookup"><span data-stu-id="acecc-303">Congratulations!</span></span> <span data-ttu-id="acecc-304">Ya ha creado correctamente un modelo de aprendizaje automático para predecir tarifas de viajes en taxi, ha evaluado su precisión y lo ha usado para hacer predicciones.</span><span class="sxs-lookup"><span data-stu-id="acecc-304">You've now successfully built a machine learning model for predicting taxi trip fares, evaluated its accuracy, and used it to make predictions.</span></span> <span data-ttu-id="acecc-305">Puede encontrar el código fuente de este tutorial en el repositorio [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TaxiFarePrediction) de GitHub.</span><span class="sxs-lookup"><span data-stu-id="acecc-305">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TaxiFarePrediction) GitHub repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="acecc-306">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="acecc-306">Next steps</span></span>

<span data-ttu-id="acecc-307">En este tutorial ha aprendido a:</span><span class="sxs-lookup"><span data-stu-id="acecc-307">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="acecc-308">Entender el problema</span><span class="sxs-lookup"><span data-stu-id="acecc-308">Understand the problem</span></span>
> * <span data-ttu-id="acecc-309">Seleccionar la tarea de aprendizaje automático adecuada</span><span class="sxs-lookup"><span data-stu-id="acecc-309">Select the appropriate machine learning task</span></span>
> * <span data-ttu-id="acecc-310">Preparar y entender los datos</span><span class="sxs-lookup"><span data-stu-id="acecc-310">Prepare and understand the data</span></span>
> * <span data-ttu-id="acecc-311">Crear una canalización de aprendizaje</span><span class="sxs-lookup"><span data-stu-id="acecc-311">Create a learning pipeline</span></span>
> * <span data-ttu-id="acecc-312">Cargar y transformar los datos</span><span class="sxs-lookup"><span data-stu-id="acecc-312">Load and transform the data</span></span>
> * <span data-ttu-id="acecc-313">Elegir un algoritmo de aprendizaje</span><span class="sxs-lookup"><span data-stu-id="acecc-313">Choose a learning algorithm</span></span>
> * <span data-ttu-id="acecc-314">Entrenar el modelo</span><span class="sxs-lookup"><span data-stu-id="acecc-314">Train the model</span></span>
> * <span data-ttu-id="acecc-315">Evaluar el modelo</span><span class="sxs-lookup"><span data-stu-id="acecc-315">Evaluate the model</span></span>
> * <span data-ttu-id="acecc-316">Usar el modelo para las predicciones</span><span class="sxs-lookup"><span data-stu-id="acecc-316">Use the model for predictions</span></span>

<span data-ttu-id="acecc-317">Siga con el siguiente tutorial para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="acecc-317">Advance to the next tutorial to learn more.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="acecc-318">Agrupación en clústeres de iris</span><span class="sxs-lookup"><span data-stu-id="acecc-318">Iris clustering</span></span>](iris-clustering.md)
