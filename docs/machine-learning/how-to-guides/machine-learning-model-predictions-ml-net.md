---
title: 학습된 모델로 예측
description: 학습된 모델을 사용한 예측 알아보기
ms.date: 09/18/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc, how-to
ms.openlocfilehash: 182350cc5143155133385c6fd77986b271f6db91
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73977042"
---
# <a name="make-predictions-with-a-trained-model"></a><span data-ttu-id="170b3-103">학습된 모델로 예측</span><span class="sxs-lookup"><span data-stu-id="170b3-103">Make predictions with a trained model</span></span>

<span data-ttu-id="170b3-104">학습된 모델을 사용하여 예측을 수행하는 방법 알아보기</span><span class="sxs-lookup"><span data-stu-id="170b3-104">Learn how to use a trained model to make predictions</span></span>

## <a name="create-data-models"></a><span data-ttu-id="170b3-105">데이터 모델 만들기</span><span class="sxs-lookup"><span data-stu-id="170b3-105">Create data models</span></span>

### <a name="input-data"></a><span data-ttu-id="170b3-106">입력 데이터</span><span class="sxs-lookup"><span data-stu-id="170b3-106">Input data</span></span>

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

### <a name="output-data"></a><span data-ttu-id="170b3-107">출력 데이터</span><span class="sxs-lookup"><span data-stu-id="170b3-107">Output data</span></span>

<span data-ttu-id="170b3-108">`Features` 및 `Label` 열 이름처럼 ML.NET에는 모델에서 생성한 예측된 값 열에 대한 기본 이름이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="170b3-108">Like the `Features` and `Label` input column names, ML.NET has default names for the predicted value columns produced by a model.</span></span> <span data-ttu-id="170b3-109">작업에 따라 이 이름을 달라질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="170b3-109">Depending on the task the name may differ.</span></span>

<span data-ttu-id="170b3-110">이 샘플에서 사용하는 알고리즘은 선형 회귀 알고리즘이므로 출력 열의 기본 이름은 `Score`이며 `PredictedPrice` 속성에 대한 [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) 특성으로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="170b3-110">Because the algorithm used in this sample is a linear regression algorithm, the default name of the output column is `Score` which is defined by the [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) attribute on the `PredictedPrice` property.</span></span>

```csharp
class HousingPrediction
{
    [ColumnName("Score")]
    public float PredictedPrice { get; set; }
}
```

## <a name="set-up-a-prediction-pipeline"></a><span data-ttu-id="170b3-111">예측 파이프라인 설정</span><span class="sxs-lookup"><span data-stu-id="170b3-111">Set up a prediction pipeline</span></span>

<span data-ttu-id="170b3-112">단일 또는 일괄 처리 예측 모두에서 예측 파이프라인을 애플리케이션에 로드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="170b3-112">Whether making a single or batch prediction, the prediction pipeline needs to be loaded into the application.</span></span> <span data-ttu-id="170b3-113">이 파이프라인은 미리 처리된 변환과 학습된 모델을 모두 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="170b3-113">This pipeline contains both the data pre-processing transformations as well as the trained model.</span></span> <span data-ttu-id="170b3-114">아래 코드 조각은 이름이 `model.zip`인 파일에서 예측 파이프라인을 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="170b3-114">The code snippet below loads the prediction pipeline from a file named `model.zip`.</span></span>

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

// Load Trained Model
DataViewSchema predictionPipelineSchema;
ITransformer predictionPipeline = mlContext.Model.Load("model.zip", out predictionPipelineSchema);
```

## <a name="single-prediction"></a><span data-ttu-id="170b3-115">단일 예측</span><span class="sxs-lookup"><span data-stu-id="170b3-115">Single prediction</span></span>

<span data-ttu-id="170b3-116">단일 예측을 만들려면 로드된 예측 파이프라인을 사용하여 [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602)을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="170b3-116">To make a single prediction, create a [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) using the loaded prediction pipeline.</span></span>

```csharp
// Create PredictionEngines
PredictionEngine<HousingData, HousingPrediction> predictionEngine = mlContext.Model.CreatePredictionEngine<HousingData, HousingPrediction>(predictionPipeline);
```

<span data-ttu-id="170b3-117">그런 다음, [`Predict`](xref:Microsoft.ML.PredictionEngineBase%602.Predict*) 메서드를 사용하여 입력 데이터를 매개 변수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="170b3-117">Then, use the [`Predict`](xref:Microsoft.ML.PredictionEngineBase%602.Predict*) method and pass in your input data as a parameter.</span></span> <span data-ttu-id="170b3-118">[`Predict`](xref:Microsoft.ML.PredictionEngineBase%602.Predict*) 메서드를 사용할 때는 입력이 [`IDataView`](xref:Microsoft.ML.IDataView)가 되지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="170b3-118">Notice that using the [`Predict`](xref:Microsoft.ML.PredictionEngineBase%602.Predict*) method does not require the input to be an [`IDataView`](xref:Microsoft.ML.IDataView)).</span></span> <span data-ttu-id="170b3-119">이것은 입력 데이터 형식의 개체를 전달할 수 있도록 입력 데이터 형식 조작을 간편하게 내부화하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="170b3-119">This is because it conveniently internalizes the input data type manipulation so you can pass in an object of the input data type.</span></span> <span data-ttu-id="170b3-120">또한 `CurrentPrice`는 새 데이터를 통해 예측하려는 대상 또는 레이블이므로 해당 시점에는 값이 없다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="170b3-120">Additionally, since `CurrentPrice` is the target or label you're trying to predict using new data, it's assumed there is no value for it at the moment.</span></span>

```csharp
// Input Data
HousingData inputData = new HousingData
{
    Size = 900f,
    HistoricalPrices = new float[] { 155000f, 190000f, 220000f }
};

// Get Prediction
HousingPrediction prediction = predictionEngine.Predict(inputData);
```

<span data-ttu-id="170b3-121">`prediction` 개체의 `Score` 속성에 액세스할 경우 `150079`와 유사한 값을 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="170b3-121">If you access the `Score` property of the `prediction` object, you should get a value similar to `150079`.</span></span>

## <a name="multiple-predictions"></a><span data-ttu-id="170b3-122">다중 예측</span><span class="sxs-lookup"><span data-stu-id="170b3-122">Multiple predictions</span></span>

<span data-ttu-id="170b3-123">다음 데이터의 경우 [`IDataView`](xref:Microsoft.ML.IDataView)에 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="170b3-123">Given the following data, load it into an [`IDataView`](xref:Microsoft.ML.IDataView).</span></span> <span data-ttu-id="170b3-124">이 경우 [`IDataView`](xref:Microsoft.ML.IDataView)의 이름은 `inputData`입니다.</span><span class="sxs-lookup"><span data-stu-id="170b3-124">In this case, the name of the [`IDataView`](xref:Microsoft.ML.IDataView) is `inputData`.</span></span> <span data-ttu-id="170b3-125">`CurrentPrice`는 새 데이터를 통해 예측하려는 대상 또는 레이블이므로 해당 시점에는 값이 없다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="170b3-125">Because `CurrentPrice` is the target or label you're trying to predict using new data, it's assumed there is no value for it at the moment.</span></span>

```csharp
// Actual data
HousingData[] housingData = new HousingData[]
{
    new HousingData
    {
        Size = 850f,
        HistoricalPrices = new float[] { 150000f, 175000f, 210000f }
    },
    new HousingData
    {
        Size = 900f,
        HistoricalPrices = new float[] { 155000f, 190000f, 220000f }
    },
    new HousingData
    {
        Size = 550f,
        HistoricalPrices = new float[] { 99000f, 98000f, 130000f }
    }
};
```

<span data-ttu-id="170b3-126">이제 [`Transform`](xref:Microsoft.ML.ITransformer.Transform*) 메서드를 사용하여 데이터 변환을 적용하고 예측을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="170b3-126">Then, use the [`Transform`](xref:Microsoft.ML.ITransformer.Transform*) method to apply the data transformations and generate predictions.</span></span>

```csharp
// Predicted Data
IDataView predictions = predictionPipeline.Transform(inputData);
```

<span data-ttu-id="170b3-127">[`GetColumn`](xref:Microsoft.ML.Data.ColumnCursorExtensions.GetColumn*) 메서드를 사용하여 예측된 값을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="170b3-127">Inspect the predicted values by using the [`GetColumn`](xref:Microsoft.ML.Data.ColumnCursorExtensions.GetColumn*) method.</span></span>

```csharp
// Get Predictions
float[] scoreColumn = predictions.GetColumn<float>("Score").ToArray();
```

<span data-ttu-id="170b3-128">점수 열의 예측된 값은 다음과 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="170b3-128">The predicted values in the score column should look like the following:</span></span>

| <span data-ttu-id="170b3-129">관측</span><span class="sxs-lookup"><span data-stu-id="170b3-129">Observation</span></span> | <span data-ttu-id="170b3-130">예측</span><span class="sxs-lookup"><span data-stu-id="170b3-130">Prediction</span></span> |
|---|---|
| <span data-ttu-id="170b3-131">1</span><span class="sxs-lookup"><span data-stu-id="170b3-131">1</span></span> | <span data-ttu-id="170b3-132">144638.2</span><span class="sxs-lookup"><span data-stu-id="170b3-132">144638.2</span></span> |
| <span data-ttu-id="170b3-133">2</span><span class="sxs-lookup"><span data-stu-id="170b3-133">2</span></span> | <span data-ttu-id="170b3-134">150079.4</span><span class="sxs-lookup"><span data-stu-id="170b3-134">150079.4</span></span> |
| <span data-ttu-id="170b3-135">3</span><span class="sxs-lookup"><span data-stu-id="170b3-135">3</span></span> | <span data-ttu-id="170b3-136">107789.8</span><span class="sxs-lookup"><span data-stu-id="170b3-136">107789.8</span></span> |
