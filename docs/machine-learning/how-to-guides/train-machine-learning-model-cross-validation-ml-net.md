---
title: 교차 유효성 검사를 사용하여 기계 학습 모델을 학습합니다.
description: 교차 유효성 검사를 사용하여 ML.NET에서 더 강력한 기계 학습 모델을 구축하는 방법을 알아봅니다. 교차 유효성 검사는 학습 데이터를 여러 파티션으로 분할하고 이 파티션에서 여러 알고리즘을 학습하는 학습 및 모델 평가 기법입니다.
ms.date: 08/29/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc,how-to,title-hack-0625
ms.openlocfilehash: 87eae789478752423f3e682d4db6cead0391aa6e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2020
ms.locfileid: "73976921"
---
# <a name="train-a-machine-learning-model-using-cross-validation"></a><span data-ttu-id="591ec-104">교차 유효성 검사를 사용하여 기계 학습 모델을 학습합니다.</span><span class="sxs-lookup"><span data-stu-id="591ec-104">Train a machine learning model using cross validation</span></span>

<span data-ttu-id="591ec-105">교차 유효성 검사를 사용하여 ML.NET에서 더 강력한 기계 학습 모델을 학습하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="591ec-105">Learn how to use cross validation to train more robust machine learning models in ML.NET.</span></span>

<span data-ttu-id="591ec-106">교차 유효성 검사는 학습 데이터를 여러 파티션으로 분할하고 이 파티션에서 여러 알고리즘을 학습하는 학습 및 모델 평가 기법입니다.</span><span class="sxs-lookup"><span data-stu-id="591ec-106">Cross-validation is a training and model evaluation technique that splits the data into several partitions and trains multiple algorithms on these partitions.</span></span> <span data-ttu-id="591ec-107">이 기법은 학습 프로세스 밖에서 데이터를 유지하여 모델의 견고성을 높입니다.</span><span class="sxs-lookup"><span data-stu-id="591ec-107">This technique improves the robustness of the model by holding out data from the training process.</span></span> <span data-ttu-id="591ec-108">보이지 않는 관찰에 대한 성능 향상 외에도, 데이터 제약 환경에서 데이터 세트가 더 적은 학습 모델에 효과적인 도구가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="591ec-108">In addition to improving performance on unseen observations, in data-constrained environments it can be an effective tool for training models with a smaller dataset.</span></span>

## <a name="the-data-and-data-model"></a><span data-ttu-id="591ec-109">데이터 및 데이터 모델</span><span class="sxs-lookup"><span data-stu-id="591ec-109">The data and data model</span></span>

<span data-ttu-id="591ec-110">다음 형식을 갖는 파일의 데이터를 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="591ec-110">Given data from a file that has the following format:</span></span>

```text
Size (Sq. ft.), HistoricalPrice1 ($), HistoricalPrice2 ($), HistoricalPrice3 ($), Current Price ($)
620.00, 148330.32, 140913.81, 136686.39, 146105.37
550.00, 557033.46, 529181.78, 513306.33, 548677.95
1127.00, 479320.99, 455354.94, 441694.30, 472131.18
1120.00, 47504.98, 45129.73, 43775.84, 46792.41
```

<span data-ttu-id="591ec-111">데이터는 `HousingData` 같은 클래스로 모델링하고 [`IDataView`](xref:Microsoft.ML.IDataView)에 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="591ec-111">The data can be modeled by a class like `HousingData` and loaded into an [`IDataView`](xref:Microsoft.ML.IDataView).</span></span>

```csharp
public class HousingData
{
    [LoadColumn(0)]
    public float Size { get; set; }

    [LoadColumn(1, 3)]
    [VectorType(3)]
    public float[] HistoricalPrices { get; set; }

    [LoadColumn(4)]
    [ColumnName("Label")]
    public float CurrentPrice { get; set; }
}
```

## <a name="prepare-the-data"></a><span data-ttu-id="591ec-112">데이터 준비</span><span class="sxs-lookup"><span data-stu-id="591ec-112">Prepare the data</span></span>

<span data-ttu-id="591ec-113">데이터를 사용하여 기계 학습 모델을 빌드하기 전에 미리 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="591ec-113">Pre-process the data before using it to build the machine learning model.</span></span> <span data-ttu-id="591ec-114">이 샘플에서는 `Size` 및 `HistoricalPrices` 열을 하나의 기능 벡터로 결합합니다. 이것은 `Features`[`Concatenate` 메서드를 사용하여 새 열 ](xref:Microsoft.ML.TransformExtensionsCatalog.Concatenate*)에 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="591ec-114">In this sample, the `Size` and `HistoricalPrices` columns are combined into a single feature vector,  which is output to a new column called `Features` using the [`Concatenate`](xref:Microsoft.ML.TransformExtensionsCatalog.Concatenate*) method.</span></span> <span data-ttu-id="591ec-115">ML.NET 알고리즘에서 예상하는 형식으로 데이터를 가져오는 것 외에도, 열을 연결하면 개별 열 각각에 대해서가 아니라 연결된 열에 대해 한 번만 작업을 적용하므로 파이프라인에서 이후의 작업을 최적화합니다.</span><span class="sxs-lookup"><span data-stu-id="591ec-115">In addition to getting the data into the format expected by ML.NET algorithms, concatenating columns optimizes subsequent operations in the pipeline by applying the operation once for the concatenated column instead of each of the separate columns.</span></span>

<span data-ttu-id="591ec-116">열이 단일 벡터로 결합되면 [`NormalizeMinMax`](xref:Microsoft.ML.NormalizationCatalog.NormalizeMinMax*)가 `Features` 열에 적용되어 같은 0-1 범위에서 `Size` 및 `HistoricalPrices`를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="591ec-116">Once the columns are combined into a single vector, [`NormalizeMinMax`](xref:Microsoft.ML.NormalizationCatalog.NormalizeMinMax*) is applied to the `Features` column to get `Size` and `HistoricalPrices` in the same range between 0-1.</span></span>

```csharp
// Define data prep estimator
IEstimator<ITransformer> dataPrepEstimator =
    mlContext.Transforms.Concatenate("Features", new string[] { "Size", "HistoricalPrices" })
        .Append(mlContext.Transforms.NormalizeMinMax("Features"));

// Create data prep transformer
ITransformer dataPrepTransformer = dataPrepEstimator.Fit(data);

// Transform data
IDataView transformedData = dataPrepTransformer.Transform(data);
```

## <a name="train-model-with-cross-validation"></a><span data-ttu-id="591ec-117">교차 유효성 검사를 통한 모델 학습</span><span class="sxs-lookup"><span data-stu-id="591ec-117">Train model with cross validation</span></span>

<span data-ttu-id="591ec-118">데이터를 사전 처리한 후에는 모델을 학습합니다.</span><span class="sxs-lookup"><span data-stu-id="591ec-118">Once the data has been pre-processed, it's time to train the model.</span></span> <span data-ttu-id="591ec-119">먼저 수행할 기계 학습 작업과 가장 밀접하게 연결되는 알고리즘을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="591ec-119">First, select the algorithm that most closely aligns with the machine learning task to be performed.</span></span> <span data-ttu-id="591ec-120">예측된 값이 연속 숫자 값이므로 이 작업은 회귀입니다.</span><span class="sxs-lookup"><span data-stu-id="591ec-120">Because the predicted value is a numerically continuous value, the task is regression.</span></span> <span data-ttu-id="591ec-121">ML.NET이 구현한 회귀 알고리즘 중 하나는 [`StochasticDualCoordinateAscentCoordinator`](xref:Microsoft.ML.Trainers.SdcaRegressionTrainer) 알고리즘입니다.</span><span class="sxs-lookup"><span data-stu-id="591ec-121">One of the regression algorithms implemented by ML.NET is the [`StochasticDualCoordinateAscentCoordinator`](xref:Microsoft.ML.Trainers.SdcaRegressionTrainer) algorithm.</span></span> <span data-ttu-id="591ec-122">교차 유효성 검사를 통해 모델을 학습하려면 [`CrossValidate`](xref:Microsoft.ML.RegressionCatalog.CrossValidate*) 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="591ec-122">To train the model with cross-validation use the [`CrossValidate`](xref:Microsoft.ML.RegressionCatalog.CrossValidate*) method.</span></span>

> [!NOTE]
> <span data-ttu-id="591ec-123">이 샘플에서는 선형 회귀 모델을 사용하지만 CrossValidate는 ML.NET에서 변칙 검색을 제외한 모든 다른 기계 학습 모델에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="591ec-123">Although this sample uses a linear regression model, CrossValidate is applicable to all other machine learning tasks in ML.NET except Anomaly Detection.</span></span>

```csharp
// Define StochasticDualCoordinateAscent algorithm estimator
IEstimator<ITransformer> sdcaEstimator = mlContext.Regression.Trainers.Sdca();

// Apply 5-fold cross validation
var cvResults = mlContext.Regression.CrossValidate(transformedData, sdcaEstimator, numberOfFolds: 5);
```

<span data-ttu-id="591ec-124">[`CrossValidate`](xref:Microsoft.ML.RegressionCatalog.CrossValidate*)는 다음 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="591ec-124">[`CrossValidate`](xref:Microsoft.ML.RegressionCatalog.CrossValidate*) performs the following operations:</span></span>

1. <span data-ttu-id="591ec-125">`numberOfFolds` 매개 변수에 지정된 값에 부합하는 수의 파티션으로 데이터를 분할합니다.</span><span class="sxs-lookup"><span data-stu-id="591ec-125">Partitions the data into a number of partitions equal to the value specified in the `numberOfFolds` parameter.</span></span> <span data-ttu-id="591ec-126">각 파티션의 결과는 [`TrainTestData`](xref:Microsoft.ML.DataOperationsCatalog.TrainTestData) 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="591ec-126">The result of each partition is a [`TrainTestData`](xref:Microsoft.ML.DataOperationsCatalog.TrainTestData) object.</span></span>
1. <span data-ttu-id="591ec-127">모델은 학습 데이터 세트에 대해 지정된 기계 학습 알고리즘 평가자를 사용하여 각 파티션에 대해 학습됩니다.</span><span class="sxs-lookup"><span data-stu-id="591ec-127">A model is trained on each of the partitions using the specified machine learning algorithm estimator on the training data set.</span></span>
1. <span data-ttu-id="591ec-128">각 모델의 성능은 테스트 데이터 세트에 대해 [`Evaluate`](xref:Microsoft.ML.RegressionCatalog.Evaluate*) 메서드를 사용하여 평가됩니다.</span><span class="sxs-lookup"><span data-stu-id="591ec-128">Each model's performance is evaluated using the [`Evaluate`](xref:Microsoft.ML.RegressionCatalog.Evaluate*) method on the test data set.</span></span>
1. <span data-ttu-id="591ec-129">각각의 모델에 대해 모델과 메트릭이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="591ec-129">The model along with its metrics are returned for each of the models.</span></span>

<span data-ttu-id="591ec-130">`cvResults`에 저장된 결과는 [`CrossValidationResult`](xref:Microsoft.ML.TrainCatalogBase.CrossValidationResult%601) 개체의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="591ec-130">The result stored in `cvResults` is a collection of [`CrossValidationResult`](xref:Microsoft.ML.TrainCatalogBase.CrossValidationResult%601) objects.</span></span> <span data-ttu-id="591ec-131">이 개체는 각각 [`Model`](xref:Microsoft.ML.TrainCatalogBase.CrossValidationResult%601.Model) 및 [`Metrics`](xref:Microsoft.ML.TrainCatalogBase.CrossValidationResult%601.Metrics) 속성에서 액세스할 수 있는 학습 모델과 메트릭을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="591ec-131">This object includes the trained model as well as metrics which are both accessible form the [`Model`](xref:Microsoft.ML.TrainCatalogBase.CrossValidationResult%601.Model) and [`Metrics`](xref:Microsoft.ML.TrainCatalogBase.CrossValidationResult%601.Metrics) properties respectively.</span></span> <span data-ttu-id="591ec-132">이 샘플에서 `Model` 속성은[`ITransformer`](xref:Microsoft.ML.ITransformer) 형식이고 `Metrics` 속성은 [`RegressionMetrics`](xref:Microsoft.ML.Data.RegressionMetrics) 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="591ec-132">In this sample, the `Model` property is of type [`ITransformer`](xref:Microsoft.ML.ITransformer) and the `Metrics` property is of type [`RegressionMetrics`](xref:Microsoft.ML.Data.RegressionMetrics).</span></span>

## <a name="evaluate-the-model"></a><span data-ttu-id="591ec-133">모델 평가</span><span class="sxs-lookup"><span data-stu-id="591ec-133">Evaluate the model</span></span>

<span data-ttu-id="591ec-134">다양한 학습 모델에 대한 메트릭은 개별 `Metrics`[`CrossValidationResult` 개체의 ](xref:Microsoft.ML.TrainCatalogBase.CrossValidationResult%601) 속성을 통해 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="591ec-134">Metrics for the different trained models can be accessed through the `Metrics` property of the individual [`CrossValidationResult`](xref:Microsoft.ML.TrainCatalogBase.CrossValidationResult%601) object.</span></span> <span data-ttu-id="591ec-135">이 경우 [R 제곱 메트릭](https://en.wikipedia.org/wiki/Coefficient_of_determination)이 `rSquared` 변수를 통해 액세스 및 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="591ec-135">In this case, the [R-Squared metric](https://en.wikipedia.org/wiki/Coefficient_of_determination) is accessed and stored in the variable `rSquared`.</span></span>

```csharp
IEnumerable<double> rSquared =
    cvResults
        .Select(fold => fold.Metrics.RSquared);
```

<span data-ttu-id="591ec-136">`rSquared` 변수의 콘텐츠를 검사할 경우 출력은 0-1 범위의 5개 값이며 1에 가까울수록 적합한 값입니다.</span><span class="sxs-lookup"><span data-stu-id="591ec-136">If you inspect the contents of the `rSquared` variable, the output should be five values ranging from 0-1 where closer to 1 means best.</span></span> <span data-ttu-id="591ec-137">R 제곱 같은 메트릭을 사용하여 가장 적합한 값에서 가장 부족한 값까지 모델을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="591ec-137">Using metrics like R-Squared, select the models from best to worst performing.</span></span> <span data-ttu-id="591ec-138">그런 다음, 최고 모델을 선택하여 예측하거나 추가적인 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="591ec-138">Then, select the top model to make predictions or perform additional operations with.</span></span>

```csharp
// Select all models
ITransformer[] models =
    cvResults
        .OrderByDescending(fold => fold.Metrics.RSquared)
        .Select(fold => fold.Model)
        .ToArray();

// Get Top Model
ITransformer topModel = models[0];
```
