---
title: 모델 구축에 사용할 데이터 준비
description: ML.NET에서 변형을 사용하여 추가 처리 또는 모델 빌드를 위해 데이터를 조작하고 준비하는 방법을 알아봅니다.
author: luisquintanilla
ms.author: luquinta
ms.date: 01/29/2020
ms.custom: mvc, how-to, title-hack-0625
ms.openlocfilehash: 12f933253af9ea519d711c20227fe075fed003de
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452989"
---
# <a name="prepare-data-for-building-a-model"></a>모델 구축에 사용할 데이터 준비

ML.NET을 사용하여 추가 처리 또는 모델 빌드를 위해 데이터를 준비하는 방법을 알아봅니다.

데이터는 정리되어 있지 않고 흩어져 있는 경우가 많습니다. ML.NET 기계 학습 알고리즘에서는 단일 숫자 벡터 형식의 입력 또는 기능을 예상합니다. 마찬가지로 예측할 값(레이블), 특히 범주 데이터의 경우에는 인코딩해야 합니다. 따라서 데이터를 준비하는 목적 중 하나가 ML.NET 알고리즘에서 예상하는 형식으로 데이터를 가져오는 것입니다.

## <a name="filter-data"></a>데이터 필터링

데이터 세트의 일부 데이터는 분석하기에 관련성이 없는 경우가 있습니다. 관련 없는 데이터를 제거하는 접근법이 필터링입니다. [`DataOperationsCatalog`](xref:Microsoft.ML.DataOperationsCatalog)에는 모든 데이터를 포함하는 [`IDataView`](xref:Microsoft.ML.IDataView)에서 수행하여 관심 있는 데이터 요소만 포함하는 [IDataView](xref:Microsoft.ML.IDataView)를 반환하는 일련의 필터 작업 세트가 있습니다. 필터 작업이 [`TransformsCatalog`](xref:Microsoft.ML.TransformsCatalog)의 것과 같은 [`IEstimator`](xref:Microsoft.ML.IEstimator%601) 또는 [`ITransformer`](xref:Microsoft.ML.ITransformer)가 아니므로, [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601) 또는 [`TransformerChain`](xref:Microsoft.ML.Data.TransformerChain%601) 데이터 준비 파이프라인으로 포함할 수는 없습니다.

다음 입력 데이터를 `data`라는 [`IDataView`](xref:Microsoft.ML.IDataView)로 로드합니다.

```csharp
HomeData[] homeDataList = new HomeData[]
{
    new HomeData
    {
        NumberOfBedrooms=1f,
        Price=100000f
    },
    new HomeData
    {
        NumberOfBedrooms=2f,
        Price=300000f
    },
    new HomeData
    {
        NumberOfBedrooms=6f,
        Price=600000f
    }
};
```

열 값에 기반하여 데이터를 필터링하려면 [`FilterRowsByColumn`](xref:Microsoft.ML.DataOperationsCatalog.FilterRowsByColumn%2A) 메서드를 사용합니다.

```csharp
// Apply filter
IDataView filteredData = mlContext.Data.FilterRowsByColumn(data, "Price", lowerBound: 200000, upperBound: 1000000);
```

위의 샘플에서는 데이터 세트에서 가격대가 200000 ~ 1000000인 행을 가져옵니다. 이 필터를 적용하면 데이터에서 마지막 두 개 행만 반환되고 첫 행은 가격이 100000이고 지정한 범위에 속하지 않으므로 제외됩니다.

## <a name="replace-missing-values"></a>누락된 값 대체

데이터 세트에서 값이 누락되는 경우는 일반적입니다. 누락된 값을 다루는 접근법 중 하나는 데이터에서 평균 값 등 다른 의미 있는 값인 경우 지정된 유형에 대한 기본 값으로 대체하는 것입니다.

다음 입력 데이터를 `data`라는 [`IDataView`](xref:Microsoft.ML.IDataView)로 로드합니다.

```csharp
HomeData[] homeDataList = new HomeData[]
{
    new HomeData
    {
        NumberOfBedrooms=1f,
        Price=100000f
    },
    new HomeData
    {
        NumberOfBedrooms=2f,
        Price=300000f
    },
    new HomeData
    {
        NumberOfBedrooms=6f,
        Price=float.NaN
    }
};
```

목록의 마지막 요소에 `Price`에 대한 누락된 값이 있습니다. `Price` 열의 누락된 값을 대체하려면 [`ReplaceMissingValues`](xref:Microsoft.ML.ExtensionsCatalog.ReplaceMissingValues%2A) 메서드를 사용하여 이 누락된 값을 채우세요.

> [!IMPORTANT]
> [`ReplaceMissingValue`](xref:Microsoft.ML.ExtensionsCatalog.ReplaceMissingValues%2A)은 숫자 데이터에만 작용합니다.

```csharp
// Define replacement estimator
var replacementEstimator = mlContext.Transforms.ReplaceMissingValues("Price", replacementMode: MissingValueReplacingEstimator.ReplacementMode.Mean);

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
ITransformer replacementTransformer = replacementEstimator.Fit(data);

// Transform data
IDataView transformedData = replacementTransformer.Transform(data);
```

ML.NET은 다양한 [대체 모드](xref:Microsoft.ML.Transforms.MissingValueReplacingEstimator.ReplacementMode) 지원합니다. 위의 샘플에서는 해당 열의 평균 값으로 누락된 값을 채우는 `Mean` 대체 모드를 사용합니다. 대체하면 데이터에서 100,000과 300,000의 평균인 200,000으로 마지막 요소에 대한 `Price` 속성을 채웁니다.

## <a name="use-normalizers"></a>노멀라이저 사용

[정규화](https://en.wikipedia.org/wiki/Feature_scaling)는 기계 학습 알고리즘이 보다 정확하게 처리할 수 있도록 기능을 동일한 범위(일반적으로 0에서 1 사이)로 조정하는 데 사용되는 데이터 전처리 기술입니다. 예를 들어, 나이는 일반적으로 0-100 범위, 소득은 0에서 수천 범위로 그 범위가 상당히 다양합니다. 정규화 변형에 대한 보다 자세한 목록과 설명은 [변형 페이지](../resources/transforms.md)를 참조하세요.

### <a name="min-max-normalization"></a>최소-최대 정규화

다음 입력 데이터를 `data`라는 [`IDataView`](xref:Microsoft.ML.IDataView)로 로드합니다.

```csharp
HomeData[] homeDataList = new HomeData[]
{
    new HomeData
    {
        NumberOfBedrooms = 2f,
        Price = 200000f
    },
    new HomeData
    {
        NumberOfBedrooms = 1f,
        Price = 100000f
    }
};
```

정규화는 단일 숫자 값뿐 아니라 벡터를 포함하는 열에도 적용할 수 있습니다. [`NormalizeMinMax`](xref:Microsoft.ML.NormalizationCatalog.NormalizeMinMax%2A) 메서드를 사용하는 최소-최대 정규화를 통해 `Price` 열의 데이터를 정규화합니다.

```csharp
// Define min-max estimator
var minMaxEstimator = mlContext.Transforms.NormalizeMinMax("Price");

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
ITransformer minMaxTransformer = minMaxEstimator.Fit(data);

// Transform data
IDataView transformedData = minMaxTransformer.Transform(data);
```

원래 가격 값 `[200000,100000]`은 0-1 범위에서 출력 값을 생성하는 `MinMax` 정규화 공식을 사용하여 `[ 1, 0.5 ]`로 변환됩니다.

### <a name="binning"></a>범주화

[범주화](https://en.wikipedia.org/wiki/Data_binning)는 연속적인 값을 별도의 값 표현으로 변환합니다. 예를 들어, 기능 중 하나가 나이라고 가정하면 범주화는 실제 나이 값 대신, 해당 값의 범위를 만듭니다. 0-18, 19-35 등이 각 범주가 될 수 있습니다.

다음 입력 데이터를 `data`라는 [`IDataView`](xref:Microsoft.ML.IDataView)로 로드합니다.

```csharp
HomeData[] homeDataList = new HomeData[]
{
    new HomeData
    {
        NumberOfBedrooms=1f,
        Price=100000f
    },
    new HomeData
    {
        NumberOfBedrooms=2f,
        Price=300000f
    },
    new HomeData
    {
        NumberOfBedrooms=6f,
        Price=600000f
    }
};
```

[`NormalizeBinning`](xref:Microsoft.ML.NormalizationCatalog.NormalizeBinning%2A) 메서드를 사용하여 데이터를 bin으로 정규합니다. `maximumBinCount` 매개 변수를 사용하면 데이터를 분류하는 데 필요한 bin 수를 지정할 수 있습니다. 이 예에서는 데이터가 2개의 bin으로 분류됩니다.

```csharp
// Define binning estimator
var binningEstimator = mlContext.Transforms.NormalizeBinning("Price", maximumBinCount: 2);

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
var binningTransformer = binningEstimator.Fit(data);

// Transform Data
IDataView transformedData = binningTransformer.Transform(data);
```

범주화 결과로, `[0,200000,Infinity]`의 bin 범위가 만들어집니다. 따라서 첫 번째 관찰 값이 0-200000이고 나머지가 200000보다 크지만, 무한보다는 적기 때문에 결과로 만들지는 bin은 `[0,1,1]`입니다.

## <a name="work-with-categorical-data"></a>범주 데이터 작업

가장 일반적인 데이터 유형 중 하나는 범주 데이터입니다. 범주 데이터에는 유한한 개수의 범주가 있습니다. 예를 들어 미국의 주 또는 그림 집합에 있는 동물 유형의 목록입니다. 범주 데이터가 기능 또는 레이블인지 관계없이 기계 학습 모델을 생성하는 데 사용할 수 있도록 숫자 값에 매핑되어야 합니다. 해결 중인 문제에 따라 ML.NET에서 범주 데이터로 작업하는 방법은 여러 가지가 있습니다.

### <a name="key-value-mapping"></a>키 값 매핑

ML.NET에서 키는 범주를 나타내는 정수 값입니다. 키 값 매핑은 학습을 위해 문자열 레이블을 고유한 정수 값에 매핑한 다음 모델을 사용하여 예측을 생성할 때 다시 문자열 값으로 매핑하는 데 사용하는 경우가 가장 많습니다.

키 값 매핑을 수행하는 데 사용되는 변환은 [MapValueToKey](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A) 및 [MapKeyToValue](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapKeyToValue%2A)입니다.

`MapValueToKey`는 모델에 매핑 사전을 추가하여 예측을 생성할 때 `MapKeyToValue`가 역방향 변환을 수행할 수 있도록 합니다.

### <a name="one-hot-encoding"></a>원 핫 인코딩(one-hot encoding)

원 핫 인코딩은 유한한 값 집합을 사용하여 이진 표현의 문자열 내 고유한 위치에 단일 `1` 값이 있는 정수로 매핑합니다. 범주 데이터를 암시적으로 정렬하지 않는 경우 원 핫 인코딩을 선택하는 것이 좋습니다. 다음 표에서는 우편 번호를 원시 값으로 사용하는 예를 보여 줍니다.

|원시 값|원 핫 인코딩된 값|
|---------|---------------------|
|98052|00...01|
|98100|00...10|
|...|...|
|98109|10...00|

범주 데이터를 원 핫 인코딩된 숫자로 변환하는 변환은 [`OneHotEncoding`](xref:Microsoft.ML.CategoricalCatalog.OneHotEncoding%2A)입니다.

### <a name="hashing"></a>해시

해시는 범주 데이터를 숫자로 변환하는 또 다른 방법입니다. 해시 함수는 임의 크기의 데이터(예: 텍스트 문자열)를 고정 범위의 숫자로 매핑합니다. 해시는 빠르고 공간 효율적으로 피터를 벡터화할 수 있습니다. 기계 학습에서 해시의 한 가지 주목할 만한 예는 알려진 단어의 사전을 유지 관리하는 대신 이메일의 모든 단어를 해시하고 큰 기능 벡터에 추가하는 스팸 메일 필터링입니다. 이러한 방식으로 해시를 사용하면 사전에 없는 단어를 사용하는 악의적인 스팸 필터링 회피 문제를 방지할 수 있습니다.

ML.NET은 [Hash](xref:Microsoft.ML.ConversionsExtensionsCatalog.Hash%2A) 변환을 제공하여 텍스트, 날짜 및 숫자 데이터에 대한 해시를 수행합니다. 값 키 매핑과 마찬가지로 해시 변환의 출력은 키 형식입니다.

## <a name="work-with-text-data"></a>텍스트 데이터 작업

범주 데이터와 마찬가지로 텍스트 데이터를 사용하여 기계 학습 모델을 빌드하려면 먼저 숫자 기능으로 변환해야 합니다. 텍스트 변형에 대한 보다 자세한 목록과 설명은 [변형 페이지](../resources/transforms.md)를 참조하세요.

[`IDataView`](xref:Microsoft.ML.IDataView)로 로드된 아래 데이터와 같은 데이터 사용:

```csharp
ReviewData[] reviews = new ReviewData[]
{
    new ReviewData
    {
        Description="This is a good product",
        Rating=4.7f
    },
    new ReviewData
    {
        Description="This is a bad product",
        Rating=2.3f
    }
};
```

ML.NET은 텍스트의 문자열 값에 일련의 개별 변환을 적용하여 텍스트에서 기능 집합을 만드는 [`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText%2A) 변환을 제공합니다.

```csharp
// Define text transform estimator
var textEstimator  = mlContext.Transforms.Text.FeaturizeText("Description");

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
ITransformer textTransformer = textEstimator.Fit(data);

// Transform data
IDataView transformedData = textTransformer.Transform(data);
```

결과로 만들어지는 변형은 `Description` 열의 텍스트 값을 아래 출력과 같은 숫자 벡터로 변환합니다.

```text
[ 0.2041241, 0.2041241, 0.2041241, 0.4082483, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0, 0, 0, 0, 0.4472136, 0.4472136, 0.4472136, 0.4472136, 0.4472136, 0 ]
```

`FeaturizeText`를 구성하는 변환은 기능 생성을 보다 세부적으로 제어하기 위해 개별적으로 적용될 수도 있습니다.

```csharp
// Define text transform estimator
var textEstimator = mlContext.Transforms.Text.NormalizeText("Description")
    .Append(mlContext.Transforms.Text.TokenizeIntoWords("Description"))
    .Append(mlContext.Transforms.Text.RemoveDefaultStopWords("Description"))
    .Append(mlContext.Transforms.Conversion.MapValueToKey("Description"))
    .Append(mlContext.Transforms.Text.ProduceNgrams("Description"))
    .Append(mlContext.Transforms.NormalizeLpNorm("Description"));
```

`textEstimator`에는 [`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText%2A) 메서드에서 수행하는 작업의 하위 세트가 있습니다. 보다 복잡한 파이프라인의 이점은 데이터에 적용되는 변형에 대한 제어와 가시성입니다.

다음은 예로 첫 번째 항목을 사용하여 `textEstimator`에서 정의하는 변형 단계에서 생성되는 결과에 대한 자세한 설명입니다.

**원문: This is a good product**

|변형 | 설명 | 결과
|--|--|--|
|1. NormalizeText | 모든 문자를 기본적으로 소문자로 변환합니다. | this is a good product
|2. TokenizeWords | 문자를 개별 단어로 분할합니다. | ["this","is","a","good","product"]
|3. RemoveDefaultStopWords | *is* 및 *a*와 같은 불용어를 제거합니다. | ["good","product"]
|4. MapValueToKey | 입력 데이터에 기반하여 값을 키(범주)에 매핑합니다. |  [1,2]
|5. ProduceNGrams | 텍스트를 연속 단어 시퀀스로 변형합니다. | [1,1,1,0,0]
|6. NormalizeLpNorm | lp-norm으로 입력 크기를 조정합니다. | [ 0.577350529, 0.577350529, 0.577350529, 0, 0 ]
