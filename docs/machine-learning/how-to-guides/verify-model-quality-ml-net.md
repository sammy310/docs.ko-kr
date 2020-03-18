---
title: 메트릭을 계산하여 기계 학습 모델 품질 평가
description: ML.NET에서 기계 학습 모델 품질을 평가하고 확인하기 위해 메트릭을 계산하는 방법 알아보기
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: d6409307cd283ae67d7546c4dc6e19e6089a0766
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2020
ms.locfileid: "73975837"
---
# <a name="calculate-metrics-to-evaluate-machine-learning-model-quality"></a><span data-ttu-id="22750-103">메트릭을 계산하여 기계 학습 모델 품질 평가</span><span class="sxs-lookup"><span data-stu-id="22750-103">Calculate metrics to evaluate machine learning model quality</span></span>

> [!NOTE]
> <span data-ttu-id="22750-104">이 항목은 현재 미리 보기로 제공되는 ML.NET을 참조하며, 자료는 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22750-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="22750-105">자세한 내용은 [ML.NET](https://dotnet.microsoft.com/apps/machinelearning-ai/ml-dotnet) 페이지를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="22750-105">For more information, visit the [ML.NET](https://dotnet.microsoft.com/apps/machinelearning-ai/ml-dotnet) page.</span></span>

<span data-ttu-id="22750-106">이 방법과 관련 샘플에서는 현재 **ML.NET 버전 0.10**을 사용하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22750-106">This how-to and related sample are currently using **ML.NET version 0.10**.</span></span> <span data-ttu-id="22750-107">자세한 내용은 [dotnet/machinelearning GitHub 리포지토리](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes)에서 릴리스 정보를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="22750-107">For more information, see the release notes at the [dotnet/machinelearning GitHub repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

<span data-ttu-id="22750-108">모델을 학습한 후에 품질을 평가하려면 어떻게 할까요?</span><span class="sxs-lookup"><span data-stu-id="22750-108">How do you evaluate quality after you train the model?</span></span> <span data-ttu-id="22750-109">각 기계 학습 작업은 품질 평가를 위한 메트릭을 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="22750-109">Each machine learning task exposes metrics for quality evaluation.</span></span>

<span data-ttu-id="22750-110">다음 예제와 같이 모델을 평가하는 작업에 해당하는 '컨텍스트'를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22750-110">You can use the corresponding 'context' of the task to evaluate the model, as in the following example:</span></span>

```csharp
// Read the test dataset.
var testData = reader.Read(testDataPath);
// Calculate metrics of the model on the test data.
var metrics = mlContext.Regression.Evaluate(model.Transform(testData), label: "Target");
```
