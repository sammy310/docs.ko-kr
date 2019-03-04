---
title: 범주 데이터에 모델 학습용 기능 엔지니어링 적용 - ML.NET
description: ML.NET를 사용하여 범주 데이터에 기계 학습 모델 학습용 기능 엔지니어링을 적용하는 방법을 알아봅니다.
ms.date: 02/06/2019
ms.custom: mvc,how-to
ms.openlocfilehash: eedbe0499784e7a99b0101c42892652daef3a114
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/28/2019
ms.locfileid: "56968415"
---
# <a name="apply-feature-engineering-for-model-training-on-categorical-data---mlnet"></a>범주 데이터에 모델 학습용 기능 엔지니어링 적용 - ML.NET

모든 ML.NET `learners`가 `float vector`로 기능을 사용하므로 비부동 데이터를 `float` 데이터 형식으로 변환해야 합니다.

데이터 세트에 `categorical` 데이터(예: ‘enum’)가 포함된 경우 ML.NET에서 기능으로 변환하는 여러 가지 방법을 제공합니다.

- 원 핫 인코딩(one-hot encoding)
- 해시 기반 원 핫 인코딩(one-hot encoding)
- 이진 인코딩(범주 인덱스를 비트 시퀀스로 변환하고 비트를 기능으로 사용)

일부 범주의 카디널리티가 매우 높은 경우(예: 자주 발생하는 세트가 작은, 각기 다른 많은 값) `one-hot encoding`은 낭비일 수 있습니다. 이 경우 개수 기반 기능 선택을 통해 인코드할 슬롯 수를 줄입니다.

ML.NET 학습 파이프라인에 범주 기능화를 직접 포함하여 범주 변환을 보장합니다.

- 테스트 데이터가 아닌 학습 데이터에 대해서만 ‘학습’됩니다.
- 예측 시 추가 전처리 없이도 새 수신 데이터에 올바르게 적용됩니다.

다음 예제에서는 [성인 인구 조사 데이터 세트](https://github.com/dotnet/machinelearning/blob/master/test/data/adult.tiny.with-schema.txt)에 대한 범주 처리를 보여 줍니다.

```console
Label   Workclass   education   marital-status  occupation  relationship    ethnicity   sex native-country-region   age fnlwgt  education-num   capital-gain    capital-loss    hours-per-week
0   Private 11th    Never-married   Machine-op-inspct   Own-child   Black   Male    United-States   25  226802  7   0   0   40
0   Private HS-grad Married-civ-spouse  Farming-fishing Husband White   Male    United-States   38  89814   9   0   0   50
1   Local-gov   Assoc-acdm  Married-civ-spouse  Protective-serv Husband White   Male    United-States   28  336951  12  0   0   40
1   Private Some-college    Married-civ-spouse  Machine-op-inspct   Husband Black   Male    United-States   44  160323  10  7688    0   40
```

```csharp
// Create a new context for ML.NET operations. It can be used for exception tracking and logging, 
// as a catalog of available operations and as the source of randomness.
var mlContext = new MLContext();

// Define the reader: specify the data columns and where to find them in the text file.
var reader = mlContext.Data.CreateTextLoader(new[] 
    {
        new TextLoader.Column("Label", DataKind.BL, 0),
        // We will load all the categorical features into one vector column of size 8.
        new TextLoader.Column("CategoricalFeatures", DataKind.TX, 1, 8),
        // Similarly, load all numerical features into one vector of size 6.
        new TextLoader.Column("NumericalFeatures", DataKind.R4, 9, 14),
        // Let's also separately load the 'Workclass' column.
        new TextLoader.Column("Workclass", DataKind.TX, 1),
    },
    hasHeader: true
);

// Read the data.
var data = reader.Read(dataPath);

// Inspect the first 10 records of the categorical columns to check that they are correctly read.
var catColumns = data.GetColumn<string[]>(mlContext, "CategoricalFeatures").Take(10).ToArray();

// Build several alternative featurization pipelines.
var pipeline =
    // Convert each categorical feature into one-hot encoding independently.
    mlContext.Transforms.Categorical.OneHotEncoding("CategoricalFeatures", "CategoricalOneHot")
        // Convert all categorical features into indices, and build a 'word bag' of these.
        .Append(mlContext.Transforms.Categorical.OneHotEncoding("CategoricalFeatures", "CategoricalBag",OneHotEncodingTransformer.OutputKind.Bag))
        // One-hot encode the workclass column, then drop all the categories that have fewer than 10 instances in the train set.
        .Append(mlContext.Transforms.Categorical.OneHotEncoding("Workclass", "WorkclassOneHot"))
        .Append(mlContext.Transforms.FeatureSelection.SelectFeaturesBasedOnCount("WorkclassOneHot", "WorkclassOneHotTrimmed", count: 10));

// Let's train our pipeline, and then apply it to the same data.
var transformedData = pipeline.Fit(data).Transform(data);

// Inspect some columns of the resulting dataset.
var categoricalBags = transformedData.GetColumn<float[]>(mlContext, "CategoricalBag").Take(10).ToArray();
var workclasses = transformedData.GetColumn<float[]>(mlContext, "WorkclassOneHotTrimmed").Take(10).ToArray();

// Of course, if we want to train the model, we will need to compose a single float vector of all the features.
// Here's how we could do this:

var fullLearningPipeline = pipeline
    // Concatenate two of the 3 categorical pipelines, and the numeric features.
    .Append(mlContext.Transforms.Concatenate("Features", "NumericalFeatures", "CategoricalBag", "WorkclassOneHotTrimmed"))
    // Cache data in memory so that the following trainer will be able to access training examples without
    // reading them from disk multiple times.
    .AppendCacheCheckpoint(mlContext)
    // Now we're ready to train. We chose our FastTree trainer for this classification task.
    .Append(mlContext.BinaryClassification.Trainers.FastTree(numTrees: 50));

// Train the model.
var model = fullLearningPipeline.Fit(data);
```
