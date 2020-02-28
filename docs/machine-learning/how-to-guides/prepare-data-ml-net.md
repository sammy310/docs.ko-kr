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
# <a name="prepare-data-for-building-a-model"></a><span data-ttu-id="d554e-103">모델 구축에 사용할 데이터 준비</span><span class="sxs-lookup"><span data-stu-id="d554e-103">Prepare data for building a model</span></span>

<span data-ttu-id="d554e-104">ML.NET을 사용하여 추가 처리 또는 모델 빌드를 위해 데이터를 준비하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="d554e-104">Learn how to use ML.NET to prepare data for additional processing or building a model.</span></span>

<span data-ttu-id="d554e-105">데이터는 정리되어 있지 않고 흩어져 있는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="d554e-105">Data is often unclean and sparse.</span></span> <span data-ttu-id="d554e-106">ML.NET 기계 학습 알고리즘에서는 단일 숫자 벡터 형식의 입력 또는 기능을 예상합니다.</span><span class="sxs-lookup"><span data-stu-id="d554e-106">ML.NET machine learning algorithms expect input or features to be in a single numerical vector.</span></span> <span data-ttu-id="d554e-107">마찬가지로 예측할 값(레이블), 특히 범주 데이터의 경우에는 인코딩해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d554e-107">Similarly, the value to predict (label), especially when it's categorical data, has to be encoded.</span></span> <span data-ttu-id="d554e-108">따라서 데이터를 준비하는 목적 중 하나가 ML.NET 알고리즘에서 예상하는 형식으로 데이터를 가져오는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d554e-108">Therefore one of the goals of data preparation is to get the data into the format expected by ML.NET algorithms.</span></span>

## <a name="filter-data"></a><span data-ttu-id="d554e-109">데이터 필터링</span><span class="sxs-lookup"><span data-stu-id="d554e-109">Filter data</span></span>

<span data-ttu-id="d554e-110">데이터 세트의 일부 데이터는 분석하기에 관련성이 없는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d554e-110">Sometimes, not all data in a dataset is relevant for analysis.</span></span> <span data-ttu-id="d554e-111">관련 없는 데이터를 제거하는 접근법이 필터링입니다.</span><span class="sxs-lookup"><span data-stu-id="d554e-111">An approach to remove irrelevant data is filtering.</span></span> <span data-ttu-id="d554e-112">[`DataOperationsCatalog`](xref:Microsoft.ML.DataOperationsCatalog)에는 모든 데이터를 포함하는 [`IDataView`](xref:Microsoft.ML.IDataView)에서 수행하여 관심 있는 데이터 요소만 포함하는 [IDataView](xref:Microsoft.ML.IDataView)를 반환하는 일련의 필터 작업 세트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d554e-112">The [`DataOperationsCatalog`](xref:Microsoft.ML.DataOperationsCatalog) contains a set of filter operations that take in an [`IDataView`](xref:Microsoft.ML.IDataView) containing all of the data and return an [IDataView](xref:Microsoft.ML.IDataView) containing only the data points of interest.</span></span> <span data-ttu-id="d554e-113">필터 작업이 [`TransformsCatalog`](xref:Microsoft.ML.TransformsCatalog)의 것과 같은 [`IEstimator`](xref:Microsoft.ML.IEstimator%601) 또는 [`ITransformer`](xref:Microsoft.ML.ITransformer)가 아니므로, [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601) 또는 [`TransformerChain`](xref:Microsoft.ML.Data.TransformerChain%601) 데이터 준비 파이프라인으로 포함할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d554e-113">It's important to note that because filter operations are not an [`IEstimator`](xref:Microsoft.ML.IEstimator%601) or [`ITransformer`](xref:Microsoft.ML.ITransformer) like those in the [`TransformsCatalog`](xref:Microsoft.ML.TransformsCatalog), they cannot be included as part of an [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601) or [`TransformerChain`](xref:Microsoft.ML.Data.TransformerChain%601) data preparation pipeline.</span></span>

<span data-ttu-id="d554e-114">다음 입력 데이터를 `data`라는 [`IDataView`](xref:Microsoft.ML.IDataView)로 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="d554e-114">Take the following input data and load it into an [`IDataView`](xref:Microsoft.ML.IDataView) called `data`:</span></span>

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

<span data-ttu-id="d554e-115">열 값에 기반하여 데이터를 필터링하려면 [`FilterRowsByColumn`](xref:Microsoft.ML.DataOperationsCatalog.FilterRowsByColumn%2A) 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d554e-115">To filter data based on the value of a column, use the [`FilterRowsByColumn`](xref:Microsoft.ML.DataOperationsCatalog.FilterRowsByColumn%2A) method.</span></span>

```csharp
// Apply filter
IDataView filteredData = mlContext.Data.FilterRowsByColumn(data, "Price", lowerBound: 200000, upperBound: 1000000);
```

<span data-ttu-id="d554e-116">위의 샘플에서는 데이터 세트에서 가격대가 200000 ~ 1000000인 행을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d554e-116">The sample above takes rows in the dataset with a price between 200000 and 1000000.</span></span> <span data-ttu-id="d554e-117">이 필터를 적용하면 데이터에서 마지막 두 개 행만 반환되고 첫 행은 가격이 100000이고 지정한 범위에 속하지 않으므로 제외됩니다.</span><span class="sxs-lookup"><span data-stu-id="d554e-117">The result of applying this filter would return only the last two rows in the data and exclude the first row because its price is 100000 and not between the specified range.</span></span>

## <a name="replace-missing-values"></a><span data-ttu-id="d554e-118">누락된 값 대체</span><span class="sxs-lookup"><span data-stu-id="d554e-118">Replace missing values</span></span>

<span data-ttu-id="d554e-119">데이터 세트에서 값이 누락되는 경우는 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="d554e-119">Missing values are a common occurrence in datasets.</span></span> <span data-ttu-id="d554e-120">누락된 값을 다루는 접근법 중 하나는 데이터에서 평균 값 등 다른 의미 있는 값인 경우 지정된 유형에 대한 기본 값으로 대체하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d554e-120">One approach to dealing with missing values is to replace them with the default value for the given type if any or another meaningful value such as the mean value in the data.</span></span>

<span data-ttu-id="d554e-121">다음 입력 데이터를 `data`라는 [`IDataView`](xref:Microsoft.ML.IDataView)로 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="d554e-121">Take the following input data and load it into an [`IDataView`](xref:Microsoft.ML.IDataView) called `data`:</span></span>

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

<span data-ttu-id="d554e-122">목록의 마지막 요소에 `Price`에 대한 누락된 값이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d554e-122">Notice that the last element in our list has a missing value for `Price`.</span></span> <span data-ttu-id="d554e-123">`Price` 열의 누락된 값을 대체하려면 [`ReplaceMissingValues`](xref:Microsoft.ML.ExtensionsCatalog.ReplaceMissingValues%2A) 메서드를 사용하여 이 누락된 값을 채우세요.</span><span class="sxs-lookup"><span data-stu-id="d554e-123">To replace the missing values in the `Price` column, use the [`ReplaceMissingValues`](xref:Microsoft.ML.ExtensionsCatalog.ReplaceMissingValues%2A) method to fill in that missing value.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d554e-124">[`ReplaceMissingValue`](xref:Microsoft.ML.ExtensionsCatalog.ReplaceMissingValues%2A)은 숫자 데이터에만 작용합니다.</span><span class="sxs-lookup"><span data-stu-id="d554e-124">[`ReplaceMissingValue`](xref:Microsoft.ML.ExtensionsCatalog.ReplaceMissingValues%2A) only works with numerical data.</span></span>

```csharp
// Define replacement estimator
var replacementEstimator = mlContext.Transforms.ReplaceMissingValues("Price", replacementMode: MissingValueReplacingEstimator.ReplacementMode.Mean);

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
ITransformer replacementTransformer = replacementEstimator.Fit(data);

// Transform data
IDataView transformedData = replacementTransformer.Transform(data);
```

<span data-ttu-id="d554e-125">ML.NET은 다양한 [대체 모드](xref:Microsoft.ML.Transforms.MissingValueReplacingEstimator.ReplacementMode) 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="d554e-125">ML.NET supports various [replacement modes](xref:Microsoft.ML.Transforms.MissingValueReplacingEstimator.ReplacementMode).</span></span> <span data-ttu-id="d554e-126">위의 샘플에서는 해당 열의 평균 값으로 누락된 값을 채우는 `Mean` 대체 모드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d554e-126">The sample above uses the `Mean` replacement mode, which fills in the missing value with that column's average value.</span></span> <span data-ttu-id="d554e-127">대체하면 데이터에서 100,000과 300,000의 평균인 200,000으로 마지막 요소에 대한 `Price` 속성을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="d554e-127">The replacement 's result fills in the `Price` property for the last element in our data with 200,000 since it's the average of 100,000 and 300,000.</span></span>

## <a name="use-normalizers"></a><span data-ttu-id="d554e-128">노멀라이저 사용</span><span class="sxs-lookup"><span data-stu-id="d554e-128">Use normalizers</span></span>

<span data-ttu-id="d554e-129">[정규화](https://en.wikipedia.org/wiki/Feature_scaling)는 기계 학습 알고리즘이 보다 정확하게 처리할 수 있도록 기능을 동일한 범위(일반적으로 0에서 1 사이)로 조정하는 데 사용되는 데이터 전처리 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="d554e-129">[Normalization](https://en.wikipedia.org/wiki/Feature_scaling) is a data pre-processing technique used to scale features to be in the same range, usually between 0 and 1, so that they can be more accurately processed by a machine learning algorithm.</span></span> <span data-ttu-id="d554e-130">예를 들어, 나이는 일반적으로 0-100 범위, 소득은 0에서 수천 범위로 그 범위가 상당히 다양합니다.</span><span class="sxs-lookup"><span data-stu-id="d554e-130">For example, the ranges for age and income vary significantly with age generally being in the range of 0-100 and income generally being in the range of zero to thousands.</span></span> <span data-ttu-id="d554e-131">정규화 변형에 대한 보다 자세한 목록과 설명은 [변형 페이지](../resources/transforms.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d554e-131">Visit the [transforms page](../resources/transforms.md) for a more detailed list and description of normalization transforms.</span></span>

### <a name="min-max-normalization"></a><span data-ttu-id="d554e-132">최소-최대 정규화</span><span class="sxs-lookup"><span data-stu-id="d554e-132">Min-Max normalization</span></span>

<span data-ttu-id="d554e-133">다음 입력 데이터를 `data`라는 [`IDataView`](xref:Microsoft.ML.IDataView)로 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="d554e-133">Take the following input data and load it into an [`IDataView`](xref:Microsoft.ML.IDataView) called `data`:</span></span>

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

<span data-ttu-id="d554e-134">정규화는 단일 숫자 값뿐 아니라 벡터를 포함하는 열에도 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d554e-134">Normalization can be applied to columns with single numerical values as well as vectors.</span></span> <span data-ttu-id="d554e-135">[`NormalizeMinMax`](xref:Microsoft.ML.NormalizationCatalog.NormalizeMinMax%2A) 메서드를 사용하는 최소-최대 정규화를 통해 `Price` 열의 데이터를 정규화합니다.</span><span class="sxs-lookup"><span data-stu-id="d554e-135">Normalize the data in the `Price` column using min-max normalization with the [`NormalizeMinMax`](xref:Microsoft.ML.NormalizationCatalog.NormalizeMinMax%2A) method.</span></span>

```csharp
// Define min-max estimator
var minMaxEstimator = mlContext.Transforms.NormalizeMinMax("Price");

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
ITransformer minMaxTransformer = minMaxEstimator.Fit(data);

// Transform data
IDataView transformedData = minMaxTransformer.Transform(data);
```

<span data-ttu-id="d554e-136">원래 가격 값 `[200000,100000]`은 0-1 범위에서 출력 값을 생성하는 `MinMax` 정규화 공식을 사용하여 `[ 1, 0.5 ]`로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="d554e-136">The original price values `[200000,100000]` are converted to `[ 1, 0.5 ]` using the `MinMax` normalization formula that generates output values in the range of 0-1.</span></span>

### <a name="binning"></a><span data-ttu-id="d554e-137">범주화</span><span class="sxs-lookup"><span data-stu-id="d554e-137">Binning</span></span>

<span data-ttu-id="d554e-138">[범주화](https://en.wikipedia.org/wiki/Data_binning)는 연속적인 값을 별도의 값 표현으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="d554e-138">[Binning](https://en.wikipedia.org/wiki/Data_binning) converts continuous values into a discrete representation of the input.</span></span> <span data-ttu-id="d554e-139">예를 들어, 기능 중 하나가 나이라고 가정하면</span><span class="sxs-lookup"><span data-stu-id="d554e-139">For example, suppose one of your features is age.</span></span> <span data-ttu-id="d554e-140">범주화는 실제 나이 값 대신, 해당 값의 범위를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d554e-140">Instead of using the actual age value,  binning creates ranges for that value.</span></span> <span data-ttu-id="d554e-141">0-18, 19-35 등이 각 범주가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d554e-141">0-18 could be one bin, another could be 19-35 and so on.</span></span>

<span data-ttu-id="d554e-142">다음 입력 데이터를 `data`라는 [`IDataView`](xref:Microsoft.ML.IDataView)로 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="d554e-142">Take the following input data and load it into an [`IDataView`](xref:Microsoft.ML.IDataView) called `data`:</span></span>

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

<span data-ttu-id="d554e-143">[`NormalizeBinning`](xref:Microsoft.ML.NormalizationCatalog.NormalizeBinning%2A) 메서드를 사용하여 데이터를 bin으로 정규합니다.</span><span class="sxs-lookup"><span data-stu-id="d554e-143">Normalize the data into bins using the [`NormalizeBinning`](xref:Microsoft.ML.NormalizationCatalog.NormalizeBinning%2A) method.</span></span> <span data-ttu-id="d554e-144">`maximumBinCount` 매개 변수를 사용하면 데이터를 분류하는 데 필요한 bin 수를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d554e-144">The `maximumBinCount` parameter enables you to specify the number of bins needed to classify your data.</span></span> <span data-ttu-id="d554e-145">이 예에서는 데이터가 2개의 bin으로 분류됩니다.</span><span class="sxs-lookup"><span data-stu-id="d554e-145">In this example, data will be put into two bins.</span></span>

```csharp
// Define binning estimator
var binningEstimator = mlContext.Transforms.NormalizeBinning("Price", maximumBinCount: 2);

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
var binningTransformer = binningEstimator.Fit(data);

// Transform Data
IDataView transformedData = binningTransformer.Transform(data);
```

<span data-ttu-id="d554e-146">범주화 결과로, `[0,200000,Infinity]`의 bin 범위가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="d554e-146">The result of binning creates bin bounds of `[0,200000,Infinity]`.</span></span> <span data-ttu-id="d554e-147">따라서 첫 번째 관찰 값이 0-200000이고 나머지가 200000보다 크지만, 무한보다는 적기 때문에 결과로 만들지는 bin은 `[0,1,1]`입니다.</span><span class="sxs-lookup"><span data-stu-id="d554e-147">Therefore the resulting bins are `[0,1,1]` because the first observation is between 0-200000 and the others are greater than 200000 but less than infinity.</span></span>

## <a name="work-with-categorical-data"></a><span data-ttu-id="d554e-148">범주 데이터 작업</span><span class="sxs-lookup"><span data-stu-id="d554e-148">Work with categorical data</span></span>

<span data-ttu-id="d554e-149">가장 일반적인 데이터 유형 중 하나는 범주 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="d554e-149">One of the most common types of data is categorical data.</span></span> <span data-ttu-id="d554e-150">범주 데이터에는 유한한 개수의 범주가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d554e-150">Categorical data has a finite number of categories.</span></span> <span data-ttu-id="d554e-151">예를 들어 미국의 주 또는 그림 집합에 있는 동물 유형의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="d554e-151">For example, the states of the USA, or a list of the types of animals found in a set of pictures.</span></span> <span data-ttu-id="d554e-152">범주 데이터가 기능 또는 레이블인지 관계없이 기계 학습 모델을 생성하는 데 사용할 수 있도록 숫자 값에 매핑되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d554e-152">Whether the categorical data are features or labels, they must be mapped onto a numerical value so they can be used to generate a machine learning model.</span></span> <span data-ttu-id="d554e-153">해결 중인 문제에 따라 ML.NET에서 범주 데이터로 작업하는 방법은 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d554e-153">There are a number of ways of working with categorical data in ML.NET, depending on the problem you are solving.</span></span>

### <a name="key-value-mapping"></a><span data-ttu-id="d554e-154">키 값 매핑</span><span class="sxs-lookup"><span data-stu-id="d554e-154">Key value mapping</span></span>

<span data-ttu-id="d554e-155">ML.NET에서 키는 범주를 나타내는 정수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="d554e-155">In ML.NET, a key is an integer value that represents a category.</span></span> <span data-ttu-id="d554e-156">키 값 매핑은 학습을 위해 문자열 레이블을 고유한 정수 값에 매핑한 다음 모델을 사용하여 예측을 생성할 때 다시 문자열 값으로 매핑하는 데 사용하는 경우가 가장 많습니다.</span><span class="sxs-lookup"><span data-stu-id="d554e-156">Key value mapping is most often used to map string labels into unique integer values for training, then back to their string values when the model is used to make a prediction.</span></span>

<span data-ttu-id="d554e-157">키 값 매핑을 수행하는 데 사용되는 변환은 [MapValueToKey](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A) 및 [MapKeyToValue](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapKeyToValue%2A)입니다.</span><span class="sxs-lookup"><span data-stu-id="d554e-157">The transforms used to perform key value mapping are [MapValueToKey](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A) and [MapKeyToValue](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapKeyToValue%2A).</span></span>

<span data-ttu-id="d554e-158">`MapValueToKey`는 모델에 매핑 사전을 추가하여 예측을 생성할 때 `MapKeyToValue`가 역방향 변환을 수행할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d554e-158">`MapValueToKey` adds a dictionary of mappings in the model, so that `MapKeyToValue` can perform the reverse transform when making a prediction.</span></span>

### <a name="one-hot-encoding"></a><span data-ttu-id="d554e-159">원 핫 인코딩(one-hot encoding)</span><span class="sxs-lookup"><span data-stu-id="d554e-159">One hot encoding</span></span>

<span data-ttu-id="d554e-160">원 핫 인코딩은 유한한 값 집합을 사용하여 이진 표현의 문자열 내 고유한 위치에 단일 `1` 값이 있는 정수로 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="d554e-160">One hot encoding takes a finite set of values and maps them onto integers whose binary representation has a single `1` value in unique positions in the string.</span></span> <span data-ttu-id="d554e-161">범주 데이터를 암시적으로 정렬하지 않는 경우 원 핫 인코딩을 선택하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d554e-161">One hot encoding can be the best choice if there is no implicit ordering of the categorical data.</span></span> <span data-ttu-id="d554e-162">다음 표에서는 우편 번호를 원시 값으로 사용하는 예를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d554e-162">The following table shows an example with zip codes as raw values.</span></span>

|<span data-ttu-id="d554e-163">원시 값</span><span class="sxs-lookup"><span data-stu-id="d554e-163">Raw value</span></span>|<span data-ttu-id="d554e-164">원 핫 인코딩된 값</span><span class="sxs-lookup"><span data-stu-id="d554e-164">One hot encoded value</span></span>|
|---------|---------------------|
|<span data-ttu-id="d554e-165">98052</span><span class="sxs-lookup"><span data-stu-id="d554e-165">98052</span></span>|<span data-ttu-id="d554e-166">00...01</span><span class="sxs-lookup"><span data-stu-id="d554e-166">00...01</span></span>|
|<span data-ttu-id="d554e-167">98100</span><span class="sxs-lookup"><span data-stu-id="d554e-167">98100</span></span>|<span data-ttu-id="d554e-168">00...10</span><span class="sxs-lookup"><span data-stu-id="d554e-168">00...10</span></span>|
|<span data-ttu-id="d554e-169">...</span><span class="sxs-lookup"><span data-stu-id="d554e-169">...</span></span>|<span data-ttu-id="d554e-170">...</span><span class="sxs-lookup"><span data-stu-id="d554e-170">...</span></span>|
|<span data-ttu-id="d554e-171">98109</span><span class="sxs-lookup"><span data-stu-id="d554e-171">98109</span></span>|<span data-ttu-id="d554e-172">10...00</span><span class="sxs-lookup"><span data-stu-id="d554e-172">10...00</span></span>|

<span data-ttu-id="d554e-173">범주 데이터를 원 핫 인코딩된 숫자로 변환하는 변환은 [`OneHotEncoding`](xref:Microsoft.ML.CategoricalCatalog.OneHotEncoding%2A)입니다.</span><span class="sxs-lookup"><span data-stu-id="d554e-173">The transform to convert categorical data to one-hot encoded numbers is [`OneHotEncoding`](xref:Microsoft.ML.CategoricalCatalog.OneHotEncoding%2A).</span></span>

### <a name="hashing"></a><span data-ttu-id="d554e-174">해시</span><span class="sxs-lookup"><span data-stu-id="d554e-174">Hashing</span></span>

<span data-ttu-id="d554e-175">해시는 범주 데이터를 숫자로 변환하는 또 다른 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="d554e-175">Hashing is another way to convert categorical data to numbers.</span></span> <span data-ttu-id="d554e-176">해시 함수는 임의 크기의 데이터(예: 텍스트 문자열)를 고정 범위의 숫자로 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="d554e-176">A hash function maps data of an arbitrary size (a string of text for example) onto a number with a fixed range.</span></span> <span data-ttu-id="d554e-177">해시는 빠르고 공간 효율적으로 피터를 벡터화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d554e-177">Hashing can be a fast and space-efficient way of vectorizing features.</span></span> <span data-ttu-id="d554e-178">기계 학습에서 해시의 한 가지 주목할 만한 예는 알려진 단어의 사전을 유지 관리하는 대신 이메일의 모든 단어를 해시하고 큰 기능 벡터에 추가하는 스팸 메일 필터링입니다.</span><span class="sxs-lookup"><span data-stu-id="d554e-178">One notable example of hashing in machine learning is email spam filtering where, instead of maintaining a dictionary of known words, every word in the email is hashed and added to a large feature vector.</span></span> <span data-ttu-id="d554e-179">이러한 방식으로 해시를 사용하면 사전에 없는 단어를 사용하는 악의적인 스팸 필터링 회피 문제를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d554e-179">Using hashing in this way avoids the problem of malicious spam filtering circumvention by the use of words that are not in the dictionary.</span></span>

<span data-ttu-id="d554e-180">ML.NET은 [Hash](xref:Microsoft.ML.ConversionsExtensionsCatalog.Hash%2A) 변환을 제공하여 텍스트, 날짜 및 숫자 데이터에 대한 해시를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="d554e-180">ML.NET provides [Hash](xref:Microsoft.ML.ConversionsExtensionsCatalog.Hash%2A) transform to perform hashing on text, dates, and numerical data.</span></span> <span data-ttu-id="d554e-181">값 키 매핑과 마찬가지로 해시 변환의 출력은 키 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d554e-181">Like value key mapping, the outputs of the hash transform are key types.</span></span>

## <a name="work-with-text-data"></a><span data-ttu-id="d554e-182">텍스트 데이터 작업</span><span class="sxs-lookup"><span data-stu-id="d554e-182">Work with text data</span></span>

<span data-ttu-id="d554e-183">범주 데이터와 마찬가지로 텍스트 데이터를 사용하여 기계 학습 모델을 빌드하려면 먼저 숫자 기능으로 변환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d554e-183">Like categorical data, text data needs to be transformed into numerical features before using it to build a machine learning model.</span></span> <span data-ttu-id="d554e-184">텍스트 변형에 대한 보다 자세한 목록과 설명은 [변형 페이지](../resources/transforms.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d554e-184">Visit the [transforms page](../resources/transforms.md) for a more detailed list and description of text transforms.</span></span>

<span data-ttu-id="d554e-185">[`IDataView`](xref:Microsoft.ML.IDataView)로 로드된 아래 데이터와 같은 데이터 사용:</span><span class="sxs-lookup"><span data-stu-id="d554e-185">Using data like the data below that has been loaded into an [`IDataView`](xref:Microsoft.ML.IDataView):</span></span>

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

<span data-ttu-id="d554e-186">ML.NET은 텍스트의 문자열 값에 일련의 개별 변환을 적용하여 텍스트에서 기능 집합을 만드는 [`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText%2A) 변환을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d554e-186">ML.NET provides the [`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText%2A) transform that takes a text's string value and creates a set of features from the text, by applying a series of individual transforms.</span></span>

```csharp
// Define text transform estimator
var textEstimator  = mlContext.Transforms.Text.FeaturizeText("Description");

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
ITransformer textTransformer = textEstimator.Fit(data);

// Transform data
IDataView transformedData = textTransformer.Transform(data);
```

<span data-ttu-id="d554e-187">결과로 만들어지는 변형은 `Description` 열의 텍스트 값을 아래 출력과 같은 숫자 벡터로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="d554e-187">The resulting transform converts the text values in the `Description` column to a numerical vector that looks similar to the output below:</span></span>

```text
[ 0.2041241, 0.2041241, 0.2041241, 0.4082483, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0, 0, 0, 0, 0.4472136, 0.4472136, 0.4472136, 0.4472136, 0.4472136, 0 ]
```

<span data-ttu-id="d554e-188">`FeaturizeText`를 구성하는 변환은 기능 생성을 보다 세부적으로 제어하기 위해 개별적으로 적용될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d554e-188">The transforms that make up `FeaturizeText` can also be applied individually for finer grain control over feature generation.</span></span>

```csharp
// Define text transform estimator
var textEstimator = mlContext.Transforms.Text.NormalizeText("Description")
    .Append(mlContext.Transforms.Text.TokenizeIntoWords("Description"))
    .Append(mlContext.Transforms.Text.RemoveDefaultStopWords("Description"))
    .Append(mlContext.Transforms.Conversion.MapValueToKey("Description"))
    .Append(mlContext.Transforms.Text.ProduceNgrams("Description"))
    .Append(mlContext.Transforms.NormalizeLpNorm("Description"));
```

<span data-ttu-id="d554e-189">`textEstimator`에는 [`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText%2A) 메서드에서 수행하는 작업의 하위 세트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d554e-189">`textEstimator` contains a subset of operations performed by the [`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText%2A) method.</span></span> <span data-ttu-id="d554e-190">보다 복잡한 파이프라인의 이점은 데이터에 적용되는 변형에 대한 제어와 가시성입니다.</span><span class="sxs-lookup"><span data-stu-id="d554e-190">The benefit of a more complex pipeline is control and visibility over the transformations applied to the data.</span></span>

<span data-ttu-id="d554e-191">다음은 예로 첫 번째 항목을 사용하여 `textEstimator`에서 정의하는 변형 단계에서 생성되는 결과에 대한 자세한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="d554e-191">Using the first entry as an example, the following is a detailed description of the results produced by the transformation steps defined by `textEstimator`:</span></span>

<span data-ttu-id="d554e-192">**원문: This is a good product**</span><span class="sxs-lookup"><span data-stu-id="d554e-192">**Original Text: This is a good product**</span></span>

|<span data-ttu-id="d554e-193">변형</span><span class="sxs-lookup"><span data-stu-id="d554e-193">Transform</span></span> | <span data-ttu-id="d554e-194">설명</span><span class="sxs-lookup"><span data-stu-id="d554e-194">Description</span></span> | <span data-ttu-id="d554e-195">결과</span><span class="sxs-lookup"><span data-stu-id="d554e-195">Result</span></span>
|--|--|--|
|<span data-ttu-id="d554e-196">1. NormalizeText</span><span class="sxs-lookup"><span data-stu-id="d554e-196">1. NormalizeText</span></span> | <span data-ttu-id="d554e-197">모든 문자를 기본적으로 소문자로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="d554e-197">Converts all letters to lowercase by default</span></span> | <span data-ttu-id="d554e-198">this is a good product</span><span class="sxs-lookup"><span data-stu-id="d554e-198">this is a good product</span></span>
|<span data-ttu-id="d554e-199">2. TokenizeWords</span><span class="sxs-lookup"><span data-stu-id="d554e-199">2. TokenizeWords</span></span> | <span data-ttu-id="d554e-200">문자를 개별 단어로 분할합니다.</span><span class="sxs-lookup"><span data-stu-id="d554e-200">Splits string into individual words</span></span> | <span data-ttu-id="d554e-201">["this","is","a","good","product"]</span><span class="sxs-lookup"><span data-stu-id="d554e-201">["this","is","a","good","product"]</span></span>
|<span data-ttu-id="d554e-202">3. RemoveDefaultStopWords</span><span class="sxs-lookup"><span data-stu-id="d554e-202">3. RemoveDefaultStopWords</span></span> | <span data-ttu-id="d554e-203">*is* 및 *a*와 같은 불용어를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d554e-203">Removes stopwords like *is* and *a*.</span></span> | <span data-ttu-id="d554e-204">["good","product"]</span><span class="sxs-lookup"><span data-stu-id="d554e-204">["good","product"]</span></span>
|<span data-ttu-id="d554e-205">4. MapValueToKey</span><span class="sxs-lookup"><span data-stu-id="d554e-205">4. MapValueToKey</span></span> | <span data-ttu-id="d554e-206">입력 데이터에 기반하여 값을 키(범주)에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="d554e-206">Maps the values to keys (categories) based on the input data</span></span> |  <span data-ttu-id="d554e-207">[1,2]</span><span class="sxs-lookup"><span data-stu-id="d554e-207">[1,2]</span></span>
|<span data-ttu-id="d554e-208">5. ProduceNGrams</span><span class="sxs-lookup"><span data-stu-id="d554e-208">5. ProduceNGrams</span></span> | <span data-ttu-id="d554e-209">텍스트를 연속 단어 시퀀스로 변형합니다.</span><span class="sxs-lookup"><span data-stu-id="d554e-209">Transforms text into sequence of consecutive words</span></span> | <span data-ttu-id="d554e-210">[1,1,1,0,0]</span><span class="sxs-lookup"><span data-stu-id="d554e-210">[1,1,1,0,0]</span></span>
|<span data-ttu-id="d554e-211">6. NormalizeLpNorm</span><span class="sxs-lookup"><span data-stu-id="d554e-211">6. NormalizeLpNorm</span></span> | <span data-ttu-id="d554e-212">lp-norm으로 입력 크기를 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="d554e-212">Scale inputs by their lp-norm</span></span> | <span data-ttu-id="d554e-213">[ 0.577350529, 0.577350529, 0.577350529, 0, 0 ]</span><span class="sxs-lookup"><span data-stu-id="d554e-213">[ 0.577350529, 0.577350529, 0.577350529, 0, 0 ]</span></span>
