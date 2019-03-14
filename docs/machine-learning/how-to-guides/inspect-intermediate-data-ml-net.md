---
title: ML.NET 파이프라인을 처리하는 동안 중간 데이터 값 검사
description: ML.NET 기계 학습 파이프라인을 처리하는 동안 실제 중간 데이터 값을 검사하는 방법 알아보기
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: 3d20f153be7b502fb5a542a942245546412efde2
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/08/2019
ms.locfileid: "57678646"
---
# <a name="inspect-intermediate-data-values-during-mlnet-pipeline-processing"></a><span data-ttu-id="14575-103">ML.NET 파이프라인을 처리하는 동안 중간 데이터 값 검사</span><span class="sxs-lookup"><span data-stu-id="14575-103">Inspect intermediate data values during ML.NET pipeline processing</span></span>

> [!NOTE]
> <span data-ttu-id="14575-104">이 항목은 현재 미리 보기로 제공되는 ML.NET을 참조하며, 자료는 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14575-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="14575-105">자세한 내용은 [ML.NET 소개](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="14575-105">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="14575-106">이 방법과 관련 샘플에서는 현재 **ML.NET 버전 0.10**을 사용하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14575-106">This how-to and related sample are currently using **ML.NET version 0.10**.</span></span> <span data-ttu-id="14575-107">자세한 내용은 [dotnet/machinelearning GitHub 리포지토리](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes)에서 릴리스 정보를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="14575-107">For more information, see the release notes at the [dotnet/machinelearning GitHub repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

<span data-ttu-id="14575-108">실험 중에 지정된 지점에서 데이터 처리 결과를 관찰하고 확인하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="14575-108">During the experiment, you may want to observe and validate the data processing results at a given point.</span></span> <span data-ttu-id="14575-109">ML.NET 작업이 지연되어 데이터의 '프라미스'인 개체를 생성하는 것이 쉽지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14575-109">This isn't easy since ML.NET operations are lazy, constructing objects that are 'promises' of data.</span></span>

<span data-ttu-id="14575-110">`GetColumn<T>` 확장 메서드를 사용하면 중간 데이터를 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14575-110">The `GetColumn<T>` extension method lets you inspect the intermediate data.</span></span> <span data-ttu-id="14575-111">그러면 한 데이터 열의 콘텐츠를 `IEnumerable`로 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="14575-111">It returns the contents of one data column as an `IEnumerable`.</span></span>

<span data-ttu-id="14575-112">다음 예제에서는 `GetColumn<T>` 확장 메서드를 사용하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="14575-112">The following example shows how to use the `GetColumn<T>` extension method:</span></span>

<span data-ttu-id="14575-113">[예제 파일](https://github.com/dotnet/machinelearning/tree/master/test/data/adult.tiny.with-schema.txt):</span><span class="sxs-lookup"><span data-stu-id="14575-113">[Example file](https://github.com/dotnet/machinelearning/tree/master/test/data/adult.tiny.with-schema.txt):</span></span>
```
Label   Workclass   education   marital-status
0   Private 11th    Never-married
0   Private HS-grad Married-civ-spouse
1   Local-gov   Assoc-acdm  Married-civ-spouse
1   Private Some-college    Married-civ-spouse

```

<span data-ttu-id="14575-114">클래스는 다음과 같이 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="14575-114">Our class is defined as follows:</span></span>

```csharp
public class InspectedRow
{
    [LoadColumn(0)]
    public bool IsOver50K { get; set; }
    [LoadColumn(1)]
    public string WorkClass { get; set; }
    [LoadColumn(2)]
    public string Education { get; set; }
    [LoadColumn(3)]
    public string MaritalStatus { get; set; }
}
```

```csharp
// Create a new context for ML.NET operations. It can be used for exception tracking and logging, 
// as a catalog of available operations and as the source of randomness.
var mlContext = new MLContext();

// Read the data into a data view.
var data = mlContext.Data.ReadFromTextFile<InspectedRow>(dataPath, hasHeader: true);

// Start creating our processing pipeline. For now, let's just concatenate all the text columns
// together into one.
var pipeline = mlContext.Transforms.Concatenate("AllFeatures", "WorkClass", "Education", "MaritalStatus");

// Fit our data pipeline and transform data with it.
var transformedData = pipeline.Fit(data).Transform(data);

// Extract the 'AllFeatures' column.
// This will give the entire dataset: make sure to only take several row
// in case the dataset is huge. The is similar to the static API, except
// you have to specify the column name and type.
var featureColumns =
    transformedData
        .GetColumn<string[]>(mlContext, "AllFeatures")
        .Take(20)
        .ToArray();
```
