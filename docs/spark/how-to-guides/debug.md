---
title: Windows에서 .NET for Apache Spark 애플리케이션 디버그
description: Windows에서 .NET for Apache Spark 애플리케이션을 디버그하는 방법을 알아봅니다.
ms.date: 08/15/2019
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: 098c7519fe99ef04773c5e4b81685ca0f06f1272
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2019
ms.locfileid: "74281522"
---
# <a name="debug-a-net-for-apache-spark-application"></a><span data-ttu-id="6bbde-103">.NET for Apache Spark 애플리케이션 디버그</span><span class="sxs-lookup"><span data-stu-id="6bbde-103">Debug a .NET for Apache Spark application</span></span>

<span data-ttu-id="6bbde-104">이 방법은 Windows에서 .NET for Apache Spark 애플리케이션과 Scala 코드를 디버그하기 위해 실행해야 하는 명령을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6bbde-104">This how-to provides the commands you need to run to debug your .NET for Apache Spark application and Scala code on Windows.</span></span>

## <a name="debug-your-application"></a><span data-ttu-id="6bbde-105">애플리케이션 디버그</span><span class="sxs-lookup"><span data-stu-id="6bbde-105">Debug your application</span></span>

<span data-ttu-id="6bbde-106">새 명령 프롬프트 창을 열고 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6bbde-106">Open a new command prompt window, run the following:</span></span>

```shell
spark-submit \
  --class org.apache.spark.deploy.dotnet.DotnetRunner \
  --master local \
  <path-to-microsoft-spark-jar> \
  debug
```

<span data-ttu-id="6bbde-107">이 명령을 실행하면 다음 출력이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6bbde-107">When you run the command, you see the following output:</span></span>

```console
***********************************************************************
* .NET Backend running debug mode. Press enter to exit *
***********************************************************************
```

<span data-ttu-id="6bbde-108">이 디버그 모드에서 `DotnetRunner`는 .NET 애플리케이션을 시작하지 않지만 연결될 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="6bbde-108">In this debug mode, `DotnetRunner` does not launch the .NET application, but it waits for it to connect.</span></span> <span data-ttu-id="6bbde-109">이 명령 프롬프트 창을 열어 둡니다.</span><span class="sxs-lookup"><span data-stu-id="6bbde-109">Leave this command prompt window open.</span></span>

<span data-ttu-id="6bbde-110">이제 디버거와 함께 .NET 애플리케이션을 실행하여 애플리케이션을 디버그할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bbde-110">Now you can run your .NET application with any debugger to debug your application.</span></span>

## <a name="debug-scala-code"></a><span data-ttu-id="6bbde-111">Scala 코드 디버그</span><span class="sxs-lookup"><span data-stu-id="6bbde-111">Debug Scala code</span></span>

<span data-ttu-id="6bbde-112">`DotnetRunner` 또는 `DotnetBackendHandler`와 같은 Scala 쪽 코드를 디버그해야 하는 경우 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6bbde-112">If you need to debug the Scala side code, such as `DotnetRunner` or `DotnetBackendHandler`, run the following command:</span></span>

```shell
spark-submit \
  --driver-java-options -agentlib:jdwp=transport=dt_socket,server=y,suspend=n,address=5005 \
  --class org.apache.spark.deploy.dotnet.DotnetRunner \
  --master local \
  <path-to-microsoft-spark-jar> \
  <path-to-your-app-exe> <argument(s)-to-your-app>
```

<span data-ttu-id="6bbde-113">명령을 실행한 후 [Intellij](https://www.jetbrains.com/help/idea/attaching-to-local-process.html)를 사용하여 실행 중인 프로세스에 디버거를 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="6bbde-113">After you run the command, attach a debugger to the running process using [Intellij](https://www.jetbrains.com/help/idea/attaching-to-local-process.html).</span></span>

## <a name="next-steps"></a><span data-ttu-id="6bbde-114">다음 단계</span><span class="sxs-lookup"><span data-stu-id="6bbde-114">Next steps</span></span>

* [<span data-ttu-id="6bbde-115">.NET for Apache Spark 시작</span><span class="sxs-lookup"><span data-stu-id="6bbde-115">Get started with .NET for Apache Spark</span></span>](../tutorials/get-started.md)
* [<span data-ttu-id="6bbde-116">Azure HDInsight에 .NET for Apache Spark 애플리케이션 배포</span><span class="sxs-lookup"><span data-stu-id="6bbde-116">Deploy a .NET for Apache Spark application to Azure HDInsight</span></span>](../tutorials/hdinsight-deployment.md)
* [<span data-ttu-id="6bbde-117">Databricks에 .NET for Apache Spark 애플리케이션 배포</span><span class="sxs-lookup"><span data-stu-id="6bbde-117">Deploy a .NET for Apache Spark application to Databricks</span></span>](../tutorials/databricks-deployment.md)
* [<span data-ttu-id="6bbde-118">Amazon EMR Spark에 .NET for Apache Spark 애플리케이션 배포</span><span class="sxs-lookup"><span data-stu-id="6bbde-118">Deploy a .NET for Apache Spark application to Amazon EMR Spark</span></span>](../tutorials/amazon-emr-spark-deployment.md)
