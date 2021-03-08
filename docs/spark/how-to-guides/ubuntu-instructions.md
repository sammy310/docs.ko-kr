---
title: Ubuntu에서 .NET for Apache Spark 애플리케이션 빌드
description: Ubuntu에서 .NET for Apache Spark 애플리케이션을 빌드하는 방법
ms.date: 10/09/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: ae5e0e24ef53b74bd34a2c0100c30a375d8bd71f
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "102103922"
---
# <a name="learn-how-to-build-your-net-for-apache-spark-application-on-ubuntu"></a><span data-ttu-id="a8e9a-103">Ubuntu에서 .NET for Apache Spark 애플리케이션을 빌드하는 방법</span><span class="sxs-lookup"><span data-stu-id="a8e9a-103">Learn how to build your .NET for Apache Spark application on Ubuntu</span></span>

<span data-ttu-id="a8e9a-104">이 문서에서는 Ubuntu에서 .NET for Apache Spark 애플리케이션을 빌드하는 방법을 배웁니다.</span><span class="sxs-lookup"><span data-stu-id="a8e9a-104">This article teaches you how to build your .NET for Apache Spark applications on Ubuntu.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a8e9a-105">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="a8e9a-105">Prerequisites</span></span>

<span data-ttu-id="a8e9a-106">다음 사전 요구 사항이 모두 있는 경우 [빌드](#build) 단계로 건너뛰세요.</span><span class="sxs-lookup"><span data-stu-id="a8e9a-106">If you already have all of the following prerequisites, skip to the [build](#build) steps.</span></span>

1. <span data-ttu-id="a8e9a-107">**[.NET Core 3.1 SDK](https://dotnet.microsoft.com/download/dotnet/3.1)** 를 다운로드하고 설치합니다. SDK를 설치하면 경로에 `dotnet` 도구 체인이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8e9a-107">Download and install **[.NET Core 3.1 SDK](https://dotnet.microsoft.com/download/dotnet/3.1)** - installing the SDK adds the `dotnet` toolchain to your path.</span></span>  <span data-ttu-id="a8e9a-108">.NET Core 2.1, 2.2, 3.1이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8e9a-108">.NET Core 2.1, 2.2 and 3.1 are supported.</span></span>

2. <span data-ttu-id="a8e9a-109">**[OpenJDK 8](https://openjdk.java.net/install/)** 을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="a8e9a-109">Install **[OpenJDK 8](https://openjdk.java.net/install/)**.</span></span>

   - <span data-ttu-id="a8e9a-110">다음 명령을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8e9a-110">You can use the following command:</span></span>

   ```bash
   sudo apt install openjdk-8-jdk
   ```

   * <span data-ttu-id="a8e9a-111">명령줄에서 `java`을 실행할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a8e9a-111">Verify you are able to run `java` from your command-line.</span></span>

      <span data-ttu-id="a8e9a-112">샘플 java -version 출력:</span><span class="sxs-lookup"><span data-stu-id="a8e9a-112">Sample java -version output:</span></span>

      ```bash
      openjdk version "1.8.0_191"
      OpenJDK Runtime Environment (build 1.8.0_191-8u191-b12-2ubuntu0.18.04.1-b12)
      OpenJDK 64-Bit Server VM (build 25.191-b12, mixed mode)
      ```

   * <span data-ttu-id="a8e9a-113">여러 OpenJDK 버전이 이미 설치되어 있고 OpenJDK 8을 선택하려면 다음 명령을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="a8e9a-113">If you already have multiple OpenJDK versions installed and want to select OpenJDK 8, use the following command:</span></span>

      ```bash
      sudo update-alternatives --config java
      ```

3. <span data-ttu-id="a8e9a-114">**[Apache Maven 3.6.0+](https://maven.apache.org/download.cgi)** 를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="a8e9a-114">Install **[Apache Maven 3.6.0+](https://maven.apache.org/download.cgi)**.</span></span>

   * <span data-ttu-id="a8e9a-115">다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a8e9a-115">Run the following command:</span></span>

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

       <span data-ttu-id="a8e9a-116">이러한 환경 변수는 터미널을 닫을 때 손실됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8e9a-116">Note that these environment variables will be lost when you close your terminal.</span></span> <span data-ttu-id="a8e9a-117">변경 내용을 영구적으로 적용하려면 `~/.bashrc` 파일에 `export` 줄을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a8e9a-117">If you want the changes to be permanent, add the `export` lines to your `~/.bashrc` file.</span></span>

   * <span data-ttu-id="a8e9a-118">명령줄에서 `mvn`을 실행할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a8e9a-118">Verify you are able to run `mvn` from your command-line</span></span>

       <span data-ttu-id="a8e9a-119">샘플 mvn -version 출력:</span><span class="sxs-lookup"><span data-stu-id="a8e9a-119">Sample mvn -version output:</span></span>

       ```output
       Apache Maven 3.6.0 (97c98ec64a1fdfee7767ce5ffb20918da4f719f3; 2018-10-24T18:41:47Z)
       Maven home: ~/bin/apache-maven-3.6.0
       Java version: 1.8.0_191, vendor: Oracle Corporation, runtime: /usr/lib/jvm/java-8-openjdk-amd64/jre
       Default locale: en, platform encoding: UTF-8
       OS name: "linux", version: "4.4.0-17763-microsoft", arch: "amd64", family: "unix"
       ```

4. <span data-ttu-id="a8e9a-120">**[Apache Spark 2.3+](https://spark.apache.org/downloads.html)** 를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="a8e9a-120">Install **[Apache Spark 2.3+](https://spark.apache.org/downloads.html)**.</span></span>
<span data-ttu-id="a8e9a-121">[Apache Spark 2.3+](https://spark.apache.org/downloads.html)를 다운로드하여 로컬 폴더(예: `~/bin/spark-3.0.1-bin-hadoop2.7`)에 압축을 풉니다.</span><span class="sxs-lookup"><span data-stu-id="a8e9a-121">Download [Apache Spark 2.3+](https://spark.apache.org/downloads.html) and extract it into a local folder (e.g., `~/bin/spark-3.0.1-bin-hadoop2.7`).</span></span> <span data-ttu-id="a8e9a-122">지원되는 Spark 버전은 2.3.\*, 2.4.0, 2.4.1, 2.4.3, 2.4.4, 2.4.5, 2.4.6, 2.4.7, 3.0.0 및 3.0.1입니다.</span><span class="sxs-lookup"><span data-stu-id="a8e9a-122">(The supported spark versions are 2.3.\*, 2.4.0, 2.4.1, 2.4.3, 2.4.4, 2.4.5, 2.4.6, 2.4.7, 3.0.0 and 3.0.1)</span></span>

   ```bash
   tar -xvzf /path/to/spark-3.0.1-bin-hadoop2.7.tgz -C ~/bin/spark-3.0.1-bin-hadoop2.7
   ```

   * <span data-ttu-id="a8e9a-123">필요한 [환경 변수](https://www.java.com/en/download/help/path.xml) `SPARK_HOME`(예: `~/bin/spark-3.0.1-bin-hadoop2.7/`) 및 `PATH`(예: `$SPARK_HOME/bin:$PATH`)를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a8e9a-123">Add the necessary [environment variables](https://www.java.com/en/download/help/path.xml) `SPARK_HOME` (e.g., `~/bin/spark-3.0.1-bin-hadoop2.7/`) and `PATH` (e.g., `$SPARK_HOME/bin:$PATH`)</span></span>

      ```bash
      export SPARK_HOME=~/bin/spark-3.0.1-hadoop2.7
      export PATH="$SPARK_HOME/bin:$PATH"
      source ~/.bashrc
      ```

      <span data-ttu-id="a8e9a-124">이러한 환경 변수는 터미널을 닫을 때 손실됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8e9a-124">Note that these environment variables will be lost when you close your terminal.</span></span> <span data-ttu-id="a8e9a-125">변경 내용을 영구적으로 적용하려면 `~/.bashrc` 파일에 `export` 줄을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a8e9a-125">If you want the changes to be permanent, add the `export` lines to your `~/.bashrc` file.</span></span>

   * <span data-ttu-id="a8e9a-126">명령줄에서 `spark-shell`을 실행할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a8e9a-126">Verify you are able to run `spark-shell` from your command-line.</span></span>

      <span data-ttu-id="a8e9a-127">샘플 콘솔 출력:</span><span class="sxs-lookup"><span data-stu-id="a8e9a-127">Sample console output:</span></span>

      ```
      Welcome to
            ____              __
           / __/__  ___ _____/ /__
          _\ \/ _ \/ _ `/ __/  '_/
         /___/ .__/\_,_/_/ /_/\_\   version 3.0.1
            /_/

      Using Scala version 2.12.10 (Java HotSpot(TM) 64-Bit Server VM, Java 1.8.0_201)
      Type in expressions to have them evaluated.
      Type :help for more information.

      scala> sc
      res0: org.apache.spark.SparkContext = org.apache.spark.SparkContext@6eaa6b0c
      ```

<span data-ttu-id="a8e9a-128">다음 섹션으로 이동하기 전에 명령줄에서 `dotnet`, `java`, `mvn`, `spark-shell`을 실행할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a8e9a-128">Make sure you are able to run `dotnet`, `java`, `mvn`, `spark-shell` from your command-line before you move to the next section.</span></span> <span data-ttu-id="a8e9a-129">더 나은 방법이 있나요?</span><span class="sxs-lookup"><span data-stu-id="a8e9a-129">Feel there is a better way?</span></span> <span data-ttu-id="a8e9a-130">[문제를 열고](https://github.com/dotnet/spark/issues) 자유롭게 참여하세요.</span><span class="sxs-lookup"><span data-stu-id="a8e9a-130">Please [open an issue](https://github.com/dotnet/spark/issues) and feel free to contribute.</span></span>

## <a name="build"></a><span data-ttu-id="a8e9a-131">빌드</span><span class="sxs-lookup"><span data-stu-id="a8e9a-131">Build</span></span>

<span data-ttu-id="a8e9a-132">이 가이드의 나머지 부분에서는 .NET for Apache Spark 리포지토리를 컴퓨터(예: `~/dotnet.spark/`)에 복제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8e9a-132">For the remainder of this guide, you will need to have cloned the .NET for Apache Spark repository into your machine e.g., `~/dotnet.spark/`.</span></span>

```bash
git clone https://github.com/dotnet/spark.git ~/dotnet.spark
```

### <a name="build-net-for-spark-scala-extensions-layer"></a><span data-ttu-id="a8e9a-133">.NET for Spark Scala 확장 레이어 빌드</span><span class="sxs-lookup"><span data-stu-id="a8e9a-133">Build .NET for Spark Scala extensions layer</span></span>

<span data-ttu-id="a8e9a-134">.NET 애플리케이션을 제출하면 .NET for Apache Spark에서 필요한 논리가 Scala로 작성되어 요청(예: 새 Spark 세션 만들기 요청, .NET 쪽에서 JVM 쪽으로 데이터 전송 요청 등)을 처리하는 방법을 Apache Spark에게 알려줍니다.</span><span class="sxs-lookup"><span data-stu-id="a8e9a-134">When you submit a .NET application, .NET for Apache Spark has the necessary logic written in Scala that informs Apache Spark how to handle your requests (e.g., request to create a new Spark Session, request to transfer data from .NET side to JVM side etc.).</span></span> <span data-ttu-id="a8e9a-135">이 논리는 [.NET for Apache Spark Scala 소스 코드](https://github.com/dotnet/spark/tree/master/src/scala)에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8e9a-135">This logic can be found in the [.NET for Apache Spark Scala Source Code](https://github.com/dotnet/spark/tree/master/src/scala).</span></span>

<span data-ttu-id="a8e9a-136">다음 단계는 .NET for Apache Spark Scala 확장 레이어를 빌드하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a8e9a-136">The next step is to build the .NET for Apache Spark Scala extension layer:</span></span>

```bash
cd src/scala
mvn clean package
```

<span data-ttu-id="a8e9a-137">지원되는 Spark 버전에 대해 생성된 JAR이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8e9a-137">You should see JARs created for the supported Spark versions:</span></span>

* `microsoft-spark-2-3\target\microsoft-spark-2-3_2.11-<spark-dotnet-version>.jar`
* `microsoft-spark-2-4\target\microsoft-spark-2-4_2.11-<spark-dotnet-version>.jar`
* `microsoft-spark-3-0\target\microsoft-spark-3-0_2.12-<spark-dotnet-version>.jar`

### <a name="build-net-sample-applications-using-net-core-cli"></a><span data-ttu-id="a8e9a-138">.NET Core CLI를 사용하여 .NET 샘플 애플리케이션 빌드</span><span class="sxs-lookup"><span data-stu-id="a8e9a-138">Build .NET sample applications using .NET Core CLI</span></span>

<span data-ttu-id="a8e9a-139">이 섹션에서는 .NET for Apache Spark용 [샘플 애플리케이션](https://github.com/dotnet/spark/tree/master/examples)을 빌드하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a8e9a-139">This section explains how to build the [sample applications](https://github.com/dotnet/spark/tree/master/examples) for .NET for Apache Spark.</span></span> <span data-ttu-id="a8e9a-140">이러한 단계는 모든 .NET for Spark 애플리케이션의 전체 빌드 프로세스를 이해하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8e9a-140">These steps will help in understanding the overall building process for any .NET for Spark application.</span></span>

1. <span data-ttu-id="a8e9a-141">작업자 빌드:</span><span class="sxs-lookup"><span data-stu-id="a8e9a-141">Build the worker:</span></span>

   ```dotnetcli
   cd ~/dotnet.spark/src/csharp/Microsoft.Spark.Worker/
   dotnet publish -f netcoreapp3.1 -r ubuntu.18.04-x64
   ```

   <span data-ttu-id="a8e9a-142">샘플 콘솔 출력:</span><span class="sxs-lookup"><span data-stu-id="a8e9a-142">Sample console output:</span></span>

   ```bash
   user@machine:/home/user/dotnet.spark/src/csharp/Microsoft.Spark.Worker$ dotnet publish -f netcoreapp3.1 -r ubuntu.18.04-x64
   Microsoft (R) Build Engine version 16.6.0+5ff7b0c9e for .NET Core
   Copyright (C) Microsoft Corporation. All rights reserved.

      Restore completed in 36.03 ms for /home/user/dotnet.spark/src/csharp/Microsoft.Spark.Worker/Microsoft.Spark.Worker.csproj.
      Restore completed in 35.94 ms for /home/user/dotnet.spark/src/csharp/Microsoft.Spark/Microsoft.Spark.csproj.
      Microsoft.Spark -> /home/user/dotnet.spark/artifacts/bin/Microsoft.Spark/Debug/netstandard2.1/Microsoft.Spark.dll
      Microsoft.Spark.Worker -> /home/user/dotnet.spark/artifacts/bin/Microsoft.Spark.Worker/Debug/netcoreapp3.1/ubuntu.18.04-x64/publish/Microsoft.Spark.Worker.dll
      Microsoft.Spark.Worker -> /home/user/dotnet.spark/artifacts/bin/Microsoft.Spark.Worker/Debug/netcoreapp3.1/ubuntu.18.04-x64/publish/
   ```

2. <span data-ttu-id="a8e9a-143">샘플 빌드:</span><span class="sxs-lookup"><span data-stu-id="a8e9a-143">Build the samples:</span></span>

   ```dotnetcli
   cd ~/dotnet.spark/examples/Microsoft.Spark.CSharp.Examples/
   dotnet publish -f netcoreapp3.1 -r ubuntu.18.04-x64
   ```

   <span data-ttu-id="a8e9a-144">샘플 콘솔 출력:</span><span class="sxs-lookup"><span data-stu-id="a8e9a-144">Sample console output:</span></span>

   ```bash
   user@machine:/home/user/dotnet.spark/examples/Microsoft.Spark.CSharp.Examples$ dotnet publish -f netcoreapp3.1 -r ubuntu.18.04-x64
   Microsoft (R) Build Engine version 16.6.0+5ff7b0c9e for .NET Core
   Copyright (C) Microsoft Corporation. All rights reserved.

      Restore completed in 37.11 ms for /home/user/dotnet.spark/src/csharp/Microsoft.Spark/Microsoft.Spark.csproj.
      Restore completed in 281.63 ms for /home/user/dotnet.spark/examples/Microsoft.Spark.CSharp.Examples/Microsoft.Spark.CSharp.Examples.csproj.
      Microsoft.Spark -> /home/user/dotnet.spark/artifacts/bin/Microsoft.Spark/Debug/netstandard2.1/Microsoft.Spark.dll
      Microsoft.Spark.CSharp.Examples -> /home/user/dotnet.spark/artifacts/bin/Microsoft.Spark.CSharp.Examples/Debug/netcoreapp3.1/ubuntu.18.04-x64/publish/Microsoft.Spark.CSharp.Examples.dll
      Microsoft.Spark.CSharp.Examples -> /home/user/dotnet.spark/artifacts/bin/Microsoft.Spark.CSharp.Examples/Debug/netcoreapp3.1/ubuntu.18.04-x64/publish/
   ```  

## <a name="run-the-net-for-spark-sample-applications"></a><span data-ttu-id="a8e9a-145">.NET for Spark 샘플 애플리케이션 실행</span><span class="sxs-lookup"><span data-stu-id="a8e9a-145">Run the .NET for Spark sample applications</span></span>

<span data-ttu-id="a8e9a-146">샘플을 빌드한 후 `spark-submit`을 사용하여 .NET Core 앱을 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8e9a-146">Once you build the samples, you can use `spark-submit` to submit your .NET Core apps.</span></span> <span data-ttu-id="a8e9a-147">[사전 요구 사항](#prerequisites) 섹션에 따라 Apache Spark를 설치했는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a8e9a-147">Make sure you have followed the [prerequisites](#prerequisites) section and installed Apache Spark.</span></span>

1. <span data-ttu-id="a8e9a-148">`Microsoft.Spark.Worker` 이진 파일이 생성된 경로(예: `~/dotnet.spark/artifacts/bin/Microsoft.Spark.Worker/Debug/netcoreapp3.1/ubuntu.18.04-x64/publish`)가 포함되도록 `DOTNET_WORKER_DIR` 또는 `PATH` 환경 변수를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a8e9a-148">Set the `DOTNET_WORKER_DIR` or `PATH` environment variable to include the path where the `Microsoft.Spark.Worker` binary has been generated (e.g., `~/dotnet.spark/artifacts/bin/Microsoft.Spark.Worker/Debug/netcoreapp3.1/ubuntu.18.04-x64/publish`).</span></span>

   ```bash
   export DOTNET_WORKER_DIR=~/dotnet.spark/artifacts/bin/Microsoft.Spark.Worker/Debug/netcoreapp3.1/ubuntu.18.04-x64/publish
   ```

2. <span data-ttu-id="a8e9a-149">터미널을 열고 앱 이진 파일이 생성된 디렉터리(예: `~/dotnet.spark/artifacts/bin/Microsoft.Spark.CSharp.Examples/Debug/netcoreapp3.1/ubuntu.18.04-x64/publish`)로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="a8e9a-149">Open a terminal and go to the directory where your app binary has been generated (e.g., `~/dotnet.spark/artifacts/bin/Microsoft.Spark.CSharp.Examples/Debug/netcoreapp3.1/ubuntu.18.04-x64/publish`).</span></span>

   ```bash
   cd ~/dotnet.spark/artifacts/bin/Microsoft.Spark.CSharp.Examples/Debug/netcoreapp3.1/ubuntu.18.04-x64/publish
   ```

3. <span data-ttu-id="a8e9a-150">앱 실행은 기본적 구조를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="a8e9a-150">Running your app follows the basic structure:</span></span>

   ```bash
   spark-submit \
     [--jars <any-jars-your-app-is-dependent-on>] \
     --class org.apache.spark.deploy.dotnet.DotnetRunner \
     --master local \
     <path-to-microsoft-spark-jar> \
     <path-to-your-app-binary> <argument(s)-to-your-app>
   ```

   <span data-ttu-id="a8e9a-151">다음은 실행할 수 있는 몇 가지 예입니다.</span><span class="sxs-lookup"><span data-stu-id="a8e9a-151">Here are some examples you can run:</span></span>

   * <span data-ttu-id="a8e9a-152">**[Microsoft.Spark.Examples.Sql.Batch.Basic](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Batch/Basic.cs)**</span><span class="sxs-lookup"><span data-stu-id="a8e9a-152">**[Microsoft.Spark.Examples.Sql.Batch.Basic](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Batch/Basic.cs)**</span></span>

      ```bash
      spark-submit \
      --class org.apache.spark.deploy.dotnet.DotnetRunner \
      --master local \
      ~/dotnet.spark/src/scala/microsoft-spark-<version>/target/microsoft-spark-<spark_majorversion-spark_minorversion>_<scala_majorversion.scala_minorversion>-<spark_dotnet_version>.jar \
      Microsoft.Spark.CSharp.Examples Sql.Batch.Basic $SPARK_HOME/examples/src/main/resources/people.json
      ```

   * <span data-ttu-id="a8e9a-153">**[Microsoft.Spark.Examples.Sql.Streaming.StructuredNetworkWordCount](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredNetworkWordCount.cs)**</span><span class="sxs-lookup"><span data-stu-id="a8e9a-153">**[Microsoft.Spark.Examples.Sql.Streaming.StructuredNetworkWordCount](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredNetworkWordCount.cs)**</span></span>

      ```bash
      spark-submit \
      --class org.apache.spark.deploy.dotnet.DotnetRunner \
      --master local \
      ~/dotnet.spark/src/scala/microsoft-spark-<version>/target/microsoft-spark-<spark_majorversion-spark_minorversion>_<scala_majorversion.scala_minorversion>-<spark_dotnet_version>.jar \
      Microsoft.Spark.CSharp.Examples Sql.Streaming.StructuredNetworkWordCount localhost 9999
      ```

   * <span data-ttu-id="a8e9a-154">**[Microsoft.Spark.Examples.Sql.Streaming.StructuredKafkaWordCount(maven 액세스 가능)](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs)**</span><span class="sxs-lookup"><span data-stu-id="a8e9a-154">**[Microsoft.Spark.Examples.Sql.Streaming.StructuredKafkaWordCount (maven accessible)](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs)**</span></span>

      ```bash
      spark-submit \
      --packages org.apache.spark:spark-sql-kafka-0-10_2.11:2.3.2 \
      --class org.apache.spark.deploy.dotnet.DotnetRunner \
      --master local \
      ~/dotnet.spark/src/scala/microsoft-spark-<version>/target/microsoft-spark-<spark_majorversion-spark_minorversion>_<scala_majorversion.scala_minorversion>-<spark_dotnet_version>.jar \
      Microsoft.Spark.CSharp.Examples Sql.Streaming.StructuredKafkaWordCount localhost:9092 subscribe test
      ```

   * <span data-ttu-id="a8e9a-155">**[Microsoft.Spark.Examples.Sql.Streaming.StructuredKafkaWordCount(jars 제공됨)](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs)**</span><span class="sxs-lookup"><span data-stu-id="a8e9a-155">**[Microsoft.Spark.Examples.Sql.Streaming.StructuredKafkaWordCount (jars provided)](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs)**</span></span>

      ```bash
      spark-submit \
      --jars path/to/net.jpountz.lz4/lz4-1.3.0.jar,path/to/org.apache.kafka/kafka-clients-0.10.0.1.jar,path/to/org.apache.spark/spark-sql-kafka-0-10_2.11-2.3.2.jar,`path/to/org.slf4j/slf4j-api-1.7.6.jar,path/to/org.spark-project.spark/unused-1.0.0.jar,path/to/org.xerial.snappy/snappy-java-1.1.2.6.jar \
      --class org.apache.spark.deploy.dotnet.DotnetRunner \
      --master local \
      ~/dotnet.spark/src/scala/microsoft-spark-<version>/target/microsoft-spark-<spark_majorversion-spark_minorversion>_<scala_majorversion.scala_minorversion>-<spark_dotnet_version>.jar \
      Microsoft.Spark.CSharp.Examples Sql.Streaming.StructuredKafkaWordCount localhost:9092 subscribe test
       ```
