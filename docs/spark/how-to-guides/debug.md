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
# <a name="debug-a-net-for-apache-spark-application"></a>.NET for Apache Spark 애플리케이션 디버그

이 방법은 Windows에서 .NET for Apache Spark 애플리케이션과 Scala 코드를 디버그하기 위해 실행해야 하는 명령을 제공합니다.

## <a name="debug-your-application"></a>애플리케이션 디버그

새 명령 프롬프트 창을 열고 다음을 실행합니다.

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

이 디버그 모드에서 `DotnetRunner`는 .NET 애플리케이션을 시작하지 않지만 연결될 때까지 기다립니다. 이 명령 프롬프트 창을 열어 둡니다.

이제 디버거와 함께 .NET 애플리케이션을 실행하여 애플리케이션을 디버그할 수 있습니다.

## <a name="debug-scala-code"></a>Scala 코드 디버그

`DotnetRunner` 또는 `DotnetBackendHandler`와 같은 Scala 쪽 코드를 디버그해야 하는 경우 다음 명령을 실행합니다.

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
