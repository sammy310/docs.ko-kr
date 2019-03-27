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
# <a name="determine-the-feature-importance-of-models-with-permutation-feature-importance-in-mlnet"></a>ML.NET에서 순열 기능 중요도를 사용하여 모델의 기능 중요도 판별

> [!NOTE]
> 이 항목은 현재 미리 보기로 제공되는 ML.NET을 참조하며, 자료는 변경될 수 있습니다. 자세한 내용은 [ML.NET 소개](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet)를 참조하세요.

이 방법과 관련 샘플에서는 현재 **ML.NET 버전 0.10**을 사용하고 있습니다. 자세한 내용은 [dotnet/machinelearning GitHub 리포지토리](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes)에서 릴리스 정보를 참조하세요.

기계 학습 모델을 만들 때는 예측을 수행하기에 부족한 경우가 많습니다. 기계 학습 개발자, 의사 결정자 및 모델의 영향을 받는 사람이 기계 학습 모델의 의사 결정 방법 및 성과에 도움이 되는 기능을 이해해야 합니다. PFI(`Permutation Feature Importance`)는 모델의 기능 중요성에 대한 기계 학습 개발자의 이해를 돕기 위해 Microsoft 내부에서 사용되는 모델 설명 도구입니다.

PFI는 [“랜덤 포레스트” 논문, 섹션 10](https://www.stat.berkeley.edu/~breiman/randomforest2001.pdf)에서 Breimanin이 제기한 기계 학습 모델의 **전역 기능 중요도**를 파악하는 기술입니다. PFI는 “기능의 값이 임의* 값으로 설정된 경우 모델에 어떤 영향을 미치나요?”라는 질문을 통해 기능 중요도를 측정합니다. PFI 방법의 장점은 모델에 종속되지 않는다는 것입니다. 평가할 수 있는 모든 모델에서 작동하며, 학습 세트만이 아닌 모든 데이터 세트를 사용하여 기능 중요도를 컴퓨팅할 수 있습니다. 따라서 PFI를 사용하여 다음 그래프와 같은 기능 중요도를 생성할 수 있습니다.

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

PFI를 사용하여 모델의 기능 중요도를 분석하는 샘플은 [dotnet/machinelearning GitHub 리포지토리](https://github.com/dotnet/machinelearning/tree/master/docs/samples/Microsoft.ML.Samples/Dynamic/PermutationFeatureImportance)를 참조하세요.

/* 정확히 임의는 아니지만 예제 세트에서 순열로 치환됩니다.
