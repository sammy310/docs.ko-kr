---
title: 파일 및 기타 소스에서 데이터 로드
description: API를 사용하여 처리 및 학습을 위한 데이터를 ML.NET으로 로드하는 방법을 알아봅니다. 데이터는 파일, 데이터베이스, JSON, XML 또는 메모리 내 컬렉션에 저장됩니다.
ms.date: 11/07/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc,how-to, title-hack-0625
ms.openlocfilehash: 83aaae2d2e75b3076841750bf5d505390a538bc0
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344750"
---
# <a name="load-data-from-files-and-other-sources"></a><span data-ttu-id="32da1-104">파일 및 기타 소스에서 데이터 로드</span><span class="sxs-lookup"><span data-stu-id="32da1-104">Load data from files and other sources</span></span>

<span data-ttu-id="32da1-105">API를 사용하여 처리 및 학습을 위한 데이터를 ML.NET으로 로드하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="32da1-105">Learn how to load data for processing and training into ML.NET using the API.</span></span> <span data-ttu-id="32da1-106">데이터는 원래 파일이나 데이터베이스, JSON, XML 또는 메모리 내 컬렉션 등의 다른 데이터 원본에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="32da1-106">The data is originally stored in files or other data sources such as databases, JSON, XML or in-memory collections.</span></span>

<span data-ttu-id="32da1-107">모델 작성기를 사용하는 경우, [모델 작성기에 학습 데이터 로드](load-data-model-builder.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="32da1-107">If you're using Model Builder, see [Load training data into Model Builder](load-data-model-builder.md).</span></span>

## <a name="create-the-data-model"></a><span data-ttu-id="32da1-108">데이터 모델 만들기</span><span class="sxs-lookup"><span data-stu-id="32da1-108">Create the data model</span></span>

<span data-ttu-id="32da1-109">ML.NET을 사용하면 클래스를 통해 데이터 모델을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32da1-109">ML.NET enables you to define data models via classes.</span></span> <span data-ttu-id="32da1-110">다음과 같은 입력 데이터를 가정하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="32da1-110">For example, given the following input data:</span></span>

```text
Size (Sq. ft.), HistoricalPrice1 ($), HistoricalPrice2 ($), HistoricalPrice3 ($), Current Price ($)
700, 100000, 3000000, 250000, 500000
1000, 600000, 400000, 650000, 700000
```

<span data-ttu-id="32da1-111">아래 코드 조각을 나타내는 데이터 모델을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="32da1-111">Create a data model that represents the snippet below:</span></span>

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

### <a name="annotating-the-data-model-with-column-attributes"></a><span data-ttu-id="32da1-112">열 특성을 사용하여 데이터 모델에 주석 지정</span><span class="sxs-lookup"><span data-stu-id="32da1-112">Annotating the data model with column attributes</span></span>

<span data-ttu-id="32da1-113">특성은 데이터 모델과 데이터 원본에 대한 더 상세한 정보를 ML.NET에 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="32da1-113">Attributes give ML.NET more information about the data model and the data source.</span></span>

<span data-ttu-id="32da1-114">[`LoadColumn`](xref:Microsoft.ML.Data.LoadColumnAttribute) 특성은 속성의 열 인덱스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="32da1-114">The [`LoadColumn`](xref:Microsoft.ML.Data.LoadColumnAttribute) attribute specifies your properties' column indices.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="32da1-115">[`LoadColumn`](xref:Microsoft.ML.Data.LoadColumnAttribute)은 파일에서 데이터를 로드할 때만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="32da1-115">[`LoadColumn`](xref:Microsoft.ML.Data.LoadColumnAttribute) is only required when loading data from a file.</span></span>

<span data-ttu-id="32da1-116">다음과 같이 열을 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="32da1-116">Load columns as:</span></span>

- <span data-ttu-id="32da1-117">`HousingData` 클래스에서 `Size` 및 `CurrentPrices` 같은 개별 열</span><span class="sxs-lookup"><span data-stu-id="32da1-117">Individual columns like `Size` and `CurrentPrices` in the `HousingData` class.</span></span>
- <span data-ttu-id="32da1-118">`HousingData` 클래스에서 `HistoricalPrices` 같이 벡터 형식으로 한 번에 여러 열</span><span class="sxs-lookup"><span data-stu-id="32da1-118">Multiple columns at a time in the form of a vector like `HistoricalPrices` in the `HousingData` class.</span></span>

<span data-ttu-id="32da1-119">벡터 속성이 있는 경우 [`VectorType`](xref:Microsoft.ML.Data.VectorTypeAttribute) 특성을 데이터 모델의 속성에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="32da1-119">If you have a vector property, apply the [`VectorType`](xref:Microsoft.ML.Data.VectorTypeAttribute) attribute to the property in your data model.</span></span> <span data-ttu-id="32da1-120">벡터의 모든 요소는 같은 반드시 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="32da1-120">It's important to note that all of the elements in the vector need to be the same type.</span></span> <span data-ttu-id="32da1-121">열을 분리된 상태로 유지하면 기능 엔지니어링을 쉽고 유연하게 사용할 수 있지만, 열 수가 매우 많은 경우 개별 열에 대해 작업하면 학습 속도에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="32da1-121">Keeping the columns separated allows for ease and flexibility of feature engineering, but for a very large number of columns, operating on the individual columns causes an impact on training speed.</span></span>

<span data-ttu-id="32da1-122">ML.NET은 열 이름으로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="32da1-122">ML.NET Operates through column names.</span></span> <span data-ttu-id="32da1-123">열 이름을 속성 이름과 다르게 변경하려면 [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) 특성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="32da1-123">If you want to change the name of a column to something other than the property name, use the [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) attribute.</span></span> <span data-ttu-id="32da1-124">메모리 내 개체를 만들 때도 속성 이름을 사용하여 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="32da1-124">When creating in-memory objects, you still create objects using the property name.</span></span> <span data-ttu-id="32da1-125">그러나 데이터 처리 및 기계 학습 모델 빌드를 위해 ML.NET은 [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) 특성에서 제공한 값으로 속성을 재정의 및 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="32da1-125">However, for data processing and building machine learning models, ML.NET overrides and references the property with the value provided in the [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) attribute.</span></span>

## <a name="load-data-from-a-single-file"></a><span data-ttu-id="32da1-126">단일 파일에서 데이터 로드</span><span class="sxs-lookup"><span data-stu-id="32da1-126">Load data from a single file</span></span>

<span data-ttu-id="32da1-127">파일에서 데이터를 로드하려면 로드할 데이터에 대해 데이터 모델에 [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*) 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="32da1-127">To load data from a file use the [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*) method along with the data model for the data to be loaded.</span></span> <span data-ttu-id="32da1-128">`separatorChar` 매개 변수는 기본적으로 탭으로 구분되므로 필요에 맞게 데이터 파일을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="32da1-128">Since `separatorChar` parameter is tab-delimited by default, change it for your data file as needed.</span></span> <span data-ttu-id="32da1-129">파일에 헤더가 있으면 `hasHeader` 매개 변수 `true`로 설정하여 파일의 첫 줄을 무시하고 두 번째 줄부터 데이터를 로드하기 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="32da1-129">If your file has a header, set the `hasHeader` parameter to `true` to ignore the first line in the file and begin to load data from the second line.</span></span>

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

//Load Data
IDataView data = mlContext.Data.LoadFromTextFile<HousingData>("my-data-file.csv", separatorChar: ',', hasHeader: true);
```

## <a name="load-data-from-multiple-files"></a><span data-ttu-id="32da1-130">여러 파일에서 데이터 로드</span><span class="sxs-lookup"><span data-stu-id="32da1-130">Load data from multiple files</span></span>

<span data-ttu-id="32da1-131">데이터가 여러 파일에 저장되어 있고 데이터 스키마가 같은 경우라면 ML.NET에서 같은 디렉터리 또는 여러 디렉터리에 있는 여러 파일에서 데이터를 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32da1-131">In the event that your data is stored in multiple files, as long as the data schema is the same, ML.NET allows you to load data from multiple files that are either in the same directory or multiple directories.</span></span>

### <a name="load-from-files-in-a-single-directory"></a><span data-ttu-id="32da1-132">단일 디렉터리의 파일에서 로드</span><span class="sxs-lookup"><span data-stu-id="32da1-132">Load from files in a single directory</span></span>

<span data-ttu-id="32da1-133">모든 데이터 파일이 같은 디렉터리에 있으면 [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*) 메서드에서 와일드카드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="32da1-133">When all of your data files are in the same directory, use wildcards in the [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*) method.</span></span>

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

//Load Data File
IDataView data = mlContext.Data.LoadFromTextFile<HousingData>("Data/*", separatorChar: ',', hasHeader: true);
```

### <a name="load-from-files-in-multiple-directories"></a><span data-ttu-id="32da1-134">여러 디렉터리의 파일에서 로드</span><span class="sxs-lookup"><span data-stu-id="32da1-134">Load from files in multiple directories</span></span>

<span data-ttu-id="32da1-135">여러 디렉터리에서 데이터를 로드하려면 [`CreateTextLoader`](xref:Microsoft.ML.TextLoaderSaverCatalog.CreateTextLoader*) 메서드를 사용하여 [`TextLoader`](xref:Microsoft.ML.Data.TextLoader)를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="32da1-135">To load data from multiple directories, use the [`CreateTextLoader`](xref:Microsoft.ML.TextLoaderSaverCatalog.CreateTextLoader*) method to create a [`TextLoader`](xref:Microsoft.ML.Data.TextLoader).</span></span> <span data-ttu-id="32da1-136">그런 다음, [`TextLoader.Load`](xref:Microsoft.ML.DataLoaderExtensions.Load*) 메서드를 사용하고 개별 파일 경로를 지정합니다(와일드카드를 사용할 수 없음).</span><span class="sxs-lookup"><span data-stu-id="32da1-136">Then, use the [`TextLoader.Load`](xref:Microsoft.ML.DataLoaderExtensions.Load*) method and specify the individual file paths (wildcards can't be used).</span></span>

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

// Create TextLoader
TextLoader textLoader = mlContext.Data.CreateTextLoader<HousingData>(separatorChar: ',', hasHeader: true);

// Load Data
IDataView data = textLoader.Load("DataFolder/SubFolder1/1.txt", "DataFolder/SubFolder2/1.txt");
```

## <a name="load-data-from-a-relational-database"></a><span data-ttu-id="32da1-137">관계형 데이터베이스에서 데이터 로드</span><span class="sxs-lookup"><span data-stu-id="32da1-137">Load data from a relational database</span></span>

<span data-ttu-id="32da1-138">ML.NET은 SQL Server, Azure Database, Oracle, SQLite, PostgreSQL, Progress, IBM DB2 등 [`System.Data`](xref:System.Data)가 지원하는 다양한 관계형 데이터베이스에서의 데이터 로드를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="32da1-138">ML.NET supports loading data from a variety of relational databases supported by [`System.Data`](xref:System.Data) that include SQL Server, Azure SQL Database, Oracle, SQLite, PostgreSQL, Progress, IBM DB2, and many more.</span></span>

> [!NOTE]
> <span data-ttu-id="32da1-139">`DatabaseLoader`를 사용하려면 [System.Data.SqlClient](https://www.nuget.org/packages/System.Data.SqlClient) NuGet 패키지를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="32da1-139">To use `DatabaseLoader`, reference the [System.Data.SqlClient](https://www.nuget.org/packages/System.Data.SqlClient) NuGet package.</span></span>

<span data-ttu-id="32da1-140">`House`라는 테이블과 다음 스키마가 포함된 데이터베이스가 있는 경우:</span><span class="sxs-lookup"><span data-stu-id="32da1-140">Given a database with a table named `House` and the following schema:</span></span>

```SQL
CREATE TABLE [House] (
    [HouseId] INT NOT NULL IDENTITY,
    [Size] INT NOT NULL,
    [NumBed] INT NOT NULL,
    [Price] REAL NOT NULL
    CONSTRAINT [PK_House] PRIMARY KEY ([HouseId])
);
```

<span data-ttu-id="32da1-141">데이터는 `HouseData` 같은 클래스로 모델링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32da1-141">The data can be modeled by a class like `HouseData`.</span></span>

```csharp
public class HouseData
{
    public float Size { get; set; }

    public float NumBed { get; set; }

    public float Price { get; set; }
}
```

<span data-ttu-id="32da1-142">그런 다음 애플리케이션 내에서 `DatabaseLoader`를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="32da1-142">Then, inside of your application, create a `DatabaseLoader`.</span></span>

```csharp
MLContext mlContext = new MLContext();

DatabaseLoader loader = mlContext.Data.CreateDatabaseLoader<HouseData>();
```

<span data-ttu-id="32da1-143">연결 문자열과 데이터베이스에서 실행할 SQL 명령을 정의하고 `DatabaseSource` 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="32da1-143">Define your connection string as well as the SQL command to be executed on the database and create a `DatabaseSource` instance.</span></span> <span data-ttu-id="32da1-144">이 샘플에서는 파일 경로가 포함된 LocalDB SQL Server 데이터베이스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="32da1-144">This sample uses a LocalDB SQL Server database with a file path.</span></span> <span data-ttu-id="32da1-145">다만 DatabaseLoader는 온-프레미스 및 클라우드의 데이터베이스에 대한 다른 유효한 연결 문자열은 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="32da1-145">However, DatabaseLoader supports any other valid connection string for databases on-premises and in the cloud.</span></span>

```csharp
string connectionString = @"Data Source=(LocalDB)\MSSQLLocalDB;AttachDbFilename=<YOUR-DB-FILEPATH>;Database=<YOUR-DB-NAME>;Integrated Security=True;Connect Timeout=30";

string sqlCommand = "SELECT Size, CAST(NumBed as REAL) as NumBed, Price FROM House";

DatabaseSource dbSource = new DatabaseSource(SqlClientFactory.Instance, connectionString, sqlCommand);
```

<span data-ttu-id="32da1-146">[`Real`](xref:System.Data.SqlDbType) 형식이 아닌 숫자 데이터를 [`Real`](xref:System.Data.SqlDbType)로 변환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="32da1-146">Numerical data that is not of type [`Real`](xref:System.Data.SqlDbType) has to be converted to [`Real`](xref:System.Data.SqlDbType).</span></span> <span data-ttu-id="32da1-147">[`Real`](xref:System.Data.SqlDbType) 형식은 ML.NET 알고리즘에서 예상하는 입력 형식인 단정밀도 부동 소수점 값 또는 [`Single`](xref:System.Single)로 표현됩니다.</span><span class="sxs-lookup"><span data-stu-id="32da1-147">The [`Real`](xref:System.Data.SqlDbType) type is represented as a single-precision floating-point value or [`Single`](xref:System.Single), the input type expected by ML.NET algorithms.</span></span> <span data-ttu-id="32da1-148">이 샘플에서 `NumBed` 열은 데이터베이스의 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="32da1-148">In this sample, the `NumBed` column is an integer in the database.</span></span> <span data-ttu-id="32da1-149">`CAST` 기본 제공 함수를 사용하여 [`Real`](xref:System.Data.SqlDbType)로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="32da1-149">Using the `CAST` built-in function, it's converted to [`Real`](xref:System.Data.SqlDbType).</span></span> <span data-ttu-id="32da1-150">`Price` 속성은 이미 로드된 대로 [`Real`](xref:System.Data.SqlDbType) 형식이기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="32da1-150">Because the `Price` property is already of type [`Real`](xref:System.Data.SqlDbType) it is loaded as is.</span></span>

<span data-ttu-id="32da1-151">`Load` 메서드를 사용하여 데이터를 [`IDataView`](xref:Microsoft.ML.IDataView)에 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="32da1-151">Use the `Load` method to load the data into an [`IDataView`](xref:Microsoft.ML.IDataView).</span></span>

```csharp
IDataView data = loader.Load(dbSource);
```

## <a name="load-data-from-other-sources"></a><span data-ttu-id="32da1-152">다른 소스에서 데이터 로드</span><span class="sxs-lookup"><span data-stu-id="32da1-152">Load data from other sources</span></span>

<span data-ttu-id="32da1-153">파일에 저장된 데이터를 로드하는 것 외에도, ML.NET은 다음을 포함하지만 이에 국한되지 않는 소스에서 데이터 로드를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="32da1-153">In addition to loading data stored in files, ML.NET supports loading data from sources that include but are not limited to:</span></span>

- <span data-ttu-id="32da1-154">메모리 내 컬렉션</span><span class="sxs-lookup"><span data-stu-id="32da1-154">In-memory collections</span></span>
- <span data-ttu-id="32da1-155">JSON/XML</span><span class="sxs-lookup"><span data-stu-id="32da1-155">JSON/XML</span></span>

<span data-ttu-id="32da1-156">스트리밍 원본을 사용할 때는 ML.NET이 메모리 내 컬렉션 형태의 입력을 기대합니다.</span><span class="sxs-lookup"><span data-stu-id="32da1-156">Note that when working with streaming sources, ML.NET expects input to be in the form of an in-memory collection.</span></span> <span data-ttu-id="32da1-157">따라서 JSON/XML 등의 원본을 사용할 때는 데이터 형식이 메모리 내 컬렉션이 되게 합니다.</span><span class="sxs-lookup"><span data-stu-id="32da1-157">Therefore, when working with sources like JSON/XML, make sure to format the data into an in-memory collection.</span></span>

<span data-ttu-id="32da1-158">다음 메모리 내 컬렉션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="32da1-158">Given the following in-memory collection:</span></span>

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

<span data-ttu-id="32da1-159">[`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*) 메서드로 메모리 내 컬렉션을 [`IDataView`](xref:Microsoft.ML.IDataView)에 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="32da1-159">Load the in-memory collection into an [`IDataView`](xref:Microsoft.ML.IDataView) with the [`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*) method:</span></span>

> [!IMPORTANT]
> <span data-ttu-id="32da1-160">[`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*)에서는 로드하는 [`IEnumerable`](xref:System.Collections.IEnumerable)이 스레드로부터 안전하다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="32da1-160">[`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*) assumes that the [`IEnumerable`](xref:System.Collections.IEnumerable) it loads from is thread-safe.</span></span>

```csharp
// Create MLContext
MLContext mlContext = new MLContext();

//Load Data
IDataView data = mlContext.Data.LoadFromEnumerable<HousingData>(inMemoryCollection);
```

## <a name="next-steps"></a><span data-ttu-id="32da1-161">다음 단계</span><span class="sxs-lookup"><span data-stu-id="32da1-161">Next steps</span></span>

- <span data-ttu-id="32da1-162">데이터를 정리하거나 처리하려면 [모델 빌드를 위해 데이터 준비](prepare-data-ml-net.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="32da1-162">To clean or otherwise process data, see [Prepare data for building a model](prepare-data-ml-net.md).</span></span>
- <span data-ttu-id="32da1-163">모델을 빌드할 준비가 된 경우, [모델 학습 및 평가](train-machine-learning-model-ml-net.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="32da1-163">When you're ready to build a model, see [Train and evaluate a model](train-machine-learning-model-ml-net.md).</span></span>
