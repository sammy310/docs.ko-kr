---
title: 파일 및 기타 소스에서 데이터 로드
description: 여기에서는 ML.NET에서의 처리 및 학습을 위해 데이터를 로드하는 방법을 보여 줍니다. 데이터는 원래 파일이나 데이터베이스, JSON, XML 또는 메모리 내 컬렉션 등의 다른 데이터 원본에 저장됩니다.
ms.date: 08/01/2019
ms.custom: mvc,how-to, title-hack-0625
ms.openlocfilehash: d5f3aab14a60a8c9860dc67f1cc98f3b1b3188ed
ms.sourcegitcommit: 8c6426a3d2adff5fbcbe1fed0f28eda718c15351
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/02/2019
ms.locfileid: "68733356"
---
# <a name="load-data-from-files-and-other-sources"></a><span data-ttu-id="9b7f3-104">파일 및 기타 소스에서 데이터 로드</span><span class="sxs-lookup"><span data-stu-id="9b7f3-104">Load data from files and other sources</span></span>

<span data-ttu-id="9b7f3-105">여기에서는 ML.NET에서의 처리 및 학습을 위해 데이터를 로드하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9b7f3-105">This how-to shows you how to load data for processing and training into ML.NET.</span></span> <span data-ttu-id="9b7f3-106">데이터는 원래 파일이나 데이터베이스, JSON, XML 또는 메모리 내 컬렉션 등의 다른 데이터 원본에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b7f3-106">The data is originally stored in files or other data sources such as databases, JSON, XML or in-memory collections.</span></span>

## <a name="create-the-data-model"></a><span data-ttu-id="9b7f3-107">데이터 모델 만들기</span><span class="sxs-lookup"><span data-stu-id="9b7f3-107">Create the data model</span></span>

<span data-ttu-id="9b7f3-108">ML.NET을 사용하면 클래스를 통해 데이터 모델을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b7f3-108">ML.NET enables you to define data models via classes.</span></span> <span data-ttu-id="9b7f3-109">다음과 같은 입력 데이터를 가정하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="9b7f3-109">For example, given the following input data:</span></span>

```text
Size (Sq. ft.), HistoricalPrice1 ($), HistoricalPrice2 ($), HistoricalPrice3 ($), Current Price ($)
700, 100000, 3000000, 250000, 500000
1000, 600000, 400000, 650000, 700000
```

<span data-ttu-id="9b7f3-110">아래 코드 조각을 나타내는 데이터 모델을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9b7f3-110">Create a data model that represents the snippet below:</span></span>

```csharp
public class HousingData
{
    [LoadColumn(0)]
    public float Size { get; set; }
 
    [LoadColumn(1, 3)]
    [VectorType(3)]
    public float[] HistoricalPrices { get; set; }

    [LoadColumn(4)]
    [ColumnName("Label")]
    public float CurrentPrice { get; set; }
}
```

### <a name="annotating-the-data-model-with-column-attributes"></a><span data-ttu-id="9b7f3-111">열 특성을 사용하여 데이터 모델에 주석 지정</span><span class="sxs-lookup"><span data-stu-id="9b7f3-111">Annotating the data model with column attributes</span></span>

<span data-ttu-id="9b7f3-112">특성은 데이터 모델과 데이터 원본에 대한 더 상세한 정보를 ML.NET에 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9b7f3-112">Attributes give ML.NET more information about the data model and the data source.</span></span>

<span data-ttu-id="9b7f3-113">[`LoadColumn`](xref:Microsoft.ML.Data.LoadColumnAttribute) 특성은 속성의 열 인덱스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9b7f3-113">The [`LoadColumn`](xref:Microsoft.ML.Data.LoadColumnAttribute) attribute specifies your properties' column indices.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9b7f3-114">[`LoadColumn`](xref:Microsoft.ML.Data.LoadColumnAttribute)은 파일에서 데이터를 로드할 때만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="9b7f3-114">[`LoadColumn`](xref:Microsoft.ML.Data.LoadColumnAttribute) is only required when loading data from a file.</span></span>

<span data-ttu-id="9b7f3-115">다음과 같이 열을 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="9b7f3-115">Load columns as:</span></span> 
- <span data-ttu-id="9b7f3-116">`HousingData` 클래스에서 `Size` 및 `CurrentPrices` 같은 개별 열</span><span class="sxs-lookup"><span data-stu-id="9b7f3-116">Individual columns like `Size` and `CurrentPrices` in the `HousingData` class.</span></span>
- <span data-ttu-id="9b7f3-117">`HousingData` 클래스에서 `HistoricalPrices` 같이 벡터 형식으로 한 번에 여러 열</span><span class="sxs-lookup"><span data-stu-id="9b7f3-117">Multiple columns at a time in the form of a vector like `HistoricalPrices` in the `HousingData` class.</span></span>

<span data-ttu-id="9b7f3-118">벡터 속성이 있는 경우 [`VectorType`](xref:Microsoft.ML.Data.VectorTypeAttribute) 특성을 데이터 모델의 속성에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="9b7f3-118">If you have a vector property, apply the [`VectorType`](xref:Microsoft.ML.Data.VectorTypeAttribute) attribute to the property in your data model.</span></span> <span data-ttu-id="9b7f3-119">벡터의 모든 요소는 같은 반드시 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b7f3-119">It's important to note that all of the elements in the vector need to be the same type.</span></span> <span data-ttu-id="9b7f3-120">열을 분리된 상태로 유지하면 기능 엔지니어링을 쉽고 유연하게 사용할 수 있지만, 열 수가 매우 많은 경우 개별 열에 대해 작업하면 학습 속도에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9b7f3-120">Keeping the columns separated allows for ease and flexibility of feature engineering, but for a very large number of columns, operating on the individual columns causes an impact on training speed.</span></span>

<span data-ttu-id="9b7f3-121">ML.NET은 열 이름으로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="9b7f3-121">ML.NET Operates through column names.</span></span> <span data-ttu-id="9b7f3-122">열 이름을 속성 이름과 다르게 변경하려면 [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) 특성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9b7f3-122">If you want to change the name of a column to something other than the property name, use the [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) attribute.</span></span> <span data-ttu-id="9b7f3-123">메모리 내 개체를 만들 때도 속성 이름을 사용하여 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9b7f3-123">When creating in-memory objects, you still create objects using the property name.</span></span> <span data-ttu-id="9b7f3-124">그러나 데이터 처리 및 기계 학습 모델 빌드를 위해 ML.NET은 [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) 특성에서 제공한 값으로 속성을 재정의 및 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="9b7f3-124">However, for data processing and building machine learning models, ML.NET overrides and references the property with the value provided in the [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) attribute.</span></span>

## <a name="load-data-from-a-single-file"></a><span data-ttu-id="9b7f3-125">단일 파일에서 데이터 로드</span><span class="sxs-lookup"><span data-stu-id="9b7f3-125">Load data from a single file</span></span>

<span data-ttu-id="9b7f3-126">파일에서 데이터를 로드하려면 로드할 데이터에 대해 데이터 모델에 [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*) 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9b7f3-126">To load data from a file use the [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*) method along with the data model for the data to be loaded.</span></span> <span data-ttu-id="9b7f3-127">`separatorChar` 매개 변수는 기본적으로 탭으로 구분되므로 필요에 맞게 데이터 파일을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="9b7f3-127">Since `separatorChar` parameter is tab-delimited by default, change it for your data file as needed.</span></span> <span data-ttu-id="9b7f3-128">파일에 헤더가 있으면 `hasHeader` 매개 변수 `true`로 설정하여 파일의 첫 줄을 무시하고 두 번째 줄부터 데이터를 로드하기 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="9b7f3-128">If your file has a header, set the `hasHeader` parameter to `true` to ignore the first line in the file and begin to load data from the second line.</span></span>

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

//Load Data
IDataView data = mlContext.Data.LoadFromTextFile<HousingData>("my-data-file.csv", separatorChar: ',', hasHeader: true);
```

## <a name="load-data-from-multiple-files"></a><span data-ttu-id="9b7f3-129">여러 파일에서 데이터 로드</span><span class="sxs-lookup"><span data-stu-id="9b7f3-129">Load data from multiple files</span></span>

<span data-ttu-id="9b7f3-130">데이터가 여러 파일에 저장되어 있고 데이터 스키마가 같은 경우라면 ML.NET에서 같은 디렉터리 또는 여러 디렉터리에 있는 여러 파일에서 데이터를 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b7f3-130">In the event that your data is stored in multiple files, as long as the data schema is the same, ML.NET allows you to load data from multiple files that are either in the same directory or multiple directories.</span></span>

### <a name="load-from-files-in-a-single-directory"></a><span data-ttu-id="9b7f3-131">단일 디렉터리의 파일에서 로드</span><span class="sxs-lookup"><span data-stu-id="9b7f3-131">Load from files in a single directory</span></span>

<span data-ttu-id="9b7f3-132">모든 데이터 파일이 같은 디렉터리에 있으면 [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*) 메서드에서 와일드카드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9b7f3-132">When all of your data files are in the same directory, use wildcards in the [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*) method.</span></span>

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

//Load Data File
IDataView data = mlContext.Data.LoadFromTextFile<HousingData>("Data/*", separatorChar: ',', hasHeader: true);
```

### <a name="load-from-files-in-multiple-directories"></a><span data-ttu-id="9b7f3-133">여러 디렉터리의 파일에서 로드</span><span class="sxs-lookup"><span data-stu-id="9b7f3-133">Load from files in multiple directories</span></span>

<span data-ttu-id="9b7f3-134">여러 디렉터리에서 데이터를 로드하려면 [`CreateTextLoader`](xref:Microsoft.ML.TextLoaderSaverCatalog.CreateTextLoader*) 메서드를 사용하여 [`TextLoader`](xref:Microsoft.ML.Data.TextLoader)를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9b7f3-134">To load data from multiple directories, use the [`CreateTextLoader`](xref:Microsoft.ML.TextLoaderSaverCatalog.CreateTextLoader*) method to create a [`TextLoader`](xref:Microsoft.ML.Data.TextLoader).</span></span> <span data-ttu-id="9b7f3-135">그런 다음, [`TextLoader.Load`](xref:Microsoft.ML.DataLoaderExtensions.Load*) 메서드를 사용하고 개별 파일 경로를 지정합니다(와일드카드를 사용할 수 없음).</span><span class="sxs-lookup"><span data-stu-id="9b7f3-135">Then, use the [`TextLoader.Load`](xref:Microsoft.ML.DataLoaderExtensions.Load*) method and specify the individual file paths (wildcards can't be used).</span></span>

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

// Create TextLoader
TextLoader textLoader = mlContext.Data.CreateTextLoader<HousingData>(separatorChar: ',', hasHeader: true);

// Load Data
IDataView data = textLoader.Load("DataFolder/SubFolder1/1.txt", "DataFolder/SubFolder2/1.txt");
```

## <a name="load-data-from-other-sources"></a><span data-ttu-id="9b7f3-136">다른 소스에서 데이터 로드</span><span class="sxs-lookup"><span data-stu-id="9b7f3-136">Load data from other sources</span></span>

<span data-ttu-id="9b7f3-137">파일에 저장된 데이터를 로드하는 것 외에도, ML.NET은 다음을 포함하지만 이에 국한되지 않는 소스에서 데이터 로드를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="9b7f3-137">In addition to loading data stored in files, ML.NET supports loading data from sources that include but are not limited to:</span></span>

- <span data-ttu-id="9b7f3-138">메모리 내 컬렉션</span><span class="sxs-lookup"><span data-stu-id="9b7f3-138">In-memory collections</span></span>
- <span data-ttu-id="9b7f3-139">JSON/XML</span><span class="sxs-lookup"><span data-stu-id="9b7f3-139">JSON/XML</span></span>
- <span data-ttu-id="9b7f3-140">Databases</span><span class="sxs-lookup"><span data-stu-id="9b7f3-140">Databases</span></span>

<span data-ttu-id="9b7f3-141">스트리밍 원본을 사용할 때는 ML.NET이 메모리 내 컬렉션 형태의 입력을 기대합니다.</span><span class="sxs-lookup"><span data-stu-id="9b7f3-141">Note that when working with streaming sources, ML.NET expects input to be in the form of an in-memory collection.</span></span> <span data-ttu-id="9b7f3-142">따라서 JSON/XML 등의 원본을 사용할 때는 데이터 형식이 메모리 내 컬렉션이 되게 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b7f3-142">Therefore, when working with sources like JSON/XML, make sure to format the data into an in-memory collection.</span></span>

<span data-ttu-id="9b7f3-143">다음 메모리 내 컬렉션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9b7f3-143">Given the following in-memory collection:</span></span>

```csharp
HousingData[] inMemoryCollection = new HousingData[]
{
    new HousingData
    {
        Size =700f,
        HistoricalPrices = new float[]
        {
            100000f, 3000000f, 250000f
        },
        CurrentPrice = 500000f
    },
    new HousingData
    {
        Size =1000f,
        HistoricalPrices = new float[]
        {
            600000f, 400000f, 650000f
        },
        CurrentPrice=700000f
    }
};
```

<span data-ttu-id="9b7f3-144">[`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*) 메서드로 메모리 내 컬렉션을 [`IDataView`](xref:Microsoft.ML.IDataView)에 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="9b7f3-144">Load the in-memory collection into an [`IDataView`](xref:Microsoft.ML.IDataView) with the [`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*) method:</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9b7f3-145">[`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*)에서는 로드하는 [`IEnumerable`](xref:System.Collections.IEnumerable)이 스레드로부터 안전하다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="9b7f3-145">[`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*) assumes that the [`IEnumerable`](xref:System.Collections.IEnumerable) it loads from is thread-safe.</span></span> 

```csharp
// Create MLContext
MLContext mlContext = new MLContext();

//Load Data
IDataView data = mlContext.Data.LoadFromEnumerable<HousingData>(inMemoryCollection);
```
