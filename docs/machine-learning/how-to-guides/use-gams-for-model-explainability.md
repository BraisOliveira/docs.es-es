---
title: Uso de modelos aditivos generalizados y funciones de forma para la explicación del modelo
description: Uso de modelos aditivos generalizados y funciones de forma para la explicación del modelo en ML.NET
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: c58cf823007196c35da093fab7423c1e40ba1158
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855604"
---
# <a name="use-generalized-additive-models-and-shape-functions-for-model-explainability-in-mlnet"></a><span data-ttu-id="d36a5-103">Uso de modelos aditivos generalizados y funciones de forma para la explicación del modelo en ML.NET</span><span class="sxs-lookup"><span data-stu-id="d36a5-103">Use Generalized Additive Models and shape functions for model explainability in ML.NET</span></span>

> [!NOTE]
> <span data-ttu-id="d36a5-104">Este tema hace referencia a ML.NET, que se encuentra actualmente en versión preliminar, por lo que el material está sujeto a cambios.</span><span class="sxs-lookup"><span data-stu-id="d36a5-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="d36a5-105">Para obtener más información, visite la página de [ML.NET](https://dotnet.microsoft.com/apps/machinelearning-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="d36a5-105">For more information, visit the [ML.NET](https://dotnet.microsoft.com/apps/machinelearning-ai/ml-dotnet) page.</span></span>

<span data-ttu-id="d36a5-106">Este tutorial y el ejemplo relacionado usan actualmente **ML.NET en su versión 0.10**.</span><span class="sxs-lookup"><span data-stu-id="d36a5-106">This how-to and related sample are currently using **ML.NET version 0.10**.</span></span> <span data-ttu-id="d36a5-107">Para obtener más información, consulte las notas de la versión en el [repositorio de GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span><span class="sxs-lookup"><span data-stu-id="d36a5-107">For more information, see the release notes at the [dotnet/machinelearning GitHub repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

<span data-ttu-id="d36a5-108">Al crear modelos de Machine Learning, a menudo no es suficiente crear simplemente predicciones.</span><span class="sxs-lookup"><span data-stu-id="d36a5-108">When creating machine learning models, it is often not enough to simply make predictions.</span></span> <span data-ttu-id="d36a5-109">Con frecuencia, los desarrolladores del aprendizaje automático, las personas que toman decisiones y aquellas que se ven afectadas por los modelos deben comprender cómo los modelos de Machine Learning toman decisiones y las características que contribuyen a su rendimiento.</span><span class="sxs-lookup"><span data-stu-id="d36a5-109">Often, machine learning developers, decision makers, and those affected by the models need to understand how machine learning models make decisions and which features contribute to their performance.</span></span> <span data-ttu-id="d36a5-110">Los **modelos aditivos generalizados (GAM)** se usan internamente en Microsoft para la explicación del modelo con el fin de ayudar a los desarrolladores de aprendizaje automático a crear modelos de alta capacidad que puedan interpretar fácilmente otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="d36a5-110">**Generalized Additive Models (GAMs)** are used internally at Microsoft for model explainability to help machine learning developers create high-capacity models that can be easily interpreted by others.</span></span>

<span data-ttu-id="d36a5-111">Los GAM son una clase de **modelos interpretables** que son modelos lineales donde los términos son funciones no lineales, denominadas "funciones de forma" de una sola variable.</span><span class="sxs-lookup"><span data-stu-id="d36a5-111">GAMs are a class of **interpretable models** that are linear models where the terms are nonlinear functions, called "shape functions" of a single variable.</span></span> <span data-ttu-id="d36a5-112">Al igual que los modelos lineales, se interpretan con facilidad, pero dado que los modelos aprenden funciones de características en lugar de una sola ponderación, pueden modelar relaciones más complejas que un modelo lineal simple.</span><span class="sxs-lookup"><span data-stu-id="d36a5-112">As linear models, they are easily interpreted but because the models learn functions of features instead of a single weight, they can model more complex relationships than a simple linear model.</span></span> <span data-ttu-id="d36a5-113">El indicador de GAM resultante tiene un término de interceptación que representa la predicción promedia con respecto al conjunto de aprendizaje, y las funciones de forma que representan la desviación de la predicción promedia.</span><span class="sxs-lookup"><span data-stu-id="d36a5-113">The resulting GAM predictor has an intercept term that represents the average prediction over the training set, and shape functions that represent the deviation from the average prediction.</span></span> <span data-ttu-id="d36a5-114">Las funciones de forma se pueden inspeccionar a ojo para ver la respuesta del modelo a valores distintos de una característica, y se visualizan como el siguiente gráfico creado al final del código de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="d36a5-114">The shape functions can be inspected by eye to see the response of the model to different values of a feature, and visualized like the following graph that is created at the end of the code example.</span></span> <span data-ttu-id="d36a5-115">El instructor de GAM en ML.NET se implementa mediante árboles impulsados por gradiente superficiales (por ejemplo, troncos) para aprender funciones de forma no paramétrica, y se basa en el método descrito en [Intelligible Models for Classification and Regression](https://www.cs.cornell.edu/~yinlou/papers/lou-kdd12.pdf) (Modelos inteligibles para clasificación y regresión) de Lou, Caruana y Gehrke.</span><span class="sxs-lookup"><span data-stu-id="d36a5-115">The GAM trainer in ML.NET is implemented using shallow gradient boosted trees (for example tree stumps) to learn nonparametric shape functions, and is based on the method described in [Intelligible Models for Classification and Regression](https://www.cs.cornell.edu/~yinlou/papers/lou-kdd12.pdf) by Lou, Caruana, and Gehrke.</span></span>

```csharp
// Train the Generalized Additive Model
var fitPipeline = pipeline.Fit(data);
var gamModel = fitPipeline.LastTransformer.Model;

// The intercept for Generalize Additive Models represent the average prediction for the training data
var intercept = gamModel.Intercept;
Console.WriteLine($"Average predicted cost: {intercept:0.00}");

// Get the column names from the training set
var columnNames = data.Schema.AsEnumerable()
    .Select(column => column.Name) // Get the column names
    .Where(name => name != "MedianHomeValue") // Drop the Label
    .ToArray();

// Get the index of a variable from the training data
var myFeatureIndex = columnNames.ToList().FindIndex(str => str.Equals("MyFeature"));

// The shape functions represent the deviation from the average prediction as a function of the feature value
// It is represented by a discrete set of bins
// First, get the array of bin upper bounds from the model for this feature
var myFeatureBins = gamModel.GetBinUpperBounds(myFeatureIndex);
// Then get the array of bin weights; these are the effect size for each bin
var myFeatureWeights = gamModel.GetBinEffects(myFeatureIndex);

// Write out the shape function for the feature (see the following figure for what this looks like)
for (int i = 0; i < myFeatureBins.Length; i++)
{
    Console.WriteLine($"x < {myFeatureBins[i]:0.00} => {myFeatureWeights[i]:0.000}");
}
```

![Gráfico de función de forma de modelos aditivos generalizados](./media/use-gams-for-model-explainability/gam-shape-function-graph.png)

<span data-ttu-id="d36a5-117">Para ver un ejemplo de cómo entrenar un modelo de GAM e inspeccionar e interpretar los resultados, consulte el [repositorio de GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/blob/master/docs/samples/Microsoft.ML.Samples/Dynamic/GeneralizedAdditiveModels.cs).</span><span class="sxs-lookup"><span data-stu-id="d36a5-117">For a sample of how to train a GAM model and inspect and interpret the results, see [the dotnet/machinelearning GitHub repository](https://github.com/dotnet/machinelearning/blob/master/docs/samples/Microsoft.ML.Samples/Dynamic/GeneralizedAdditiveModels.cs).</span></span>
