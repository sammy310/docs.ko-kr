---
title: Ubuntu에서 .NET for Apache Spark 애플리케이션 빌드
description: Ubuntu에서 .NET for Apache Spark 애플리케이션을 빌드하는 방법
ms.date: 01/29/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: a12c861d0f231910f715a13fd41d1f3f0d6748a7
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/01/2020
ms.locfileid: "76928069"
---
# <a name="learn-how-to-build-your-net-for-apache-spark-application-on-ubuntu"></a>Ubuntu에서 .NET for Apache Spark 애플리케이션을 빌드하는 방법

이 문서에서는 Ubuntu에서 .NET for Apache Spark 애플리케이션을 빌드하는 방법을 배웁니다.

## <a name="prerequisites"></a>사전 요구 사항

다음 사전 요구 사항이 모두 있는 경우 [빌드](#build) 단계로 건너뛰세요.

1. **[.NET Core 2.1 SDK](https://dotnet.microsoft.com/download/dotnet-core/2.1)** 또는 **[.NET Core 3.1 SDK](https://dotnet.microsoft.com/download/dotnet-core/3.1)** 를 다운로드하고 설치합니다. SDK를 설치하면 경로에 `dotnet` 도구 체인이 추가됩니다.  .NET Core 2.1, 2.2, 3.1이 지원됩니다.

2. **[OpenJDK 8](https://openjdk.java.net/install/)** 을 설치합니다. 

   - 다음 명령을 사용할 수 있습니다.

   ```bash
   sudo apt install openjdk-8-jdk
   ```

   * 명령줄에서 `java`를 실행할 수 있는지 확인합니다.       

      샘플 java -version 출력:
          
      ```bash
      openjdk version "1.8.0_191"
      OpenJDK Runtime Environment (build 1.8.0_191-8u191-b12-2ubuntu0.18.04.1-b12)
      OpenJDK 64-Bit Server VM (build 25.191-b12, mixed mode)
      ```

   * 여러 OpenJDK 버전이 이미 설치되어 있고 OpenJDK 8을 선택하려면 다음 명령을 사용하세요.

      ```bash
      sudo update-alternatives --config java
      ```

3. **[Apache Maven 3.6.0+](https://maven.apache.org/download.cgi)** 를 설치합니다.

   * 다음 명령을 실행합니다.

      ```bash
      mkdir -p ~/bin/maven
      cd ~/bin/maven
      wget https://www-us.apache.org/dist/maven/maven-3/3.6.0/binaries/apache-maven-3.6.0-bin.tar.gz
      tar -xvzf apache-maven-3.6.0-bin.tar.gz
      ln -s apache-maven-3.6.0 current
      export M2_HOME=~/bin/maven/current
      export PATH=${M2_HOME}/bin:${PATH}
      source ~/.bashrc
      ```
       
       이러한 환경 변수는 터미널을 닫을 때 손실됩니다. 변경 내용을 영구적으로 적용하려면 `~/.bashrc` 파일에 `export` 줄을 추가합니다.

   * 명령줄에서 `mvn`을 실행할 수 있는지 확인합니다.       

       샘플 mvn -version 출력:
       
       ```
       Apache Maven 3.6.0 (97c98ec64a1fdfee7767ce5ffb20918da4f719f3; 2018-10-24T18:41:47Z)
       Maven home: ~/bin/apache-maven-3.6.0
       Java version: 1.8.0_191, vendor: Oracle Corporation, runtime: /usr/lib/jvm/java-8-openjdk-amd64/jre
       Default locale: en, platform encoding: UTF-8
       OS name: "linux", version: "4.4.0-17763-microsoft", arch: "amd64", family: "unix"
       ```

4. **[Apache Spark 2.3+](https://spark.apache.org/downloads.html)** 를 설치합니다.
[Apache Spark 2.3+](https://spark.apache.org/downloads.html)를 다운로드하여 로컬 폴더(예: `~/bin/spark-2.3.2-bin-hadoop2.7`)에 압축을 풉니다. (지원되는 Spark 버전은 2.3.*, 2.4.0, 2.4.1, 2.4.3, 2.4.4입니다.)

   ```bash
   tar -xvzf /path/to/spark-2.3.2-bin-hadoop2.7.tgz -C ~/bin/spark-2.3.2-bin-hadoop2.7
   ```

   * 필요한 [환경 변수](https://www.java.com/en/download/help/path.xml) `SPARK_HOME`(예: `~/bin/spark-2.3.2-bin-hadoop2.7/`) 및 `PATH`(예: `$SPARK_HOME/bin:$PATH`)를 추가합니다.

      ```bash
      export SPARK_HOME=~/bin/spark-2.3.2-hadoop2.7
      export PATH="$SPARK_HOME/bin:$PATH"
      source ~/.bashrc
      ```
       
      이러한 환경 변수는 터미널을 닫을 때 손실됩니다. 변경 내용을 영구적으로 적용하려면 `~/.bashrc` 파일에 `export` 줄을 추가합니다.

   * 명령줄에서 `spark-shell`을 실행할 수 있는지 확인합니다.

      샘플 콘솔 출력:
      
      ```
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

다음 섹션으로 이동하기 전에 명령줄에서 `dotnet`, `java`, `mvn`, `spark-shell`을 실행할 수 있는지 확인합니다. 더 나은 방법이 있나요? [문제를 열고](https://github.com/dotnet/spark/issues) 자유롭게 참여하세요.

## <a name="build"></a>빌드

이 가이드의 나머지 부분에서는 .NET for Apache Spark 리포지토리를 컴퓨터(예: `~/dotnet.spark/`)에 복제해야 합니다.

```bash
git clone https://github.com/dotnet/spark.git ~/dotnet.spark
```

### <a name="build-net-for-spark-scala-extensions-layer"></a>.NET for Spark Scala 확장 레이어 빌드

.NET 애플리케이션을 제출하면 .NET for Apache Spark에서 필요한 논리가 Scala로 작성되어 요청(예: 새 Spark 세션 만들기 요청, .NET 쪽에서 JVM 쪽으로 데이터 전송 요청 등)을 처리하는 방법을 Apache Spark에게 알려줍니다. 이 논리는 [.NET for Apache Spark Scala 소스 코드](https://github.com/dotnet/spark/tree/master/src/scala)에서 찾을 수 있습니다.

다음 단계는 .NET for Apache Spark Scala 확장 레이어를 빌드하는 것입니다.

```bash
cd src/scala
mvn clean package 
```

지원되는 Spark 버전에 대해 생성된 JAR이 표시됩니다.

* `microsoft-spark-2.3.x/target/microsoft-spark-2.3.x-<version>.jar`
* `microsoft-spark-2.4.x/target/microsoft-spark-2.4.x-<version>.jar`

### <a name="build-net-sample-applications-using-net-core-cli"></a>.NET Core CLI를 사용하여 .NET 샘플 애플리케이션 빌드

이 섹션에서는 .NET for Apache Spark용 [샘플 애플리케이션](https://github.com/dotnet/spark/tree/master/examples)을 빌드하는 방법에 대해 설명합니다. 이러한 단계는 모든 .NET for Spark 애플리케이션의 전체 빌드 프로세스를 이해하는 데 도움이 됩니다.

1. 작업자 빌드:

   ```dotnetcli
   cd ~/dotnet.spark/src/csharp/Microsoft.Spark.Worker/
   dotnet publish -f netcoreapp2.1 -r ubuntu.18.04-x64
   ```
      
   샘플 콘솔 출력:

   ```bash
   user@machine:/home/user/dotnet.spark/src/csharp/Microsoft.Spark.Worker$ dotnet publish -f netcoreapp2.1 -r ubuntu.18.04-x64
   Microsoft (R) Build Engine version 16.0.462+g62fb89029d for .NET Core
   Copyright (C) Microsoft Corporation. All rights reserved.
      
      Restore completed in 36.03 ms for /home/user/dotnet.spark/src/csharp/Microsoft.Spark.Worker/Microsoft.Spark.Worker.csproj.
      Restore completed in 35.94 ms for /home/user/dotnet.spark/src/csharp/Microsoft.Spark/Microsoft.Spark.csproj.
      Microsoft.Spark -> /home/user/dotnet.spark/artifacts/bin/Microsoft.Spark/Debug/netstandard2.0/Microsoft.Spark.dll
      Microsoft.Spark.Worker -> /home/user/dotnet.spark/artifacts/bin/Microsoft.Spark.Worker/Debug/netcoreapp2.1/ubuntu.18.04-x64/Microsoft.Spark.Worker.dll
      Microsoft.Spark.Worker -> /home/user/dotnet.spark/artifacts/bin/Microsoft.Spark.Worker/Debug/netcoreapp2.1/ubuntu.18.04-x64/publish/
   ```

2. 샘플 빌드:

   ```dotnetcli
   cd ~/dotnet.spark/examples/Microsoft.Spark.CSharp.Examples/
   dotnet publish -f netcoreapp2.1 -r ubuntu.18.04-x64
   ```
      
   샘플 콘솔 출력:

   ```bash
   user@machine:/home/user/dotnet.spark/examples/Microsoft.Spark.CSharp.Examples$ dotnet publish -f netcoreapp2.1 -r ubuntu.18.04-x64
   Microsoft (R) Build Engine version 16.0.462+g62fb89029d for .NET Core
   Copyright (C) Microsoft Corporation. All rights reserved.

      Restore completed in 37.11 ms for /home/user/dotnet.spark/src/csharp/Microsoft.Spark/Microsoft.Spark.csproj.
      Restore completed in 281.63 ms for /home/user/dotnet.spark/examples/Microsoft.Spark.CSharp.Examples/Microsoft.Spark.CSharp.Examples.csproj.
      Microsoft.Spark -> /home/user/dotnet.spark/artifacts/bin/Microsoft.Spark/Debug/netstandard2.0/Microsoft.Spark.dll
      Microsoft.Spark.CSharp.Examples -> /home/user/dotnet.spark/artifacts/bin/Microsoft.Spark.CSharp.Examples/Debug/netcoreapp2.1/ubuntu.18.04-x64/Microsoft.Spark.CSharp.Examples.dll
      Microsoft.Spark.CSharp.Examples -> /home/user/dotnet.spark/artifacts/bin/Microsoft.Spark.CSharp.Examples/Debug/netcoreapp2.1/ubuntu.18.04-x64/publish/
   ```  

## <a name="run-the-net-for-spark-sample-applications"></a>.NET for Spark 샘플 애플리케이션 실행

샘플을 빌드한 후 `spark-submit`을 사용하여 .NET Core 앱을 제출할 수 있습니다. [사전 요구 사항](#prerequisites) 섹션에 따라 Apache Spark를 설치했는지 확인합니다.

1. `Microsoft.Spark.Worker` 이진 파일이 생성된 경로(예: `~/dotnet.spark/artifacts/bin/Microsoft.Spark.Worker/Debug/netcoreapp2.1/ubuntu.18.04-x64/publish`)가 포함되도록 `DOTNET_WORKER_DIR` 또는 `PATH` 환경 변수를 설정합니다.

   ```bash
   export DOTNET_WORKER_DIR=~/dotnet.spark/artifacts/bin/Microsoft.Spark.Worker/Debug/netcoreapp2.1/ubuntu.18.04-x64/publish
   ```

2. 터미널을 열고 앱 이진 파일이 생성된 디렉터리(예: `~/dotnet.spark/artifacts/bin/Microsoft.Spark.CSharp.Examples/Debug/netcoreapp2.1/ubuntu.18.04-x64/publish`)로 이동합니다.

   ```bash
   cd ~/dotnet.spark/artifacts/bin/Microsoft.Spark.CSharp.Examples/Debug/netcoreapp2.1/ubuntu.18.04-x64/publish
   ```

3. 앱 실행은 기본적 구조를 따릅니다.

   ```bash
   spark-submit \
     [--jars <any-jars-your-app-is-dependent-on>] \
     --class org.apache.spark.deploy.dotnet.DotnetRunner \
     --master local \
     <path-to-microsoft-spark-jar> \
     <path-to-your-app-binary> <argument(s)-to-your-app>
   ```

   다음은 실행할 수 있는 몇 가지 예입니다.

   * **[Microsoft.Spark.Examples.Sql.Batch.Basic](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Batch/Basic.cs)**

      ```bash
      spark-submit \
      --class org.apache.spark.deploy.dotnet.DotnetRunner \
      --master local \
      ~/dotnet.spark/src/scala/microsoft-spark-<version>/target/microsoft-spark-<version>.jar \
      Microsoft.Spark.CSharp.Examples Sql.Batch.Basic $SPARK_HOME/examples/src/main/resources/people.json
      ```

   * **[Microsoft.Spark.Examples.Sql.Streaming.StructuredNetworkWordCount](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredNetworkWordCount.cs)**

      ```bash
      spark-submit \
      --class org.apache.spark.deploy.dotnet.DotnetRunner \
      --master local \
      ~/dotnet.spark/src/scala/microsoft-spark-<version>/target/microsoft-spark-<version>.jar \
      Microsoft.Spark.CSharp.Examples Sql.Streaming.StructuredNetworkWordCount localhost 9999
      ```

   * **[Microsoft.Spark.Examples.Sql.Streaming.StructuredKafkaWordCount(maven 액세스 가능)](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs)**

      ```bash
      spark-submit \
      --packages org.apache.spark:spark-sql-kafka-0-10_2.11:2.3.2 \
      --class org.apache.spark.deploy.dotnet.DotnetRunner \
      --master local \
      ~/dotnet.spark/src/scala/microsoft-spark-<version>/target/microsoft-spark-<version>.jar \
      Microsoft.Spark.CSharp.Examples Sql.Streaming.StructuredKafkaWordCount localhost:9092 subscribe test
      ```

   * **[Microsoft.Spark.Examples.Sql.Streaming.StructuredKafkaWordCount(jars 제공됨)](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs)**

      ```bash
      spark-submit \
      --jars path/to/net.jpountz.lz4/lz4-1.3.0.jar,path/to/org.apache.kafka/kafka-clients-0.10.0.1.jar,path/to/org.apache.spark/spark-sql-kafka-0-10_2.11-2.3.2.jar,`path/to/org.slf4j/slf4j-api-1.7.6.jar,path/to/org.spark-project.spark/unused-1.0.0.jar,path/to/org.xerial.snappy/snappy-java-1.1.2.6.jar \
      --class org.apache.spark.deploy.dotnet.DotnetRunner \
      --master local \
      ~/dotnet.spark/src/scala/microsoft-spark-<version>/target/microsoft-spark-<version>.jar \
      Microsoft.Spark.CSharp.Examples Sql.Streaming.StructuredKafkaWordCount localhost:9092 subscribe test
       ```
