---
title: 모델 학습 및 평가
description: ML.NET을 사용한 기계 학습 모델 빌드, 메트릭 수집 및 성능 측정 방법을 알아봅니다. 기계 학습 모델은 새 데이터를 사용하여 예측을 수행하기 위해 학습 데이터에서 패턴을 식별합니다.
ms.date: 08/29/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc, how-to, title-hack-0625
ms.openlocfilehash: 0e0f43225b9bf243c31b3095817bdcbdb3123012
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2020
ms.locfileid: "73976766"
---
# <a name="train-and-evaluate-a-model"></a><span data-ttu-id="2a0ac-104">모델 학습 및 평가</span><span class="sxs-lookup"><span data-stu-id="2a0ac-104">Train and evaluate a model</span></span>

<span data-ttu-id="2a0ac-105">ML.NET을 사용한 기계 학습 모델 빌드, 메트릭 수집 및 성능 측정 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="2a0ac-105">Learn how to build machine learning models, collect metrics, and measure performance with ML.NET.</span></span> <span data-ttu-id="2a0ac-106">이 샘플에서는 회귀 모델을 학습하지만 개념은 대부분의 다른 알고리즘에 널리 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a0ac-106">Although this sample trains a regression model, the concepts are applicable throughout a majority of the other algorithms.</span></span>

## <a name="split-data-for-training-and-testing"></a><span data-ttu-id="2a0ac-107">학습 및 테스트를 위한 데이터 분할</span><span class="sxs-lookup"><span data-stu-id="2a0ac-107">Split data for training and testing</span></span>

<span data-ttu-id="2a0ac-108">기계 학습 모델의 목표는 학습 데이터 안에서 패턴을 식별하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2a0ac-108">The goal of a machine learning model is to identify patterns within training data.</span></span> <span data-ttu-id="2a0ac-109">이러한 패턴은 새 데이터를 사용하여 예측을 수행하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a0ac-109">These patterns are used to make predictions using new data.</span></span>

<span data-ttu-id="2a0ac-110">데이터는 `HousingData` 같은 클래스로 모델링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a0ac-110">The data can be modeled by a class like `HousingData`.</span></span>

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

<span data-ttu-id="2a0ac-111">[`IDataView`](xref:Microsoft.ML.IDataView)로 로드되는 다음 데이터의 경우:</span><span class="sxs-lookup"><span data-stu-id="2a0ac-111">Given the following data which is loaded into an [`IDataView`](xref:Microsoft.ML.IDataView).</span></span>

```csharp
HousingData[] housingData = new HousingData[]
{
    new HousingData
    {
        Size = 600f,
        HistoricalPrices = new float[] { 100000f ,125000f ,122000f },
        CurrentPrice = 170000f
    },
    new HousingData
    {
        Size = 1000f,
        HistoricalPrices = new float[] { 200000f, 250000f, 230000f },
        CurrentPrice = 225000f
    },
    new HousingData
    {
        Size = 1000f,
        HistoricalPrices = new float[] { 126000f, 130000f, 200000f },
        CurrentPrice = 195000f
    },
    new HousingData
    {
        Size = 850f,
        HistoricalPrices = new float[] { 150000f,175000f,210000f },
        CurrentPrice = 205000f
    },
    new HousingData
    {
        Size = 900f,
        HistoricalPrices = new float[] { 155000f, 190000f, 220000f },
        CurrentPrice = 210000f
    },
    new HousingData
    {
        Size = 550f,
        HistoricalPrices = new float[] { 99000f, 98000f, 130000f },
        CurrentPrice = 180000f
    }
};
```

<span data-ttu-id="2a0ac-112">[`TrainTestSplit`](xref:Microsoft.ML.DataOperationsCatalog.TrainTestSplit*) 메서드를 사용하여 데이터를 학습 및 테스트 집합으로 분할합니다.</span><span class="sxs-lookup"><span data-stu-id="2a0ac-112">Use the [`TrainTestSplit`](xref:Microsoft.ML.DataOperationsCatalog.TrainTestSplit*) method to split the data into train and test sets.</span></span> <span data-ttu-id="2a0ac-113">그 결과는 학습 집합용 하나와 테스트 집합용 하나 등, 두 [`TrainTestData`](xref:Microsoft.ML.DataOperationsCatalog.TrainTestData) 멤버를 갖는 [`IDataView`](xref:Microsoft.ML.IDataView) 개체가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a0ac-113">The result will be a [`TrainTestData`](xref:Microsoft.ML.DataOperationsCatalog.TrainTestData) object which contains two [`IDataView`](xref:Microsoft.ML.IDataView) members, one for the train set and the other for the test set.</span></span> <span data-ttu-id="2a0ac-114">데이터 분할 백분율은 `testFraction` 매개 변수로 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a0ac-114">The data split percentage is determined by the `testFraction` parameter.</span></span> <span data-ttu-id="2a0ac-115">아래 코드 조각은 원래 데이터의 20%를 테스트 집합용으로 보유합니다.</span><span class="sxs-lookup"><span data-stu-id="2a0ac-115">The snippet below is holding out 20 percent of the original data for the test set.</span></span>

```csharp
DataOperationsCatalog.TrainTestData dataSplit = mlContext.Data.TrainTestSplit(data, testFraction: 0.2);
IDataView trainData = dataSplit.TrainSet;
IDataView testData = dataSplit.TestSet;
```

## <a name="prepare-the-data"></a><span data-ttu-id="2a0ac-116">데이터 준비</span><span class="sxs-lookup"><span data-stu-id="2a0ac-116">Prepare the data</span></span>

<span data-ttu-id="2a0ac-117">기계 학습 모델로 학습하려면 먼저 데이터를 미리 처리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a0ac-117">The data needs to be pre-processed before training a machine learning model.</span></span> <span data-ttu-id="2a0ac-118">데이터 준비에 대한 자세한 정보는 [데이터 준비 방법 문서](prepare-data-ml-net.md) 및 [`transforms page`](../resources/transforms.md)에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a0ac-118">More information on data preparation can be found on the [data prep how-to article](prepare-data-ml-net.md) as well as the [`transforms page`](../resources/transforms.md).</span></span>

<span data-ttu-id="2a0ac-119">ML.NET 알고리즘은 입력 열 형식에 제약 조건이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a0ac-119">ML.NET algorithms have constraints on input column types.</span></span> <span data-ttu-id="2a0ac-120">또한 값을 지정하지 않은 경우 입력 및 출력 열에 기본값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2a0ac-120">Additionally, default values are used for input and output column names when no values are specified.</span></span>

### <a name="working-with-expected-column-types"></a><span data-ttu-id="2a0ac-121">예상한 열 형식 작업</span><span class="sxs-lookup"><span data-stu-id="2a0ac-121">Working with expected column types</span></span>

<span data-ttu-id="2a0ac-122">ML.NET의 기계 학습 알고리즘은 입력으로 알려진 크기의 부동 소수점 벡터를 기대합니다.</span><span class="sxs-lookup"><span data-stu-id="2a0ac-122">The machine learning algorithms in ML.NET expect a float vector of known size as input.</span></span> <span data-ttu-id="2a0ac-123">모든 데이터가 이미 숫자 형식이고 다 함께 처리될 예정이라면(즉 이미지 픽셀) 데이터 모델에 [`VectorType`](xref:Microsoft.ML.Data.VectorTypeAttribute) 특성을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="2a0ac-123">Apply the [`VectorType`](xref:Microsoft.ML.Data.VectorTypeAttribute) attribute to your data model when all of the data is already in numerical format and is intended to be processed together (i.e. image pixels).</span></span>

<span data-ttu-id="2a0ac-124">데이터의 일부가 숫자가 아니며 열마다 각기 다른 데이터 변환을 적용하려는 경우 모든 열이 처리된 뒤에 [`Concatenate`](xref:Microsoft.ML.TransformExtensionsCatalog.Concatenate*) 메서드를 사용하여 모든 개별 열을 새 열에 출력되는 단일 기능 벡터로 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="2a0ac-124">If data is not all numerical and you want to apply different data transformations on each of the columns individually, use the [`Concatenate`](xref:Microsoft.ML.TransformExtensionsCatalog.Concatenate*) method after all of the columns have been processed to combine all of the individual columns into a single feature vector that is output to a new column.</span></span>

<span data-ttu-id="2a0ac-125">다음 코드 조각은 `Size` 및 `HistoricalPrices` 열을 새 열 `Features`에 출력되는 단일 기능 벡터로 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="2a0ac-125">The following snippet combines the `Size` and `HistoricalPrices` columns into a single feature vector that is output to a new column called `Features`.</span></span> <span data-ttu-id="2a0ac-126">배율에 차이가 있기 때문에 [`NormalizeMinMax`](xref:Microsoft.ML.NormalizationCatalog.NormalizeMinMax*)는 데이터 표준화를 위해 `Features` 열에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a0ac-126">Because there is a difference in scales, [`NormalizeMinMax`](xref:Microsoft.ML.NormalizationCatalog.NormalizeMinMax*) is applied to the `Features` column to normalize the data.</span></span>

```csharp
// Define Data Prep Estimator
// 1. Concatenate Size and Historical into a single feature vector output to a new column called Features
// 2. Normalize Features vector
IEstimator<ITransformer> dataPrepEstimator =
    mlContext.Transforms.Concatenate("Features", "Size", "HistoricalPrices")
        .Append(mlContext.Transforms.NormalizeMinMax("Features"));

// Create data prep transformer
ITransformer dataPrepTransformer = dataPrepEstimator.Fit(trainData);

// Apply transforms to training data
IDataView transformedTrainingData = dataPrepTransformer.Transform(trainData);
```

### <a name="working-with-default-column-names"></a><span data-ttu-id="2a0ac-127">기본 열 이름 작업</span><span class="sxs-lookup"><span data-stu-id="2a0ac-127">Working with default column names</span></span>

<span data-ttu-id="2a0ac-128">지정하지 않은 경우 ML.NET 알고리즘은 기본 열 이름을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2a0ac-128">ML.NET algorithms use default column names when none are specified.</span></span> <span data-ttu-id="2a0ac-129">모든 학습자는 알고리즘 입력을 위해 `featureColumnName` 매개 변수를 가지며 해당하는 경우 예상된 값에 대한 매개 변수 `labelColumnName`도 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="2a0ac-129">All trainers have a parameter called `featureColumnName` for the inputs of the algorithm and when applicable they also have a parameter for the expected value called `labelColumnName`.</span></span> <span data-ttu-id="2a0ac-130">이러한 값은 기본적으로 각각 `Features` 및 `Label`입니다.</span><span class="sxs-lookup"><span data-stu-id="2a0ac-130">By default those values are `Features` and `Label` respectively.</span></span>

<span data-ttu-id="2a0ac-131">미리 처리하는 중에 [`Concatenate`](xref:Microsoft.ML.TransformExtensionsCatalog.Concatenate*) 메서드를 사용하여 `Features`라는 새 열을 만들면 알고리즘의 매개 변수에서 기능 열을 지정할 필요가 없습니다. 미리 처리된 `IDataView`에 이미 존재하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="2a0ac-131">By using the [`Concatenate`](xref:Microsoft.ML.TransformExtensionsCatalog.Concatenate*) method during pre-processing to create a new column called `Features`, there is no need to specify the feature column name in the parameters of the algorithm since it already exists in the pre-processed `IDataView`.</span></span> <span data-ttu-id="2a0ac-132">레이블 열은 `CurrentPrice`이지만 데이터 모델에서 [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) 특성을 사용하므로 ML.NET이 `CurrentPrice` 열의 이름을 `Label`로 바꿉니다. 이 때문에 `labelColumnName` 매개 변수를 기계 학습 모델 평가자에 제공할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2a0ac-132">The label column is `CurrentPrice`, but since the [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) attribute is used in the data model, ML.NET renames the `CurrentPrice` column to `Label` which removes the need to provide the `labelColumnName` parameter to the machine learning algorithm estimator.</span></span>

<span data-ttu-id="2a0ac-133">기본 열 이름을 사용하지 않으려면 이후의 코드 조각에서 설명하는 것처럼 기계 학습 알고리즘 평가자를 정의할 때 기능과 레이블 열 이름을 매개 변수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="2a0ac-133">If you don't want to use the default column names, pass in the names of the feature and label columns as parameters when defining the machine learning algorithm estimator as demonstrated by the subsequent snippet:</span></span>

```csharp
var UserDefinedColumnSdcaEstimator = mlContext.Regression.Trainers.Sdca(labelColumnName: "MyLabelColumnName", featureColumnName: "MyFeatureColumnName");
```

## <a name="train-the-machine-learning-model"></a><span data-ttu-id="2a0ac-134">기계 학습 모델 학습</span><span class="sxs-lookup"><span data-stu-id="2a0ac-134">Train the machine learning model</span></span>

<span data-ttu-id="2a0ac-135">데이터를 미리 처리한 후에는 [`Fit`](xref:Microsoft.ML.Trainers.TrainerEstimatorBase`2.Fit*) 메서드를 사용하여 [`StochasticDualCoordinateAscent`](xref:Microsoft.ML.Trainers.SdcaRegressionTrainer) 회귀 알고리즘으로 기계 학습 모델을 학습합니다.</span><span class="sxs-lookup"><span data-stu-id="2a0ac-135">Once the data is pre-processed, use the [`Fit`](xref:Microsoft.ML.Trainers.TrainerEstimatorBase`2.Fit*) method to train the machine learning model with the [`StochasticDualCoordinateAscent`](xref:Microsoft.ML.Trainers.SdcaRegressionTrainer) regression algorithm.</span></span>

```csharp
// Define StochasticDualCoordinateAscent regression algorithm estimator
var sdcaEstimator = mlContext.Regression.Trainers.Sdca();

// Build machine learning model
var trainedModel = sdcaEstimator.Fit(transformedTrainingData);
```

## <a name="extract-model-parameters"></a><span data-ttu-id="2a0ac-136">모델 매개 변수 추출</span><span class="sxs-lookup"><span data-stu-id="2a0ac-136">Extract model parameters</span></span>

<span data-ttu-id="2a0ac-137">모델을 학습한 후에는 검사 또는 재학습을 위해 학습한 [`ModelParameters`](xref:Microsoft.ML.Trainers.ModelParametersBase%601)를 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="2a0ac-137">After the model has been trained, extract the learned [`ModelParameters`](xref:Microsoft.ML.Trainers.ModelParametersBase%601) for inspection or re-training.</span></span> <span data-ttu-id="2a0ac-138">[`LinearRegressionModelParameters`](xref:Microsoft.ML.Trainers.LinearRegressionModelParameters)는 편차와 학습된 계수 또는 학습된 모델의 가중치를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2a0ac-138">The [`LinearRegressionModelParameters`](xref:Microsoft.ML.Trainers.LinearRegressionModelParameters) provide the bias and learned coefficients or weights of the trained model.</span></span>

```csharp
var trainedModelParameters = trainedModel.Model as LinearRegressionModelParameters;
```

> [!NOTE]
> <span data-ttu-id="2a0ac-139">다른 모델에는 해당 작업에 특정한 매개 변수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a0ac-139">Other models have parameters that are specific to their tasks.</span></span> <span data-ttu-id="2a0ac-140">예를 들어, [K-Means 알고리즘](xref:Microsoft.ML.Trainers.KMeansTrainer)은 무게 중심에 따라 클러스터에 데이터를 배치하며 [`KMeansModelParameters`](xref:Microsoft.ML.Trainers.KMeansModelParameters)에는 이러한 학습된 무게 중심을 저장하는 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a0ac-140">For example, the [K-Means algorithm](xref:Microsoft.ML.Trainers.KMeansTrainer) puts data into cluster based on centroids and the [`KMeansModelParameters`](xref:Microsoft.ML.Trainers.KMeansModelParameters) contains a property that stores these learned centroids.</span></span> <span data-ttu-id="2a0ac-141">자세한 정보는 [`Microsoft.ML.Trainers` API 설명서](xref:Microsoft.ML.Trainers)에서 이름에 `ModelParameters`가 포함된 클래스를 찾아보세요.</span><span class="sxs-lookup"><span data-stu-id="2a0ac-141">To learn more, visit the [`Microsoft.ML.Trainers` API Documentation](xref:Microsoft.ML.Trainers) and look for classes that contain `ModelParameters` in their name.</span></span>

## <a name="evaluate-model-quality"></a><span data-ttu-id="2a0ac-142">모델 품질 평가</span><span class="sxs-lookup"><span data-stu-id="2a0ac-142">Evaluate model quality</span></span>

<span data-ttu-id="2a0ac-143">최상의 모델을 선택하기 위해 테스트 데이터에서 성능을 반드시 평가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a0ac-143">To help choose the best performing model, it is essential to evaluate its performance on test data.</span></span> <span data-ttu-id="2a0ac-144">[`Evaluate`](xref:Microsoft.ML.RegressionCatalog.Evaluate*) 메서드를 사용하여 학습된 모델에 대한 여러 메트릭을 측정합니다.</span><span class="sxs-lookup"><span data-stu-id="2a0ac-144">Use the [`Evaluate`](xref:Microsoft.ML.RegressionCatalog.Evaluate*) method, to measure various metrics for the trained model.</span></span>

> [!NOTE]
> <span data-ttu-id="2a0ac-145">`Evaluate` 메서드는 수행된 기계 학습 작업에 따라 다른 메트릭을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="2a0ac-145">The `Evaluate` method produces different metrics depending on which machine learning task was performed.</span></span> <span data-ttu-id="2a0ac-146">자세한 정보는 [`Microsoft.ML.Data` API 설명서](xref:Microsoft.ML.Data)에서 이름에 `Metrics`가 포함된 클래스를 찾아보세요.</span><span class="sxs-lookup"><span data-stu-id="2a0ac-146">For more details, visit the [`Microsoft.ML.Data` API Documentation](xref:Microsoft.ML.Data) and look for classes that contain `Metrics` in their name.</span></span>

```csharp
// Measure trained model performance
// Apply data prep transformer to test data
IDataView transformedTestData = dataPrepTransformer.Transform(testData);

// Use trained model to make inferences on test data
IDataView testDataPredictions = trainedModel.Transform(transformedTestData);

// Extract model metrics and get RSquared
RegressionMetrics trainedModelMetrics = mlContext.Regression.Evaluate(testDataPredictions);
double rSquared = trainedModelMetrics.RSquared;
```

<span data-ttu-id="2a0ac-147">앞의 코드 샘플에서:</span><span class="sxs-lookup"><span data-stu-id="2a0ac-147">In the previous code sample:</span></span>

1. <span data-ttu-id="2a0ac-148">테스트 데이터 세트는 앞에서 정의한 데이터 준비 변환을 통해 미리 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a0ac-148">Test data set is pre-processed using the data preparation transforms previously defined.</span></span>
2. <span data-ttu-id="2a0ac-149">학습된 기계 학습 모델을 사용하여 테스트 데이터에 대한 예측을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="2a0ac-149">The trained machine learning model is used to make predictions on the test data.</span></span>
3. <span data-ttu-id="2a0ac-150">`Evaluate` 메서드에서 테스트 데이터 세트의 `CurrentPrice` 열 값을 새 출력 예측의 `Score` 열과 비교하여 회귀 모델의 메트릭을 계산하는데, 이 중 하나인 R 제곱이 `rSquared` 변수에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a0ac-150">In the `Evaluate` method, the values in the `CurrentPrice` column of the test data set are compared against the `Score` column of the newly output predictions to calculate the metrics for the regression model, one of which, R-Squared is stored in the `rSquared` variable.</span></span>

> [!NOTE]
> <span data-ttu-id="2a0ac-151">이 작은 예제에서 R 제곱은 데이터의 크기 제한으로 인해 0-1 범위에 있지 않은 숫자입니다.</span><span class="sxs-lookup"><span data-stu-id="2a0ac-151">In this small example, the R-Squared is a number not in the range of 0-1 because of the limited size of the data.</span></span> <span data-ttu-id="2a0ac-152">실제 시나리오에서는 0과 1 사이의 값이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a0ac-152">In a real-world scenario, you should expect to see a value between 0 and 1.</span></span>
