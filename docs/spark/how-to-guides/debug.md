---
title: Windows에서 .NET for Apache Spark 애플리케이션 디버그
description: Windows에서 .NET for Apache Spark 애플리케이션을 디버그하는 방법을 알아봅니다.
ms.date: 06/25/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: 9209d5bdec6dd85f6d21a502fb07204effef1934
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617758"
---
# <a name="debug-a-net-for-apache-spark-application"></a><span data-ttu-id="19851-103">.NET for Apache Spark 애플리케이션 디버그</span><span class="sxs-lookup"><span data-stu-id="19851-103">Debug a .NET for Apache Spark application</span></span>

<span data-ttu-id="19851-104">이 방법은 Windows에서 .NET for Apache Spark 애플리케이션을 디버그하는 단계를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="19851-104">This how-to provides the steps to debug your .NET for Apache Spark application on Windows.</span></span>

[!INCLUDE [spark-preview-note](../../../includes/spark-preview-note.md)]

## <a name="debug-your-application"></a><span data-ttu-id="19851-105">애플리케이션 디버그</span><span class="sxs-lookup"><span data-stu-id="19851-105">Debug your application</span></span>

<span data-ttu-id="19851-106">새 명령 프롬프트 창을 열고 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="19851-106">Open a new command prompt window and run the following command:</span></span>

```shell
spark-submit \
  --class org.apache.spark.deploy.dotnet.DotnetRunner \
  --master local \
  <path-to-microsoft-spark-jar> \
  debug
```

<span data-ttu-id="19851-107">이 명령을 실행하면 다음 출력이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="19851-107">When you run the command, you see the following output:</span></span>

```console
***********************************************************************
* .NET Backend running debug mode. Press enter to exit *
***********************************************************************
```

<span data-ttu-id="19851-108">디버그 모드에서 DotnetRunner는 .NET 애플리케이션을 시작하지 않고 .NET 앱을 시작할 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="19851-108">In debug mode, DotnetRunner does not launch the .NET application, but instead waits for you to start the .NET app.</span></span> <span data-ttu-id="19851-109">이 명령 프롬프트 창을 열어 두고 C# 디버거를 통해 .NET 애플리케이션을 시작하여 애플리케이션을 디버그합니다.</span><span class="sxs-lookup"><span data-stu-id="19851-109">Leave this command prompt window open and start your .NET application through C# debugger to debug your application.</span></span> <span data-ttu-id="19851-110">C# 디버거([Windows/macOS용 Visual Studio 디버거](https://visualstudio.microsoft.com/vs/) 또는 [Visual Studio Code의 C# 디버거 확장](https://code.visualstudio.com/Docs/editor/debugging))로 .NET 애플리케이션을 시작하여 애플리케이션을 디버그합니다.</span><span class="sxs-lookup"><span data-stu-id="19851-110">Start your .NET application with a C# debugger ([Visual Studio Debugger for Windows/macOS](https://visualstudio.microsoft.com/vs/) or [C# Debugger Extension in Visual Studio Code](https://code.visualstudio.com/Docs/editor/debugging)) to debug your application.</span></span>

## <a name="debug-a-user-defined-function-udf"></a><span data-ttu-id="19851-111">사용자 정의 함수(UDF) 디버그</span><span class="sxs-lookup"><span data-stu-id="19851-111">Debug a user-defined function (UDF)</span></span>

> [!NOTE]
> <span data-ttu-id="19851-112">사용자 정의 함수는 Visual Studio 디버거를 사용하는 Windows에서만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="19851-112">User-defined functions are supported only on Windows with Visual Studio Debugger.</span></span>

<span data-ttu-id="19851-113">`spark-submit`을 실행하기 전에 다음 환경 변수를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="19851-113">Before running `spark-submit`, set the following environment variable:</span></span>

```bat
set DOTNET_WORKER_DEBUG=1
```

<span data-ttu-id="19851-114">Spark 애플리케이션을 실행하면 `Choose Just-In-Time Debugger` 창이 팝업됩니다.</span><span class="sxs-lookup"><span data-stu-id="19851-114">When you run your Spark application, a `Choose Just-In-Time Debugger` window will pop up.</span></span> <span data-ttu-id="19851-115">Visual Studio 디버거를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="19851-115">Choose a Visual Studio debugger.</span></span>

<span data-ttu-id="19851-116">디버거는 [TaskRunner.cs](https://github.com/dotnet/spark/blob/5e9c08b430b4bc56b5f42252c4b73437377afaed/src/csharp/Microsoft.Spark.Worker/TaskRunner.cs#L52)의 다음 위치에서 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="19851-116">The debugger will break at the following location in [TaskRunner.cs](https://github.com/dotnet/spark/blob/5e9c08b430b4bc56b5f42252c4b73437377afaed/src/csharp/Microsoft.Spark.Worker/TaskRunner.cs#L52):</span></span>

```csharp
if (EnvironmentUtils.GetEnvironmentVariableAsBool("DOTNET_WORKER_DEBUG"))
{
    Debugger.Launch(); // <-- The debugger will break here.
}
```

<span data-ttu-id="19851-117">디버그하려는 UDF가 포함된 *.cs* 파일로 이동하여 [중단점을 설정](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints?view=vs-2019)합니다.</span><span class="sxs-lookup"><span data-stu-id="19851-117">Navigate to the *.cs* file that contains the UDF that you plan to debug, and [set a breakpoint](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints?view=vs-2019).</span></span> <span data-ttu-id="19851-118">작업자가 아직 UDF가 포함된 어셈블리를 로드하지 않았기 때문에 중단점에 `The breakpoint will not currently be hit`가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="19851-118">The breakpoint will say `The breakpoint will not currently be hit` because the worker hasn't loaded the assembly that contains UDF yet.</span></span>

<span data-ttu-id="19851-119">`F5`를 눌러 애플리케이션을 계속하면 중단점이 결국 적중됩니다.</span><span class="sxs-lookup"><span data-stu-id="19851-119">Hit `F5` to continue your application and the breakpoint will eventually be hit.</span></span>

> [!NOTE]
> <span data-ttu-id="19851-120">각 작업에 대해 Just-In-Time 디버거 선택 창이 팝업됩니다.</span><span class="sxs-lookup"><span data-stu-id="19851-120">The Choose Just-In-Time Debugger window pops up for each task.</span></span> <span data-ttu-id="19851-121">지나치게 많은 팝업을 방지하려면 실행기 수를 낮은 수로 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="19851-121">To avoid excessive pop-ups, set the number of executors to a low number.</span></span> <span data-ttu-id="19851-122">예를 들어 spark-submit의 **--master local[1]** 옵션을 사용하여 작업 수를 1로 설정하면 단일 디버거 인스턴스만 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="19851-122">For example, you can use the **--master local[1]** option for spark-submit to set the number of tasks to 1, which launches a single debugger instance.</span></span>

## <a name="debug-scala-code"></a><span data-ttu-id="19851-123">Scala 코드 디버그</span><span class="sxs-lookup"><span data-stu-id="19851-123">Debug Scala code</span></span>

<span data-ttu-id="19851-124">Scala쪽 코드(`DotnetRunner`, `DotnetBackendHandler` 등)를 디버그해야 하는 경우, 다음 명령을 사용하고 실행 중인 프로세스에 [IntelliJ](https://www.jetbrains.com/help/idea/attaching-to-local-process.html)를 사용하여 디버거를 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19851-124">If you need to debug the Scala-side code (`DotnetRunner`, `DotnetBackendHandler`, etc.), you can use the following command and attach a debugger to the running process using [IntelliJ](https://www.jetbrains.com/help/idea/attaching-to-local-process.html):</span></span>

```shell
spark-submit \
  --driver-java-options -agentlib:jdwp=transport=dt_socket,server=y,suspend=n,address=5005 \
  --class org.apache.spark.deploy.dotnet.DotnetRunner \
  --master local \
  <path-to-microsoft-spark-jar> \
  <path-to-your-app-exe> <argument(s)-to-your-app>
```

<span data-ttu-id="19851-125">명령을 실행한 후 [Intellij](https://www.jetbrains.com/help/idea/attaching-to-local-process.html)를 사용하여 실행 중인 프로세스에 디버거를 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="19851-125">After you run the command, attach a debugger to the running process using [Intellij](https://www.jetbrains.com/help/idea/attaching-to-local-process.html).</span></span>

## <a name="next-steps"></a><span data-ttu-id="19851-126">다음 단계</span><span class="sxs-lookup"><span data-stu-id="19851-126">Next steps</span></span>

* [<span data-ttu-id="19851-127">.NET for Apache Spark 시작</span><span class="sxs-lookup"><span data-stu-id="19851-127">Get started with .NET for Apache Spark</span></span>](../tutorials/get-started.md)
* [<span data-ttu-id="19851-128">Azure HDInsight에 .NET for Apache Spark 애플리케이션 배포</span><span class="sxs-lookup"><span data-stu-id="19851-128">Deploy a .NET for Apache Spark application to Azure HDInsight</span></span>](../tutorials/hdinsight-deployment.md)
* [<span data-ttu-id="19851-129">Databricks에 .NET for Apache Spark 애플리케이션 배포</span><span class="sxs-lookup"><span data-stu-id="19851-129">Deploy a .NET for Apache Spark application to Databricks</span></span>](../tutorials/databricks-deployment.md)
* [<span data-ttu-id="19851-130">Amazon EMR Spark에 .NET for Apache Spark 애플리케이션 배포</span><span class="sxs-lookup"><span data-stu-id="19851-130">Deploy a .NET for Apache Spark application to Amazon EMR Spark</span></span>](../tutorials/amazon-emr-spark-deployment.md)
