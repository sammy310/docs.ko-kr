---
title: .NET for Apache Spark를 사용한 일괄 처리 자습서
description: .NET for Apache Spark를 사용하여 일괄 처리하는 방법을 알아봅니다.
author: mamccrea
ms.author: mamccrea
ms.date: 10/09/2020
ms.topic: tutorial
ms.openlocfilehash: c161a0420de9e99478768926e5385dcfda1f9ee7
ms.sourcegitcommit: 34968a61e9bac0f6be23ed6ffb837f52d2390c85
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/17/2020
ms.locfileid: "94688230"
---
# <a name="tutorial-do-batch-processing-with-net-for-apache-spark"></a><span data-ttu-id="01b42-103">자습서: .NET for Apache Spark를 사용한 일괄 처리</span><span class="sxs-lookup"><span data-stu-id="01b42-103">Tutorial: Do batch processing with .NET for Apache Spark</span></span>

<span data-ttu-id="01b42-104">이 자습서에서는 .NET for Apache Spark를 사용하여 일괄 처리하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="01b42-104">In this tutorial, you learn how to do batch processing using .NET for Apache Spark.</span></span> <span data-ttu-id="01b42-105">일괄 처리는 미사용 데이터의 변환으로 원본 데이터가 이미 데이터 스토리지에 로드되었음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="01b42-105">Batch processing is the transformation of data at rest, meaning that the source data has already been loaded into data storage.</span></span>

<span data-ttu-id="01b42-106">일괄 처리는 일반적으로 추가 분석을 준비해야 하는 대량의 플랫 데이터 세트를 대상으로 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="01b42-106">Batch processing is generally performed over large, flat datasets that need to be prepared for further analysis.</span></span> <span data-ttu-id="01b42-107">로그 처리 및 데이터 웨어하우징은 일반적인 일괄 처리 시나리오입니다.</span><span class="sxs-lookup"><span data-stu-id="01b42-107">Log processing and data warehousing are common batch processing scenarios.</span></span> <span data-ttu-id="01b42-108">이 시나리오에서는 각 프로젝트가 분기된 횟수 또는 프로젝트 업데이트 후 경과한 기간과 같이 GitHub 프로젝트 정보를 분석합니다.</span><span class="sxs-lookup"><span data-stu-id="01b42-108">In this scenario, you analyze information about GitHub projects, such as the number of time different projects have been forked or how recently projects have been updated.</span></span>

<span data-ttu-id="01b42-109">이 자습서에서는 다음과 같은 작업을 수행하는 방법을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="01b42-109">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="01b42-110">.NET for Apache Spark 애플리케이션 만들기 및 실행</span><span class="sxs-lookup"><span data-stu-id="01b42-110">Create and run a .NET for Apache Spark application</span></span>
> * <span data-ttu-id="01b42-111">DataFrame으로 데이터를 읽고 분석 준비</span><span class="sxs-lookup"><span data-stu-id="01b42-111">Read data into a DataFrame and prepare it for analysis</span></span>
> * <span data-ttu-id="01b42-112">Spark SQL을 사용하여 데이터 처리</span><span class="sxs-lookup"><span data-stu-id="01b42-112">Process the data using Spark SQL</span></span>

## <a name="prerequisites"></a><span data-ttu-id="01b42-113">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="01b42-113">Prerequisites</span></span>

<span data-ttu-id="01b42-114">.NET for Apache Spark를 처름 사용하는 경우 [.NET for Apache Spark 시작](get-started.md) 자습서를 확인하여 환경을 준비하고 첫 번째 .NET for Apache Spark 애플리케이션을 실행하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="01b42-114">If this is your first time using .NET for Apache Spark, check out the [Get started with .NET for Apache Spark](get-started.md) tutorial to learn how to prepare your environment and run your first .NET for Apache Spark application.</span></span>

## <a name="download-the-sample-data"></a><span data-ttu-id="01b42-115">샘플 데이터 다운로드</span><span class="sxs-lookup"><span data-stu-id="01b42-115">Download the sample data</span></span>

<span data-ttu-id="01b42-116">[GHTorrent](http://ghtorrent.org/)는 프로젝트, 커밋 및 감시자 관련 정보와 같은 모든 공용 GitHub 이벤트를 모니터링하고 데이터베이스에 이벤트와 이벤트 구조를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="01b42-116">[GHTorrent](http://ghtorrent.org/) monitors all public GitHub events, such as info about projects, commits, and watchers, and stores the events and their structure in databases.</span></span> <span data-ttu-id="01b42-117">다른 기간에 걸쳐 수집된 데이터는 다운로드 가능한 보관 파일로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="01b42-117">Data collected over different time periods is available as downloadable archives.</span></span> <span data-ttu-id="01b42-118">덤프 파일이 매우 크기 때문에 이 가이드에서는 GitHub에서 다운로드할 수 있는 [잘린 버전의 덤프 파일](https://github.com/dotnet/spark/tree/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Batch/projects_smaller.csv)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="01b42-118">Because the dump files are very large, this guide uses a [truncated version of the dump file](https://github.com/dotnet/spark/tree/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Batch/projects_smaller.csv) that can be downloaded from GitHub.</span></span>

> [!NOTE]
> <span data-ttu-id="01b42-119">GHTorrent 데이터 세트는 이중 라이선스 체계([Creative Commons +](https://wiki.creativecommons.org/wiki/CCPlus))를 통해 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="01b42-119">The GHTorrent dataset is distributed under a dual licensing scheme ([Creative Commons +](https://wiki.creativecommons.org/wiki/CCPlus)).</span></span> <span data-ttu-id="01b42-120">비상업적 용도(교육, 연구 또는 개인 용도를 포함하지만 이에 국한되지 않음)의 경우 데이터 세트는 [CC-BY-SA 라이선스](https://creativecommons.org/licenses/by-sa/4.0/)를 통해 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="01b42-120">For non-commercial uses (including, but not limited to, educational, research or personal uses), the dataset is distributed under the [CC-BY-SA license](https://creativecommons.org/licenses/by-sa/4.0/).</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="01b42-121">콘솔 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="01b42-121">Create a console application</span></span>

1. <span data-ttu-id="01b42-122">명령 프롬프트에서 다음 명령을 실행하여 새 콘솔 애플리케이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="01b42-122">In your command prompt, run the following commands to create a new console application:</span></span>

   ```dotnetcli
   dotnet new console -o mySparkBatchApp
   cd mySparkBatchApp
   ```

   <span data-ttu-id="01b42-123">`dotnet` 명령은 `console` 형식의 `new` 애플리케이션을 자동으로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="01b42-123">The `dotnet` command creates a `new` application of type `console` for you.</span></span> <span data-ttu-id="01b42-124">`-o` 매개 변수는 앱이 저장되는 *mySparkBatchApp* 이라는 디렉터리를 만들고 필요한 파일로 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="01b42-124">The `-o` parameter creates a directory named *mySparkBatchApp* where your app is stored and populates it with the required files.</span></span> <span data-ttu-id="01b42-125">`cd mySparkBatchApp` 명령은 디렉터리를 방금 만든 앱 디렉터리로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="01b42-125">The `cd mySparkBatchApp` command changes the directory to the app directory you just created.</span></span>

1. <span data-ttu-id="01b42-126">앱에서 .NET for Apache Spark를 사용하려면 Microsoft.Spark 패키지를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="01b42-126">To use .NET for Apache Spark in an app, install the Microsoft.Spark package.</span></span> <span data-ttu-id="01b42-127">콘솔에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="01b42-127">In your console, run the following command:</span></span>

   ```dotnetcli
   dotnet add package Microsoft.Spark
   ```

## <a name="create-a-sparksession"></a><span data-ttu-id="01b42-128">SparkSession 만들기</span><span class="sxs-lookup"><span data-stu-id="01b42-128">Create a SparkSession</span></span>

1. <span data-ttu-id="01b42-129">다음 추가 `using` 문을 *mySparkBatchApp* 에서 *Program.cs* 파일의 맨 위에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="01b42-129">Add the following additional `using` statements to the top of the *Program.cs* file in *mySparkBatchApp*.</span></span>

   ```csharp
   using System;
   using Microsoft.Spark.Sql;
   using static Microsoft.Spark.Sql.Functions;
   ```

1. <span data-ttu-id="01b42-130">프로젝트 네임스페이스에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="01b42-130">Add the following code to your project namespace.</span></span> <span data-ttu-id="01b42-131">*s_referenceData* 는 나중에 프로그램에서 날짜를 기준으로 필터링하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="01b42-131">*s_referenceData* is used later in the program to filter based on date.</span></span>

   ```csharp
   static readonly DateTime s_referenceDate = new DateTime(2015, 10, 20);
   ```

1. <span data-ttu-id="01b42-132">Main 메서드 내에 다음 코드를 추가하여 새 SparkSession을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="01b42-132">Add the following code inside your Main method to establish a new SparkSession.</span></span> <span data-ttu-id="01b42-133">SparkSession은 Dataset 및 DataFrame API를 사용하여 Spark를 프로그래밍하기 위한 진입점입니다.</span><span class="sxs-lookup"><span data-stu-id="01b42-133">The SparkSession is the entry point to programming Spark with the Dataset and DataFrame API.</span></span> <span data-ttu-id="01b42-134">`spark` 개체를 호출하면 프로그램 전체에서 Spark 및 DataFrame 기능에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01b42-134">By calling the `spark` object, you can access Spark and DataFrame functionality throughout your program.</span></span>

   ```csharp
   SparkSession spark = SparkSession
        .Builder()
        .AppName("GitHub and Spark Batch")
        .GetOrCreate();
   ```

## <a name="prepare-the-data"></a><span data-ttu-id="01b42-135">데이터 준비</span><span class="sxs-lookup"><span data-stu-id="01b42-135">Prepare the data</span></span>

1. <span data-ttu-id="01b42-136">입력 파일을 명명된 열로 구성된 데이터의 분산된 컬렉션인 `DataFrame`으로 읽어 들입니다.</span><span class="sxs-lookup"><span data-stu-id="01b42-136">Read the input file into a `DataFrame`, which is a distributed collection of data organized into named columns.</span></span> <span data-ttu-id="01b42-137"><xref:Microsoft.Spark.Sql.DataFrame.Schema%2A> 사용을 통해 데이터의 열을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01b42-137">You can set the columns for your data through <xref:Microsoft.Spark.Sql.DataFrame.Schema%2A>.</span></span> <span data-ttu-id="01b42-138"><xref:Microsoft.Spark.Sql.DataFrame.Show%2A> 메서드를 사용하여 DataFrame에 데이터를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="01b42-138">Use the <xref:Microsoft.Spark.Sql.DataFrame.Show%2A> method to display the data in your DataFrame.</span></span> <span data-ttu-id="01b42-139">CSV 파일 경로를 다운로드한 GitHub 데이터의 위치로 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="01b42-139">Be sure to update the CSV file path to the location of the GitHub data you downloaded.</span></span>

   ```csharp
   DataFrame projectsDf = spark
       .Read()
       .Schema("id INT, url STRING, owner_id INT, " +
       "name STRING, descriptor STRING, language STRING, " +
       "created_at STRING, forked_from INT, deleted STRING" +
       "updated_at STRING")
       .Csv("filepath");

   projectsDf.Show();
   ```

1. <span data-ttu-id="01b42-140"><xref:Microsoft.Spark.Sql.DataFrame.Na%2A> 메서드를 사용하여 NA(null) 값이 있는 행을 삭제하고 <xref:Microsoft.Spark.Sql.DataFrame.Drop%2A> 메서드를 사용하여 데이터에서 특정 열을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="01b42-140">Use the <xref:Microsoft.Spark.Sql.DataFrame.Na%2A> method to drop rows with NA (null) values, and the <xref:Microsoft.Spark.Sql.DataFrame.Drop%2A> method to remove certain columns from your data.</span></span> <span data-ttu-id="01b42-141">이렇게 하면 최종 분석과 관련이 없는 null 데이터 또는 열을 분석하려 할 때 오류를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01b42-141">This helps prevent errors if you try to analyze null data or columns that are not relevant to your final analysis.</span></span>

   ```csharp
   // Drop any rows with NA values
   DataFrameNaFunctions dropEmptyProjects = projectsDf.Na();
   DataFrame cleanedProjects = dropEmptyProjects.Drop("any");

   // Remove unnecessary columns
   cleanedProjects = cleanedProjects.Drop("id", "url", "owner_id");
   cleanedProjects.Show();
   ```

## <a name="analyze-the-data"></a><span data-ttu-id="01b42-142">데이터 분석</span><span class="sxs-lookup"><span data-stu-id="01b42-142">Analyze the data</span></span>

<span data-ttu-id="01b42-143">Spark SQL을 사용하면 데이터에 대한 SQL 호출을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01b42-143">Spark SQL allows you to make SQL calls on your data.</span></span> <span data-ttu-id="01b42-144">사용자 정의 함수와 Spark SQL을 결합하여 사용자 정의 함수를 DataFrame의 모든 행에 적용하는 것이 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="01b42-144">It's common to combine user-defined functions and Spark SQL to apply a user-defined function to all rows of your DataFrame.</span></span>

<span data-ttu-id="01b42-145">특히 `spark.Sql`을 호출하여 다른 유형의 앱에서 볼 수 있는 표준 SQL 호출을 모방할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01b42-145">You can specifically call `spark.Sql` to mimic standard SQL calls seen in other types of apps.</span></span> <span data-ttu-id="01b42-146">또한 <xref:Microsoft.Spark.Sql.DataFrame.GroupBy%2A> 및 <xref:Microsoft.Spark.Sql.DataFrame.Agg%2A>와 같은 메서드를 호출하여 데이터의 결합, 필터링 및 계산 수행을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01b42-146">You can also call methods like <xref:Microsoft.Spark.Sql.DataFrame.GroupBy%2A> and <xref:Microsoft.Spark.Sql.DataFrame.Agg%2A> to specifically combine, filter, and perform calculations on your data.</span></span>

<span data-ttu-id="01b42-147">이 앱의 목표는 GitHub 프로젝트 데이터에 관한 인사이트를 얻는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="01b42-147">The goal of this app is to gain some insights about the GitHub projects data.</span></span> <span data-ttu-id="01b42-148">프로그램에 다음 코드 조각을 추가하여 데이터를 분석합니다.</span><span class="sxs-lookup"><span data-stu-id="01b42-148">Add the following code snippets to your program to analyze the data.</span></span>

1. <span data-ttu-id="01b42-149">다음 코드 블록을 추가하여 각 언어가 분기된 횟수를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="01b42-149">Add the following block of code finds the number of times each language has been forked.</span></span> <span data-ttu-id="01b42-150">먼저 데이터를 언어별로 그룹화합니다.</span><span class="sxs-lookup"><span data-stu-id="01b42-150">First, the data is grouped by language.</span></span> <span data-ttu-id="01b42-151">그런 다음 각 언어의 평균 분기 횟수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="01b42-151">Then, the average number of forks from each language is taken.</span></span>

   ```csharp
   // Average number of times each language has been forked
   DataFrame groupedDF = cleanedProjects
       .GroupBy("language")
       .Agg(Avg(cleanedProjects["forked_from"]);
   ```

1. <span data-ttu-id="01b42-152">다음 코드 블록을 추가하여 평균 분기 횟수를 내림차순으로 정렬하고 가장 많이 분기된 언어를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="01b42-152">Add the following block of code to order the average number of forks in descending order to see which languages are the most forked.</span></span> <span data-ttu-id="01b42-153">가장 많은 분기 횟수가 먼저 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="01b42-153">That is, the largest number of forks will appear first.</span></span>

   ```csharp
   // Sort by most forked languages first
   groupedDF.OrderBy(Desc("avg(forked_from)")).Show();
   ```

1. <span data-ttu-id="01b42-154">다음 코드 블록은 최근 프로젝트가 어떻게 업데이트되었는지 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="01b42-154">The next block of code shows you how recently projects have been updated.</span></span> <span data-ttu-id="01b42-155">*MyUDF* 라는 새 사용자 정의 함수를 등록하고 자습서의 시작 부분에 선언된 날짜인 *s_referenceDate* 와 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="01b42-155">You register a new user-defined function called *MyUDF* and compare it with a date, *s_referenceDate*, which was declared at the beginning of the tutorial.</span></span> <span data-ttu-id="01b42-156">각 프로젝트의 날짜가 참조 날짜와 비교됩니다.</span><span class="sxs-lookup"><span data-stu-id="01b42-156">The date for each project is compared against the reference date.</span></span> <span data-ttu-id="01b42-157">그런 다음 Spark SQL을 사용하여 데이터의 각 행에서 UDF를 호출하고 데이터 세트의 각 프로젝트를 분석합니다.</span><span class="sxs-lookup"><span data-stu-id="01b42-157">Then, Spark SQL is used to call the UDF on each row of the data to analyze each project in the data set.</span></span>

   ```csharp
   spark.Udf().Register<string, bool>(
       "MyUDF",
       (date) => DateTime.TryParse(date, out DateTime convertedDate) &&
           (convertedDate > s_referenceDate);
   cleanedProjects.CreateOrReplaceTempView("dateView");

   DataFrame dateDf = spark.Sql(
       "SELECT *, MyUDF(dateView.updated_at) AS datebefore FROM dateView");
   dateDf.Show();
   ```

1. <span data-ttu-id="01b42-158">`spark.Stop()`을 호출하여 SparkSession을 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="01b42-158">Call `spark.Stop()` to end the SparkSession.</span></span>

## <a name="use-spark-submit-to-run-your-app"></a><span data-ttu-id="01b42-159">spark-submit을 사용하여 앱 실행</span><span class="sxs-lookup"><span data-stu-id="01b42-159">Use spark-submit to run your app</span></span>

1. <span data-ttu-id="01b42-160">다음 명령을 사용하여 .NET 앱을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="01b42-160">Use the following command to build your .NET app:</span></span>

   ```dotnetcli
   dotnet build
   ```

1. <span data-ttu-id="01b42-161">`spark-submit`을 사용하여 앱을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="01b42-161">Run your app with `spark-submit`.</span></span> <span data-ttu-id="01b42-162">다음 명령을 Microsoft Spark jar 파일의 실제 경로로 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="01b42-162">Be sure to update the following command with the actual paths to your Microsoft Spark jar file.</span></span>

   ```console
   spark-submit --class org.apache.spark.deploy.dotnet.DotnetRunner --master local /<path>/to/microsoft-spark-<spark_majorversion-spark_minorversion>_<scala_majorversion.scala_minorversion>-<spark_dotnet_version>.jar dotnet /<path>/to/netcoreapp<version>/mySparkBatchApp.dll
   ```

## <a name="get-the-code"></a><span data-ttu-id="01b42-163">코드 가져오기</span><span class="sxs-lookup"><span data-stu-id="01b42-163">Get the code</span></span>

<span data-ttu-id="01b42-164">GitHub에서 [전체 솔루션](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Batch/GitHubProjects.cs)을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01b42-164">You can see the [full solution](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Batch/GitHubProjects.cs) on GitHub.</span></span>

## <a name="next-steps"></a><span data-ttu-id="01b42-165">다음 단계</span><span class="sxs-lookup"><span data-stu-id="01b42-165">Next steps</span></span>

<span data-ttu-id="01b42-166">다음 문서로 이동하면 .NET for Apache Spark를 사용하여 스트리밍 데이터를 처리하는 방법을 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01b42-166">Advance to the next article to learn how to process streaming data with .NET for Apache Spark.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="01b42-167">자습서: .NET for Apache Spark를 사용한 구조적 스트리밍</span><span class="sxs-lookup"><span data-stu-id="01b42-167">Tutorial: Structured Streaming with .NET for Apache Spark</span></span>](streaming.md)
