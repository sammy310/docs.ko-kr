---
title: 데이터 처리에서 사용할 normalizer를 사용하여 학습 데이터 전처리 - ML.NET
description: normalizer를 사용하여 ML.NET에서 기계 학습 모델 빌드, 교육 및 점수 매기기에 사용하기 위해 학습 데이터를 전처리하는 방법 알아보기
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: 2d18f7c19a51fd929ac6efb7f600cb1ac2733de8
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/08/2019
ms.locfileid: "57676605"
---
# <a name="preprocess-training-data-with-normalizers-to-use-in-data-processing---mlnet"></a>데이터 처리에서 사용할 normalizer를 사용하여 학습 데이터 전처리 - ML.NET

> [!NOTE]
> 이 항목은 현재 미리 보기로 제공되는 ML.NET을 참조하며, 자료는 변경될 수 있습니다. 자세한 내용은 [ML.NET 소개](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet)를 참조하세요.

이 방법과 관련 샘플에서는 현재 **ML.NET 버전 0.10**을 사용하고 있습니다. 자세한 내용은 [dotnet/machinelearning GitHub 리포지토리](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes)에서 릴리스 정보를 참조하세요.

ML.NET는 많은 [파라메트릭 및 비파라메트릭 알고리즘](https://machinelearningmastery.com/parametric-and-nonparametric-machine-learning-algorithms/)을 노출합니다.

선형 또는 기타 파라메트릭 모델을 학습할 때 normalizer를 **사용**하는 것만큼 normalizer를 선택하는 것이 중요하지 **않습니다**.

항상 ML.NET 학습 파이프라인에 직접 normalizer를 포함합니다. 따라서:

- 테스트 데이터가 아닌 학습 데이터에 대해서만 학습합니다.
- 예측 시 추가 사전 처리를 수행할 필요 없이 새로 들어오는 모든 데이터에 올바르게 적용됩니다.

학습 파이프라인의 정규화를 보여주는 코드 조각은 다음과 같습니다. 아이리스 데이터 세트를 가정합니다.

```csharp
// Create a new context for ML.NET operations. It can be used for exception tracking and logging, 
// as a catalog of available operations and as the source of randomness.
var mlContext = new MLContext();

// Define the reader: specify the data columns and where to find them in the text file.
var reader = mlContext.Data.CreateTextLoader(
    columns: new TextLoader.Column[]
    {
        // The four features of the Iris dataset will be grouped together as one Features column.
        new TextLoader.Column("Features",DataKind.R4,0,3),
        // Label: kind of iris.
        new TextLoader.Column("Label",DataKind.TX,4)
    },
    // Default separator is tab, but the dataset has comma.
    separatorChar: ',',
    // First line of the file is a header, not a data row.
    hasHeader: true
);

// Read the training data.
var trainData = reader.Read(dataPath);

// Apply all kinds of standard ML.NET normalization to the raw features.
var pipeline =
    mlContext.Transforms.Normalize(
            new NormalizingEstimator.MinMaxColumn(inputColumnName:"Features", outputColumnName:"MinMaxNormalized", fixZero: true),
            new NormalizingEstimator.MeanVarColumn(inputColumnName: "Features", outputColumnName: "MeanVarNormalized", fixZero: true),
            new NormalizingEstimator.BinningColumn(inputColumnName: "Features", outputColumnName: "BinNormalized", numBins: 256));

// Let's train our pipeline of normalizers, and then apply it to the same data.
var normalizedData = pipeline.Fit(trainData).Transform(trainData);

// Inspect one column of the resulting dataset.
var meanVarValues = normalizedData.GetColumn<float[]>(mlContext, "MeanVarNormalized").ToArray();
```
