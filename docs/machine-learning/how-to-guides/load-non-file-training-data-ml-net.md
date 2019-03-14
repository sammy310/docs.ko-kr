---
title: 텍스트 파일에 포함되지 않은 데이터를 사용하여 기계 학습 모델 학습 - ML.NET
description: ML.NET를 사용하여 기계 학습 모델 학습의 파일이 아닌 학습 데이터를 예측 파이프라인의 일부로 로드하는 방법을 알아봅니다.
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: 27b327a63cb55b7fce0f4ff7facd3ee7c4a1c85c
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/08/2019
ms.locfileid: "57678618"
---
# <a name="train-a-machine-learning-model-with-data-thats-not-in-a-text-file---mlnet"></a>텍스트 파일에 포함되지 않은 데이터를 사용하여 기계 학습 모델 학습 - ML.NET

> [!NOTE]
> 이 항목은 현재 미리 보기로 제공되는 ML.NET을 참조하며, 자료는 변경될 수 있습니다. 자세한 내용은 [ML.NET 소개](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet)를 참조하세요.

이 방법과 관련 샘플에서는 현재 **ML.NET 버전 0.10**을 사용하고 있습니다. 자세한 내용은 [dotnet/machinelearning GitHub 리포지토리](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes)에서 릴리스 정보를 참조하세요.

ML.NET에 대해 일반적으로 설명한 사용 사례에서는 `TextLoader`를 사용하여 파일의 학습 데이터를 읽을 수 있습니다.
그러나 실시간 교육 시나리오에서 데이터는 다음과 같이 다른 곳에 위치할 수 있습니다.

* SQL 테이블
* 로그 파일에서 추출
* 즉석에서 생성

[스키마 이해](https://github.com/dotnet/machinelearning/tree/master/docs/code/SchemaComprehension.md)를 사용하여 기존 C# `IEnumerable`을 ML.NET에 `DataView`로 가져옵니다.

예를 들어 고객 변동 예측 모델을 빌드하고, 프로덕션 시스템에서 다음 기능을 추출합니다.

* 고객 ID(모델에서 무시됨)
* 고객(대상 '레이블')이 변동되었는지 여부
* '인구 통계 범주'('청년'과 같은 하나의 문자열)
* 지난 5일의 방문 횟수

```csharp
private class CustomerChurnInfo
{
    public string CustomerID { get; set; }
    public bool HasChurned { get; set; }
    public string DemographicCategory { get; set; }
    // Visits during last 5 days, latest to newest.
    [VectorType(5)]
    public float[] LastVisits { get; set; }
}
```

다음 코드를 사용하여 이 데이터를 `DataView`에 로드하고 모델을 학습합니다.

```csharp
// Create a new context for ML.NET operations. It can be used for exception tracking and logging,
// as a catalog of available operations and as the source of randomness.
var mlContext = new MLContext();

// Step one: read the data as an IDataView.
// Let's assume that 'GetChurnData()' fetches and returns the training data from somewhere.
IEnumerable<CustomerChurnInfo> churnData = GetChurnInfo();

// Turn the data into the ML.NET data view.
// We can use CreateDataView or CreateStreamingDataView, depending on whether 'churnData' is an IList,
// or merely an IEnumerable.
var trainData = mlContext.Data.ReadFromEnumerable(churnData);

// Build the learning pipeline.
// In our case, we will one-hot encode the demographic category, and concatenate that with the number of visits.
// We apply our FastTree binary classifier to predict the 'HasChurned' label.

var pipeline = mlContext.Transforms.Categorical.OneHotEncoding("DemographicCategory")
    .Append(mlContext.Transforms.Concatenate("Features", "DemographicCategory", "LastVisits"))
    .Append(mlContext.BinaryClassification.Trainers.FastTree("HasChurned", "Features", numTrees: 20));

var model = pipeline.Fit(trainData);
```
