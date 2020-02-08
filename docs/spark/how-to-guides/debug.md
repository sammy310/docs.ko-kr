---
title: Windows에서 .NET for Apache Spark 애플리케이션 디버그
description: Windows에서 .NET for Apache Spark 애플리케이션을 디버그하는 방법을 알아봅니다.
ms.date: 01/29/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: 25f5291c47dc1cdf2668cb077fae7439e330cc1c
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/01/2020
ms.locfileid: "76919933"
---
# <a name="debug-a-net-for-apache-spark-application"></a>.NET for Apache Spark 애플리케이션 디버그

이 방법은 Windows에서 .NET for Apache Spark 애플리케이션을 디버그하는 단계를 설명합니다.

## <a name="debug-your-application"></a>애플리케이션 디버그

새 명령 프롬프트 창을 열고 다음 명령을 실행합니다.

```shell
spark-submit \
  --class org.apache.spark.deploy.dotnet.DotnetRunner \
  --master local \
  <path-to-microsoft-spark-jar> \
  debug
```

이 명령을 실행하면 다음 출력이 표시됩니다.

```console
***********************************************************************
* .NET Backend running debug mode. Press enter to exit *
***********************************************************************
```

디버그 모드에서 DotnetRunner는 .NET 애플리케이션을 시작하지 않고 .NET 앱을 시작할 때까지 기다립니다. 이 명령 프롬프트 창을 열어 두고 C# 디버거를 통해 .NET 애플리케이션을 시작하여 애플리케이션을 디버그합니다. C# 디버거([Windows/macOS용 Visual Studio 디버거](https://visualstudio.microsoft.com/vs/) 또는 [Visual Studio Code의 C# 디버거 확장](https://code.visualstudio.com/Docs/editor/debugging))로 .NET 애플리케이션을 시작하여 애플리케이션을 디버그합니다.

## <a name="debug-a-user-defined-function-udf"></a>사용자 정의 함수(UDF) 디버그

> [!NOTE]
> 사용자 정의 함수는 Visual Studio 디버거를 사용하는 Windows에서만 지원됩니다.

`spark-submit`을 실행하기 전에 다음 환경 변수를 설정합니다.

```bat
set DOTNET_WORKER_DEBUG=1
```

Spark 애플리케이션을 실행하면 `Choose Just-In-Time Debugger` 창이 팝업됩니다. Visual Studio 디버거를 선택합니다.

디버거는 [TaskRunner.cs](https://github.com/dotnet/spark/blob/5e9c08b430b4bc56b5f42252c4b73437377afaed/src/csharp/Microsoft.Spark.Worker/TaskRunner.cs#L52)의 다음 위치에서 중단됩니다.

```csharp
if (EnvironmentUtils.GetEnvironmentVariableAsBool("DOTNET_WORKER_DEBUG"))
{
    Debugger.Launch(); // <-- The debugger will break here.
}
```

디버그하려는 UDF가 포함된 *.cs* 파일로 이동하여 [중단점을 설정](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints?view=vs-2019)합니다. 작업자가 아직 UDF가 포함된 어셈블리를 로드하지 않았기 때문에 중단점에 `The breakpoint will not currently be hit`가 표시됩니다.

`F5`를 눌러 애플리케이션을 계속하면 중단점이 결국 적중됩니다.

> [!NOTE] 
> 각 작업에 대해 Just-In-Time 디버거 선택 창이 팝업됩니다. 지나치게 많은 팝업을 방지하려면 실행기 수를 낮은 수로 설정하세요. 예를 들어 spark-submit의 **--master local[1]** 옵션을 사용하여 작업 수를 1로 설정하면 단일 디버거 인스턴스만 시작됩니다.

## <a name="debug-scala-code"></a>Scala 코드 디버그

Scala쪽 코드(`DotnetRunner`, `DotnetBackendHandler` 등)를 디버그해야 하는 경우, 다음 명령을 사용하고 실행 중인 프로세스에 [IntelliJ](https://www.jetbrains.com/help/idea/attaching-to-local-process.html)를 사용하여 디버거를 연결할 수 있습니다.

```shell
spark-submit \
  --driver-java-options -agentlib:jdwp=transport=dt_socket,server=y,suspend=n,address=5005 \
  --class org.apache.spark.deploy.dotnet.DotnetRunner \
  --master local \
  <path-to-microsoft-spark-jar> \
  <path-to-your-app-exe> <argument(s)-to-your-app>
```

명령을 실행한 후 [Intellij](https://www.jetbrains.com/help/idea/attaching-to-local-process.html)를 사용하여 실행 중인 프로세스에 디버거를 연결합니다.

## <a name="next-steps"></a>다음 단계

* [.NET for Apache Spark 시작](../tutorials/get-started.md)
* [Azure HDInsight에 .NET for Apache Spark 애플리케이션 배포](../tutorials/hdinsight-deployment.md)
* [Databricks에 .NET for Apache Spark 애플리케이션 배포](../tutorials/databricks-deployment.md)
* [Amazon EMR Spark에 .NET for Apache Spark 애플리케이션 배포](../tutorials/amazon-emr-spark-deployment.md)
