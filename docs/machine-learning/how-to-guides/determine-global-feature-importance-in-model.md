---
title: ML.NET에서 순열 기능 중요도를 사용하여 모델의 기능 중요도 판별
description: ML.NET에서 순열 기능 중요도를 사용하여 모델의 기능 중요도 파악
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: b0457bc07168579403e5a00383864c5612e1d17f
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/08/2019
ms.locfileid: "57675552"
---
# <a name="determine-the-feature-importance-of-models-with-permutation-feature-importance-in-mlnet"></a><span data-ttu-id="89447-103">ML.NET에서 순열 기능 중요도를 사용하여 모델의 기능 중요도 판별</span><span class="sxs-lookup"><span data-stu-id="89447-103">Determine the feature importance of models with Permutation Feature Importance in ML.NET</span></span>

> [!NOTE]
> <span data-ttu-id="89447-104">이 항목은 현재 미리 보기로 제공되는 ML.NET을 참조하며, 자료는 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89447-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="89447-105">자세한 내용은 [ML.NET 소개](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="89447-105">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="89447-106">이 방법과 관련 샘플에서는 현재 **ML.NET 버전 0.10**을 사용하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89447-106">This how-to and related sample are currently using **ML.NET version 0.10**.</span></span> <span data-ttu-id="89447-107">자세한 내용은 [dotnet/machinelearning GitHub 리포지토리](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes)에서 릴리스 정보를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="89447-107">For more information, see the release notes at the [dotnet/machinelearning GitHub repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

<span data-ttu-id="89447-108">기계 학습 모델을 만들 때는 예측을 수행하기에 부족한 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="89447-108">When creating machine learning models, it is often not enough to simply make predictions.</span></span> <span data-ttu-id="89447-109">기계 학습 개발자, 의사 결정자 및 모델의 영향을 받는 사람이 기계 학습 모델의 의사 결정 방법 및 성과에 도움이 되는 기능을 이해해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="89447-109">Often, machine learning developers, decision makers, and those affected by the models need to understand how machine learning models make decisions and which features contribute to their performance.</span></span> <span data-ttu-id="89447-110">PFI(`Permutation Feature Importance`)는 모델의 기능 중요성에 대한 기계 학습 개발자의 이해를 돕기 위해 Microsoft 내부에서 사용되는 모델 설명 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="89447-110">`Permutation Feature Importance` (PFI) is a model explainability tool that is used internally at Microsoft to help machine learning developers better understand the feature importance of models.</span></span>

<span data-ttu-id="89447-111">PFI는 [“랜덤 포레스트” 논문, 섹션 10](https://www.stat.berkeley.edu/~breiman/randomforest2001.pdf)에서 Breimanin이 제기한 기계 학습 모델의 **전역 기능 중요도**를 파악하는 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="89447-111">PFI is a technique to determine **global feature importance** in a trained machine learning model, motivated by Breiman in the ["Random Forests" paper, section 10](https://www.stat.berkeley.edu/~breiman/randomforest2001.pdf).</span></span> <span data-ttu-id="89447-112">PFI는 “기능의 값이 임의\* 값으로 설정된 경우 모델에 어떤 영향을 미치나요?”라는 질문을 통해 기능 중요도를 측정합니다.</span><span class="sxs-lookup"><span data-stu-id="89447-112">PFI measures feature importance by asking the question, "What would the effect on the model be if the values for a feature were set to a random\* value?".</span></span> <span data-ttu-id="89447-113">PFI 방법의 장점은 모델에 종속되지 않는다는 것입니다. 평가할 수 있는 모든 모델에서 작동하며, 학습 세트만이 아닌 모든 데이터 세트를 사용하여 기능 중요도를 컴퓨팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89447-113">The advantage of the PFI method is that it is model agnostic — it works with any model that can be evaluated — and it can use any dataset, not just the training set, to compute feature importance.</span></span> <span data-ttu-id="89447-114">따라서 PFI를 사용하여 다음 그래프와 같은 기능 중요도를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89447-114">You can use PFI like so to produce feature importances like this graph:</span></span>

![순열 기능 중요도 그래프](./media/determine-global-feature-importance-in-model/pfi-graph.png)

```csharp
// Compute the feature importance using PFI
var permutationMetrics = mlContext.Regression.PermutationFeatureImportance(model.LastTransformer, model.Transform(data), "MedianHomeValue");

// Get the feature names from the training set
var featureNames =
    data.Schema.AsEnumerable()
    .Select(column => column.Name) // Get the column names
    .Where(name => name != "MedianHomeValue") // Drop the Label
    .ToArray();

// Write out the feature names and their importance to the model's Mean R-squared value
for (int i = 0; i < featureNames.Length;i++)
{
    Console.WriteLine($"{featureNames[i]}\t{permutationMetrics[i].RSquared.Mean:G4}");
}
```

<span data-ttu-id="89447-116">PFI를 사용하여 모델의 기능 중요도를 분석하는 샘플은 [dotnet/machinelearning GitHub 리포지토리](https://github.com/dotnet/machinelearning/tree/master/docs/samples/Microsoft.ML.Samples/Dynamic/PermutationFeatureImportance)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="89447-116">For a sample using PFI to analyze the feature importance of a model, see [the dotnet/machinelearning GitHub repository](https://github.com/dotnet/machinelearning/tree/master/docs/samples/Microsoft.ML.Samples/Dynamic/PermutationFeatureImportance).</span></span>

<span data-ttu-id="89447-117">/\* 정확히 임의는 아니지만 예제 세트에서 순열로 치환됩니다.</span><span class="sxs-lookup"><span data-stu-id="89447-117">/\* Well, not random exactly, but permuted across the set of examples.</span></span>
