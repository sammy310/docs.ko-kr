---
title: .NET for Apache Spark를 사용한 구조적 스트리밍 자습서
description: 이 자습서에서는 Spark 구조적 스트리밍을 위해 .NET for Apache Spark를 사용하는 방법을 알아봅니다.
author: mamccrea
ms.author: mamccrea
ms.date: 06/25/2020
ms.topic: tutorial
ms.openlocfilehash: 5420fe081db1704d7af647e8c88826c1bcf614d9
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617845"
---
# <a name="tutorial-structured-streaming-with-net-for-apache-spark"></a>자습서: .NET for Apache Spark를 사용한 구조적 스트리밍

이 자습서에서는 .NET for Apache Spark를 사용하여 Spark 구조적 스트리밍을 호출하는 방법을 설명합니다. Spark 구조적 스트리밍은 실시간 데이터 스트림을 처리하기 위한 Apache Spark의 지원 기능입니다. 스트림 처리는 라이브 데이터를 생성하는 동안 분석하는 것을 의미합니다.

이 자습서에서는 다음과 같은 작업을 수행하는 방법을 살펴봅니다.

> [!div class="checklist"]
>
> * .NET for Apache Spark 애플리케이션 만들기 및 실행
> * netcat을 사용하여 데이터 스트림 만들기
> * 사용자 정의 함수 및 SparkSQL를 사용하여 스트리밍 데이터 분석

[!INCLUDE [spark-preview-note](../../../includes/spark-preview-note.md)]

## <a name="prerequisites"></a>사전 요구 사항

첫 번째 .NET for Apache Spark 애플리케이션인 경우 [자습서 시작](get-started.md)을 먼저 시작하여 기본 사항을 숙지하세요.

## <a name="create-a-console-application"></a>콘솔 애플리케이션 만들기

1. 명령 프롬프트에서 다음 명령을 실행하여 새 콘솔 애플리케이션을 만듭니다.

   ```dotnetcli
   dotnet new console -o mySparkStreamingApp
   cd mySparkStreamingApp
   ```

   `dotnet` 명령은 `console` 형식의 `new` 애플리케이션을 자동으로 만듭니다. `-o` 매개 변수는 앱이 저장되는 *mySparkStreamingApp*이라는 디렉터리를 만들고 필요한 파일로 채웁니다. `cd mySparkStreamingApp` 명령은 디렉터리를 방금 만든 앱 디렉터리로 변경합니다.

1. 앱에서 .NET for Apache Spark를 사용하려면 Microsoft.Spark 패키지를 설치합니다. 콘솔에서 다음 명령을 실행합니다.

   ```dotnetcli
   dotnet add package Microsoft.Spark
   ```

## <a name="establish-and-connect-to-a-data-stream"></a>데이터 스트림 설정 및 연결

스트림 처리를 테스트하는 일반적인 방법 중 하나는 **netcat**을 사용하는 것입니다. netcat(*nc*라고도 함)를 사용하여 네트워크 연결에서 읽고 쓸 수 있습니다. 터미널 창에서 netcat을 사용하여 네트워크 연결을 설정합니다.

### <a name="create-a-data-stream-with-netcat"></a>netcat을 사용하여 데이터 스트림 만들기

1. [netcat을 다운로드](https://sourceforge.net/projects/nc110/files/)합니다. 그런 다음, zip 다운로드에서 파일의 압축을 풀고 "PATH" 환경 변수에 압출을 푼 해당 디렉터리를 추가합니다.

2. 새 연결을 시작하려면 새 콘솔을 열고 포트 9999에서 localhost에 연결하는 다음 명령을 실행합니다.

   Windows에서:

   ```console
   nc -vvv -l -p 9999
   ```

   Linux에서:

   ```console
   nc -lk 9999
   ```

   Spark 프로그램은 이 명령 프롬프트에 입력하는 입력을 수신 대기합니다.

### <a name="create-a-sparksession"></a>SparkSession 만들기

1. 다음 추가 `using` 문을 *mySparkStreamingApp*에서 *Program.cs* 파일의 맨 위에 추가합니다.

   ```csharp
   using System;
   using Microsoft.Spark.Sql;
   using Microsoft.Spark.Sql.Streaming;
   using static Microsoft.Spark.Sql.Functions;
   ```

1. `Main` 메서드에 다음 코드를 추가하여 새 `SparkSession`을 만듭니다. Spark 세션은 Dataset 및 DataFrame API를 사용하여 Spark를 프로그래밍하기 위한 진입점입니다.

   ```csharp
   SparkSession spark = SparkSession
        .Builder()
        .AppName("Streaming example with a UDF")
        .GetOrCreate();
   ```

   위에서 만든 *spark* 개체를 호출하면 프로그램 전체에서 Spark 및 DataFrame 기능에 액세스할 수 있습니다.

### <a name="connect-to-a-stream-with-readstream"></a>ReadStream()을 사용하여 스트림에 연결

`ReadStream()` 메서드는 스트리밍 데이터를 `DataFrame`으로 읽는 데 사용할 수 있는 `DataStreamReader`를 반환합니다. Spark 앱이 스트리밍 데이터 위치를 알리도록 하려면 호스트 및 포트 정보를 포함합니다.

```csharp
DataFrame lines = spark
    .ReadStream()
    .Format("socket")
    .Option("host", hostname)
    .Option("port", port)
    .Load();
```

## <a name="register-a-user-defined-function"></a>사용자 정의 함수 등록

Spark 애플리케이션에서 *사용자 정의 함수*인 UDF를 사용하여 데이터에 대한 계산 및 분석을 수행할 수 있습니다.

`Main` 메서드에 다음 코드를 추가하여 `udfArray`라는 UDF를 등록합니다.

```csharp
Func<Column, Column> udfArray =
    Udf<string, string[]>((str) => new string[] { str, $"{str} {str.Length}" });
```

이 UDF는 netcat 터미널에서 수신하는 각 문자열을 처리하여 원래 문자열(*str*에 포함됨)과 원래 문자열의 길이가 연결된 원래 문자열을 포함하는 배열을 생성합니다.

예를 들어 netcat 터미널에 *Hello world*를 입력하면 다음과 같은 배열이 생성됩니다.

* 배열\[0] = Hello world
* 배열\[1] = Hello world 11

## <a name="use-sparksql"></a>SparkSQL 사용

SparkSQL을 사용하여 데이터 프레임에 저장된 데이터에 대해 다양한 기능을 수행할 수 있습니다. UDF와 SparkSQL을 결합하여 데이터 프레임의 각 행에 UDF를 적용하는 것이 일반적입니다.

```csharp
DataFrame arrayDF = lines.Select(Explode(udfArray(lines["value"])));
```

이 코드 조각은 netcat 터미널에서 읽은 각 문자열을 나타내는 데이터 프레임의 각 값에 *udfArray*를 적용합니다. SparkSQL 메서드 <xref:Microsoft.Spark.Sql.Functions.Explode%2A>를 적용하여 배열의 각 항목을 자체 행에 배치합니다. 마지막으로 <xref:Microsoft.Spark.Sql.DataFrame.Select%2A>를 사용하여 새 데이터 프레임 *arrayDF*에 생성한 열을 배치합니다.

## <a name="display-your-stream"></a>스트림 표시

<xref:Microsoft.Spark.Sql.DataFrame.WriteStream>을 사용하여 콘솔 결과를 인쇄하고 최신 출력만 표시하는 등 출력의 특성을 설정할 수 있습니다.

```csharp
StreamingQuery query = arrayDf
    .WriteStream()
    .Format("console")
    .Start();
```

## <a name="run-your-code"></a>코드 실행

Spark의 구조적 스트리밍은 일련의 소규모 **일괄 처리**를 통해 데이터를 처리합니다.  프로그램을 실행할 때 netcat 연결을 설정하는 명령 프롬프트로 입력을 시작할 수 있습니다. 해당 명령 프롬프트에서 데이터를 입력한 후 Enter 키를 누를 때마다 Spark는 항목을 일괄 처리로 간주하고 UDF를 실행합니다.

### <a name="use-spark-submit-to-run-your-app"></a>spark-submit을 사용하여 앱 실행

새 netcat 세션을 시작한 후 새 터미널을 열고 다음 명령과 유사한 `spark-submit` 명령을 실행합니다.

```powershell
spark-submit --class org.apache.spark.deploy.dotnet.DotnetRunner --master local /path/to/microsoft-spark-<version>.jar Microsoft.Spark.CSharp.Examples.exe Sql.Streaming.StructuredNetworkCharacterCount localhost 9999
```

> [!NOTE]
> 위의 명령을 Microsoft Spark jar 파일의 실제 경로로 업데이트해야 합니다. 또한 위의 명령은 netcat 서버가 localhost 포트 9999에서 실행되는 것으로 가정합니다.

## <a name="get-the-code"></a>코드 가져오기

이 자습서에서는 [StructuredNetworkCharacterCount.cs](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredNetworkCharacterCount.cs) 예제를 사용하지만 GitHub에는 세 가지의 전체 스트림 처리 예제가 있습니다.

* [StructuredNetworkWordCount.cs](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredNetworkWordCount.cs): 원본에서 스트리밍된 데이터의 단어 개수
* [StructuredNetworkWordCountWindowed.cs](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredNetworkWordCountWindowed.cs): 창 작업 논리를 사용하는 데이터의 단어 개수
* [StructuredKafkaWordCount.cs](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs): Kafka에서 스트리밍된 데이터의 단어 개수

## <a name="next-steps"></a>다음 단계

다음 문서로 이동하여 Databricks에 .NET for Apache Spark 애플리케이션을 배포하는 방법을 알아보세요.
> [!div class="nextstepaction"]
> [자습서: Databricks에 .NET for Apache Spark 애플리케이션 배포](databricks-deployment.md)
