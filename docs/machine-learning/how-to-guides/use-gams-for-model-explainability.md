---
title: 모델 설명을 위해 일반화된 추가 모델 및 도형 함수 사용
description: ML.NET에서 모델 설명을 위해 일반화된 추가 모델 및 형상 함수 사용
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: ef56f737a2ad0cba616e32229ac3a395146fb6d2
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64662125"
---
# <a name="use-generalized-additive-models-and-shape-functions-for-model-explainability-in-mlnet"></a><span data-ttu-id="50d9c-103">ML.NET에서 모델 설명을 위해 일반화된 추가 모델 및 형상 함수 사용</span><span class="sxs-lookup"><span data-stu-id="50d9c-103">Use Generalized Additive Models and shape functions for model explainability in ML.NET</span></span>

> [!NOTE]
> <span data-ttu-id="50d9c-104">이 항목은 현재 미리 보기로 제공되는 ML.NET을 참조하며, 자료는 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50d9c-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="50d9c-105">자세한 내용은 [ML.NET 소개](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="50d9c-105">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="50d9c-106">이 방법과 관련 샘플에서는 현재 **ML.NET 버전 0.10**을 사용하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50d9c-106">This how-to and related sample are currently using **ML.NET version 0.10**.</span></span> <span data-ttu-id="50d9c-107">자세한 내용은 [dotnet/machinelearning GitHub 리포지토리](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes)에서 릴리스 정보를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="50d9c-107">For more information, see the release notes at the [dotnet/machinelearning GitHub repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

<span data-ttu-id="50d9c-108">기계 학습 모델을 만들 때는 예측을 수행하기에 부족한 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="50d9c-108">When creating machine learning models, it is often not enough to simply make predictions.</span></span> <span data-ttu-id="50d9c-109">기계 학습 개발자, 의사 결정자 및 모델의 영향을 받는 사람이 기계 학습 모델의 의사 결정 방법 및 성과에 도움이 되는 기능을 이해해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="50d9c-109">Often, machine learning developers, decision makers, and those affected by the models need to understand how machine learning models make decisions and which features contribute to their performance.</span></span> <span data-ttu-id="50d9c-110">**GAM(일반화된 추가 모델)** 은 기계 학습 개발자가 다른 사람이 쉽게 해석할 수 있는 고용량 모델을 만들 수 있도록 돕기 위해 Microsoft 내부에서 모델 설명에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="50d9c-110">**Generalized Additive Models (GAMs)** are used internally at Microsoft for model explainability to help machine learning developers create high-capacity models that can be easily interpreted by others.</span></span>

<span data-ttu-id="50d9c-111">GAM은 항이 단일 변수의 “형상 함수”라는 비선형 모델인 선형 모델을 나타내는 **해석 가능 모델** 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="50d9c-111">GAMs are a class of **interpretable models** that are linear models where the terms are nonlinear functions, called "shape functions" of a single variable.</span></span> <span data-ttu-id="50d9c-112">선형 모델이므로 간단하게 해석되지만, 모델이 단일 가중치 대신 기능의 함수를 학습하기 때문에 단순 선형 모델보다 복잡한 관계를 모델링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50d9c-112">As linear models, they are easily interpreted but because the models learn functions of features instead of a single weight, they can model more complex relationships than a simple linear model.</span></span> <span data-ttu-id="50d9c-113">결과로 생성된 GAM 추정기에는 학습 세트에 대한 평균 예측을 나타내는 절편항과 평균 예측의 편차를 나타내는 형상 함수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50d9c-113">The resulting GAM predictor has an intercept term that represents the average prediction over the training set, and shape functions that represent the deviation from the average prediction.</span></span> <span data-ttu-id="50d9c-114">형상 함수는 기능의 다양한 값에 대한 모델의 응답을 확인하기 위해 눈으로 검사하고, 코드 예제의 끝에 생성된 다음 그래프처럼 시각화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50d9c-114">The shape functions can be inspected by eye to see the response of the model to different values of a feature, and visualized like the following graph that is created at the end of the code example.</span></span> <span data-ttu-id="50d9c-115">ML.NET의 GAM 학습자는 비모수 형상 함수를 학습하기 위해 단순 그래디언트 부스팅 트리(예: 트리 스텀프)를 사용하여 구현되었으며, Lou, Caruana 및 Gehrke에 의해 [지능형 분류 및 회귀 모델](https://www.cs.cornell.edu/~yinlou/papers/lou-kdd12.pdf)에 설명된 방법을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="50d9c-115">The GAM trainer in ML.NET is implemented using shallow gradient boosted trees (for example tree stumps) to learn nonparametric shape functions, and is based on the method described in [Intelligible Models for Classification and Regression](https://www.cs.cornell.edu/~yinlou/papers/lou-kdd12.pdf) by Lou, Caruana, and Gehrke.</span></span>

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

![일반화된 추가 모델 형상 함수 그래프](./media/use-gams-for-model-explainability/gam-shape-function-graph.png)

<span data-ttu-id="50d9c-117">GAM 모델을 학습시키고 결과를 검사 및 해석하는 방법에 대한 샘플은 [dotnet/machinelearning GitHub 리포지토리](https://github.com/dotnet/machinelearning/blob/master/docs/samples/Microsoft.ML.Samples/Dynamic/GeneralizedAdditiveModels.cs)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="50d9c-117">For a sample of how to train a GAM model and inspect and interpret the results, see [the dotnet/machinelearning GitHub repository](https://github.com/dotnet/machinelearning/blob/master/docs/samples/Microsoft.ML.Samples/Dynamic/GeneralizedAdditiveModels.cs).</span></span>
