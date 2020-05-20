---
title: 모델 다시 학습
description: ML.NET에서의 모델 다시 학습 방법 알아보기
ms.date: 05/03/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc, how-to
ms.openlocfilehash: 735782a4a0877a917b6e1885f009aa49d834170f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2020
ms.locfileid: "73976960"
---
# <a name="re-train-a-model"></a><span data-ttu-id="3f140-103">모델 다시 학습</span><span class="sxs-lookup"><span data-stu-id="3f140-103">Re-train a model</span></span>

<span data-ttu-id="3f140-104">ML.NET에서 기계 학습 모델을 다시 학습하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="3f140-104">Learn how to retrain a machine learning model in ML.NET.</span></span>

<span data-ttu-id="3f140-105">세계 및 관련 데이터는 지속적으로 변화합니다.</span><span class="sxs-lookup"><span data-stu-id="3f140-105">The world and the data around it change at a constant pace.</span></span> <span data-ttu-id="3f140-106">이 때문에 모델도 변화와 업데이트가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3f140-106">As such, models need to change and update as well.</span></span> <span data-ttu-id="3f140-107">ML.NET은 매번 처음부터 다시 시작하는 것이 아니라 이전의 경험을 바탕으로 학습된 모델 매개 변수를 시작점으로 사용하여 모델을 다시 학습하는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3f140-107">ML.NET provides functionality for re-training models using learned model parameters as a starting point to continually build on previous experience rather than starting from scratch every time.</span></span>

<span data-ttu-id="3f140-108">다음 알고리즘은 ML.NET에서 다시 학습 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="3f140-108">The following algorithms are re-trainable in ML.NET:</span></span>

- [<span data-ttu-id="3f140-109">AveragedPerceptronTrainer</span><span class="sxs-lookup"><span data-stu-id="3f140-109">AveragedPerceptronTrainer</span></span>](xref:Microsoft.ML.Trainers.AveragedPerceptronTrainer)
- [<span data-ttu-id="3f140-110">FieldAwareFactorizationMachineTrainer</span><span class="sxs-lookup"><span data-stu-id="3f140-110">FieldAwareFactorizationMachineTrainer</span></span>](xref:Microsoft.ML.Trainers.FieldAwareFactorizationMachineTrainer)
- [<span data-ttu-id="3f140-111">LbfgsLogisticRegressionBinaryTrainer</span><span class="sxs-lookup"><span data-stu-id="3f140-111">LbfgsLogisticRegressionBinaryTrainer</span></span>](xref:Microsoft.ML.Trainers.LbfgsLogisticRegressionBinaryTrainer)
- [<span data-ttu-id="3f140-112">LbfgsMaximumEntropyMulticlassTrainer</span><span class="sxs-lookup"><span data-stu-id="3f140-112">LbfgsMaximumEntropyMulticlassTrainer</span></span>](xref:Microsoft.ML.Trainers.LbfgsMaximumEntropyMulticlassTrainer)
- [<span data-ttu-id="3f140-113">LbfgsPoissonRegressionTrainer</span><span class="sxs-lookup"><span data-stu-id="3f140-113">LbfgsPoissonRegressionTrainer</span></span>](xref:Microsoft.ML.Trainers.LbfgsPoissonRegressionTrainer)
- [<span data-ttu-id="3f140-114">LinearSvmTrainer</span><span class="sxs-lookup"><span data-stu-id="3f140-114">LinearSvmTrainer</span></span>](xref:Microsoft.ML.Trainers.LinearSvmTrainer)
- [<span data-ttu-id="3f140-115">OnlineGradientDescentTrainer</span><span class="sxs-lookup"><span data-stu-id="3f140-115">OnlineGradientDescentTrainer</span></span>](xref:Microsoft.ML.Trainers.OnlineGradientDescentTrainer)
- [<span data-ttu-id="3f140-116">SgdCalibratedTrainer</span><span class="sxs-lookup"><span data-stu-id="3f140-116">SgdCalibratedTrainer</span></span>](xref:Microsoft.ML.Trainers.SgdCalibratedTrainer)
- [<span data-ttu-id="3f140-117">SgdNonCalibratedTrainer</span><span class="sxs-lookup"><span data-stu-id="3f140-117">SgdNonCalibratedTrainer</span></span>](xref:Microsoft.ML.Trainers.SgdNonCalibratedTrainer)
- [<span data-ttu-id="3f140-118">SymbolicSgdLogisticRegressionBinaryTrainer</span><span class="sxs-lookup"><span data-stu-id="3f140-118">SymbolicSgdLogisticRegressionBinaryTrainer</span></span>](xref:Microsoft.ML.Trainers.SymbolicSgdLogisticRegressionBinaryTrainer)

## <a name="load-pre-trained-model"></a><span data-ttu-id="3f140-119">미리 학습된 모델 로드</span><span class="sxs-lookup"><span data-stu-id="3f140-119">Load pre-trained model</span></span>

<span data-ttu-id="3f140-120">먼저, 미리 학습된 모델을 애플리케이션에 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="3f140-120">First, load the pre-trained model into your application.</span></span> <span data-ttu-id="3f140-121">학습 파이프라인 및 모델 로드에 대한 자세한 정보는 [학습된 모델 저장 및 로드](save-load-machine-learning-models-ml-net.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3f140-121">To learn more about loading training pipelines and models, see [Save and load a trained model](save-load-machine-learning-models-ml-net.md).</span></span>

```csharp
// Create MLContext
MLContext mlContext = new MLContext();

// Define DataViewSchema of data prep pipeline and trained model
DataViewSchema dataPrepPipelineSchema, modelSchema;

// Load data preparation pipeline
ITransformer dataPrepPipeline = mlContext.Model.Load("data_preparation_pipeline.zip", out dataPrepPipelineSchema);

// Load trained model
ITransformer trainedModel = mlContext.Model.Load("ogd_model.zip", out modelSchema);
```

## <a name="extract-pre-trained-model-parameters"></a><span data-ttu-id="3f140-122">미리 학습된 모델 매개 변수 추출</span><span class="sxs-lookup"><span data-stu-id="3f140-122">Extract pre-trained model parameters</span></span>

<span data-ttu-id="3f140-123">모델이 로드되면 미리 학습된 모델의 [`Model`](xref:Microsoft.ML.Data.PredictionTransformerBase`1.Model*) 속성에 액세스하여 학습된 모델 매개 변수를 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="3f140-123">Once the model is loaded, extract the learned model parameters by accessing the [`Model`](xref:Microsoft.ML.Data.PredictionTransformerBase`1.Model*) property of the pre-trained model.</span></span> <span data-ttu-id="3f140-124">미리 학습된 모델은 [`LinearRegressionModelParameters`](xref:Microsoft.ML.Trainers.LinearRegressionModelParameters)를 출력하는 [`RegressionPredictionTransformer`](xref:Microsoft.ML.Data.RegressionPredictionTransformer%601)를 만드는 선형 회귀 모델 [`OnlineGradientDescentTrainer`](xref:Microsoft.ML.Trainers.OnlineGradientDescentTrainer)를 사용하여 학습되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3f140-124">The pre-trained model was trained using the linear regression model [`OnlineGradientDescentTrainer`](xref:Microsoft.ML.Trainers.OnlineGradientDescentTrainer) which creates a[`RegressionPredictionTransformer`](xref:Microsoft.ML.Data.RegressionPredictionTransformer%601) that outputs [`LinearRegressionModelParameters`](xref:Microsoft.ML.Trainers.LinearRegressionModelParameters).</span></span> <span data-ttu-id="3f140-125">이러한 선형 회귀 모델 매개 변수에는 학습된 편차 및 가중치와 모델 계수가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f140-125">These linear regression model parameters contain the learned bias and weights or coefficients of the model.</span></span> <span data-ttu-id="3f140-126">이런 값은 다시 학습되는 새 모델의 시작점이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f140-126">These values will be used as a starting point for the new re-trained model.</span></span>

```csharp
// Extract trained model parameters
LinearRegressionModelParameters originalModelParameters =
    ((ISingleFeaturePredictionTransformer<object>)trainedModel).Model as LinearRegressionModelParameters;
```

## <a name="re-train-model"></a><span data-ttu-id="3f140-127">모델 다시 학습</span><span class="sxs-lookup"><span data-stu-id="3f140-127">Re-train model</span></span>

<span data-ttu-id="3f140-128">모델을 다시 학습하는 프로세스는 모델 학습과 차이가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3f140-128">The process for retraining a model is no different than that of training a model.</span></span> <span data-ttu-id="3f140-129">유일한 차이점은 데이터와 함께 [`Fit`](xref:Microsoft.ML.Trainers.OnlineLinearTrainer`2.Fit*) 메서드도 원래 학습한 모델 매개 변수를 입력을 취하고 이를 다시 학습 프로세스의 시작점으로 사용한다는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="3f140-129">The only difference is, the [`Fit`](xref:Microsoft.ML.Trainers.OnlineLinearTrainer`2.Fit*) method in addition to the data also takes as input the original learned model parameters and uses them as a starting point in the re-training process.</span></span>

```csharp
// New Data
HousingData[] housingData = new HousingData[]
{
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

//Load New Data
IDataView newData = mlContext.Data.LoadFromEnumerable<HousingData>(housingData);

// Preprocess Data
IDataView transformedNewData = dataPrepPipeline.Transform(newData);

// Retrain model
RegressionPredictionTransformer<LinearRegressionModelParameters> retrainedModel =
    mlContext.Regression.Trainers.OnlineGradientDescent()
        .Fit(transformedNewData, originalModelParameters);
```

## <a name="compare-model-parameters"></a><span data-ttu-id="3f140-130">모델 매개 변수 비교</span><span class="sxs-lookup"><span data-stu-id="3f140-130">Compare model parameters</span></span>

<span data-ttu-id="3f140-131">다시 학습이 실제로 일어나는지 어떻게 알 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="3f140-131">How do you know if re-training actually happened?</span></span> <span data-ttu-id="3f140-132">한 가지 방법으로 다시 학습한 모델의 매개 변수가 원래 모델의 것과 다른지 비교할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f140-132">One way would be to compare whether the re-trained model's parameters are different than those of the original model.</span></span> <span data-ttu-id="3f140-133">아래 코드 샘플은 다시 학습한 모델 가중치에 대해 원래 항목을 비교하고 콘솔에 이를 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="3f140-133">The code sample below compares the original against the re-trained model weights and outputs them to the console.</span></span>

```csharp
// Extract Model Parameters of re-trained model
LinearRegressionModelParameters retrainedModelParameters = retrainedModel.Model as LinearRegressionModelParameters;

// Inspect Change in Weights
var weightDiffs =
    originalModelParameters.Weights.Zip(
        retrainedModelParameters.Weights, (original, retrained) => original - retrained).ToArray();

Console.WriteLine("Original | Retrained | Difference");
for(int i=0;i < weightDiffs.Count();i++)
{
    Console.WriteLine($"{originalModelParameters.Weights[i]} | {retrainedModelParameters.Weights[i]} | {weightDiffs[i]}");
}
```

<span data-ttu-id="3f140-134">아래 표는 출력의 모습을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3f140-134">The table below shows what the output might look like.</span></span>

|<span data-ttu-id="3f140-135">원래 이름</span><span class="sxs-lookup"><span data-stu-id="3f140-135">Original</span></span> | <span data-ttu-id="3f140-136">다시 학습</span><span class="sxs-lookup"><span data-stu-id="3f140-136">Retrained</span></span> | <span data-ttu-id="3f140-137">차이</span><span class="sxs-lookup"><span data-stu-id="3f140-137">Difference</span></span> |
|---|---|---|
| <span data-ttu-id="3f140-138">33039.86</span><span class="sxs-lookup"><span data-stu-id="3f140-138">33039.86</span></span> | <span data-ttu-id="3f140-139">56293.76</span><span class="sxs-lookup"><span data-stu-id="3f140-139">56293.76</span></span> | <span data-ttu-id="3f140-140">-23253.9</span><span class="sxs-lookup"><span data-stu-id="3f140-140">-23253.9</span></span> |
| <span data-ttu-id="3f140-141">29099.14</span><span class="sxs-lookup"><span data-stu-id="3f140-141">29099.14</span></span> | <span data-ttu-id="3f140-142">49586.03</span><span class="sxs-lookup"><span data-stu-id="3f140-142">49586.03</span></span> | <span data-ttu-id="3f140-143">-20486.89</span><span class="sxs-lookup"><span data-stu-id="3f140-143">-20486.89</span></span> |
| <span data-ttu-id="3f140-144">28938.38</span><span class="sxs-lookup"><span data-stu-id="3f140-144">28938.38</span></span> | <span data-ttu-id="3f140-145">48609.23</span><span class="sxs-lookup"><span data-stu-id="3f140-145">48609.23</span></span> | <span data-ttu-id="3f140-146">-19670.85</span><span class="sxs-lookup"><span data-stu-id="3f140-146">-19670.85</span></span> |
| <span data-ttu-id="3f140-147">30484.02</span><span class="sxs-lookup"><span data-stu-id="3f140-147">30484.02</span></span> | <span data-ttu-id="3f140-148">53745.43</span><span class="sxs-lookup"><span data-stu-id="3f140-148">53745.43</span></span> | <span data-ttu-id="3f140-149">-23261.41</span><span class="sxs-lookup"><span data-stu-id="3f140-149">-23261.41</span></span> |
