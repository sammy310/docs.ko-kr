---
title: 순열 기능 중요도를 사용하여 ML.NET 모델 해석
description: ML.NET에서 순열 기능 중요도를 사용하여 모델의 기능 중요도 파악
ms.date: 01/30/2020
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc,how-to
ms.openlocfilehash: c1163a41cd2feb0e8785ae9d4c6a71dfbedf3f12
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2020
ms.locfileid: "77092618"
---
# <a name="interpret-model-predictions-using-permutation-feature-importance"></a><span data-ttu-id="3e507-103">순열 기능 중요도를 사용하여 모델 예측 해석</span><span class="sxs-lookup"><span data-stu-id="3e507-103">Interpret model predictions using Permutation Feature Importance</span></span>

<span data-ttu-id="3e507-104">PFI(순열 기능 중요도)를 사용하여 ML.NET 기계 학습 모델 예측을 해석하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="3e507-104">Using Permutation Feature Importance (PFI), learn how to interpret ML.NET machine learning model predictions.</span></span> <span data-ttu-id="3e507-105">PFI를 통해 각 기능이 예측에 공헌하는 상대적 기여도를 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e507-105">PFI gives the relative contribution each feature makes to a prediction.</span></span>

<span data-ttu-id="3e507-106">기계 학습 모델은 종종 입력을 받아 출력을 생성하는 블랙 박스처럼 여겨지곤 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e507-106">Machine learning models are often thought of as black boxes that take inputs and generate an output.</span></span> <span data-ttu-id="3e507-107">출력에 영향을 미치는 중간 단계 또는 기능 간 상호 작용은 거의 해석되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3e507-107">The intermediate steps or interactions among the features that influence the output are rarely understood.</span></span> <span data-ttu-id="3e507-108">의료 등, 다양한 일상에서 기계 학습의 도입이 증가하면서 기계 학습 모델이 그러한 의사 결정을 내리게 되는 이유를 해석하는 것이 매우 중요해졌습니다.</span><span class="sxs-lookup"><span data-stu-id="3e507-108">As machine learning is introduced into more aspects of everyday life such as healthcare, it's of utmost importance to understand why a machine learning model makes the decisions it does.</span></span> <span data-ttu-id="3e507-109">예를 들어, 기계 학습 모델에서 진단을 수행할 경우 의료 전문가가 해당 진단에 반영된 요소를 살펴볼 방법이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3e507-109">For example, if diagnoses are made by a machine learning model, healthcare professionals need a way to look into the factors that went into making that diagnoses.</span></span> <span data-ttu-id="3e507-110">올바른 진단을 제공하면 환자의 빠른 회복 여부에 큰 차이를 낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e507-110">Providing the right diagnosis could make a great difference on whether a patient has a speedy recovery or not.</span></span> <span data-ttu-id="3e507-111">따라서 모델의 설명 가능한 수준이 높을수록 의료 전문가는 더 자신 있게 모델의 의사 결정을 수락 또는 거부할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e507-111">Therefore the higher the level of explainability in a model, the greater confidence healthcare professionals have to accept or reject the decisions made by the model.</span></span>

<span data-ttu-id="3e507-112">다양한 기법을 사용하여 모델을 설명하며, 그 방법 중 하나가 PFI입니다.</span><span class="sxs-lookup"><span data-stu-id="3e507-112">Various techniques are used to explain models, one of which is PFI.</span></span> <span data-ttu-id="3e507-113">PFI는 [Breiman의 *랜덤 포리스트* 논문](https://www.stat.berkeley.edu/~breiman/randomforest2001.pdf)(섹션 10 참조)에서 착안한 분류 및 회귀 모델을 설명하는 데 사용되는 기법입니다.</span><span class="sxs-lookup"><span data-stu-id="3e507-113">PFI is a technique used to explain classification and regression models that is inspired by [Breiman's *Random Forests* paper](https://www.stat.berkeley.edu/~breiman/randomforest2001.pdf) (see section 10).</span></span> <span data-ttu-id="3e507-114">높은 수준에서는, 전체 데이터 세트에 대해 한 번에 한 기능씩 임의로 데이터를 섞고 해당 성능 메트릭이 얼마나 감소하는지를 산출하는 방식으로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="3e507-114">At a high level, the way it works is by randomly shuffling data one feature at a time for the entire dataset and calculating how much the performance metric of interest decreases.</span></span> <span data-ttu-id="3e507-115">변화가 클수록 해당 기능이 중요한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3e507-115">The larger the change, the more important that feature is.</span></span>

<span data-ttu-id="3e507-116">또한 가장 중요한 기능을 강조 표시하므로 모델을 빌드하는 사람이 노이즈 및 학습 시간을 줄일 수 있는 더 의미 있는 기능의 하위 집합에 주력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e507-116">Additionally, by highlighting the most important features, model builders can focus on using a subset of more meaningful features which can potentially reduce noise and training time.</span></span>

## <a name="load-the-data"></a><span data-ttu-id="3e507-117">데이터 로드</span><span class="sxs-lookup"><span data-stu-id="3e507-117">Load the data</span></span>

<span data-ttu-id="3e507-118">이 샘플에 사용되는 데이터 세트의 기능은 1-12열에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e507-118">The features in the dataset being used for this sample are in columns 1-12.</span></span> <span data-ttu-id="3e507-119">목표는 `Price` 예측입니다.</span><span class="sxs-lookup"><span data-stu-id="3e507-119">The goal is to predict `Price`.</span></span>

| <span data-ttu-id="3e507-120">열</span><span class="sxs-lookup"><span data-stu-id="3e507-120">Column</span></span> | <span data-ttu-id="3e507-121">기능</span><span class="sxs-lookup"><span data-stu-id="3e507-121">Feature</span></span> | <span data-ttu-id="3e507-122">설명</span><span class="sxs-lookup"><span data-stu-id="3e507-122">Description</span></span>
| --- | --- | --- |
| <span data-ttu-id="3e507-123">1</span><span class="sxs-lookup"><span data-stu-id="3e507-123">1</span></span> | <span data-ttu-id="3e507-124">CrimeRate</span><span class="sxs-lookup"><span data-stu-id="3e507-124">CrimeRate</span></span> | <span data-ttu-id="3e507-125">인당 범죄율</span><span class="sxs-lookup"><span data-stu-id="3e507-125">Per capita crime rate</span></span>
| <span data-ttu-id="3e507-126">2</span><span class="sxs-lookup"><span data-stu-id="3e507-126">2</span></span> | <span data-ttu-id="3e507-127">ResidentialZones</span><span class="sxs-lookup"><span data-stu-id="3e507-127">ResidentialZones</span></span> | <span data-ttu-id="3e507-128">도시 내 주거지</span><span class="sxs-lookup"><span data-stu-id="3e507-128">Residential zones in town</span></span>
| <span data-ttu-id="3e507-129">3</span><span class="sxs-lookup"><span data-stu-id="3e507-129">3</span></span> | <span data-ttu-id="3e507-130">CommercialZones</span><span class="sxs-lookup"><span data-stu-id="3e507-130">CommercialZones</span></span> | <span data-ttu-id="3e507-131">도시 내 비주거지</span><span class="sxs-lookup"><span data-stu-id="3e507-131">Non-residential zones in town</span></span>
| <span data-ttu-id="3e507-132">4</span><span class="sxs-lookup"><span data-stu-id="3e507-132">4</span></span> | <span data-ttu-id="3e507-133">NearWater</span><span class="sxs-lookup"><span data-stu-id="3e507-133">NearWater</span></span> | <span data-ttu-id="3e507-134">수원 근접성</span><span class="sxs-lookup"><span data-stu-id="3e507-134">Proximity to body of water</span></span>
| <span data-ttu-id="3e507-135">5</span><span class="sxs-lookup"><span data-stu-id="3e507-135">5</span></span> | <span data-ttu-id="3e507-136">ToxicWasteLevels</span><span class="sxs-lookup"><span data-stu-id="3e507-136">ToxicWasteLevels</span></span> | <span data-ttu-id="3e507-137">독성 물질 수준(PPM)</span><span class="sxs-lookup"><span data-stu-id="3e507-137">Toxicity levels (PPM)</span></span>
| <span data-ttu-id="3e507-138">6</span><span class="sxs-lookup"><span data-stu-id="3e507-138">6</span></span> | <span data-ttu-id="3e507-139">AverageRoomNumber</span><span class="sxs-lookup"><span data-stu-id="3e507-139">AverageRoomNumber</span></span> | <span data-ttu-id="3e507-140">가구 내 평균 방 수</span><span class="sxs-lookup"><span data-stu-id="3e507-140">Average number of rooms in house</span></span>
| <span data-ttu-id="3e507-141">7</span><span class="sxs-lookup"><span data-stu-id="3e507-141">7</span></span> | <span data-ttu-id="3e507-142">HomeAge</span><span class="sxs-lookup"><span data-stu-id="3e507-142">HomeAge</span></span> | <span data-ttu-id="3e507-143">가구 연령</span><span class="sxs-lookup"><span data-stu-id="3e507-143">Age of home</span></span>
| <span data-ttu-id="3e507-144">8</span><span class="sxs-lookup"><span data-stu-id="3e507-144">8</span></span> | <span data-ttu-id="3e507-145">BusinessCenterDistance</span><span class="sxs-lookup"><span data-stu-id="3e507-145">BusinessCenterDistance</span></span> | <span data-ttu-id="3e507-146">가장 가까운 비즈니스 지구까지 거리</span><span class="sxs-lookup"><span data-stu-id="3e507-146">Distance to nearest business district</span></span>
| <span data-ttu-id="3e507-147">10</span><span class="sxs-lookup"><span data-stu-id="3e507-147">9</span></span> | <span data-ttu-id="3e507-148">HighwayAccess</span><span class="sxs-lookup"><span data-stu-id="3e507-148">HighwayAccess</span></span> | <span data-ttu-id="3e507-149">고속도로 근접성</span><span class="sxs-lookup"><span data-stu-id="3e507-149">Proximity to highways</span></span>
| <span data-ttu-id="3e507-150">10</span><span class="sxs-lookup"><span data-stu-id="3e507-150">10</span></span> | <span data-ttu-id="3e507-151">TaxRate</span><span class="sxs-lookup"><span data-stu-id="3e507-151">TaxRate</span></span> | <span data-ttu-id="3e507-152">재산세율</span><span class="sxs-lookup"><span data-stu-id="3e507-152">Property tax rate</span></span>
| <span data-ttu-id="3e507-153">11</span><span class="sxs-lookup"><span data-stu-id="3e507-153">11</span></span> | <span data-ttu-id="3e507-154">StudentTeacherRatio</span><span class="sxs-lookup"><span data-stu-id="3e507-154">StudentTeacherRatio</span></span> | <span data-ttu-id="3e507-155">교사 학생 비율</span><span class="sxs-lookup"><span data-stu-id="3e507-155">Ratio of students to teachers</span></span>
| <span data-ttu-id="3e507-156">12</span><span class="sxs-lookup"><span data-stu-id="3e507-156">12</span></span> | <span data-ttu-id="3e507-157">PercentPopulationBelowPoverty</span><span class="sxs-lookup"><span data-stu-id="3e507-157">PercentPopulationBelowPoverty</span></span> | <span data-ttu-id="3e507-158">빈곤 인구 비율</span><span class="sxs-lookup"><span data-stu-id="3e507-158">Percent of population living below poverty</span></span>
| <span data-ttu-id="3e507-159">13</span><span class="sxs-lookup"><span data-stu-id="3e507-159">13</span></span> | <span data-ttu-id="3e507-160">Price</span><span class="sxs-lookup"><span data-stu-id="3e507-160">Price</span></span> | <span data-ttu-id="3e507-161">주택 가격</span><span class="sxs-lookup"><span data-stu-id="3e507-161">Price of the home</span></span>

<span data-ttu-id="3e507-162">데이터 세트의 샘플은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3e507-162">A sample of the dataset is shown below:</span></span>

```text
1,24,13,1,0.59,3,96,11,23,608,14,13,32
4,80,18,1,0.37,5,14,7,4,346,19,13,41
2,98,16,1,0.25,10,5,1,8,689,13,36,12
```

<span data-ttu-id="3e507-163">이 샘플의 데이터는 `HousingPriceData` 같은 클래스로 모델링하고 [`IDataView`](xref:Microsoft.ML.IDataView)에 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e507-163">The data in this sample can be modeled by a class like `HousingPriceData` and loaded into an [`IDataView`](xref:Microsoft.ML.IDataView).</span></span>

```csharp
class HousingPriceData
{
    [LoadColumn(0)]
    public float CrimeRate { get; set; }

    [LoadColumn(1)]
    public float ResidentialZones { get; set; }

    [LoadColumn(2)]
    public float CommercialZones { get; set; }

    [LoadColumn(3)]
    public float NearWater { get; set; }

    [LoadColumn(4)]
    public float ToxicWasteLevels { get; set; }

    [LoadColumn(5)]
    public float AverageRoomNumber { get; set; }

    [LoadColumn(6)]
    public float HomeAge { get; set; }

    [LoadColumn(7)]
    public float BusinessCenterDistance { get; set; }

    [LoadColumn(8)]
    public float HighwayAccess { get; set; }

    [LoadColumn(9)]
    public float TaxRate { get; set; }

    [LoadColumn(10)]
    public float StudentTeacherRatio { get; set; }

    [LoadColumn(11)]
    public float PercentPopulationBelowPoverty { get; set; }

    [LoadColumn(12)]
    [ColumnName("Label")]
    public float Price { get; set; }
}
```

## <a name="train-the-model"></a><span data-ttu-id="3e507-164">모델 학습</span><span class="sxs-lookup"><span data-stu-id="3e507-164">Train the model</span></span>

<span data-ttu-id="3e507-165">다음 코드 샘플은 선형 회귀 모델을 학습하여 주택 가격을 예측하는 프로세스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3e507-165">The code sample below illustrates the process of training a linear regression model to predict house prices.</span></span>

```csharp
// 1. Get the column name of input features.
string[] featureColumnNames =
    data.Schema
        .Select(column => column.Name)
        .Where(columnName => columnName != "Label").ToArray();

// 2. Define estimator with data pre-processing steps
IEstimator<ITransformer> dataPrepEstimator =
    mlContext.Transforms.Concatenate("Features", featureColumnNames)
        .Append(mlContext.Transforms.NormalizeMinMax("Features"));

// 3. Create transformer using the data pre-processing estimator
ITransformer dataPrepTransformer = dataPrepEstimator.Fit(data);

// 4. Pre-process the training data
IDataView preprocessedTrainData = dataPrepTransformer.Transform(data);

// 5. Define Stochastic Dual Coordinate Ascent machine learning estimator
var sdcaEstimator = mlContext.Regression.Trainers.Sdca();

// 6. Train machine learning model
var sdcaModel = sdcaEstimator.Fit(preprocessedTrainData);
```

## <a name="explain-the-model-with-permutation-feature-importance-pfi"></a><span data-ttu-id="3e507-166">PFI(순열 기능 중요도)를 사용하여 모델 설명</span><span class="sxs-lookup"><span data-stu-id="3e507-166">Explain the model with Permutation Feature Importance (PFI)</span></span>

<span data-ttu-id="3e507-167">ML.NET에서는 해당 작업에 [`PermutationFeatureImportance`](xref:Microsoft.ML.PermutationFeatureImportanceExtensions) 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3e507-167">In ML.NET use the [`PermutationFeatureImportance`](xref:Microsoft.ML.PermutationFeatureImportanceExtensions) method for your respective task.</span></span>

```csharp
ImmutableArray<RegressionMetricsStatistics> permutationFeatureImportance =
    mlContext
        .Regression
        .PermutationFeatureImportance(sdcaModel, preprocessedTrainData, permutationCount:3);
```

<span data-ttu-id="3e507-168">학습 데이터 세트에 [`PermutationFeatureImportance`](xref:Microsoft.ML.PermutationFeatureImportanceExtensions)를 사용한 결과는 [`RegressionMetricsStatistics`](xref:Microsoft.ML.Data.RegressionMetricsStatistics) 개체의 [`ImmutableArray`](xref:System.Collections.Immutable.ImmutableArray)입니다.</span><span class="sxs-lookup"><span data-stu-id="3e507-168">The result of using [`PermutationFeatureImportance`](xref:Microsoft.ML.PermutationFeatureImportanceExtensions) on the training dataset is an [`ImmutableArray`](xref:System.Collections.Immutable.ImmutableArray) of [`RegressionMetricsStatistics`](xref:Microsoft.ML.Data.RegressionMetricsStatistics) objects.</span></span> <span data-ttu-id="3e507-169">[`RegressionMetricsStatistics`](xref:Microsoft.ML.Data.RegressionMetricsStatistics)는 [ 매개 변수에서 지정한 순열 수에 해당하는 여러 `RegressionMetrics`](xref:Microsoft.ML.Data.RegressionMetrics)`permutationCount` 관찰에 대해 평균, 표준 편차 같은 요약 통계를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3e507-169">[`RegressionMetricsStatistics`](xref:Microsoft.ML.Data.RegressionMetricsStatistics) provides summary statistics like mean and standard deviation for multiple observations of [`RegressionMetrics`](xref:Microsoft.ML.Data.RegressionMetrics) equal to the number of permutations specified by the `permutationCount` parameter.</span></span>

<span data-ttu-id="3e507-170">중요도, 이 경우 [`PermutationFeatureImportance`](xref:Microsoft.ML.PermutationFeatureImportanceExtensions)에서 계산한 R 제곱 메트릭의 절대 평균 감소를 가장 중요함에서 가장 중요하지 않음의 순서로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e507-170">The importance, or in this case, the absolute average decrease in R-squared metric calculated by [`PermutationFeatureImportance`](xref:Microsoft.ML.PermutationFeatureImportanceExtensions) can then be ordered from most important to least important.</span></span>

```csharp
// Order features by importance
var featureImportanceMetrics =
    permutationFeatureImportance
        .Select((metric, index) => new { index, metric.RSquared })
        .OrderByDescending(myFeatures => Math.Abs(myFeatures.RSquared.Mean));

Console.WriteLine("Feature\tPFI");

foreach (var feature in featureImportanceMetrics)
{
    Console.WriteLine($"{featureColumnNames[feature.index],-20}|\t{feature.RSquared.Mean:F6}");
}
```

<span data-ttu-id="3e507-171">`featureImportanceMetrics`에서 각 기능에 대한 값을 출력하면 다음과 유사한 출력이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e507-171">Printing the values for each of the features in `featureImportanceMetrics` would generate output similar to that below.</span></span> <span data-ttu-id="3e507-172">이 값은 제공된 데이터에 따라 달라지므로 결과가 다르게 보일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e507-172">Keep in mind that you should expect to see different results because these values vary based on the data that they are given.</span></span>

| <span data-ttu-id="3e507-173">기능</span><span class="sxs-lookup"><span data-stu-id="3e507-173">Feature</span></span> | <span data-ttu-id="3e507-174">R 제곱으로 변경</span><span class="sxs-lookup"><span data-stu-id="3e507-174">Change to R-Squared</span></span> |
|:--|:--:|
<span data-ttu-id="3e507-175">HighwayAccess</span><span class="sxs-lookup"><span data-stu-id="3e507-175">HighwayAccess</span></span>       |   <span data-ttu-id="3e507-176">-0.042731</span><span class="sxs-lookup"><span data-stu-id="3e507-176">-0.042731</span></span>
<span data-ttu-id="3e507-177">StudentTeacherRatio</span><span class="sxs-lookup"><span data-stu-id="3e507-177">StudentTeacherRatio</span></span> |   <span data-ttu-id="3e507-178">-0.012730</span><span class="sxs-lookup"><span data-stu-id="3e507-178">-0.012730</span></span>
<span data-ttu-id="3e507-179">BusinessCenterDistance</span><span class="sxs-lookup"><span data-stu-id="3e507-179">BusinessCenterDistance</span></span>| <span data-ttu-id="3e507-180">-0.010491</span><span class="sxs-lookup"><span data-stu-id="3e507-180">-0.010491</span></span>
<span data-ttu-id="3e507-181">TaxRate</span><span class="sxs-lookup"><span data-stu-id="3e507-181">TaxRate</span></span>             |   <span data-ttu-id="3e507-182">-0.008545</span><span class="sxs-lookup"><span data-stu-id="3e507-182">-0.008545</span></span>
<span data-ttu-id="3e507-183">AverageRoomNumber</span><span class="sxs-lookup"><span data-stu-id="3e507-183">AverageRoomNumber</span></span>   |   <span data-ttu-id="3e507-184">-0.003949</span><span class="sxs-lookup"><span data-stu-id="3e507-184">-0.003949</span></span>
<span data-ttu-id="3e507-185">CrimeRate</span><span class="sxs-lookup"><span data-stu-id="3e507-185">CrimeRate</span></span>           |   <span data-ttu-id="3e507-186">-0.003665</span><span class="sxs-lookup"><span data-stu-id="3e507-186">-0.003665</span></span>
<span data-ttu-id="3e507-187">CommercialZones</span><span class="sxs-lookup"><span data-stu-id="3e507-187">CommercialZones</span></span>     |   <span data-ttu-id="3e507-188">0.002749</span><span class="sxs-lookup"><span data-stu-id="3e507-188">0.002749</span></span>
<span data-ttu-id="3e507-189">HomeAge</span><span class="sxs-lookup"><span data-stu-id="3e507-189">HomeAge</span></span>             |   <span data-ttu-id="3e507-190">-0.002426</span><span class="sxs-lookup"><span data-stu-id="3e507-190">-0.002426</span></span>
<span data-ttu-id="3e507-191">ResidentialZones</span><span class="sxs-lookup"><span data-stu-id="3e507-191">ResidentialZones</span></span>    |   <span data-ttu-id="3e507-192">-0.002319</span><span class="sxs-lookup"><span data-stu-id="3e507-192">-0.002319</span></span>
<span data-ttu-id="3e507-193">NearWater</span><span class="sxs-lookup"><span data-stu-id="3e507-193">NearWater</span></span>           |   <span data-ttu-id="3e507-194">0.000203</span><span class="sxs-lookup"><span data-stu-id="3e507-194">0.000203</span></span>
<span data-ttu-id="3e507-195">PercentPopulationLivingBelowPoverty</span><span class="sxs-lookup"><span data-stu-id="3e507-195">PercentPopulationLivingBelowPoverty</span></span>|    <span data-ttu-id="3e507-196">0.000031</span><span class="sxs-lookup"><span data-stu-id="3e507-196">0.000031</span></span>
<span data-ttu-id="3e507-197">ToxicWasteLevels</span><span class="sxs-lookup"><span data-stu-id="3e507-197">ToxicWasteLevels</span></span>    |   <span data-ttu-id="3e507-198">-0.000019</span><span class="sxs-lookup"><span data-stu-id="3e507-198">-0.000019</span></span>

<span data-ttu-id="3e507-199">이 데이터 세트에 가장 중요한 기능 5개를 살펴보면 이 모델이 예측한 주택 가격은 고속도로 근접성, 지역 내 학교의 학생-교사 비율, 주요 업무 지구 근접성, 재산세율, 주택의 평균 방 수의 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="3e507-199">Taking a look at the five most important features for this dataset, the price of a house predicted by this model is influenced by its proximity to highways, student teacher ratio of schools in the area, proximity to major employment centers, property tax rate and average number of rooms in the home.</span></span>
