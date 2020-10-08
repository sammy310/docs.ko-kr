---
title: Windows에서 .NET for Apache Spark 애플리케이션 빌드
description: Windows에서 .NET for Apache Spark 애플리케이션을 빌드하는 방법을 알아봅니다.
ms.date: 06/25/2020
ms.topic: conceptual
ms.custom: how-to
ms.openlocfilehash: d355380e92235e799d366dca02eaf8450f563f33
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2020
ms.locfileid: "91609280"
---
# <a name="learn-how-to-build-your-net-for-apache-spark-application-on-windows"></a>Windows에서 .NET for Apache Spark 애플리케이션을 빌드하는 방법

이 문서에서는 Windows에서 .NET for Apache Spark 애플리케이션을 빌드하는 방법을 배웁니다.

[!INCLUDE [spark-preview-note](../../../includes/spark-preview-note.md)]

## <a name="prerequisites"></a>사전 요구 사항

다음 사전 요구 사항이 모두 있는 경우 [빌드](#build) 단계로 건너뛰세요.

  1. **[.NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core/2.1)** 를 다운로드하고 설치합니다. SDK를 설치하면 경로에 `dotnet` 도구 체인이 추가됩니다. .NET Core 2.1, 2.2, 3.1이 지원됩니다.
  2. **[Visual Studio 2019](https://www.visualstudio.com/downloads/)** (버전 16.3 이상)를 설치합니다. Community 버전은 완전 무료입니다. 설치를 구성할 때 적어도 다음 구성 요소를 포함시킵니다.
     * .NET 데스크톱 개발
       * 필요한 모든 구성 요소
         * .NET Framework 4.6.1 개발 도구
     * .NET Core 플랫폼 간 개발
       * 필요한 모든 구성 요소
  3. **[Java 1.8](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)** 을 설치합니다.
     - 운영 체제에 적합한 버전을 선택합니다. 예를 들어 Windows x64 머신의 경우 *jdk-8u201-windows-x64.exe*를 선택합니다.
     - 설치 프로그램을 사용하여 설치하고 명령줄에서 `java`를 실행할 수 있는지 확인합니다.
  4. **[Apache Maven 3.6.0+](https://maven.apache.org/download.cgi)** 를 설치합니다.
     - [Apache Maven 3.6.0](http://mirror.metrocast.net/apache/maven/maven-3/3.6.3/binaries/apache-maven-3.6.3-bin.zip)을 다운로드합니다.
     - 로컬 디렉터리로 추출합니다. 예를 들어 *C:\bin\apache-maven-3.6.0\*으로 추출합니다.
     - Apache Maven을 [PATH 환경 변수](https://www.java.com/en/download/help/path.xml)에 추가합니다. 예를 들어 *C:\bin\apache-maven-3.6.0\bin*과 같이 추가합니다.
     - 명령줄에서 `mvn`을 실행할 수 있는지 확인합니다.
  5. **[Apache Spark 2.3+](https://spark.apache.org/downloads.html)** 를 설치합니다.
     - [Apache Spark 2.3+](https://spark.apache.org/downloads.html)를 다운로드하고 [7-zip](https://www.7-zip.org/)을 사용하여 로컬 폴더(예: *C:\bin\spark-2.3.2-bin-hadoop2.7\*)로 추출합니다. (지원되는 Spark 버전은 2.3.* , 2.4.0, 2.4.1, 2.4.3, 2.4.4입니다.)
     - [새 환경 변수](https://www.java.com/en/download/help/path.xml) `SPARK_HOME`을 추가합니다. 예를 들어 *C:\bin\spark-2.3.2-bin-hadoop2.7\*과 같이 추가합니다.

       ```powershell
       set SPARK_HOME=C:\bin\spark-2.3.2-bin-hadoop2.7\
       ```

     - Apache Spark를 [PATH 환경 변수](https://www.java.com/en/download/help/path.xml)에 추가합니다. 예를 들어 *C:\bin\spark-2.3.2-bin-hadoop2.7\bin*과 같이 추가합니다.

       ```powershell
       set PATH=%SPARK_HOME%\bin;%PATH%
       ```

     - 명령줄에서 `spark-shell`을 실행할 수 있는지 확인합니다.
        샘플 콘솔 출력:

        ```output
        Welcome to
              ____              __
             / __/__  ___ _____/ /__
            _\ \/ _ \/ _ `/ __/  '_/
           /___/ .__/\_,_/_/ /_/\_\   version 2.3.2
              /_/

        Using Scala version 2.11.8 (Java HotSpot(TM) 64-Bit Server VM, Java 1.8.0_201)
        Type in expressions to have them evaluated.
        Type :help for more information.

        scala> sc
        res0: org.apache.spark.SparkContext = org.apache.spark.SparkContext@6eaa6b0c
        ```

        </details>

  6. **[WinUtils](https://github.com/steveloughran/winutils)** 를 설치합니다.
     - [WinUtils 리포지토리](https://github.com/steveloughran/winutils)에서 `winutils.exe` 이진 파일을 다운로드합니다. 해당 Spark 배포의 컴파일에 사용된 Hadoop 버전을 선택해야 합니다. 예를 들어 Spark 2.3.2의 경우 hadoop-2.7.1을 사용합니다.
     - `winutils.exe` 이진 파일을 원하는 디렉터리에 저장합니다. 예를 들어 *C:\hadoop\bin*에 저장합니다.
     - (bin 없이) winutils.exe가 있는 디렉터리를 반영하도록 `HADOOP_HOME`을 설정합니다. 예를 들어 명령줄을 사용하여

       ```powershell
       set HADOOP_HOME=C:\hadoop
       ```

     - `%HADOOP_HOME%\bin`을 포함하도록 PATH 환경 변수를 설정합니다. 예를 들어 다음과 같이 명령줄을 사용하여 설정합니다.

       ```powershell
       set PATH=%HADOOP_HOME%\bin;%PATH%
       ```

다음 섹션으로 이동하기 전에 명령줄에서 `dotnet`, `java`, `mvn`, `spark-shell`을 실행할 수 있는지 확인합니다. 더 나은 방법이 있나요? [문제를 만들고](https://github.com/dotnet/spark/issues) 자유롭게 참여하세요.

> [!NOTE]
> 환경 변수가 업데이트된 경우 명령줄의 새 인스턴스가 필요할 수 있습니다.

## <a name="build"></a>빌드

이 가이드의 나머지 부분에서는 .NET for Apache Spark 리포지토리를 컴퓨터에 복제해야 합니다. 복제된 리포지토리의 위치를 선택할 수 있습니다. 예를 들어 *C:\github\dotnet-spark\*를 사용합니다.

```bash
git clone https://github.com/dotnet/spark.git C:\github\dotnet-spark
```

### <a name="build-net-for-apache-spark-scala-extensions-layer"></a>.NET for Apache Spark Scala 확장 레이어 빌드

.NET 애플리케이션을 제출하면 .NET for Apache Spark에서 필요한 논리가 Scala로 작성되어 요청(예: 새 Spark 세션 만들기 요청, .NET 쪽에서 JVM 쪽으로 데이터 전송 요청 등)을 처리하는 방법을 Apache Spark에 알려줍니다. 이 논리는 [.NET for Spark Scala 소스 코드](https://github.com/dotnet/spark/tree/master/src/scala)에서 찾을 수 있습니다.

.NET Framework를 사용하는지 .NET Core를 사용하는지에 상관없이 .NET for Apache Spark Scala 확장 레이어를 빌드해야 합니다.

```powershell
cd src\scala
mvn clean package
```

지원되는 Spark 버전에 대해 생성된 JAR이 표시됩니다.

* `microsoft-spark-2.3.x\target\microsoft-spark-2.3.x-<version>.jar`
* `microsoft-spark-2.4.x\target\microsoft-spark-2.4.x-<version>.jar`

### <a name="build-the-net-for-spark-sample-applications"></a>.NET for Spark 샘플 애플리케이션 빌드

이 섹션에서는 .NET for Apache Spark용 [샘플 애플리케이션](https://github.com/dotnet/spark/tree/master/examples)을 빌드하는 방법에 대해 설명합니다. 이러한 단계는 모든 .NET for Spark 애플리케이션의 전체 빌드 프로세스를 이해하는 데 도움이 됩니다.

#### <a name="using-visual-studio-for-net-framework"></a>.NET Framework 용 Visual Studio 사용

  1. Visual Studio에서 `src\csharp\Microsoft.Spark.sln`을 열고 `examples` 폴더 아래에 `Microsoft.Spark.CSharp.Examples` 프로젝트를 빌드합니다(그러면 .NET 바인딩 프로젝트도 빌드됨). 원하는 경우 `Microsoft.Spark.Examples` 프로젝트에서 자체 코드를 작성할 수 있습니다(이 예의 'input_file.json'은 데이터 프레임를 만들 데이터가 포함된 json 파일입니다).
  
      ```csharp
        // Instantiate a session
        var spark = SparkSession
            .Builder()
            .AppName("Hello Spark!")
            .GetOrCreate();

        // Create initial DataFrame
        DataFrame df = spark.Read().Json(input_file.json);

        // Print schema
        df.PrintSchema();

        // Apply a filter and show results
        df.Filter(df["age"] > 21).Show();
      ```

     빌드가 성공하면 출력 디렉터리에 생성된 적절한 이진 파일이 표시됩니다.
     샘플 콘솔 출력:

      ```powershell
            Directory: C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.CSharp.Examples\Debug\net461


        Mode                LastWriteTime         Length Name
        ----                -------------         ------ ----
        -a----         3/6/2019  12:18 AM         125440 Apache.Arrow.dll
        -a----        3/16/2019  12:00 AM          13824 Microsoft.Spark.CSharp.Examples.exe
        -a----        3/16/2019  12:00 AM          19423 Microsoft.Spark.CSharp.Examples.exe.config
        -a----        3/16/2019  12:00 AM           2720 Microsoft.Spark.CSharp.Examples.pdb
        -a----        3/16/2019  12:00 AM         143360 Microsoft.Spark.dll
        -a----        3/16/2019  12:00 AM          63388 Microsoft.Spark.pdb
        -a----        3/16/2019  12:00 AM          34304 Microsoft.Spark.Worker.exe
        -a----        3/16/2019  12:00 AM          19423 Microsoft.Spark.Worker.exe.config
        -a----        3/16/2019  12:00 AM          11900 Microsoft.Spark.Worker.pdb
        -a----        3/16/2019  12:00 AM          23552 Microsoft.Spark.Worker.xml
        -a----        3/16/2019  12:00 AM         332363 Microsoft.Spark.xml
        ------------------------------------------- More framework files -------------------------------------
      ```

#### <a name="using-net-core-cli-for-net-core"></a>.NET Core용 .NET Core CLI 사용

> [!NOTE]
> 현재 Spark .NET을 위한 .NET Core 빌드를 자동화하는 작업을 진행 중입니다. 그때까지는 일부 단계를 수동으로 수행하는 것을 감수해 주시면 고맙겠습니다.

  1. 작업자 빌드:

      ```powershell
      cd C:\github\dotnet-spark\src\csharp\Microsoft.Spark.Worker\
      dotnet publish -f netcoreapp2.1 -r win10-x64
      ```

      샘플 콘솔 출력:

      ```powershell
      PS C:\github\dotnet-spark\src\csharp\Microsoft.Spark.Worker> dotnet publish -f netcoreapp2.1 -r win10-x64
      Microsoft (R) Build Engine version 16.0.462+g62fb89029d for .NET Core
      Copyright (C) Microsoft Corporation. All rights reserved.

        Restore completed in 299.95 ms for C:\github\dotnet-spark\src\csharp\Microsoft.Spark\Microsoft.Spark.csproj.
        Restore completed in 306.62 ms for C:\github\dotnet-spark\src\csharp\Microsoft.Spark.Worker\Microsoft.Spark.Worker.csproj.
        Microsoft.Spark -> C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark\Debug\netstandard2.0\Microsoft.Spark.dll
        Microsoft.Spark.Worker -> C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.Worker\Debug\netcoreapp2.1\win10-x64\Microsoft.Spark.Worker.dll
        Microsoft.Spark.Worker -> C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.Worker\Debug\netcoreapp2.1\win10-x64\publish\
      ```

  2. 샘플 빌드:

      ```powershell
      cd C:\github\dotnet-spark\examples\Microsoft.Spark.CSharp.Examples\
      dotnet publish -f netcoreapp2.1 -r win10-x64
      ```

      샘플 콘솔 출력:

      ```powershell
      PS C:\github\dotnet-spark\examples\Microsoft.Spark.CSharp.Examples> dotnet publish -f netcoreapp2.1 -r win10-x64
      Microsoft (R) Build Engine version 16.0.462+g62fb89029d for .NET Core
      Copyright (C) Microsoft Corporation. All rights reserved.

        Restore completed in 44.22 ms for C:\github\dotnet-spark\src\csharp\Microsoft.Spark\Microsoft.Spark.csproj.
        Restore completed in 336.94 ms for C:\github\dotnet-spark\examples\Microsoft.Spark.CSharp.Examples\Microsoft.Spark.CSharp.Examples.csproj.
        Microsoft.Spark -> C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark\Debug\netstandard2.0\Microsoft.Spark.dll
        Microsoft.Spark.CSharp.Examples -> C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.CSharp.Examples\Debug\netcoreapp2.1\win10-x64\Microsoft.Spark.CSharp.Examples.dll
        Microsoft.Spark.CSharp.Examples -> C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.CSharp.Examples\Debug\netcoreapp2.1\win10-x64\publish\
      ```

## <a name="run-the-net-for-spark-sample-applications"></a>.NET for Spark 샘플 애플리케이션 실행

샘플을 빌드한 후에는 .NET Framework 또는 .NET Core를 대상으로 하는지 여부에 관계 없이 `spark-submit`을 통해 샘플이 실행됩니다. [사전 요구 사항](#prerequisites) 섹션에 따라 Apache Spark를 설치했는지 확인합니다.

  1. `Microsoft.Spark.Worker` 이진 파일이 생성된 경로(예: .NET Framework의 경우 *C:\github\dotnet\spark\artifacts\bin\Microsoft.Spark.Worker\Debug\net461*, .NET Core의 경우 *C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.Worker\Debug\netcoreapp2.1\win10-x64\publish*)를 포함하도록 `DOTNET_WORKER_DIR` 또는 `PATH` 환경 변수를 설정합니다.

      ```powershell
      set DOTNET_WORKER_DIR=C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.Worker\Debug\netcoreapp2.1\win10-x64\publish
      ```
  
  2. PowerShell을 열고 앱 이진 파일이 생성된 디렉터리(예: .NET Framework의 경우 *C:\github\dotnet\spark\artifacts\bin\Microsoft.Spark.CSharp.Examples\Debug\net461*, .NET Core의 경우 *C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.CSharp.Examples\Debug\netcoreapp2.1\win10-x64\publish*)로 이동합니다.

      ```powershell
      cd C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.CSharp.Examples\Debug\netcoreapp2.1\win10-x64\publish
      ```

  3. 앱 실행은 기본적 구조를 따릅니다.

     ```powershell
     spark-submit.cmd `
       [--jars <any-jars-your-app-is-dependent-on>] `
       --class org.apache.spark.deploy.dotnet.DotnetRunner `
       --master local `
       <path-to-microsoft-spark-jar> `
       <path-to-your-app-exe> <argument(s)-to-your-app>
     ```

     다음은 실행할 수 있는 몇 가지 예입니다.

     - **[Microsoft.Spark.Examples.Sql.Batch.Basic](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Batch/Basic.cs)**

         ```powershell
         spark-submit.cmd `
         --class org.apache.spark.deploy.dotnet.DotnetRunner `
         --master local `
         C:\github\dotnet-spark\src\scala\microsoft-spark-<version>\target\microsoft-spark-<version>.jar `
         Microsoft.Spark.CSharp.Examples.exe Sql.Batch.Basic %SPARK_HOME%\examples\src\main\resources\people.json
         ```

     - **[Microsoft.Spark.Examples.Sql.Streaming.StructuredNetworkWordCount](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredNetworkWordCount.cs)**

         ```powershell
         spark-submit.cmd `
         --class org.apache.spark.deploy.dotnet.DotnetRunner `
         --master local `
         C:\github\dotnet-spark\src\scala\microsoft-spark-<version>\target\microsoft-spark-<version>.jar `
         Microsoft.Spark.CSharp.Examples.exe Sql.Streaming.StructuredNetworkWordCount localhost 9999
         ```

     - **[Microsoft.Spark.Examples.Sql.Streaming.StructuredKafkaWordCount(maven 액세스 가능)](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs)**

         ```powershell
         spark-submit.cmd `
         --packages org.apache.spark:spark-sql-kafka-0-10_2.11:2.3.2 `
         --class org.apache.spark.deploy.dotnet.DotnetRunner `
         --master local `
         C:\github\dotnet-spark\src\scala\microsoft-spark-<version>\target\microsoft-spark-<version>.jar `
         Microsoft.Spark.CSharp.Examples.exe Sql.Streaming.StructuredKafkaWordCount localhost:9092 subscribe test
         ```

     - **[Microsoft.Spark.Examples.Sql.Streaming.StructuredKafkaWordCount(jars 제공됨)](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs)**

         ```powershell
         spark-submit.cmd
         --jars path\to\net.jpountz.lz4\lz4-1.3.0.jar,path\to\org.apache.kafka\kafka-clients-0.10.0.1.jar,path\to\org.apache.spark\spark-sql-kafka-0-10_2.11-2.3.2.jar,`path\to\org.slf4j\slf4j-api-1.7.6.jar,path\to\org.spark-project.spark\unused-1.0.0.jar,path\to\org.xerial.snappy\snappy-java-1.1.2.6.jar `
         --class org.apache.spark.deploy.dotnet.DotnetRunner `
         --master local `
         C:\github\dotnet-spark\src\scala\microsoft-spark-<version>\target\microsoft-spark-<version>.jar `
         Microsoft.Spark.CSharp.Examples.exe Sql.Streaming.StructuredKafkaWordCount localhost:9092 subscribe test
          ```
