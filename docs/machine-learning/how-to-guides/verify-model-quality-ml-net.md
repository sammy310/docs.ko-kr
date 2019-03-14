---
title: 메트릭을 계산하여 기계 학습 모델 품질 평가 - ML.NET
description: ML.NET에서 기계 학습 모델 품질을 평가하고 확인하기 위해 메트릭을 계산하는 방법 알아보기
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: ad71f7da6981ac370e60725f88d3c70b1d5c5237
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/08/2019
ms.locfileid: "57679218"
---
# <a name="calculate-metrics-to-evaluate-machine-learning-model-quality---mlnet"></a><span data-ttu-id="9be2d-103">메트릭을 계산하여 기계 학습 모델 품질 평가 - ML.NET</span><span class="sxs-lookup"><span data-stu-id="9be2d-103">Calculate metrics to evaluate machine learning model quality - ML.NET</span></span>

> [!NOTE]
> <span data-ttu-id="9be2d-104">이 항목은 현재 미리 보기로 제공되는 ML.NET을 참조하며, 자료는 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9be2d-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="9be2d-105">자세한 내용은 [ML.NET 소개](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9be2d-105">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="9be2d-106">이 방법과 관련 샘플에서는 현재 **ML.NET 버전 0.10**을 사용하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9be2d-106">This how-to and related sample are currently using **ML.NET version 0.10**.</span></span> <span data-ttu-id="9be2d-107">자세한 내용은 [dotnet/machinelearning GitHub 리포지토리](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes)에서 릴리스 정보를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9be2d-107">For more information, see the release notes at the [dotnet/machinelearning GitHub repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

<span data-ttu-id="9be2d-108">모델을 학습한 후에 품질을 평가하려면 어떻게 할까요?</span><span class="sxs-lookup"><span data-stu-id="9be2d-108">How do you evaluate quality after you train the model?</span></span> <span data-ttu-id="9be2d-109">각 기계 학습 작업은 품질 평가를 위한 메트릭을 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="9be2d-109">Each machine learning task exposes metrics for quality evaluation.</span></span>

<span data-ttu-id="9be2d-110">다음 예제와 같이 모델을 평가하는 작업에 해당하는 '컨텍스트'를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9be2d-110">You can use the corresponding 'context' of the task to evaluate the model, as in the following example:</span></span>

```csharp
// Read the test dataset.
var testData = reader.Read(testDataPath);
// Calculate metrics of the model on the test data.
var metrics = mlContext.Regression.Evaluate(model.Transform(testData), label: "Target");
```