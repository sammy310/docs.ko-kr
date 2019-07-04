---
title: 데이터 준비
description: ML.NET에서 변형을 사용하여 추가 처리 또는 모델 빌드를 위해 데이터를 조작하고 준비하는 방법을 알아봅니다.
author: luisquintanilla
ms.author: luquinta
ms.date: 05/03/2019
ms.custom: mvc, how-to
ms.openlocfilehash: abf43260a438c9b1febffc77cf39e7328e0377ee
ms.sourcegitcommit: 4c41ec195caf03d98b7900007c3c8e24eba20d34
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/20/2019
ms.locfileid: "67268240"
---
# <a name="prepare-data"></a><span data-ttu-id="4d1b8-103">데이터 준비</span><span class="sxs-lookup"><span data-stu-id="4d1b8-103">Prepare Data</span></span>

<span data-ttu-id="4d1b8-104">ML.NET을 사용하여 추가 처리 또는 모델 빌드를 위해 데이터를 준비하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b8-104">Learn how to use ML.NET to prepare data for additional processing or building a model.</span></span>

<span data-ttu-id="4d1b8-105">데이터는 정리되어 있지 않고 흩어져 있는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b8-105">Data is often unclean and sparse.</span></span> <span data-ttu-id="4d1b8-106">또한, ML.NET 기계 학습 알고리즘에서는 단일 숫자 벡터 형식의 입력 또는 기능을 예상합니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b8-106">Additionally, ML.NET machine learning algorithms expect input or features to be in a single numerical vector.</span></span> <span data-ttu-id="4d1b8-107">따라서 데이터를 준비하는 목적 중 하나가 ML.NET 알고리즘에서 예상하는 형식으로 데이터를 가져오는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b8-107">Therefore one of the goals of data preparation is to get the data into the format expected by ML.NET algorithms.</span></span> 

## <a name="filter-data"></a><span data-ttu-id="4d1b8-108">데이터 필터링</span><span class="sxs-lookup"><span data-stu-id="4d1b8-108">Filter data</span></span>

<span data-ttu-id="4d1b8-109">데이터 세트의 일부 데이터는 분석하기에 관련성이 없는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b8-109">Sometimes, not all data in a dataset is relevant for analysis.</span></span> <span data-ttu-id="4d1b8-110">관련 없는 데이터를 제거하는 접근법이 필터링입니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b8-110">An approach to remove irrelevant data is filtering.</span></span> <span data-ttu-id="4d1b8-111">[`DataOperationsCatalog`](xref:Microsoft.ML.DataOperationsCatalog)에는 모든 데이터를 포함하는 [`IDataView`](xref:Microsoft.ML.IDataView)에서 수행하여 관심 있는 데이터 요소만 포함하는 [IDataView](xref:Microsoft.ML.IDataView)를 반환하는 일련의 필터 작업 세트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b8-111">The [`DataOperationsCatalog`](xref:Microsoft.ML.DataOperationsCatalog) contains a set of filter operations that take in an [`IDataView`](xref:Microsoft.ML.IDataView) containing all of the data and return an [IDataView](xref:Microsoft.ML.IDataView) containing only the data points of interest.</span></span> <span data-ttu-id="4d1b8-112">필터 작업이 [`TransformsCatalog`](xref:Microsoft.ML.TransformsCatalog)의 것과 같은 [`IEstimator`](xref:Microsoft.ML.IEstimator%601) 또는 [`ITransformer`](xref:Microsoft.ML.ITransformer)가 아니므로, [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601) 또는 [`TransformerChain`](xref:Microsoft.ML.Data.TransformerChain%601) 데이터 준비 파이프라인으로 포함할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b8-112">It's important to note that because filter operations are not an [`IEstimator`](xref:Microsoft.ML.IEstimator%601) or [`ITransformer`](xref:Microsoft.ML.ITransformer) like those in the [`TransformsCatalog`](xref:Microsoft.ML.TransformsCatalog), they cannot be included as part of an [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601) or [`TransformerChain`](xref:Microsoft.ML.Data.TransformerChain%601) data preparation pipeline.</span></span> 

<span data-ttu-id="4d1b8-113">[`IDataView`](xref:Microsoft.ML.IDataView)로 로드되는 다음 입력 데이터 사용:</span><span class="sxs-lookup"><span data-stu-id="4d1b8-113">Using the following input data which is loaded into an [`IDataView`](xref:Microsoft.ML.IDataView):</span></span>

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

<span data-ttu-id="4d1b8-114">열 값에 기반하여 데이터를 필터링하려면 [`FilterRowsByColumn`](xref:Microsoft.ML.DataOperationsCatalog.FilterRowsByColumn*) 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b8-114">To filter data based on the value of a column, use the [`FilterRowsByColumn`](xref:Microsoft.ML.DataOperationsCatalog.FilterRowsByColumn*) method.</span></span>

```csharp
// Apply filter
IDataView filteredData = mlContext.Data.FilterRowsByColumn(data, "Price", lowerBound: 200000, upperBound: 1000000);
```

<span data-ttu-id="4d1b8-115">위의 샘플에서는 데이터 세트에서 가격대가 200000 ~ 1000000인 행을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b8-115">The sample above takes rows in the dataset with a price between 200000 and 1000000.</span></span> <span data-ttu-id="4d1b8-116">이 필터를 적용하면 데이터에서 마지막 두 개 행만 반환되고 첫 행은 가격이 100000이고 지정한 범위에 속하지 않으므로 제외됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b8-116">The result of applying this filter would return only the last two rows in the data and exclude the first row because its price is 100000 and not between the specified range.</span></span>

## <a name="replace-missing-values"></a><span data-ttu-id="4d1b8-117">누락된 값 대체</span><span class="sxs-lookup"><span data-stu-id="4d1b8-117">Replace missing values</span></span>

<span data-ttu-id="4d1b8-118">데이터 세트에서 값이 누락되는 경우는 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b8-118">Missing values are a common occurrence in datasets.</span></span> <span data-ttu-id="4d1b8-119">누락된 값을 다루는 접근법 중 하나는 데이터에서 평균 값 등 다른 의미 있는 값인 경우 지정된 유형에 대한 기본 값으로 대체하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b8-119">One approach to dealing with missing values is to replace them with the default value for the given type if any or another meaningful value such as the mean value in the data.</span></span> 

<span data-ttu-id="4d1b8-120">[`IDataView`](xref:Microsoft.ML.IDataView)로 로드되는 다음 입력 데이터 사용:</span><span class="sxs-lookup"><span data-stu-id="4d1b8-120">Using the following input data which is loaded into an [`IDataView`](xref:Microsoft.ML.IDataView):</span></span>

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

<span data-ttu-id="4d1b8-121">목록의 마지막 요소에 `Price`에 대한 누락된 값이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b8-121">Notice that the last element in our list has a missing value for `Price`.</span></span> <span data-ttu-id="4d1b8-122">`Price` 열의 누락된 값을 대체하려면 [`ReplaceMissingValues`](xref:Microsoft.ML.ExtensionsCatalog.ReplaceMissingValues*) 메서드를 사용하여 이 누락된 값을 채우세요.</span><span class="sxs-lookup"><span data-stu-id="4d1b8-122">To replace the missing values in the `Price` column, use the [`ReplaceMissingValues`](xref:Microsoft.ML.ExtensionsCatalog.ReplaceMissingValues*) method to fill in that missing value.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4d1b8-123">[`ReplaceMissingValue`](xref:Microsoft.ML.ExtensionsCatalog.ReplaceMissingValues*)은 숫자 데이터에만 작용합니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b8-123">[`ReplaceMissingValue`](xref:Microsoft.ML.ExtensionsCatalog.ReplaceMissingValues*) only works with numerical data.</span></span>

```csharp
// Define replacement estimator
var replacementEstimator = mlContext.Transforms.ReplaceMissingValues("Price", replacementMode: MissingValueReplacingEstimator.ReplacementMode.Mean);

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
ITransformer replacementTransformer = replacementEstimator.Fit(data);

// Transform data
IDataView transformedData = replacementTransformer.Transform(data);
```

<span data-ttu-id="4d1b8-124">ML.NET은 다양한 [대체 모드](xref:Microsoft.ML.Transforms.MissingValueReplacingEstimator.ReplacementMode) 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b8-124">ML.NET supports various [replacement modes](xref:Microsoft.ML.Transforms.MissingValueReplacingEstimator.ReplacementMode).</span></span> <span data-ttu-id="4d1b8-125">위의 샘플에서는 해당 열의 평균 값으로 누락된 값을 채울 `Mean` 대체 모드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b8-125">The sample above uses the `Mean` replacement mode which will fill in the missing value with that column's average value.</span></span> <span data-ttu-id="4d1b8-126">대체하면 데이터에서 100,000과 300,000의 평균인 200,000으로 마지막 요소에 대한 `Price` 속성을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b8-126">The replacement 's result fills in the `Price` property for the last element in our data with 200,000 since it's the average of 100,000 and 300,000.</span></span> 

## <a name="use-normalizers"></a><span data-ttu-id="4d1b8-127">노멀라이저 사용</span><span class="sxs-lookup"><span data-stu-id="4d1b8-127">Use normalizers</span></span>

<span data-ttu-id="4d1b8-128">[정규화](https://en.wikipedia.org/wiki/Feature_scaling)는 알고리즘이 보다 빠르게 수렴할 수 있도록 동일한 척도가 아닌 기능을 표준화하는 데 사용하는 데이터 사전 처리 기법입니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b8-128">[Normalization](https://en.wikipedia.org/wiki/Feature_scaling) is a data pre-processing technique used to standardize features that are not on the same scale which helps algorithms converge faster.</span></span> <span data-ttu-id="4d1b8-129">예를 들어, 나이와 수입과 같은 값의 범위는 나이가 일반적으로 0-100 범위, 수입이 0에서 수천 범위로 상당히 다양합니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b8-129">For example, the ranges for values like age and income vary significantly with age generally being in the range of 0-100 and income generally being in the range of zero to thousands.</span></span> <span data-ttu-id="4d1b8-130">정규화 변형에 대한 보다 자세한 목록과 설명은 [변형 페이지](../resources/transforms.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4d1b8-130">Visit the [transforms page](../resources/transforms.md) for a more detailed list and description of normalization transforms.</span></span> 

### <a name="min-max-normalization"></a><span data-ttu-id="4d1b8-131">최소-최대 정규화</span><span class="sxs-lookup"><span data-stu-id="4d1b8-131">Min-Max normalization</span></span>

<span data-ttu-id="4d1b8-132">[`IDataView`](xref:Microsoft.ML.IDataView)로 로드되는 다음 입력 데이터 사용:</span><span class="sxs-lookup"><span data-stu-id="4d1b8-132">Using the following input data which is loaded into an [`IDataView`](xref:Microsoft.ML.IDataView):</span></span>

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

<span data-ttu-id="4d1b8-133">정규화는 단일 숫자 값뿐 아니라 벡터를 포함하는 열에도 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b8-133">Normalization can be applied to columns with single numerical values as well as vectors.</span></span> <span data-ttu-id="4d1b8-134">[`NormalizeMinMax`](xref:Microsoft.ML.NormalizationCatalog.NormalizeMinMax*) 메서드를 사용하는 최소-최대 정규화를 통해 `Price` 열의 데이터를 정규화합니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b8-134">Normalize the data in the `Price` column using min-max normalization with the [`NormalizeMinMax`](xref:Microsoft.ML.NormalizationCatalog.NormalizeMinMax*) method.</span></span>

```csharp
// Define min-max estimator
var minMaxEstimator = mlContext.Transforms.NormalizeMinMax("Price");

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
ITransformer minMaxTransformer = minMaxEstimator.Fit(data);

// Transform data
IDataView transformedData = minMaxTransformer.Transform(data);
```

<span data-ttu-id="4d1b8-135">원래 가격 값 `[200000,100000]`은 0-1 범위에서 출력 값을 생성하는 `MinMax` 정규화 공식을 사용하여 `[ 1, 0.5 ]`로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b8-135">The original price values `[200000,100000]` are converted to `[ 1, 0.5 ]` using the `MinMax` normalization formula which generates output values in the range of 0-1.</span></span>

### <a name="binning"></a><span data-ttu-id="4d1b8-136">범주화</span><span class="sxs-lookup"><span data-stu-id="4d1b8-136">Binning</span></span>

<span data-ttu-id="4d1b8-137">[범주화](https://en.wikipedia.org/wiki/Data_binning)는 연속적인 값을 별도의 값 표현으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b8-137">[Binning](https://en.wikipedia.org/wiki/Data_binning) converts continuous values into a discrete representation of the input.</span></span> <span data-ttu-id="4d1b8-138">예를 들어, 기능 중 하나가 나이라고 가정하면</span><span class="sxs-lookup"><span data-stu-id="4d1b8-138">For example, suppose one of your features is age.</span></span> <span data-ttu-id="4d1b8-139">범주화는 실제 나이 값 대신, 해당 값의 범위를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b8-139">Instead of using the actual age value,  binning creates ranges for that value.</span></span> <span data-ttu-id="4d1b8-140">0-18, 19-35 등이 각 범주가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b8-140">0-18 could be one bin, another could be 19-35 and so on.</span></span> 

<span data-ttu-id="4d1b8-141">[`IDataView`](xref:Microsoft.ML.IDataView)로 로드되는 다음 입력 데이터 사용:</span><span class="sxs-lookup"><span data-stu-id="4d1b8-141">Using the following input data which is loaded into an [`IDataView`](xref:Microsoft.ML.IDataView):</span></span>

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

<span data-ttu-id="4d1b8-142">[`NormalizeBinning`](xref:Microsoft.ML.NormalizationCatalog.NormalizeBinning*) 메서드를 사용하여 데이터를 bin으로 정규합니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b8-142">Normalize the data into bins using the [`NormalizeBinning`](xref:Microsoft.ML.NormalizationCatalog.NormalizeBinning*) method.</span></span> <span data-ttu-id="4d1b8-143">`maximumBinCount` 매개 변수를 사용하면 데이터를 분류하는 데 필요한 bin 수를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b8-143">The `maximumBinCount` parameter enables you to specify the number of bins needed to classify your data.</span></span> <span data-ttu-id="4d1b8-144">이 예에서는 데이터가 2개의 bin으로 분류됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b8-144">In this example, data will be put into two bins.</span></span>  

```csharp
// Define binning estimator
var binningEstimator = mlContext.Transforms.NormalizeBinning("Price", maximumBinCount: 2);

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
var binningTransformer = binningEstimator.Fit(data);

// Transform Data
IDataView transformedData = binningTransformer.Transform(data);
```

<span data-ttu-id="4d1b8-145">범주화 결과로, `[0,200000,Infinity]`의 bin 범위가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b8-145">The result of binning creates bin bounds of `[0,200000,Infinity]`.</span></span> <span data-ttu-id="4d1b8-146">따라서 첫 번째 관찰 값이 0-200000이고 나머지가 200000보다 크지만, 무한보다는 적기 때문에 결과로 만들지는 bin은 `[0,1,1]`입니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b8-146">Therefore the resulting bins are `[0,1,1]` because the first observation is between 0-200000 and the others are greater than 200000 but less than infinity.</span></span>

## <a name="work-with-categorical-data"></a><span data-ttu-id="4d1b8-147">범주 데이터 작업</span><span class="sxs-lookup"><span data-stu-id="4d1b8-147">Work with categorical data</span></span>

<span data-ttu-id="4d1b8-148">숫자 이외의 범주 데이터는 기계 학습 모델을 빌드하는 데 사용하려면 숫자로 변환되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b8-148">Non-numeric categorical data needs to be converted to a number before being used to build a machine learning model.</span></span> 

<span data-ttu-id="4d1b8-149">[`IDataView`](xref:Microsoft.ML.IDataView)로 로드되는 다음 입력 데이터 사용:</span><span class="sxs-lookup"><span data-stu-id="4d1b8-149">Using the following input data which is loaded into an [`IDataView`](xref:Microsoft.ML.IDataView):</span></span>

```csharp
CarData[] cars = new CarData[] 
{
    new CarData
    {
        Color="Red",
        VehicleType="SUV"
    },
    new CarData
    {
        Color="Blue",
        VehicleType="Sedan"
    },
    new CarData
    {
        Color="Black",
        VehicleType="SUV"
    }
};
```

<span data-ttu-id="4d1b8-150">범주 `VehicleType` 속성은 [`OneHotEncoding`](xref:Microsoft.ML.CategoricalCatalog.OneHotEncoding*) 메서드를 사용해 숫자로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b8-150">The categorical `VehicleType` property can be converted into a number using the [`OneHotEncoding`](xref:Microsoft.ML.CategoricalCatalog.OneHotEncoding*) method.</span></span> 

```csharp
// Define categorical transform estimator
var categoricalEstimator = mlContext.Transforms.Categorical.OneHotEncoding("VehicleType");

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
ITransformer categoricalTransformer = categoricalEstimator.Fit(data);

// Transform Data
IDataView transformedData = categoricalTransformer.Transform(data);
```

<span data-ttu-id="4d1b8-151">결과로 만들어지는 변형은 `VehicleType`의 텍스트 값을 숫자로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b8-151">The resulting transform converts the text value of `VehicleType` to a number.</span></span> <span data-ttu-id="4d1b8-152">`VehicleType` 열의 항목은 변형이 적용되면 다음이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b8-152">The entries in the `VehicleType` column become the following when the transform is applied:</span></span> 

```text
[
    1, // SUV
    2, // Sedan
    1 // SUV
]
```

## <a name="work-with-text-data"></a><span data-ttu-id="4d1b8-153">텍스트 데이터 작업</span><span class="sxs-lookup"><span data-stu-id="4d1b8-153">Work with text data</span></span>

<span data-ttu-id="4d1b8-154">텍스트 데이터는 기계 학습 모델을 빌드하기 위해 사용하려면 숫자로 변형되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b8-154">Text data needs to be transformed into numbers before using it to build a machine learning model.</span></span> <span data-ttu-id="4d1b8-155">텍스트 변형에 대한 보다 자세한 목록과 설명은 [변형 페이지](../resources/transforms.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4d1b8-155">Visit the [transforms page](../resources/transforms.md) for a more detailed list and description of text transforms.</span></span>

<span data-ttu-id="4d1b8-156">[`IDataView`](xref:Microsoft.ML.IDataView)로 로드된 아래 데이터와 같은 데이터 사용:</span><span class="sxs-lookup"><span data-stu-id="4d1b8-156">Using data like the data below that has been loaded into an [`IDataView`](xref:Microsoft.ML.IDataView):</span></span>

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

<span data-ttu-id="4d1b8-157">텍스트를 숫자 벡터 표현으로 변형하는 최소 단계는 [`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText*) 메서드를 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b8-157">The minimum step to convert text to a numerical vector representation is to use the [`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText*) method.</span></span> <span data-ttu-id="4d1b8-158">[`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText*) 변형을 사용하여, 입력 텍스트 열에 일련의 변형이 적용되면 lg 정규화된 단어 및 문자 n그램을 나타내는 숫자 벡터가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b8-158">By using the [`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText*) transform, a series of transformations is applied to the input text column resulting in a numerical vector representing the lp-normalized word and character ngrams.</span></span> 

```csharp
// Define text transform estimator
var textEstimator  = mlContext.Transforms.Text.FeaturizeText("Description");

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
ITransformer textTransformer = textEstimator.Fit(data);

// Transform data
IDataView transformedData = textTransformer.Transform(data);
```

<span data-ttu-id="4d1b8-159">결과로 만들어지는 변형은 `Description` 열의 텍스트 값을 아래 출력과 유사하게 보이는 숫자 벡터로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b8-159">The resulting transform would convert the text values in the `Description` column to a numerical vector that looks similar to the output below:</span></span>

```text
[ 0.2041241, 0.2041241, 0.2041241, 0.4082483, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0, 0, 0, 0, 0.4472136, 0.4472136, 0.4472136, 0.4472136, 0.4472136, 0 ]
```

<span data-ttu-id="4d1b8-160">복잡한 텍스트 처리 단계를 [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601)으로 통합하여 노이즈를 제거하고 필요에 따라 필요한 처리량을 줄일 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b8-160">Combine complex text processing steps into an [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601) to remove noise and potentially reduce the amount of required processing resources as needed.</span></span>

```csharp
// Define text transform estimator
var textEstimator = mlContext.Transforms.Text.NormalizeText("Description")
    .Append(mlContext.Transforms.Text.TokenizeIntoWords("Description"))
    .Append(mlContext.Transforms.Text.RemoveDefaultStopWords("Description"))
    .Append(mlContext.Transforms.Conversion.MapValueToKey("Description"))
    .Append(mlContext.Transforms.Text.ProduceNgrams("Description"))
    .Append(mlContext.Transforms.NormalizeLpNorm("Description"));
```

<span data-ttu-id="4d1b8-161">`textEstimator`에는 [`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText*) 메서드에서 수행하는 작업의 하위 세트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b8-161">`textEstimator` contains a subset of operations performed by the [`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText*) method.</span></span> <span data-ttu-id="4d1b8-162">보다 복잡한 파이프라인의 이점은 데이터에 적용되는 변형에 대한 제어와 가시성입니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b8-162">The benefit of a more complex pipeline is control and visibility over the transformations applied to the data.</span></span> 

<span data-ttu-id="4d1b8-163">다음은 예로 첫 번째 항목을 사용하여 `textEstimator`에서 정의하는 변형 단계에서 생성되는 결과에 대한 자세한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b8-163">Using the first entry as an example, the following is a detailed description of the results produced by the transformation steps defined by `textEstimator`:</span></span>

<span data-ttu-id="4d1b8-164">**원문: This is a good product**</span><span class="sxs-lookup"><span data-stu-id="4d1b8-164">**Original Text: This is a good product**</span></span>

|<span data-ttu-id="4d1b8-165">변형</span><span class="sxs-lookup"><span data-stu-id="4d1b8-165">Transform</span></span> | <span data-ttu-id="4d1b8-166">설명</span><span class="sxs-lookup"><span data-stu-id="4d1b8-166">Description</span></span> | <span data-ttu-id="4d1b8-167">결과</span><span class="sxs-lookup"><span data-stu-id="4d1b8-167">Result</span></span>
|--|--|--|
|<span data-ttu-id="4d1b8-168">1. NormalizeText</span><span class="sxs-lookup"><span data-stu-id="4d1b8-168">1. NormalizeText</span></span> | <span data-ttu-id="4d1b8-169">모든 문자를 기본적으로 소문자로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b8-169">Converts all letters to lowercase by default</span></span> | <span data-ttu-id="4d1b8-170">this is a good product</span><span class="sxs-lookup"><span data-stu-id="4d1b8-170">this is a good product</span></span>
|<span data-ttu-id="4d1b8-171">2. TokenizeWords</span><span class="sxs-lookup"><span data-stu-id="4d1b8-171">2. TokenizeWords</span></span> | <span data-ttu-id="4d1b8-172">문자를 개별 단어로 분할합니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b8-172">Splits string into individual words</span></span> | <span data-ttu-id="4d1b8-173">["this","is","a","good","product"]</span><span class="sxs-lookup"><span data-stu-id="4d1b8-173">["this","is","a","good","product"]</span></span>
|<span data-ttu-id="4d1b8-174">3. RemoveDefaultStopWords</span><span class="sxs-lookup"><span data-stu-id="4d1b8-174">3. RemoveDefaultStopWords</span></span> | <span data-ttu-id="4d1b8-175">*is* 및 *a*와 같은 불용어를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b8-175">Removes stopwords like *is* and *a*.</span></span> | <span data-ttu-id="4d1b8-176">["good","product"]</span><span class="sxs-lookup"><span data-stu-id="4d1b8-176">["good","product"]</span></span>
|<span data-ttu-id="4d1b8-177">4. MapValueToKey</span><span class="sxs-lookup"><span data-stu-id="4d1b8-177">4. MapValueToKey</span></span> | <span data-ttu-id="4d1b8-178">입력 데이터에 기반하여 값을 키(범주)에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b8-178">Maps the values to keys (categories) based on the input data</span></span> |  <span data-ttu-id="4d1b8-179">[1,2]</span><span class="sxs-lookup"><span data-stu-id="4d1b8-179">[1,2]</span></span>
|<span data-ttu-id="4d1b8-180">5. ProduceNGrams</span><span class="sxs-lookup"><span data-stu-id="4d1b8-180">5. ProduceNGrams</span></span> | <span data-ttu-id="4d1b8-181">텍스트를 연속 단어 시퀀스로 변형합니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b8-181">Transforms text into sequence of consecutive words</span></span> | <span data-ttu-id="4d1b8-182">[1,1,1,0,0]</span><span class="sxs-lookup"><span data-stu-id="4d1b8-182">[1,1,1,0,0]</span></span>
|<span data-ttu-id="4d1b8-183">6. NormalizeLpNorm</span><span class="sxs-lookup"><span data-stu-id="4d1b8-183">6. NormalizeLpNorm</span></span> | <span data-ttu-id="4d1b8-184">lp-norm으로 입력 크기를 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b8-184">Scale inputs by their lp-norm</span></span> | <span data-ttu-id="4d1b8-185">[ 0.577350529, 0.577350529, 0.577350529, 0, 0 ]</span><span class="sxs-lookup"><span data-stu-id="4d1b8-185">[ 0.577350529, 0.577350529, 0.577350529, 0, 0 ]</span></span>
