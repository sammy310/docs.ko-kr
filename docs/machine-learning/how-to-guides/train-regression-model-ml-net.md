---
title: ML.NET을 사용하여 값을 예측하도록 회귀 모델 학습시키기
description: ML.NET을 사용하여 값을 예측하도록 기계 학습 회귀 모델을 학습시키는 방법 알아보기
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: e7ea07471e155804a7ad36481aa469beda7028ae
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/08/2019
ms.locfileid: "57673147"
---
# <a name="train-a-regression-model-to-predict-a-value-using-mlnet"></a>ML.NET을 사용하여 값을 예측하도록 회귀 모델 학습시키기

> [!NOTE]
> 이 항목은 현재 미리 보기로 제공되는 ML.NET을 참조하며, 자료는 변경될 수 있습니다. 자세한 내용은 [ML.NET 소개](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet)를 참조하세요.

이 방법과 관련 샘플에서는 현재 **ML.NET 버전 0.10**을 사용하고 있습니다. 자세한 내용은 [dotnet/machinelearning GitHub 리포지토리](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes)에서 릴리스 정보를 참조하세요.

일반적으로 ML.NET의 모델 학습은 다음 세 단계로 이루어집니다.

1. `IDataView` 형식의 학습 데이터를 가져옵니다.
2. ‘학습 파이프라인’을 기본 ‘연산자’(추정기) 시퀀스로 빌드합니다.
3. 파이프라인에서 `Fit`을 호출하여 학습된 모델을 가져옵니다.

이 [예제 파일](https://github.com/dotnet/machinelearning/tree/master/test/data/generated_regression_dataset.csv)에서 예측된 레이블(`target`)은 마지막 열(12번째)이고, 나머지 열은 모두 기능입니다.

```console
feature_0;feature_1;feature_2;feature_3;feature_4;feature_5;feature_6;feature_7;feature_8;feature_9;feature_10;target
-2.75;0.77;-0.61;0.14;1.39;0.38;-0.53;-0.50;-2.13;-0.39;0.46;140.66
-0.61;-0.37;-0.12;0.55;-1.00;0.84;-0.02;1.30;-0.24;-0.50;-2.12;148.12
-0.85;-0.91;1.81;0.02;-0.78;-1.41;-1.09;-0.65;0.90;-0.37;-0.22;402.20
```

```csharp
// Create a new context for ML.NET operations. It can be used for exception tracking and logging, 
// as a catalog of available operations and as the source of randomness.
var mlContext = new MLContext();

// Step one: read the data as an IDataView.

// First, we define the reader: specify the data columns and where to find them in the text file.
var reader = mlContext.Data.CreateTextLoader(
        columns: new TextLoader.Column[]
        {
            // We read the first 11 values as a single float vector.
            new TextLoader.Column("FeatureVector",DataKind.R4,0,10),
            // Separately, read the target variable.
            new TextLoader.Column("Target",DataKind.R4,11)
        },
        // Default separator is tab, but the dataset has semicolon.
        separatorChar: ';',
        // First line of the file is a header, not a data row.
        hasHeader: true
);

// Now read the file (remember though, readers are lazy, so the actual reading will happen when the data is accessed).
var trainData = reader.Read(dataPath);

// Step two: define the learning pipeline.

// We 'start' the pipeline with the output of the reader.
var pipeline =
        // First 'normalize' the data (rescale to be
        // between -1 and 1 for all examples)
        mlContext.Transforms.Normalize("FeatureVector")
        // Cache data in memory so that SDCA trainer will be able to randomly access training examples without
        // reading data from disk multiple times. Data will be cached at its first use in any downstream step.
        // Notice that unused part in the data may not be cached.
        .AppendCacheCheckpoint(mlContext)
        // First 'normalize' the data (rescale to be
        // between -1 and 1 for all examples)
        .Append(mlContext.Regression.Trainers.StochasticDualCoordinateAscent("Target", "FeatureVector"));

// Step three. Fit the pipeline to the training data.
var model = pipeline.Fit(trainData);
```