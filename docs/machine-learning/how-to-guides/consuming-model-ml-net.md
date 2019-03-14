---
title: 앱에서 학습된 기계 학습 모델 운용 - ML.NET
description: ML.NET을 사용하여 애플리케이션에서 학습 및 평가된 기계 학습 모델을 이용하는 방법을 알아봅니다.
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: be6906c939b82d00067babaeebe809dae3de413a
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/08/2019
ms.locfileid: "57675136"
---
# <a name="operationalize-a-trained-machine-learning-model-in-apps---mlnet"></a>앱에서 학습된 기계 학습 모델 운용 - ML.NET

> [!NOTE]
> 이 항목은 현재 미리 보기로 제공되는 ML.NET을 참조하며, 자료는 변경될 수 있습니다. 자세한 내용은 [ML.NET 소개](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet)를 참조하세요.

이 방법과 관련 샘플에서는 현재 **ML.NET 버전 0.10**을 사용하고 있습니다. 자세한 내용은 [dotnet/machinelearning GitHub 리포지토리](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes)에서 릴리스 정보를 참조하세요.

모델 메트릭이 올바른 것으로 보이면 모델을 ‘운용’할 때가 되었습니다. 빌드한 `model` 개체를 사용 및 유지하고 다양한 환경에서 학습 중에 ‘배운’ 것과 동일한 단계를 적용하여 다시 사용할 수 있습니다.

모델을 파일에 저장하고 (잠재적으로 다른 컨텍스트에서) 다시 로드하려면 다음 예제를 사용합니다.

```csharp
using (var stream = File.Create(modelPath))
{
    // Saving and loading happens to 'dynamic' models.
    mlContext.Model.Save(model, stream);
}

// Potentially, the lines below can be in a different process altogether.

// When you load the model, it's a transformer.
ITransformer loadedModel;
using (var stream = File.OpenRead(modelPath))
    loadedModel = mlContext.Model.Load(stream);
```
