---
title: '자습서: 제품 판매의 변칙 검색'
description: 제품 판매 데이터에 대한 변칙 검색 애플리케이션을 빌드하는 방법을 알아봅니다. 이 자습서에서는 Visual Studio 2019에서 C#을 사용하여 .NET Core 콘솔 애플리케이션을 만듭니다.
ms.date: 07/17/2019
ms.topic: tutorial
ms.custom: mvc, title-hack-0612
ms.openlocfilehash: e87034733b048153202bc11ab94ed7605749f60c
ms.sourcegitcommit: 09d699aca28ae9723399bbd9d3d44aa0cbd3848d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/19/2019
ms.locfileid: "68331703"
---
# <a name="tutorial-detect-anomalies-in-product-sales-with-mlnet"></a><span data-ttu-id="f3d84-104">자습서: ML.NET을 사용하여 제품 판매의 변칙 검색</span><span class="sxs-lookup"><span data-stu-id="f3d84-104">Tutorial: Detect anomalies in product sales with ML.NET</span></span>

<span data-ttu-id="f3d84-105">제품 판매 데이터에 대한 변칙 검색 애플리케이션을 빌드하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-105">Learn how to build an anomaly detection application for product sales data.</span></span> <span data-ttu-id="f3d84-106">이 자습서에서는 Visual Studio에서 C#을 사용하여 .NET Core 콘솔 애플리케이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-106">This tutorial creates a .NET Core console application using C# in Visual Studio.</span></span>

<span data-ttu-id="f3d84-107">이 자습서에서는 다음과 같은 작업을 수행하는 방법을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-107">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="f3d84-108">데이터 로드</span><span class="sxs-lookup"><span data-stu-id="f3d84-108">Load the data</span></span>
> * <span data-ttu-id="f3d84-109">급증 변칙 검색에 대한 모델 학습</span><span class="sxs-lookup"><span data-stu-id="f3d84-109">Train the model for spike anomaly detection</span></span>
> * <span data-ttu-id="f3d84-110">학습된 모델로 급증 변칙 검색</span><span class="sxs-lookup"><span data-stu-id="f3d84-110">Detect spike anomalies with the trained model</span></span>
> * <span data-ttu-id="f3d84-111">변화 지점 변칙 검색에 대한 모델 훈련</span><span class="sxs-lookup"><span data-stu-id="f3d84-111">Train the model for change point anomaly detection</span></span>
> * <span data-ttu-id="f3d84-112">학습된 모델로 변화 지점 변칙 검색</span><span class="sxs-lookup"><span data-stu-id="f3d84-112">Detect change point anomalies with the trained model</span></span>

<span data-ttu-id="f3d84-113">[dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/ProductSalesAnomalyDetection) 리포지토리에서 이 자습서의 소스 코드를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-113">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/ProductSalesAnomalyDetection) repository.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f3d84-114">전제 조건</span><span class="sxs-lookup"><span data-stu-id="f3d84-114">Prerequisites</span></span>

* <span data-ttu-id="f3d84-115">“.NET Core 플랫폼 간 개발” 워크로드가 설치된 [Visual Studio 2017 15.6 이상](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019).</span><span class="sxs-lookup"><span data-stu-id="f3d84-115">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) with the ".NET Core cross-platform development" workload installed.</span></span>

* [<span data-ttu-id="f3d84-116">product-sales.csv 데이터 세트</span><span class="sxs-lookup"><span data-stu-id="f3d84-116">The product-sales.csv dataset</span></span>](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/AnomalyDetection_Sales/SpikeDetection/Data/product-sales.csv)

>[!NOTE]
> <span data-ttu-id="f3d84-117">`product-sales.csv`에서 데이터 형식은 “3년간 샴푸 판매량” 데이터 세트(출처: DataMarket, 제공: TSDL(시계열 데이터 라이브러리), 작성: Rob Hyndman)에 기반합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-117">The data format in `product-sales.csv` is based on the dataset “Shampoo Sales Over a Three Year Period” originally sourced from DataMarket and provided by Time Series Data Library (TSDL), created by Rob Hyndman.</span></span> <span data-ttu-id="f3d84-118">"3년간 샴푸 판매량”데이터 세트는 DataMarket 기본 오픈 라이선스 하에 사용이 허가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-118">“Shampoo Sales Over a Three Year Period” Dataset Licensed Under the DataMarket Default Open License.</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="f3d84-119">콘솔 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="f3d84-119">Create a console application</span></span>

1. <span data-ttu-id="f3d84-120">"ProductSalesAnomalyDetection"이라고 하는 **.NET Core 콘솔 애플리케이션**을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-120">Create a **.NET Core Console Application** called "ProductSalesAnomalyDetection".</span></span>

2. <span data-ttu-id="f3d84-121">프로젝트에 이름이 *Data*인 디렉터리를 만들어 데이터 세트 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-121">Create a directory named *Data* in your project to save your data set files.</span></span>

3. <span data-ttu-id="f3d84-122">**Microsoft.ML NuGet 패키지**를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-122">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="f3d84-123">솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **NuGet 패키지 관리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-123">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="f3d84-124">"nuget.org"를 패키지 소스로 선택하고, 찾아보기 탭을 선택하고, **Microsoft.ML**을 검색하고, 목록에서 **v1.0.0** 패키지를 선택하고, **설치** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-124">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select the **v1.0.0** package in the list, and select the **Install** button.</span></span> <span data-ttu-id="f3d84-125">**변경 내용 미리 보기** 대화 상자에서 **확인** 단추를 선택한 다음, 나열된 패키지의 사용 조건에 동의하는 경우 **라이선스 승인** 대화 상자에서 **동의함** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-125">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span> <span data-ttu-id="f3d84-126">**Microsoft.ML.TimeSeries v0.12.0**에 대해 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-126">Repeat these steps for **Microsoft.ML.TimeSeries v0.12.0**.</span></span>

4. <span data-ttu-id="f3d84-127">*Program.cs* 파일 맨 위에 다음 `using` 문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-127">Add the following `using` statements at the top of your *Program.cs* file:</span></span>

    [!code-csharp[AddUsings](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#AddUsings "Add necessary usings")]

### <a name="download-your-data"></a><span data-ttu-id="f3d84-128">데이터 다운로드</span><span class="sxs-lookup"><span data-stu-id="f3d84-128">Download your data</span></span>

1. <span data-ttu-id="f3d84-129">데이터 세트를 다운로드하여 이전에 만든 *Data* 폴더에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-129">Download the dataset and save it to the *Data* folder you previously created:</span></span>

   * <span data-ttu-id="f3d84-130">[*product-sales.csv*](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/AnomalyDetection_Sales/SpikeDetection/Data/product-sales.csv)를 마우스 오른쪽 단추로 클릭하고 "링크(또는 대상)를 다른 이름으로 저장..."을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-130">Right click on [*product-sales.csv*](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/AnomalyDetection_Sales/SpikeDetection/Data/product-sales.csv) and select "Save Link (or Target) As..."</span></span>

     <span data-ttu-id="f3d84-131">\*.csv 파일을 *Data* 폴더에 저장하거나 다른 곳에 저장한 후 \*.csv 파일을 *Data* 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-131">Make sure you either save the \*.csv file to the *Data* folder, or after you save it elsewhere, move the \*.csv file to the *Data* folder.</span></span>

2. <span data-ttu-id="f3d84-132">솔루션 탐색기에서 \*.csv 파일을 마우스 오른쪽 단추로 클릭하고 **속성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-132">In Solution Explorer, right-click the \*.csv file and select **Properties**.</span></span> <span data-ttu-id="f3d84-133">**고급** 아래에서 **출력 디렉터리에 복사** 값을 **변경된 내용만 복사**로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-133">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

<span data-ttu-id="f3d84-134">다음 표는 \*.csv 파일의 데이터 미리 보기입니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-134">The following table is a data preview from your \*.csv file:</span></span>

|<span data-ttu-id="f3d84-135">월</span><span class="sxs-lookup"><span data-stu-id="f3d84-135">Month</span></span>  |<span data-ttu-id="f3d84-136">ProductSales</span><span class="sxs-lookup"><span data-stu-id="f3d84-136">ProductSales</span></span> |
|-------|-------------|
|<span data-ttu-id="f3d84-137">1-Jan</span><span class="sxs-lookup"><span data-stu-id="f3d84-137">1-Jan</span></span>  |    <span data-ttu-id="f3d84-138">271</span><span class="sxs-lookup"><span data-stu-id="f3d84-138">271</span></span>      |
|<span data-ttu-id="f3d84-139">2-Jan</span><span class="sxs-lookup"><span data-stu-id="f3d84-139">2-Jan</span></span>  |    <span data-ttu-id="f3d84-140">150.9</span><span class="sxs-lookup"><span data-stu-id="f3d84-140">150.9</span></span>    |
|<span data-ttu-id="f3d84-141">.....</span><span class="sxs-lookup"><span data-stu-id="f3d84-141">.....</span></span>  |    <span data-ttu-id="f3d84-142">.....</span><span class="sxs-lookup"><span data-stu-id="f3d84-142">.....</span></span>    |
|<span data-ttu-id="f3d84-143">1-Feb</span><span class="sxs-lookup"><span data-stu-id="f3d84-143">1-Feb</span></span>  |    <span data-ttu-id="f3d84-144">199.3</span><span class="sxs-lookup"><span data-stu-id="f3d84-144">199.3</span></span>    |
|<span data-ttu-id="f3d84-145">.....</span><span class="sxs-lookup"><span data-stu-id="f3d84-145">.....</span></span>  |    <span data-ttu-id="f3d84-146">.....</span><span class="sxs-lookup"><span data-stu-id="f3d84-146">.....</span></span>    |

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="f3d84-147">클래스 만들기 및 경로 정의</span><span class="sxs-lookup"><span data-stu-id="f3d84-147">Create classes and define paths</span></span>

<span data-ttu-id="f3d84-148">그런 다음, 입력 클래스 데이터 구조를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-148">Next, define your input class data structure.</span></span>

<span data-ttu-id="f3d84-149">새 클래스를 프로젝트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-149">Add a new class to your project:</span></span>

1. <span data-ttu-id="f3d84-150">**솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭한 다음, **추가 > 새 항목**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-150">In **Solution Explorer**, right-click the project, and then select **Add > New Item**.</span></span>

2. <span data-ttu-id="f3d84-151">**새 항목 추가** 대화 상자에서 **클래스**를 선택하고 **이름** 필드를 *ProductSalesData.cs*로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-151">In the **Add New Item dialog box**, select **Class** and change the **Name** field to *ProductSalesData.cs*.</span></span> <span data-ttu-id="f3d84-152">그런 다음, **추가** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-152">Then, select the **Add** button.</span></span>

<span data-ttu-id="f3d84-153">*ProductSalesData.cs* 파일이 코드 편집기에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-153">The *ProductSalesData.cs* file opens in the code editor.</span></span> <span data-ttu-id="f3d84-154">다음 `using` 문을 *ProductSalesData.cs*의 맨 위에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-154">Add the following `using` statement to the top of *ProductSalesData.cs*:</span></span>

```csharp
using Microsoft.ML.Data;
```

<span data-ttu-id="f3d84-155">기존 클래스 정의를 제거하고 두 개의 클래스 `ProductSalesData` 및 `ProductSalesPrediction`이 있는 다음 코드를 *ProductSalesData.cs* 파일에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-155">Remove the existing class definition and add the following code, which has two classes `ProductSalesData` and `ProductSalesPrediction`, to the *ProductSalesData.cs* file:</span></span>

[!code-csharp[DeclareTypes](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/ProductSalesData.cs#DeclareTypes "Declare data record types")]

<span data-ttu-id="f3d84-156">`ProductSalesData`은 입력 데이터 클래스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-156">`ProductSalesData` specifies an input data class.</span></span> <span data-ttu-id="f3d84-157">[LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29) 특성은 데이터 세트에서 로드해야 하는 열(열 인덱스 기준)을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-157">The [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29) attribute specifies which columns (by column index) in the dataset should be loaded.</span></span> 

<span data-ttu-id="f3d84-158">*Program.cs* 파일 맨 위에 다음 추가 `using` 문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-158">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

[!code-csharp[AddUsings](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#AddUsings "Add necessary usings")]

<span data-ttu-id="f3d84-159">최근에 다운로드한 데이터 세트 파일 경로 및 저장된 모델 파일 경로를 포함할 두 개의 전역 필드를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-159">You need to create two global fields to hold the recently downloaded dataset file path and the saved model file path:</span></span>

* <span data-ttu-id="f3d84-160">`_dataPath`에는 모델을 학습시키는 데 사용되는 데이터 세트의 경로가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-160">`_dataPath` has the path to the dataset used to train the model.</span></span>
* <span data-ttu-id="f3d84-161">`_docsize`에는 데이터 세트 파일의 레코드 수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-161">`_docsize` has the number of records in dataset file.</span></span> <span data-ttu-id="f3d84-162">이 수를 사용하여 `pvalueHistoryLength`를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-162">You'll use this to calculate `pvalueHistoryLength`.</span></span>

<span data-ttu-id="f3d84-163">`Main` 메서드 바로 위의 줄에 다음 코드를 추가하여 해당 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-163">Add the following code to the line right above the `Main` method to specify those paths:</span></span>

[!code-csharp[Declare global variables](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#DeclareGlobalVariables "Declare global variables")]

<span data-ttu-id="f3d84-164">[MLContext 클래스](xref:Microsoft.ML.MLContext)는 모든 ML.NET 작업의 시작점이며, `mlContext`를 초기화하면 모델 생성 워크플로 개체 간에 공유할 수 있는 새 ML.NET 환경이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-164">The [MLContext class](xref:Microsoft.ML.MLContext) is a starting point for all ML.NET operations, and initializing `mlContext` creates a new ML.NET environment that can be shared across the model creation workflow objects.</span></span> <span data-ttu-id="f3d84-165">개념적으로 Entity Framework의 `DBContext`와 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-165">It's similar, conceptually, to `DBContext` in Entity Framework.</span></span>

### <a name="initialize-variables-in-main"></a><span data-ttu-id="f3d84-166">Main에서 변수 초기화</span><span class="sxs-lookup"><span data-stu-id="f3d84-166">Initialize variables in Main</span></span>

<span data-ttu-id="f3d84-167">`Main` 메서드의 `Console.WriteLine("Hello World!")` 줄을 다음 코드로 대체하여 `mlContext` 변수를 선언하고 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-167">Replace the `Console.WriteLine("Hello World!")` line in the `Main` method with the following code to declare and initialize the `mlContext` variable:</span></span>

[!code-csharp[CreateMLContext](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#CreateMLContext "Create the ML Context")]

### <a name="load-the-data"></a><span data-ttu-id="f3d84-168">데이터 로드</span><span class="sxs-lookup"><span data-stu-id="f3d84-168">Load the data</span></span>

<span data-ttu-id="f3d84-169">ML.NET의 데이터는 [IDataView 클래스](xref:Microsoft.ML.IDataView)로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-169">Data in ML.NET is represented as an [IDataView class](xref:Microsoft.ML.IDataView).</span></span> <span data-ttu-id="f3d84-170">`IDataView`는 표 형식 데이터(숫자 및 텍스트)를 유연하고 효율적으로 설명하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-170">`IDataView` is a flexible, efficient way of describing tabular data (numeric and text).</span></span> <span data-ttu-id="f3d84-171">데이터를 텍스트 파일 또는 실시간(예: SQL 데이터베이스 또는 로그 파일)에서 `IDataView` 개체로 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-171">Data can be loaded from a text file or in real time (for example, SQL database or log files) to an `IDataView` object.</span></span> <span data-ttu-id="f3d84-172">아래 코드를 `Main()` 메서드의 다음 줄로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-172">Add the following code as the next line of the `Main()` method:</span></span>

[!code-csharp[LoadData](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#LoadData "loading dataset")]

<span data-ttu-id="f3d84-173">[LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29)은 데이터 스키마를 정의하고 파일에서 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-173">The [LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) defines the data schema and reads in the file.</span></span> <span data-ttu-id="f3d84-174">데이터 경로 변수를 가져와서 `IDataView`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-174">It takes in the data path variables and returns an `IDataView`.</span></span>

## <a name="ml-task---time-series-anomaly-detection"></a><span data-ttu-id="f3d84-175">ML 작업 - 시계열 변칙 검색</span><span class="sxs-lookup"><span data-stu-id="f3d84-175">ML task - time series anomaly detection</span></span> 

<span data-ttu-id="f3d84-176">변칙 검색은 예기치 않거나 비정상적인 이벤트 또는 동작을 플래그합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-176">Anomaly detection flags unexpected or unusual events or behaviors.</span></span> <span data-ttu-id="f3d84-177">문제를 살펴봐야 할 곳에 대한 단서를 제공하고 "이상한가?"라는 질문에 대해 답할 수 있도록 도와줍니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-177">It gives clues where to look for problems and helps you answer the question "Is this weird?".</span></span>

![이상한가](./media/sales-anomaly-detection/anomalydetection.png)

<span data-ttu-id="f3d84-179">변칙 검색은 시계열 데이터의 이상값 즉, 예상치 않거나 “이상한” 동작이 발생한 지정된 시계열의 지점을 검색하는 프로세스로서,</span><span class="sxs-lookup"><span data-stu-id="f3d84-179">Anomaly detection is the process of detecting time-series data outliers; points on a given input time-series where the behavior isn't what was expected, or "weird".</span></span>

<span data-ttu-id="f3d84-180">많은 방식에서 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-180">This can be useful in lots of ways.</span></span> <span data-ttu-id="f3d84-181">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-181">For instance:</span></span>

<span data-ttu-id="f3d84-182">자동차가 있다면 다음 사항을 알고 싶을 것입니다. 이 오일 게이지 판독치가 정상인가? 누유가 있나?</span><span class="sxs-lookup"><span data-stu-id="f3d84-182">If you have a car, you might want to know: Is this oil gauge reading normal, or do I have a leak?</span></span>
<span data-ttu-id="f3d84-183">전력 소비를 모니터링하는 경우 다음 사항을 알고 싶을 것입니다. 정전이 있나?</span><span class="sxs-lookup"><span data-stu-id="f3d84-183">If you're monitoring power consumption, you’d want to know: Is there an outage?</span></span>

<span data-ttu-id="f3d84-184">검색할 수 있는 시간 시계열 변칙에는 다음과 같은 두 종류가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-184">There are two types of time series anomalies that can be detected:</span></span> 

* <span data-ttu-id="f3d84-185">**급증** - 시스템에서 변칙 동작의 일시적인 버스트를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-185">**Spikes** indicate temporary bursts of anomalous behavior in the system.</span></span> 

* <span data-ttu-id="f3d84-186">**변화점** - 시스템에서 시간에 따른 지속적인 변화의 시작점을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-186">**Change points** indicate the beginning of persistent changes over time in the system.</span></span> 

<span data-ttu-id="f3d84-187">ML.NET에서 IID 급증 검색 또는 IID 변화점 검색 알고리즘은 [독립적이고 동일하게 분산된 데이터 세트](https://en.wikipedia.org/wiki/Independent_and_identically_distributed_random_variables)에 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-187">In ML.NET, The IID Spike Detection or IID Change point Detection algorithms are suited for [independent and identically distributed datasets](https://en.wikipedia.org/wiki/Independent_and_identically_distributed_random_variables).</span></span> 

<span data-ttu-id="f3d84-188">급증 및 변화점을 검색하기 위해 동일한 제품 판매 데이터를 분석할 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-188">You'll analyze the same product sales data to detect spikes and change points.</span></span> <span data-ttu-id="f3d84-189">모델 빌드 및 학습 프로세스는 급증 검색과 변화점 검색에 동일하지만, 특정 검색 알고리즘이 사용된다는 기본적인 차이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-189">The building and training model process is the same for spike detection and change point detection; the main difference is the specific detection algorithm used.</span></span>

## <a name="spike-detection"></a><span data-ttu-id="f3d84-190">급증 검색</span><span class="sxs-lookup"><span data-stu-id="f3d84-190">Spike detection</span></span> 

<span data-ttu-id="f3d84-191">스파이크 검색의 목표는 대다수의 시계열 데이터 값과는 상당히 다른 갑작스럽지만 일시적인 버스트를 식별하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-191">The goal of spike detection is to identify sudden yet temporary bursts that significantly differ from the majority of the time series data values.</span></span> <span data-ttu-id="f3d84-192">시기적절하게 이러한 의심스러운 드문 항목, 이벤트 또는 관찰 사항을 검색하여 최소화하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-192">It's important to detect these suspicious rare items, events or observations in a timely manner to be minimized.</span></span> <span data-ttu-id="f3d84-193">정전, 사이버 공격 또는 바이러스성 웹 콘텐츠 등의 다양한 변칙을 검색하기 위해 다음과 같은 접근 방식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-193">The following approach can be used to detect a variety of anomalies such as: outages, cyber-attacks, or viral web content.</span></span> <span data-ttu-id="f3d84-194">다음 이미지는 시계열 데이터 세트에서 급증의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-194">The following image is an example of spikes in a time series dataset:</span></span>

![SpikeDetection](./media/sales-anomaly-detection/SpikeDetection.png)

### <a name="create-the-detectspike-method"></a><span data-ttu-id="f3d84-196">DetectSpike() 메서드 만들기</span><span class="sxs-lookup"><span data-stu-id="f3d84-196">Create the DetectSpike() method</span></span>

<span data-ttu-id="f3d84-197">`DetectSpike()` 메서드에 다음 호출을 `Main()` 메서드의 다음 코드 줄로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-197">Add the following call to the `DetectSpike()`method as the next line of code in the `Main()` method:</span></span>

[!code-csharp[CallDetectSpike](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#CallDetectSpike)]

<span data-ttu-id="f3d84-198">`DetectSpike()` 메서드는 다음 작업을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-198">The `DetectSpike()` method executes the following tasks:</span></span>

* <span data-ttu-id="f3d84-199">모델을 학습시킵니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-199">Trains the model.</span></span>
* <span data-ttu-id="f3d84-200">판매 기록 데이터를 기준으로 급증을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-200">Detects spikes based on historical sales data.</span></span>
* <span data-ttu-id="f3d84-201">결과를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-201">Displays the results.</span></span>

<span data-ttu-id="f3d84-202">다음 코드를 사용하여 `Main()` 메서드 바로 뒤에 `DetectSpike()` 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-202">Create the `DetectSpike()` method, just after the `Main()` method, using the following code:</span></span>

```csharp
static void DetectSpike(MLContext mlContext, int docSize, IDataView productSales)
{

}
```

<span data-ttu-id="f3d84-203">[IidSpikeEstimator](xref:Microsoft.ML.Transforms.TimeSeries.IidSpikeEstimator)를 사용하여 급증 검색에 대한 모델을 학습합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-203">Use the [IidSpikeEstimator](xref:Microsoft.ML.Transforms.TimeSeries.IidSpikeEstimator) to train the model for spike detection.</span></span> <span data-ttu-id="f3d84-204">다음 코드를 사용하여 `DetectSpike()` 메서드에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-204">Add it to the `DetectSpike()` method with the following code:</span></span>

[!code-csharp[AddSpikeTrainer](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#AddSpikeTrainer)]

<span data-ttu-id="f3d84-205">`DetectSpike()` 메서드에서 다음 코드 줄로 다음 항목을 추가하여 모델을 `productSales` 데이터에 맞춥니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-205">Fit the model to the `productSales` data by adding the following as the next line of code in the `DetectSpike()` method:</span></span>

[!code-csharp[TrainModel1](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#TrainModel1)]

<span data-ttu-id="f3d84-206">[Fit()](xref:Microsoft.ML.Data.TrivialEstimator%601.Fit%2A) 메서드는 데이터 세트를 변환하고 학습을 적용하여 모델을 학습합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-206">The [Fit()](xref:Microsoft.ML.Data.TrivialEstimator%601.Fit%2A) method trains your model by transforming the dataset and applying the training.</span></span>

<span data-ttu-id="f3d84-207">다음 코드 줄을 추가하여 `productSales` 데이터를 `DetectSpike()` 메서드에서 다음 줄로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-207">Add the following line of code to transform the `productSales` data as the next line in the `DetectSpike()` method:</span></span>

[!code-csharp[TransformData1](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#TransformData1)]

<span data-ttu-id="f3d84-208">이전 코드는 [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) 메서드를 사용하여 여러 제공된 테스트 데이터 세트 입력 행에 대한 예측을 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-208">The previous code uses the [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) method to make predictions for multiple provided input rows of a test dataset.</span></span>

<span data-ttu-id="f3d84-209">`transformedData`를 다음 코드로 [CreateEnumerable()](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable%2A) 메서드를 사용하여 쉽게 표시하도록 강력한 형식의 `IEnumerable`로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-209">Convert your `transformedData` into a strongly-typed `IEnumerable` for easier display using the [CreateEnumerable()](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable%2A) method with the following code:</span></span>

[!code-csharp[CreateEnumerable1](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#CreateEnumerable1)]

<span data-ttu-id="f3d84-210">다음 <xref:System.Console.WriteLine?displayProperty=nameWithType> 코드를 사용하여 표시 헤더 줄을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-210">Create a display header line using the following <xref:System.Console.WriteLine?displayProperty=nameWithType> code:</span></span>

[!code-csharp[DisplayHeader1](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#DisplayHeader1)]

<span data-ttu-id="f3d84-211">급증 검색 결과에서 다음 정보를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-211">You'll display the following information in your spike detection results:</span></span>

* <span data-ttu-id="f3d84-212">`Alert` - 지정된 데이터 요소에 대한 급증 경고를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-212">`Alert` indicates a spike alert for a given data point.</span></span>

* <span data-ttu-id="f3d84-213">`Score` - 데이터 세트에서 지정된 데이터 요소에 대한 `ProductSales` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-213">`Score` is the `ProductSales` value for a given data point in the dataset.</span></span>

* <span data-ttu-id="f3d84-214">`P-Value` "P"는 확률을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-214">`P-Value` The "P" stands for probability.</span></span> <span data-ttu-id="f3d84-215">이 데이터 요소가 변칙일 가능성을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-215">This indicates how likely this data point is an anomaly.</span></span> 

<span data-ttu-id="f3d84-216">다음 코드를 사용하여 `predictions` `IEnumerable`을 반복하고 결과를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-216">Use the following code to iterate through the `predictions` `IEnumerable` and display the results:</span></span>

[!code-csharp[DisplayResults1](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#DisplayResults1)]

## <a name="spike-detection-results"></a><span data-ttu-id="f3d84-217">급증 검색 결과</span><span class="sxs-lookup"><span data-stu-id="f3d84-217">Spike detection results</span></span>

<span data-ttu-id="f3d84-218">다음과 같은 결과가 나타나야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-218">Your results should be similar to the following.</span></span> <span data-ttu-id="f3d84-219">처리 중 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-219">During processing, messages are displayed.</span></span> <span data-ttu-id="f3d84-220">경고 또는 메시지 처리를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-220">You may see warnings, or processing messages.</span></span> <span data-ttu-id="f3d84-221">이해하기 쉽도록 이러한 결과는 다음 결과에서 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-221">These have been removed from the following results for clarity.</span></span>

```console
Detect temporary changes in pattern
=============== Training the model ===============
=============== End of training process ===============
Alert   Score   P-Value
0       271.00  0.50
0       150.90  0.00
0       188.10  0.41
0       124.30  0.13
0       185.30  0.47
0       173.50  0.47
0       236.80  0.19
0       229.50  0.27
0       197.80  0.48
0       127.90  0.13
1       341.50  0.00 <-- Spike detected
0       190.90  0.48
0       199.30  0.48
0       154.50  0.24
0       215.10  0.42
0       278.30  0.19
0       196.40  0.43
0       292.00  0.17
0       231.00  0.45
0       308.60  0.18
0       294.90  0.19
1       426.60  0.00 <-- Spike detected
0       269.50  0.47
0       347.30  0.21
0       344.70  0.27
0       445.40  0.06
0       320.90  0.49
0       444.30  0.12
0       406.30  0.29
0       442.40  0.21
1       580.50  0.00 <-- Spike detected
0       412.60  0.45
1       687.00  0.01 <-- Spike detected
0       480.30  0.40
0       586.30  0.20
0       651.90  0.14
```

## <a name="change-point-detection"></a><span data-ttu-id="f3d84-222">변화점 검색</span><span class="sxs-lookup"><span data-stu-id="f3d84-222">Change point detection</span></span>

<span data-ttu-id="f3d84-223">`Change points`은 수치 변화 및 추세와 같은 값의 시계열 이벤트 스트림 분산에서 지속적인 변화입니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-223">`Change points` are persistent changes in a time series event stream distribution of values, like level changes and trends.</span></span> <span data-ttu-id="f3d84-224">이러한 지속적인 변화는 `spikes`보다 훨씬 오래 지속되며 심각한 이벤트를 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-224">These persistent changes last much longer than `spikes` and could indicate catastrophic event(s).</span></span> <span data-ttu-id="f3d84-225">`Change points`는 보통 육안으로는 보이지 않지만, 다음 메서드에서와 같은 접근법을 사용하여 데이터에서 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-225">`Change points` are not usually visible to the naked eye, but can be detected in your data using approaches such as in the following method.</span></span>  <span data-ttu-id="f3d84-226">다음 이미지는 변화점 검색의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-226">The following image is an example of a change point detection:</span></span>

![ChangePointDetection](./media/sales-anomaly-detection/ChangePointDetection.png)

### <a name="create-the-detectchangepoint-method"></a><span data-ttu-id="f3d84-228">DetectChangepoint() 메서드 만들기</span><span class="sxs-lookup"><span data-stu-id="f3d84-228">Create the DetectChangepoint() method</span></span>

<span data-ttu-id="f3d84-229">`DetectChangepoint()` 메서드에 다음 호출을 `Main()` 메서드의 다음 코드 줄로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-229">Add the following call to the `DetectChangepoint()`method as the next line of code in the `Main()` method:</span></span>

[!code-csharp[CallDetectChangepoint](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#CallDetectChangepoint)]

<span data-ttu-id="f3d84-230">`DetectChangepoint()` 메서드는 다음 작업을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-230">The `DetectChangepoint()` method executes the following tasks:</span></span>

* <span data-ttu-id="f3d84-231">모델을 학습시킵니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-231">Trains the model.</span></span>
* <span data-ttu-id="f3d84-232">판매 내역 데이터에 기반하여 변화점을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-232">Detects change points based on historical sales data.</span></span>
* <span data-ttu-id="f3d84-233">결과를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-233">Displays the results.</span></span>

<span data-ttu-id="f3d84-234">다음 코드를 사용하여 `Main()` 메서드 바로 뒤에 `DetectChangepoint()` 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-234">Create the `DetectChangepoint()` method, just after the `Main()` method, using the following code:</span></span>

```csharp
static void DetectChangepoint(MLContext mlContext, int docSize, IDataView productSales)
{

}
```

<span data-ttu-id="f3d84-235">[iidChangePointEstimator](xref:Microsoft.ML.Transforms.TimeSeries.IidChangePointEstimator)는 변화점 검색에 대한 모델을 학습하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-235">The [iidChangePointEstimator](xref:Microsoft.ML.Transforms.TimeSeries.IidChangePointEstimator) is used to train the model for change point detection.</span></span> <span data-ttu-id="f3d84-236">다음 코드를 사용하여 `DetectChangepoint()` 메서드에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-236">Add it to the `DetectChangepoint()` method with the following code:</span></span>

[!code-csharp[AddChangepointTrainer](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#AddChangepointTrainer)]

<span data-ttu-id="f3d84-237">이전에 했던 것처럼 `DetectChangePoint()` 메서드에서 다음 코드 줄로 다음 항목을 추가하여 모델을 `productSales` 데이터에 맞춥니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-237">As you did previously, fit the model to the `productSales` data by adding the following as the next line of code in the `DetectChangePoint()` method:</span></span>

[!code-csharp[TrainModel2](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#TrainModel2)]

<span data-ttu-id="f3d84-238">`Transform()` 메서드를 사용하여 `DetectChangePoint()`에 다음 코드를 추가하여 `Training` 데이터를 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-238">Use the `Transform()` method to transform the `Training` data by adding the following code to `DetectChangePoint()`:</span></span>

[!code-csharp[TransformData2](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#TransformData2)]

<span data-ttu-id="f3d84-239">이전에 했던 것처럼, `transformedData`를 다음 코드로 `CreateEnumerable()` 메서드를 사용하여 쉽게 표시하도록 강력한 형식의 `IEnumerable`로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-239">As you did previously, convert your `transformedData` into a strongly-typed `IEnumerable` for easier display using the `CreateEnumerable()`method with the following code:</span></span>

[!code-csharp[CreateEnumerable2](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#CreateEnumerable2)]

<span data-ttu-id="f3d84-240">`DetectChangePoint()` 메서드에 아래 코드를 사용하여 표시 헤더를 다음 줄로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-240">Create a display header with the following code as the next line in the `DetectChangePoint()` method:</span></span>

[!code-csharp[DisplayHeader2](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#DisplayHeader2)]

<span data-ttu-id="f3d84-241">변화점 검색 결과에서 다음 정보를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-241">You'll display the following information in your change point detection results:</span></span>

* <span data-ttu-id="f3d84-242">`Alert` - 지정된 데이터 요소에 대한 변화점 경고를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-242">`Alert` indicates a change point alert for a given data point.</span></span>
* <span data-ttu-id="f3d84-243">`Score` - 데이터 세트에서 지정된 데이터 요소에 대한 `ProductSales` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-243">`Score` is the `ProductSales` value for a given data point in the dataset.</span></span>
* <span data-ttu-id="f3d84-244">`P-Value` "P"는 확률을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-244">`P-Value` The "P" stands for probability.</span></span> <span data-ttu-id="f3d84-245">이 데이터 요소가 변칙일 가능성을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-245">This indicates how likely this data point is an anomaly.</span></span> 
* <span data-ttu-id="f3d84-246">`Martingale value`는 P 값의 시퀀스에 기반하여 데이터 요소의 “이상한” 정도를 식별하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-246">`Martingale value` is used to identify how "weird" a data point is, based on the sequence of P-values.</span></span>  

<span data-ttu-id="f3d84-247">다음 코드를 사용하여 `predictions` `IEnumerable`을 반복하고 결과를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-247">Iterate through the `predictions` `IEnumerable` and display the results with the following code:</span></span>

[!code-csharp[DisplayResults2](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#DisplayResults2)]

## <a name="change-point-detection-results"></a><span data-ttu-id="f3d84-248">변화점 검색 결과</span><span class="sxs-lookup"><span data-stu-id="f3d84-248">Change point detection results</span></span>

<span data-ttu-id="f3d84-249">다음과 같은 결과가 나타나야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-249">Your results should be similar to the following.</span></span> <span data-ttu-id="f3d84-250">처리 중 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-250">During processing, messages are displayed.</span></span> <span data-ttu-id="f3d84-251">경고 또는 메시지 처리를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-251">You may see warnings, or processing messages.</span></span> <span data-ttu-id="f3d84-252">이해하기 쉽도록 이러한 결과는 다음 결과에서 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-252">These have been removed from the following results for clarity.</span></span>

```console
Detect Persistent changes in pattern
=============== Training the model Using Change Point Detection Algorithm===============
=============== End of training process ===============
Alert   Score   P-Value Martingale value
0       271.00  0.50    0.00
0       150.90  0.00    2.33
0       188.10  0.41    2.80
0       124.30  0.13    9.16
0       185.30  0.47    9.77
0       173.50  0.47    10.41
0       236.80  0.19    24.46
0       229.50  0.27    42.38
1       197.80  0.48    44.23 <-- alert is on, predicted changepoint
0       127.90  0.13    145.25
0       341.50  0.00    0.01
0       190.90  0.48    0.01
0       199.30  0.48    0.00
0       154.50  0.24    0.00
0       215.10  0.42    0.00
0       278.30  0.19    0.00
0       196.40  0.43    0.00
0       292.00  0.17    0.01
0       231.00  0.45    0.00
0       308.60  0.18    0.00
0       294.90  0.19    0.00
0       426.60  0.00    0.00
0       269.50  0.47    0.00
0       347.30  0.21    0.00
0       344.70  0.27    0.00
0       445.40  0.06    0.02
0       320.90  0.49    0.01
0       444.30  0.12    0.02
0       406.30  0.29    0.01
0       442.40  0.21    0.01
0       580.50  0.00    0.01
0       412.60  0.45    0.01
0       687.00  0.01    0.12
0       480.30  0.40    0.08
0       586.30  0.20    0.03
0       651.90  0.14    0.09
```

<span data-ttu-id="f3d84-253">지금까지</span><span class="sxs-lookup"><span data-stu-id="f3d84-253">Congratulations!</span></span> <span data-ttu-id="f3d84-254">이제 판매 데이터에서 급증 및 변화점 변칙을 검색하기 위한 기계 학습 모델을 성공적으로 빌드했습니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-254">You've now successfully built machine learning models for detecting spikes and change point anomalies in sales data.</span></span>

<span data-ttu-id="f3d84-255">[dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/ProductSalesAnomalyDetection) 리포지토리에서 이 자습서의 소스 코드를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-255">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/ProductSalesAnomalyDetection) repository.</span></span>

<span data-ttu-id="f3d84-256">본 자습서에서는 다음 작업에 관한 방법을 학습했습니다.</span><span class="sxs-lookup"><span data-stu-id="f3d84-256">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="f3d84-257">데이터 로드</span><span class="sxs-lookup"><span data-stu-id="f3d84-257">Load the data</span></span>
> * <span data-ttu-id="f3d84-258">급증 변칙 검색에 대한 모델 학습</span><span class="sxs-lookup"><span data-stu-id="f3d84-258">Train the model for spike anomaly detection</span></span>
> * <span data-ttu-id="f3d84-259">학습된 모델로 급증 변칙 검색</span><span class="sxs-lookup"><span data-stu-id="f3d84-259">Detect spike anomalies with the trained model</span></span>
> * <span data-ttu-id="f3d84-260">변화 지점 변칙 검색에 대한 모델 학습</span><span class="sxs-lookup"><span data-stu-id="f3d84-260">Train the model for change point anomaly detection</span></span>
> * <span data-ttu-id="f3d84-261">학습된 모델로 변화점 변칙 검색</span><span class="sxs-lookup"><span data-stu-id="f3d84-261">Detect change point anomalies with the trained mode</span></span>

## <a name="next-steps"></a><span data-ttu-id="f3d84-262">다음 단계</span><span class="sxs-lookup"><span data-stu-id="f3d84-262">Next steps</span></span>

<span data-ttu-id="f3d84-263">Machine Learning 샘플 GitHub 리포지토리를 확인하여 전력 소비 변칙 검색 샘플을 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="f3d84-263">Check out the Machine Learning samples GitHub repository to explore a Power Consumption Anomaly Detection sample.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="f3d84-264">dotnet/machinelearning-samples GitHub 리포지토리</span><span class="sxs-lookup"><span data-stu-id="f3d84-264">dotnet/machinelearning-samples GitHub repository</span></span>](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/AnomalyDetection_PowerMeterReadings)
