---
title: .NET for Apache Spark 및 ML.NET을 사용한 감정 분석 자습서
description: 이 자습서에서는 감정 분석을 위해 .NET for Apache Spark와 함께 ML.NET을 사용하는 방법을 알아봅니다.
author: mamccrea
ms.author: mamccrea
ms.date: 10/09/2020
ms.topic: tutorial
ms.openlocfilehash: 16b4d34e4c581da2cd0ba798d87e53ccfc49f0e9
ms.sourcegitcommit: b59237ca4ec763969a0dd775a3f8f39f8c59fe24
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2020
ms.locfileid: "91954895"
---
# <a name="tutorial-sentiment-analysis-with-net-for-apache-spark-and-mlnet"></a><span data-ttu-id="449c7-103">자습서: .NET for Apache Spark 및 ML.NET을 사용한 감정 분석</span><span class="sxs-lookup"><span data-stu-id="449c7-103">Tutorial: Sentiment analysis with .NET for Apache Spark and ML.NET</span></span>

<span data-ttu-id="449c7-104">이 자습서에서는 ML.NET 및 .NET for Apache Spark를 사용하여 온라인 리뷰에 대한 감정 분석을 수행하는 방법을 배웁니다.</span><span class="sxs-lookup"><span data-stu-id="449c7-104">This tutorial teaches you how to do sentiment analysis of online reviews using ML.NET and .NET for Apache Spark.</span></span> <span data-ttu-id="449c7-105">[ML.NET](http://dot.net/ml)은 무료 플랫폼 간 오픈 소스 기계 학습 프레임워크입니다.</span><span class="sxs-lookup"><span data-stu-id="449c7-105">[ML.NET](http://dot.net/ml) is a free, cross-platform, open-source machine learning framework.</span></span> <span data-ttu-id="449c7-106">ML.NET을 .NET for Apache Spark와 함께 사용하여 기계 학습 알고리즘의 학습 및 예측을 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="449c7-106">You can use ML.NET with .NET for Apache Spark to scale the training and prediction of machine learning algorithms.</span></span>

<span data-ttu-id="449c7-107">이 자습서에서는 다음과 같은 작업을 수행하는 방법을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="449c7-107">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="449c7-108">Visual Studio에서 ML.NET 모델 작성기를 사용하여 감정 분석 모델을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="449c7-108">Create a sentiment analysis model using ML.NET Model Builder in Visual Studio.</span></span>
> * <span data-ttu-id="449c7-109">.NET for Apache Spark 콘솔 앱을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="449c7-109">Create a .NET for Apache Spark console app.</span></span>
> * <span data-ttu-id="449c7-110">사용자 정의 함수를 작성하고 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="449c7-110">Write and implement a user-defined function.</span></span>
> * <span data-ttu-id="449c7-111">.NET for Apache Spark 콘솔 앱을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="449c7-111">Run a .NET for Apache Spark console app.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="449c7-112">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="449c7-112">Prerequisites</span></span>

* <span data-ttu-id="449c7-113">.NET for Apache Spark 애플리케이션을 개발한 적이 없다면 [자습서 시작](get-started.md)부터 시작하여 기본 사항을 숙지하세요.</span><span class="sxs-lookup"><span data-stu-id="449c7-113">If you haven't developed a .NET for Apache Spark application before, start with the [Getting Started tutorial](get-started.md) to become familiar with the basics.</span></span> <span data-ttu-id="449c7-114">이 자습서를 계속 진행하기 전에 시작 자습서에 대한 모든 필수 구성 요소를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="449c7-114">Complete all of the prerequisites for the Getting Started tutorial before you continue with this tutorial.</span></span>

* <span data-ttu-id="449c7-115">이 자습서에서는 Visual Studio에서 사용할 수 있는 시각적 인터페이스인 ML.NET 모델 작성기(미리 보기)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="449c7-115">This tutorial uses the ML.NET Model Builder (preview), a visual interface available in Visual Studio.</span></span> <span data-ttu-id="449c7-116">Visual Studio가 아직 없는 경우 [Visual Studio의 Community 버전을 무료로 다운로드](https://visualstudio.microsoft.com/downloads/)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="449c7-116">If you don't already have Visual Studio, you can [download the Community version of Visual Studio](https://visualstudio.microsoft.com/downloads/) for free.</span></span>

* <span data-ttu-id="449c7-117">ML.NET 모델 작성기(미리 보기)를 [다운로드 및 설치](https://marketplace.visualstudio.com/items?itemName=MLNET.07)합니다.</span><span class="sxs-lookup"><span data-stu-id="449c7-117">[Download and install](https://marketplace.visualstudio.com/items?itemName=MLNET.07) ML.NET Model Builder (preview).</span></span>

* <span data-ttu-id="449c7-118">[yelptest.csv](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/MachineLearning/Sentiment/Resources/yelptest.csv) 및 [yelptrain.csv](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/MachineLearning/Sentiment/Resources/yelptrain.csv) 리뷰 데이터 세트를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="449c7-118">Download the [yelptest.csv](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/MachineLearning/Sentiment/Resources/yelptest.csv) and [yelptrain.csv](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/MachineLearning/Sentiment/Resources/yelptrain.csv) Yelp review datasets.</span></span>

## <a name="review-the-data"></a><span data-ttu-id="449c7-119">데이터 검토</span><span class="sxs-lookup"><span data-stu-id="449c7-119">Review the data</span></span>

<span data-ttu-id="449c7-120">Yelp 리뷰 데이터 세트는 다양한 서비스에 대한 온라인 Yelp 리뷰를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="449c7-120">The Yelp reviews dataset contains online Yelp reviews about various services.</span></span> <span data-ttu-id="449c7-121">[yelptrain.csv](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/MachineLearning/Sentiment/Resources/yelptrain.csv)를 열고 데이터 구조를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="449c7-121">Open [yelptrain.csv](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/MachineLearning/Sentiment/Resources/yelptrain.csv) and notice the structure of the data.</span></span> <span data-ttu-id="449c7-122">첫 번째 열에는 리뷰 텍스트가 포함되고 두 번째 열에는 감정 점수가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="449c7-122">The first column contains review text, and the second column contains sentiment scores.</span></span> <span data-ttu-id="449c7-123">감정 점수가 1이면 리뷰는 긍정적이고 감정 점수가 0이면 리뷰는 부정적입니다.</span><span class="sxs-lookup"><span data-stu-id="449c7-123">If the sentiment score is 1, the review is positive, and if the sentiment score is 0, the review is negative.</span></span>

<span data-ttu-id="449c7-124">다음 표는 샘플 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="449c7-124">The following table contains sample data:</span></span>

|<span data-ttu-id="449c7-125">ReviewText</span><span class="sxs-lookup"><span data-stu-id="449c7-125">ReviewText</span></span>|<span data-ttu-id="449c7-126">감정</span><span class="sxs-lookup"><span data-stu-id="449c7-126">Sentiment</span></span>|
|-|-|
|<span data-ttu-id="449c7-127">우와... 여기가 좋았습니다.</span><span class="sxs-lookup"><span data-stu-id="449c7-127">Wow... Loved this place.</span></span>|    <span data-ttu-id="449c7-128">1</span><span class="sxs-lookup"><span data-stu-id="449c7-128">1</span></span>|
|<span data-ttu-id="449c7-129">크러스트가 좋지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="449c7-129">Crust is not good.</span></span>|    <span data-ttu-id="449c7-130">0</span><span class="sxs-lookup"><span data-stu-id="449c7-130">0</span></span>|

## <a name="build-your-machine-learning-model"></a><span data-ttu-id="449c7-131">기계 학습 모델 빌드</span><span class="sxs-lookup"><span data-stu-id="449c7-131">Build your machine learning model</span></span>

1. <span data-ttu-id="449c7-132">Visual Studio를 열고 새 C# 콘솔 앱(.NET Core)을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="449c7-132">Open Visual Studio and create a new C# Console App (.NET Core).</span></span> <span data-ttu-id="449c7-133">프로젝트 이름을 *MLSparkModel*로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="449c7-133">Name the project *MLSparkModel*.</span></span>

1. <span data-ttu-id="449c7-134">**솔루션 탐색기**에서 *MLSparkModel* 프로젝트를 마우스 오른쪽 단추로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="449c7-134">In **Solution Explorer**, right-click the *MLSparkModel* project.</span></span> <span data-ttu-id="449c7-135">그런 다음 **추가 > Machine Learning**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="449c7-135">Then select **Add > Machine Learning**.</span></span>

1. <span data-ttu-id="449c7-136">ML.NET 모델 작성기에서 **감정 분석** 시나리오 타일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="449c7-136">From the ML.NET Model Builder, select the **Sentiment Analysis** scenario tile.</span></span>

1. <span data-ttu-id="449c7-137">**데이터 추가** 페이지에서 *yelptrain.csv* 데이터 세트를 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="449c7-137">On the **Add data** page, upload the *yelptrain.csv* data set.</span></span>

1. <span data-ttu-id="449c7-138">**예측할 열** 드롭다운에서 *감정*을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="449c7-138">Choose *Sentiment* from the **Columns to Predict** dropdown.</span></span>

1. <span data-ttu-id="449c7-139">**학습** 페이지에서 학습 시간을 *60초*로 설정하고 **학습 시작**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="449c7-139">On the **Train** page, set the time to train to *60 seconds* and select **Start training**.</span></span> <span data-ttu-id="449c7-140">**진행률**에서 학습 상태를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="449c7-140">Notice the status of your training under **Progress**.</span></span>

1. <span data-ttu-id="449c7-141">모델 작성기가 학습을 완료하면 학습 결과를 **평가**합니다.</span><span class="sxs-lookup"><span data-stu-id="449c7-141">Once Model Builder is finished training, **Evaluate** the training results.</span></span> <span data-ttu-id="449c7-142">**모델 테스트** 아래 텍스트 상자에 구를 입력하고 **예측**을 선택하여 출력을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="449c7-142">You can type phrases into the text box below **Try your model** and select **Predict** to see the output.</span></span>

1. <span data-ttu-id="449c7-143">**코드**를 선택한 다음 **프로젝트 추가**를 선택하여 ML 모델을 솔루션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="449c7-143">Select **Code** and then select **Add Projects** to add the ML model to the solution.</span></span>

1. <span data-ttu-id="449c7-144">다음 두 프로젝트가 솔루션에 추가됩니다. **MLSparkModelML.ConsoleApp** 및 **MLSparkModelML.Model**.</span><span class="sxs-lookup"><span data-stu-id="449c7-144">Notice that two projects are added to your solutions: **MLSparkModelML.ConsoleApp** and **MLSparkModelML.Model**.</span></span>

1. <span data-ttu-id="449c7-145">*MLSpark* C# 프로젝트를 두 번 클릭하면 다음 프로젝트 참조가 추가된 것을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="449c7-145">Double-click on your *MLSpark* C# project and notice that the following project reference has been added.</span></span>

   ```xml
   <ItemGroup>
       <ProjectReference Include="..\MLSparkModelML.Model\MLSparkModelML.Model.csproj" />
   </ItemGroup>
   ```

## <a name="create-a-console-app"></a><span data-ttu-id="449c7-146">콘솔 앱 만들기</span><span class="sxs-lookup"><span data-stu-id="449c7-146">Create a console app</span></span>

<span data-ttu-id="449c7-147">모델 작성기는 콘솔 앱을 자동으로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="449c7-147">Model Builder creates a console app for you.</span></span>

1. <span data-ttu-id="449c7-148">솔루션 탐색기에서 **MLSparkModelML**을 마우스 오른쪽 단추로 클릭하고 **NuGet 패키지 관리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="449c7-148">Right-click on **MLSparkModelML.Console** in Solution Explorer, and select **Manage NuGet Packages**.</span></span>

1. <span data-ttu-id="449c7-149">**Microsoft.Spark**를 검색하여 패키지를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="449c7-149">Search for **Microsoft.Spark** and install the package.</span></span> <span data-ttu-id="449c7-150">**Microsoft.ML**은 모델 작성기에 의해 자동으로 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="449c7-150">**Microsoft.ML** is automatically installed for you by Model Builder.</span></span>

### <a name="create-a-sparksession"></a><span data-ttu-id="449c7-151">SparkSession 만들기</span><span class="sxs-lookup"><span data-stu-id="449c7-151">Create a SparkSession</span></span>

1. <span data-ttu-id="449c7-152">**MLSparkModelML.ConsoleApp**에 대한 *Program.cs* 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="449c7-152">Open the *Program.cs* file for **MLSparkModelML.ConsoleApp**.</span></span> <span data-ttu-id="449c7-153">이 파일은 모델 작성기가 자동으로 생성한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="449c7-153">This file was autogenerated by Model Builder.</span></span> <span data-ttu-id="449c7-154">`using` 문, Main() 메서드의 내용 및 `CreateSingleDataSample` 영역을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="449c7-154">Delete the `using` statements, the contents of the Main() method, and the `CreateSingleDataSample` region.</span></span>

1. <span data-ttu-id="449c7-155">*Program.cs*의 맨 위에 다음 `using` 문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="449c7-155">Add the following additional `using` statements to the top of the *Program.cs*:</span></span>

   ```csharp
   using System;
   using System.Collections.Generic;
   using Microsoft.ML;
   using Microsoft.ML.Data;
   using Microsoft.Spark.Sql;
   using MLSparkModelML.Model;
   ```

1. <span data-ttu-id="449c7-156">`DATA_FILEPATH`를 *yelptest.csv*의 경로로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="449c7-156">Change the `DATA_FILEPATH` to the path of your *yelptest.csv*.</span></span>

1. <span data-ttu-id="449c7-157">`Main` 메서드에 다음 코드를 추가하여 새 `SparkSession`을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="449c7-157">Add the following code to your `Main` method to create a new `SparkSession`.</span></span> <span data-ttu-id="449c7-158">Spark 세션은 Dataset 및 DataFrame API를 사용하여 Spark를 프로그래밍하기 위한 진입점입니다.</span><span class="sxs-lookup"><span data-stu-id="449c7-158">The Spark Session is the entry point to programming Spark with the Dataset and DataFrame API.</span></span>

   ```csharp
   SparkSession spark = SparkSession
        .Builder()
        .AppName(".NET for Apache Spark Sentiment Analysis")
        .GetOrCreate();
   ```

   <span data-ttu-id="449c7-159">위에서 만든 *spark* 개체를 호출하면 프로그램 전체에서 Spark 및 DataFrame 기능에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="449c7-159">Calling the *spark* object created above allows you to access Spark and DataFrame functionality throughout your program.</span></span>

### <a name="create-a-dataframe-and-print-to-console"></a><span data-ttu-id="449c7-160">데이터 프레임을 만들고 콘솔에 인쇄</span><span class="sxs-lookup"><span data-stu-id="449c7-160">Create a DataFrame and print to console</span></span>

<span data-ttu-id="449c7-161">*yelptest.csv* 파일에서 `DataFrame`으로 Yelp 리뷰 데이터를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="449c7-161">Read in the Yelp review data from the *yelptest.csv* file as a `DataFrame`.</span></span> <span data-ttu-id="449c7-162">`header` 및 `inferSchema` 옵션을 포함시킵니다.</span><span class="sxs-lookup"><span data-stu-id="449c7-162">Include `header` and `inferSchema` options.</span></span> <span data-ttu-id="449c7-163">`header` 옵션은 *yelptest.csv*의 첫 번째 줄을 데이터가 아니라 열 이름으로 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="449c7-163">The `header` option reads the first line of *yelptest.csv* as column names instead of data.</span></span> <span data-ttu-id="449c7-164">`inferSchema` 옵션은 데이터를 기반으로 열 형식을 유추합니다.</span><span class="sxs-lookup"><span data-stu-id="449c7-164">The `inferSchema` option infers column types based on the data.</span></span>

```csharp
DataFrame df = spark
    .ReadStream()
    .Option("header", true)
    .Option("inferSchema", true)
    .Csv(DATA_FILEPATH);

df.Show();
```

### <a name="register-a-user-defined-function"></a><span data-ttu-id="449c7-165">사용자 정의 함수 등록</span><span class="sxs-lookup"><span data-stu-id="449c7-165">Register a user-defined function</span></span>

<span data-ttu-id="449c7-166">Spark 애플리케이션에서 *UDF(사용자 정의 함수)* 를 사용하여 데이터에 대한 계산 및 분석을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="449c7-166">You can use UDFs, *user-defined functions*, in Spark applications to do calculations and analysis on your data.</span></span> <span data-ttu-id="449c7-167">이 자습서에서는 ML.NET을 UDF와 함께 사용하여 각 Yelp 리뷰를 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="449c7-167">In this tutorial, you use ML.NET with a UDF to evaluate each Yelp review.</span></span>

<span data-ttu-id="449c7-168">`Main` 메서드에 다음 코드를 추가하여 `MLudf`라는 UDF를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="449c7-168">Add the following code to your `Main` method to register a UDF called `MLudf`.</span></span>

```csharp
spark.Udf()
    .Register<string, bool>("MLudf", predict);
```

<span data-ttu-id="449c7-169">이 UDF는 Yelp 리뷰 문자열을 입력으로 사용하고 긍정적 또는 부정적 감정 각각에 대해 true 또는 false를 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="449c7-169">This UDF takes a Yelp review string as input, and outputs true or false for positive or negative sentiments, respectively.</span></span> <span data-ttu-id="449c7-170">이후 단계에서 정의하는 *predict()* 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="449c7-170">It uses the *predict()* method that you define in a later step.</span></span>

### <a name="use-spark-sql-to-call-the-udf"></a><span data-ttu-id="449c7-171">Spark SQL을 사용하여 UDF 호출</span><span class="sxs-lookup"><span data-stu-id="449c7-171">Use Spark SQL to call the UDF</span></span>

<span data-ttu-id="449c7-172">이제 데이터를 읽고 ML을 통합했으므로 Spark SQL을 사용하여 데이터 프레임의 각 행에 감정 분석을 실행하는 UDF를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="449c7-172">Now that you've read in your data and incorporated ML, use Spark SQL to call the UDF that will run sentiment analysis on each row of your DataFrame.</span></span> <span data-ttu-id="449c7-173">`Main` 메서드에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="449c7-173">Add the following code to your `Main` method:</span></span>

```csharp
// Use Spark SQL to call ML.NET UDF
// Display results of sentiment analysis on reviews
df.CreateOrReplaceTempView("Reviews");
DataFrame sqlDf = spark.Sql("SELECT ReviewText, MLudf(ReviewText) FROM Reviews");
sqlDf.Show();

// Print out first 20 rows of data
// Prevent data getting cut off by setting truncate = 0
sqlDf.Show(20, 0, false);

spark.Stop();
```

### <a name="create-predict-method"></a><span data-ttu-id="449c7-174">predict() 메서드 만들기</span><span class="sxs-lookup"><span data-stu-id="449c7-174">Create predict() method</span></span>

<span data-ttu-id="449c7-175">`Main()` 메서드 앞에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="449c7-175">Add the following code before your `Main()` method.</span></span> <span data-ttu-id="449c7-176">이 코드는 *ConsumeModel.cs*에서 모델 작성기에 의해 생성된 코드와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="449c7-176">This code is similar to what is produced by Model Builder in *ConsumeModel.cs*.</span></span> <span data-ttu-id="449c7-177">이 메서드를 콘솔로 이동하면 앱을 실행할 때마다 모델을 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="449c7-177">Moving this method to your console loads the model loading each time you run your app.</span></span>

```csharp
private static readonly PredictionEngine<ModelInput, ModelOutput> _predictionEngine;

static Program()
{
    MLContext mlContext = new MLContext();
    ITransformer model = mlContext.Model.Load("MLModel.zip", out DataViewSchema schema);
    _predictionEngine = mlContext.Model.CreatePredictionEngine<ModelInput, ModelOutput>(model);
}

static bool predict(string text)
{
    ModelInput input = new ModelInput
    {
        ReviewText = text
    };

    return _predictionEngine.Predict(input).Prediction;
}
```

## <a name="add-the-model-to-your-console-app"></a><span data-ttu-id="449c7-178">콘솔 앱에 모델 추가</span><span class="sxs-lookup"><span data-stu-id="449c7-178">Add the model to your console app</span></span>

<span data-ttu-id="449c7-179">솔루션 탐색기에서 **MLSparkModelML.Model** 프로젝트의 *MLModel.zip* 파일을 복사하여 **MLSparkModelML.ConsoleApp** 프로젝트에 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="449c7-179">In Solution Explorer, copy the *MLModel.zip* file from the **MLSparkModelML.Model** project and paste it in the **MLSparkModelML.ConsoleApp** project.</span></span> <span data-ttu-id="449c7-180">*MLSparkModelML.ConsoleApp.csproj*에 참조가 자동으로 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="449c7-180">A reference is automatically added in *MLSparkModelML.ConsoleApp.csproj*.</span></span>

## <a name="run-your-code"></a><span data-ttu-id="449c7-181">코드 실행</span><span class="sxs-lookup"><span data-stu-id="449c7-181">Run your code</span></span>

<span data-ttu-id="449c7-182">`spark-submit`을 사용하여 코드를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="449c7-182">Use `spark-submit` to run your code.</span></span> <span data-ttu-id="449c7-183">명령 프롬프트를 사용하여 콘솔 앱의 루트 폴더로 이동하고 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="449c7-183">Navigate to your console app's root folder using the command prompt and run the following commands.</span></span>

<span data-ttu-id="449c7-184">먼저 앱을 정리하고 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="449c7-184">First, clean and publish your app.</span></span>

```dotnetcli
dotnet clean
dotnet publish
```

<span data-ttu-id="449c7-185">그런 다음 콘솔 앱의 게시 폴더로 이동하고 다음 `spark-submit` 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="449c7-185">Then navigate to the console app's publish folder and run the following `spark-submit` command.</span></span> <span data-ttu-id="449c7-186">이 명령을 Microsoft Spark jar 파일의 실제 경로로 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="449c7-186">Remember to update the command with the actual path of your Microsoft Spark jar file.</span></span>

```dotnetcli
%SPARK_HOME%\bin\spark-submit --class org.apache.spark.deploy.dotnet.DotnetRunner --master local microsoft-spark-2.4.x-0.10.0.jar dotnet MLSparkModelML.ConsoleApp.dll
```

## <a name="get-the-code"></a><span data-ttu-id="449c7-187">코드 가져오기</span><span class="sxs-lookup"><span data-stu-id="449c7-187">Get the code</span></span>

<span data-ttu-id="449c7-188">이 자습서는 [빅 데이터를 사용한 감정 분석](https://github.com/dotnet/spark/tree/master/examples/Microsoft.Spark.CSharp.Examples/MachineLearning/Sentiment) 예제의 코드와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="449c7-188">This tutorial is similar to the code from the [Sentiment Analysis with Big Data](https://github.com/dotnet/spark/tree/master/examples/Microsoft.Spark.CSharp.Examples/MachineLearning/Sentiment) example.</span></span>

## <a name="next-steps"></a><span data-ttu-id="449c7-189">다음 단계</span><span class="sxs-lookup"><span data-stu-id="449c7-189">Next steps</span></span>

<span data-ttu-id="449c7-190">다음 문서로 이동하면 .NET for Apache Spark를 사용하여 구조적 스트리밍을 수행하는 방법을 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="449c7-190">Advance to the next article to learn how to do Structured Streaming with .NET for Apache Spark.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="449c7-191">자습서: .NET for Apache Spark를 사용한 구조적 스트리밍</span><span class="sxs-lookup"><span data-stu-id="449c7-191">Tutorial: Structured Streaming with .NET for Apache Spark</span></span>](streaming.md)
