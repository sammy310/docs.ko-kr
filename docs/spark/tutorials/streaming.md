---
title: .NET for Apache Spark를 사용한 구조적 스트리밍 자습서
description: 이 자습서에서는 Spark 구조적 스트리밍을 위해 .NET for Apache Spark를 사용하는 방법을 알아봅니다.
author: mamccrea
ms.author: mamccrea
ms.date: 12/04/2019
ms.topic: tutorial
ms.openlocfilehash: d0fe79ef79125c06be9acd8ba80001a33e150adb
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/04/2019
ms.locfileid: "74802860"
---
# <a name="tutorial-structured-streaming-with-net-for-apache-spark"></a><span data-ttu-id="3403d-103">자습서: .NET for Apache Spark를 사용한 구조적 스트리밍</span><span class="sxs-lookup"><span data-stu-id="3403d-103">Tutorial: Structured Streaming with .NET for Apache Spark</span></span> 

<span data-ttu-id="3403d-104">이 자습서에서는 .NET for Apache Spark를 사용하여 Spark 구조적 스트리밍을 호출하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3403d-104">This tutorial teaches you how to invoke Spark Structured Streaming using .NET for Apache Spark.</span></span> <span data-ttu-id="3403d-105">Spark 구조적 스트리밍은 실시간 데이터 스트림을 처리하기 위한 Apache Spark의 지원 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="3403d-105">Spark Structured Streaming is Apache Spark's support for processing real-time data streams.</span></span> <span data-ttu-id="3403d-106">스트림 처리는 라이브 데이터를 생성하는 동안 분석하는 것을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="3403d-106">Stream processing means analyzing live data as it's being produced.</span></span>

<span data-ttu-id="3403d-107">이 자습서에서는 다음과 같은 작업을 수행하는 방법을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="3403d-107">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="3403d-108">.NET for Apache Spark 애플리케이션 만들기 및 실행</span><span class="sxs-lookup"><span data-stu-id="3403d-108">Create and run a .NET for Apache Spark application</span></span>
> * <span data-ttu-id="3403d-109">netcat을 사용하여 데이터 스트림 만들기</span><span class="sxs-lookup"><span data-stu-id="3403d-109">Use netcat to create a data stream</span></span>
> * <span data-ttu-id="3403d-110">사용자 정의 함수 및 SparkSQL를 사용하여 스트리밍 데이터 분석</span><span class="sxs-lookup"><span data-stu-id="3403d-110">Use user-defined functions and SparkSQL to analyze streaming data</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3403d-111">전제 조건</span><span class="sxs-lookup"><span data-stu-id="3403d-111">Prerequisites</span></span>

<span data-ttu-id="3403d-112">첫 번째 .NET for Apache Spark 애플리케이션인 경우 [자습서 시작](get-started.md)을 먼저 시작하여 기본 사항을 숙지하세요.</span><span class="sxs-lookup"><span data-stu-id="3403d-112">If this is your first .NET for Apache Spark application, start with the [Getting Started tutorial](get-started.md) to become familiar with the basics.</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="3403d-113">콘솔 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="3403d-113">Create a console application</span></span>

1. <span data-ttu-id="3403d-114">명령 프롬프트에서 다음 명령을 실행하여 새 콘솔 애플리케이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3403d-114">In your command prompt, run the following commands to create a new console application:</span></span>

   ```console
   dotnet new console -o mySparkStreamingApp
   cd mySparkStreamingApp
   ```

   <span data-ttu-id="3403d-115">`dotnet` 명령은 `console` 형식의 `new` 애플리케이션을 자동으로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3403d-115">The `dotnet` command creates a `new` application of type `console` for you.</span></span> <span data-ttu-id="3403d-116">`-o` 매개 변수는 앱이 저장되는 *mySparkStreamingApp*이라는 디렉터리를 만들고 필요한 파일로 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="3403d-116">The `-o` parameter creates a directory named *mySparkStreamingApp* where your app is stored and populates it with the required files.</span></span> <span data-ttu-id="3403d-117">`cd mySparkStreamingApp` 명령은 디렉터리를 방금 만든 앱 디렉터리로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="3403d-117">The `cd mySparkStreamingApp` command changes the directory to the app directory you just created.</span></span>

1. <span data-ttu-id="3403d-118">앱에서 .NET for Apache Spark를 사용하려면 Microsoft.Spark 패키지를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="3403d-118">To use .NET for Apache Spark in an app, install the Microsoft.Spark package.</span></span> <span data-ttu-id="3403d-119">콘솔에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3403d-119">In your console, run the following command:</span></span>

   ```console
   dotnet add package Microsoft.Spark
   ```

## <a name="establish-and-connect-to-a-data-stream"></a><span data-ttu-id="3403d-120">데이터 스트림 설정 및 연결</span><span class="sxs-lookup"><span data-stu-id="3403d-120">Establish and connect to a data stream</span></span>

<span data-ttu-id="3403d-121">스트림 처리를 테스트하는 일반적인 방법 중 하나는 **netcat**을 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3403d-121">One popular way to test stream processing is through **netcat**.</span></span> <span data-ttu-id="3403d-122">netcat(*nc*라고도 함)를 사용하여 네트워크 연결에서 읽고 쓸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3403d-122">netcat (also known as *nc*) allows you to read from and write to network connections.</span></span> <span data-ttu-id="3403d-123">터미널 창에서 netcat을 사용하여 네트워크 연결을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3403d-123">You establish a network connection with netcat through a terminal window.</span></span> 

### <a name="create-a-data-stream-with-netcat"></a><span data-ttu-id="3403d-124">netcat을 사용하여 데이터 스트림 만들기</span><span class="sxs-lookup"><span data-stu-id="3403d-124">Create a data stream with netcat</span></span>

1. <span data-ttu-id="3403d-125">[netcat을 다운로드](https://sourceforge.net/projects/nc110/files/)합니다.</span><span class="sxs-lookup"><span data-stu-id="3403d-125">[Download netcat](https://sourceforge.net/projects/nc110/files/).</span></span> <span data-ttu-id="3403d-126">그런 다음, zip 다운로드에서 파일의 압축을 풀고 "PATH" 환경 변수에 압출을 푼 해당 디렉터리를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3403d-126">Then, extract the file from the zip download and append the directory you extracted to your "PATH" environment variable.</span></span>

2. <span data-ttu-id="3403d-127">새 연결을 시작하려면 새 콘솔을 열고 포트 9999에서 localhost에 연결하는 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3403d-127">To start a new connection, open a new console and run the following command which connects to localhost on port 9999.</span></span>

   <span data-ttu-id="3403d-128">Windows에서:</span><span class="sxs-lookup"><span data-stu-id="3403d-128">On Windows:</span></span>

   ```console
   nc -vvv -l -p 9999
   ```

   <span data-ttu-id="3403d-129">Linux에서:</span><span class="sxs-lookup"><span data-stu-id="3403d-129">On Linux:</span></span>

   ```console
   nc -lk 9999
   ```

   <span data-ttu-id="3403d-130">Spark 프로그램은 이 명령 프롬프트에 입력하는 입력을 수신 대기합니다.</span><span class="sxs-lookup"><span data-stu-id="3403d-130">Your Spark program listens for the input you type into this command prompt.</span></span>

### <a name="create-a-sparksession"></a><span data-ttu-id="3403d-131">SparkSession 만들기</span><span class="sxs-lookup"><span data-stu-id="3403d-131">Create a SparkSession</span></span>

1. <span data-ttu-id="3403d-132">다음 추가 `using` 문을 *mySparkStreamingApp*에서 *Program.cs* 파일의 맨 위에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3403d-132">Add the following additional `using` statements to the top of the *Program.cs* file in *mySparkStreamingApp*:</span></span>

   ```csharp
   using System;
   using Microsoft.Spark.Sql;
   using Microsoft.Spark.Sql.Streaming;
   using static Microsoft.Spark.Sql.Functions;
   ```

1. <span data-ttu-id="3403d-133">`Main` 메서드에 다음 코드를 추가하여 새 `SparkSession`을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3403d-133">Add the following code to your `Main` method to create a new `SparkSession`.</span></span> <span data-ttu-id="3403d-134">Spark 세션은 Dataset 및 DataFrame API를 사용하여 Spark를 프로그래밍하기 위한 진입점입니다.</span><span class="sxs-lookup"><span data-stu-id="3403d-134">The Spark Session is the entry point to programming Spark with the Dataset and DataFrame API.</span></span>

   ```csharp
   SparkSession spark = SparkSession
        .Builder()
        .AppName("Streaming example with a UDF")
        .GetOrCreate();
   ```

   <span data-ttu-id="3403d-135">위에서 만든 *spark* 개체를 호출하면 프로그램 전체에서 Spark 및 DataFrame 기능에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3403d-135">Calling the *spark* object created above allows you to access Spark and DataFrame functionality throughout your program.</span></span>

### <a name="connect-to-a-stream-with-readstream"></a><span data-ttu-id="3403d-136">ReadStream()을 사용하여 스트림에 연결</span><span class="sxs-lookup"><span data-stu-id="3403d-136">Connect to a stream with ReadStream()</span></span>

<span data-ttu-id="3403d-137">`ReadStream()` 메서드는 스트리밍 데이터를 `DataFrame`으로 읽는 데 사용할 수 있는 `DataStreamReader`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="3403d-137">The `ReadStream()` method returns a `DataStreamReader` that can be used to read streaming data in as a `DataFrame`.</span></span> <span data-ttu-id="3403d-138">Spark 앱이 스트리밍 데이터 위치를 알리도록 하려면 호스트 및 포트 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="3403d-138">Include the host and port information to tell your Spark app where to expect its streaming data.</span></span>

```csharp
DataFrame lines = spark
    .ReadStream()
    .Format("socket")
    .Option("host", hostname)
    .Option("port", port)
    .Load();
```

## <a name="register-a-user-defined-function"></a><span data-ttu-id="3403d-139">사용자 정의 함수 등록</span><span class="sxs-lookup"><span data-stu-id="3403d-139">Register a user-defined function</span></span>

<span data-ttu-id="3403d-140">Spark 애플리케이션에서 *사용자 정의 함수*인 UDF를 사용하여 데이터에 대한 계산 및 분석을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3403d-140">You can use UDFs, *user-defined functions*, in Spark applications to perform calculations and analysis on your data.</span></span>

<span data-ttu-id="3403d-141">`Main` 메서드에 다음 코드를 추가하여 `udfArray`라는 UDF를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="3403d-141">Add the following code to your `Main` method to register a UDF called `udfArray`.</span></span> 

```csharp
Func<Column, Column> udfArray =
    Udf<string, string[]>((str) => new string[] { str, $"{str} {str.Length}" });
```

<span data-ttu-id="3403d-142">이 UDF는 netcat 터미널에서 수신하는 각 문자열을 처리하여 원래 문자열(*str*에 포함됨)과 원래 문자열의 길이가 연결된 원래 문자열을 포함하는 배열을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="3403d-142">This UDF processes each string it receives from the netcat terminal to produce an array that includes the original string (contained in *str*), followed by the original string concatenated with the length of the original string.</span></span> 

<span data-ttu-id="3403d-143">예를 들어 netcat 터미널에 *Hello world*를 입력하면 다음과 같은 배열이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="3403d-143">For example, entering *Hello world* in the netcat terminal produces an array where:</span></span>

* <span data-ttu-id="3403d-144">배열\[0] = Hello world</span><span class="sxs-lookup"><span data-stu-id="3403d-144">array\[0] = Hello world</span></span>
* <span data-ttu-id="3403d-145">배열\[1] = Hello world 11</span><span class="sxs-lookup"><span data-stu-id="3403d-145">array\[1] = Hello world 11</span></span>

## <a name="use-sparksql"></a><span data-ttu-id="3403d-146">SparkSQL 사용</span><span class="sxs-lookup"><span data-stu-id="3403d-146">Use SparkSQL</span></span>

<span data-ttu-id="3403d-147">SparkSQL을 사용하여 데이터 프레임에 저장된 데이터에 대해 다양한 기능을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3403d-147">Use SparkSQL to perform various functions on the data stored in your DataFrame.</span></span> <span data-ttu-id="3403d-148">UDF와 SparkSQL을 결합하여 데이터 프레임의 각 행에 UDF를 적용하는 것이 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="3403d-148">It's common to combine UDFs and SparkSQL to apply a UDF to each row of a DataFrame.</span></span>

```csharp
DataFrame arrayDF = lines.Select(Explode(udfArray(lines["value"])));
```

<span data-ttu-id="3403d-149">이 코드 조각은 netcat 터미널에서 읽은 각 문자열을 나타내는 데이터 프레임의 각 값에 *udfArray*를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="3403d-149">This code snippet applies *udfArray* to each value in your DataFrame, which represents each string read from your netcat terminal.</span></span> <span data-ttu-id="3403d-150">SparkSQL 메서드 <xref:Microsoft.Spark.Sql.Functions.Explode%2A>를 적용하여 배열의 각 항목을 자체 행에 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="3403d-150">Apply the SparkSQL method <xref:Microsoft.Spark.Sql.Functions.Explode%2A> to put each entry of your array in its own row.</span></span> <span data-ttu-id="3403d-151">마지막으로 <xref:Microsoft.Spark.Sql.DataFrame.Select%2A>를 사용하여 새 데이터 프레임 *arrayDF*에 생성한 열을 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="3403d-151">Finally, use <xref:Microsoft.Spark.Sql.DataFrame.Select%2A> to place the columns you've produced in the new DataFrame *arrayDF.*</span></span>

## <a name="display-your-stream"></a><span data-ttu-id="3403d-152">스트림 표시</span><span class="sxs-lookup"><span data-stu-id="3403d-152">Display your stream</span></span>

<span data-ttu-id="3403d-153"><xref:Microsoft.Spark.Sql.DataFrame.WriteStream>을 사용하여 콘솔 결과를 인쇄하고 최신 출력만 표시하는 등 출력의 특성을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3403d-153">Use <xref:Microsoft.Spark.Sql.DataFrame.WriteStream> to establish characteristics of your output, such as printing results to the console and displaying only the most recent output.</span></span>

```csharp
StreamingQuery query = arrayDf
    .WriteStream()
    .Format("console")
    .Start();
```

## <a name="run-your-code"></a><span data-ttu-id="3403d-154">코드 실행</span><span class="sxs-lookup"><span data-stu-id="3403d-154">Run your code</span></span>

<span data-ttu-id="3403d-155">Spark의 구조적 스트리밍은 일련의 소규모 **일괄 처리**를 통해 데이터를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="3403d-155">Structured streaming in Spark processes data through a series of small **batches**.</span></span>  <span data-ttu-id="3403d-156">프로그램을 실행할 때 netcat 연결을 설정하는 명령 프롬프트로 입력을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3403d-156">When you run your program, the command prompt where you establish the netcat connection allows you to start typing.</span></span> <span data-ttu-id="3403d-157">해당 명령 프롬프트에서 데이터를 입력한 후 Enter 키를 누를 때마다 Spark는 항목을 일괄 처리로 간주하고 UDF를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3403d-157">Each time you press the Enter key after typing data in that command prompt, Spark considers your entry a batch and runs the UDF.</span></span>

### <a name="use-spark-submit-to-run-your-app"></a><span data-ttu-id="3403d-158">spark-submit을 사용하여 앱 실행</span><span class="sxs-lookup"><span data-stu-id="3403d-158">Use spark-submit to run your app</span></span>

<span data-ttu-id="3403d-159">새 netcat 세션을 시작한 후 새 터미널을 열고 다음 명령과 유사한 `spark-submit` 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3403d-159">After starting a new netcat session, open a new terminal and run your `spark-submit` command, similar to the following command:</span></span>

```powershell
spark-submit --class org.apache.spark.deploy.dotnet.DotnetRunner --master local /path/to/microsoft-spark-<version>.jar Microsoft.Spark.CSharp.Examples.exe Sql.Streaming.StructuredNetworkCharacterCount localhost 9999
```

> [!NOTE]
> <span data-ttu-id="3403d-160">위의 명령을 Microsoft Spark jar 파일의 실제 경로로 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3403d-160">Be sure to update the above command with the actual path to your Microsoft Spark jar file.</span></span> <span data-ttu-id="3403d-161">또한 위의 명령은 netcat 서버가 localhost 포트 9999에서 실행되는 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="3403d-161">The above command also assumes your netcat server is running on localhost port 9999.</span></span>

## <a name="get-the-code"></a><span data-ttu-id="3403d-162">코드 가져오기</span><span class="sxs-lookup"><span data-stu-id="3403d-162">Get the code</span></span>

<span data-ttu-id="3403d-163">이 자습서에서는 [StructuredNetworkCharacterCount.cs](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredNetworkCharacterCount.cs) 예제를 사용하지만 GitHub에는 세 가지의 전체 스트림 처리 예제가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3403d-163">This tutorial uses the [StructuredNetworkCharacterCount.cs](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredNetworkCharacterCount.cs) example, but there are three other full stream processing examples on GitHub:</span></span>

* <span data-ttu-id="3403d-164">[StructuredNetworkWordCount.cs](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredNetworkWordCount.cs): 원본에서 스트리밍된 데이터의 단어 개수</span><span class="sxs-lookup"><span data-stu-id="3403d-164">[StructuredNetworkWordCount.cs](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredNetworkWordCount.cs): word count on data streamed from any source</span></span>
* <span data-ttu-id="3403d-165">[StructuredNetworkWordCountWindowed.cs](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredNetworkWordCountWindowed.cs): 창 작업 논리를 사용하는 데이터의 단어 개수</span><span class="sxs-lookup"><span data-stu-id="3403d-165">[StructuredNetworkWordCountWindowed.cs](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredNetworkWordCountWindowed.cs): word count on data with windowing logic</span></span>
* <span data-ttu-id="3403d-166">[StructuredKafkaWordCount.cs](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs): Kafka에서 스트리밍된 데이터의 단어 개수</span><span class="sxs-lookup"><span data-stu-id="3403d-166">[StructuredKafkaWordCount.cs](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs): word count on data streamed from Kafka</span></span>

## <a name="next-steps"></a><span data-ttu-id="3403d-167">다음 단계</span><span class="sxs-lookup"><span data-stu-id="3403d-167">Next steps</span></span>

<span data-ttu-id="3403d-168">다음 문서로 이동하여 Databricks에 .NET for Apache Spark 애플리케이션을 배포하는 방법을 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="3403d-168">Advance to the next article to learn how to deploy your .NET for Apache Spark application to Databricks.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="3403d-169">자습서: Databricks에 .NET for Apache Spark 애플리케이션 배포</span><span class="sxs-lookup"><span data-stu-id="3403d-169">Tutorial: Deploy a .NET for Apache Spark application to Databricks</span></span>](databricks-deployment.md)
