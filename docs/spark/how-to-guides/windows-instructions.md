---
title: Windows에서 .NET for Apache Spark 애플리케이션 빌드
description: Windows에서 .NET for Apache Spark 애플리케이션을 빌드하는 방법을 알아봅니다.
ms.date: 01/29/2020
ms.topic: conceptual
ms.custom: how-to
ms.openlocfilehash: 640459c8c80b6d798718b89d4965802cdacd6c63
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628659"
---
# <a name="learn-how-to-build-your-net-for-apache-spark-application-on-windows"></a><span data-ttu-id="dcf14-103">Windows에서 .NET for Apache Spark 애플리케이션을 빌드하는 방법</span><span class="sxs-lookup"><span data-stu-id="dcf14-103">Learn how to build your .NET for Apache Spark application on Windows</span></span>

<span data-ttu-id="dcf14-104">이 문서에서는 Windows에서 .NET for Apache Spark 애플리케이션을 빌드하는 방법을 배웁니다.</span><span class="sxs-lookup"><span data-stu-id="dcf14-104">This article teaches you how to build your .NET for Apache Spark applications on Windows.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="dcf14-105">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="dcf14-105">Prerequisites</span></span>

<span data-ttu-id="dcf14-106">다음 사전 요구 사항이 모두 있는 경우 [빌드](#build) 단계로 건너뛰세요.</span><span class="sxs-lookup"><span data-stu-id="dcf14-106">If you already have all of the following prerequisites, skip to the [build](#build) steps.</span></span>

  1. <span data-ttu-id="dcf14-107">**[.NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core/2.1)** 를 다운로드하고 설치합니다. SDK를 설치하면 경로에 `dotnet` 도구 체인이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcf14-107">Download and install the **[.NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core/2.1)** - installing the SDK will add the `dotnet` toolchain to your path.</span></span> <span data-ttu-id="dcf14-108">.NET Core 2.1, 2.2, 3.1이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcf14-108">.NET Core 2.1, 2.2 and 3.1 are supported.</span></span>
  2. <span data-ttu-id="dcf14-109">**[Visual Studio 2019](https://www.visualstudio.com/downloads/)** (버전 16.3 이상)를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="dcf14-109">Install **[Visual Studio 2019](https://www.visualstudio.com/downloads/)** (Version 16.3 or later).</span></span> <span data-ttu-id="dcf14-110">Community 버전은 완전 무료입니다.</span><span class="sxs-lookup"><span data-stu-id="dcf14-110">The Community version is completely free.</span></span> <span data-ttu-id="dcf14-111">설치를 구성할 때 적어도 다음 구성 요소를 포함시킵니다.</span><span class="sxs-lookup"><span data-stu-id="dcf14-111">When configuring your installation, include these components at minimum:</span></span>
     * <span data-ttu-id="dcf14-112">.NET 데스크톱 개발</span><span class="sxs-lookup"><span data-stu-id="dcf14-112">.NET desktop development</span></span>
       * <span data-ttu-id="dcf14-113">필요한 모든 구성 요소</span><span class="sxs-lookup"><span data-stu-id="dcf14-113">All Required Components</span></span>
         * <span data-ttu-id="dcf14-114">.NET Framework 4.6.1 개발 도구</span><span class="sxs-lookup"><span data-stu-id="dcf14-114">.NET Framework 4.6.1 Development Tools</span></span>
     * <span data-ttu-id="dcf14-115">.NET Core 플랫폼 간 개발</span><span class="sxs-lookup"><span data-stu-id="dcf14-115">.NET Core cross-platform development</span></span>
       * <span data-ttu-id="dcf14-116">필요한 모든 구성 요소</span><span class="sxs-lookup"><span data-stu-id="dcf14-116">All Required Components</span></span>
  3. <span data-ttu-id="dcf14-117">**[Java 1.8](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)** 을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="dcf14-117">Install **[Java 1.8](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)**.</span></span> 
     - <span data-ttu-id="dcf14-118">운영 체제에 적합한 버전을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="dcf14-118">Select the appropriate version for your operating system.</span></span> <span data-ttu-id="dcf14-119">예를 들어 Windows x64 머신의 경우 *jdk-8u201-windows-x64.exe*를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="dcf14-119">For example, *jdk-8u201-windows-x64.exe* for Windows x64 machine.</span></span>
     - <span data-ttu-id="dcf14-120">설치 프로그램을 사용하여 설치하고 명령줄에서 `java`를 실행할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="dcf14-120">Install using the installer and verify you are able to run `java` from your command line.</span></span>
  4. <span data-ttu-id="dcf14-121">**[Apache Maven 3.6.0+](https://maven.apache.org/download.cgi)** 를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="dcf14-121">Install **[Apache Maven 3.6.0+](https://maven.apache.org/download.cgi)**.</span></span>
     - <span data-ttu-id="dcf14-122">[Apache Maven 3.6.0](http://mirror.metrocast.net/apache/maven/maven-3/3.6.3/binaries/apache-maven-3.6.3-bin.zip)을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="dcf14-122">Download [Apache Maven 3.6.0](http://mirror.metrocast.net/apache/maven/maven-3/3.6.3/binaries/apache-maven-3.6.3-bin.zip).</span></span>
     - <span data-ttu-id="dcf14-123">로컬 디렉터리로 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="dcf14-123">Extract to a local directory.</span></span> <span data-ttu-id="dcf14-124">예를 들어 \*C:\bin\apache-maven-3.6.0\*으로 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="dcf14-124">For example, \*C:\bin\apache-maven-3.6.0\*.</span></span>
     - <span data-ttu-id="dcf14-125">Apache Maven을 [PATH 환경 변수](https://www.java.com/en/download/help/path.xml)에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="dcf14-125">Add Apache Maven to your [PATH environment variable](https://www.java.com/en/download/help/path.xml).</span></span> <span data-ttu-id="dcf14-126">예를 들어 *C:\bin\apache-maven-3.6.0\bin*과 같이 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="dcf14-126">For example, *C:\bin\apache-maven-3.6.0\bin*.</span></span>
     - <span data-ttu-id="dcf14-127">명령줄에서 `mvn`을 실행할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="dcf14-127">Verify you are able to run `mvn` from your command-line.</span></span>
  5. <span data-ttu-id="dcf14-128">**[Apache Spark 2.3+](https://spark.apache.org/downloads.html)** 를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="dcf14-128">Install **[Apache Spark 2.3+](https://spark.apache.org/downloads.html)**.</span></span>
     - <span data-ttu-id="dcf14-129">[Apache Spark 2.3+](https://spark.apache.org/downloads.html)를 다운로드하고 [7-zip](https://www.7-zip.org/)을 사용하여 로컬 폴더(예: *C:\bin\spark-2.3.2-bin-hadoop2.7\*)로 추출합니다. (지원되는 Spark 버전은 2.3.* , 2.4.0, 2.4.1, 2.4.3, 2.4.4입니다.)</span><span class="sxs-lookup"><span data-stu-id="dcf14-129">Download [Apache Spark 2.3+](https://spark.apache.org/downloads.html) and extract it into a local folder (for example, *C:\bin\spark-2.3.2-bin-hadoop2.7\*) using [7-zip](https://www.7-zip.org/). (The supported spark versions are 2.3.*, 2.4.0, 2.4.1, 2.4.3 and 2.4.4)</span></span>
     - <span data-ttu-id="dcf14-130">[새 환경 변수](https://www.java.com/en/download/help/path.xml) `SPARK_HOME`을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="dcf14-130">Add a [new environment variable](https://www.java.com/en/download/help/path.xml) `SPARK_HOME`.</span></span> <span data-ttu-id="dcf14-131">예를 들어 \*C:\bin\spark-2.3.2-bin-hadoop2.7\*과 같이 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="dcf14-131">For example, \*C:\bin\spark-2.3.2-bin-hadoop2.7\*.</span></span>

       ```powershell
       set SPARK_HOME=C:\bin\spark-2.3.2-bin-hadoop2.7\       
       ```

     - <span data-ttu-id="dcf14-132">Apache Spark를 [PATH 환경 변수](https://www.java.com/en/download/help/path.xml)에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="dcf14-132">Add Apache Spark to your [PATH environment variable](https://www.java.com/en/download/help/path.xml).</span></span> <span data-ttu-id="dcf14-133">예를 들어 *C:\bin\spark-2.3.2-bin-hadoop2.7\bin*과 같이 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="dcf14-133">For example, *C:\bin\spark-2.3.2-bin-hadoop2.7\bin*.</span></span>

       ```powershell       
       set PATH=%SPARK_HOME%\bin;%PATH%
       ```
     
     - <span data-ttu-id="dcf14-134">명령줄에서 `spark-shell`을 실행할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="dcf14-134">Verify you are able to run `spark-shell` from your command-line.</span></span>        
        <span data-ttu-id="dcf14-135">샘플 콘솔 출력:</span><span class="sxs-lookup"><span data-stu-id="dcf14-135">Sample console output:</span></span>

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

        </details>

  6. <span data-ttu-id="dcf14-136">**[WinUtils](https://github.com/steveloughran/winutils)** 를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="dcf14-136">Install **[WinUtils](https://github.com/steveloughran/winutils)**.</span></span>
     - <span data-ttu-id="dcf14-137">[WinUtils 리포지토리](https://github.com/steveloughran/winutils)에서 `winutils.exe` 이진 파일을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="dcf14-137">Download `winutils.exe` binary from [WinUtils repository](https://github.com/steveloughran/winutils).</span></span> <span data-ttu-id="dcf14-138">해당 Spark 배포의 컴파일에 사용된 Hadoop 버전을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcf14-138">You should select the version of Hadoop the Spark distribution was compiled with.</span></span> <span data-ttu-id="dcf14-139">예를 들어 Spark 2.3.2의 경우 hadoop-2.7.1을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="dcf14-139">For exammple, use hadoop-2.7.1 for Spark 2.3.2.</span></span>
     - <span data-ttu-id="dcf14-140">`winutils.exe` 이진 파일을 원하는 디렉터리에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="dcf14-140">Save `winutils.exe` binary to a directory of your choice.</span></span> <span data-ttu-id="dcf14-141">예를 들어 *C:\hadoop\bin*에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="dcf14-141">For example, *C:\hadoop\bin*.</span></span>
     - <span data-ttu-id="dcf14-142">(bin 없이) winutils.exe가 있는 디렉터리를 반영하도록 `HADOOP_HOME`을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="dcf14-142">Set `HADOOP_HOME` to reflect the directory with winutils.exe (without bin).</span></span> <span data-ttu-id="dcf14-143">예를 들어 명령줄을 사용하여</span><span class="sxs-lookup"><span data-stu-id="dcf14-143">For instance, using command-line:</span></span>

       ```powershell
       set HADOOP_HOME=C:\hadoop
       ```

     - <span data-ttu-id="dcf14-144">`%HADOOP_HOME%\bin`을 포함하도록 PATH 환경 변수를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="dcf14-144">Set PATH environment variable to include `%HADOOP_HOME%\bin`.</span></span> <span data-ttu-id="dcf14-145">예를 들어 다음과 같이 명령줄을 사용하여 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="dcf14-145">For instance, using command line:</span></span>

       ```powershell
       set PATH=%HADOOP_HOME%\bin;%PATH%
       ```

<span data-ttu-id="dcf14-146">다음 섹션으로 이동하기 전에 명령줄에서 `dotnet`, `java`, `mvn`, `spark-shell`을 실행할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="dcf14-146">Make sure you are able to run `dotnet`, `java`, `mvn`, `spark-shell` from your command line before you move to the next section.</span></span> <span data-ttu-id="dcf14-147">더 나은 방법이 있나요?</span><span class="sxs-lookup"><span data-stu-id="dcf14-147">Feel there is a better way?</span></span> <span data-ttu-id="dcf14-148">[문제를 만들고](https://github.com/dotnet/spark/issues) 자유롭게 참여하세요.</span><span class="sxs-lookup"><span data-stu-id="dcf14-148">[Open an issue](https://github.com/dotnet/spark/issues) and feel free to contribute.</span></span>

> [!NOTE]
> <span data-ttu-id="dcf14-149">환경 변수가 업데이트된 경우 명령줄의 새 인스턴스가 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcf14-149">A new instance of the command line may be required if any environment variables were updated.</span></span>

## <a name="build"></a><span data-ttu-id="dcf14-150">빌드</span><span class="sxs-lookup"><span data-stu-id="dcf14-150">Build</span></span>

<span data-ttu-id="dcf14-151">이 가이드의 나머지 부분에서는 .NET for Apache Spark 리포지토리를 머신에 복제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcf14-151">For the remainder of this guide, you will need to have cloned the .NET for Apache Spark repository into your machine.</span></span> <span data-ttu-id="dcf14-152">복제된 리포지토리의 위치를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcf14-152">You can choose any location for the cloned repository.</span></span> <span data-ttu-id="dcf14-153">예를 들어 \*C:\github\dotnet-spark\*를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="dcf14-153">For example, \*C:\github\dotnet-spark\*.</span></span>

```bash
git clone https://github.com/dotnet/spark.git C:\github\dotnet-spark
```

### <a name="build-net-for-apache-spark-scala-extensions-layer"></a><span data-ttu-id="dcf14-154">.NET for Apache Spark Scala 확장 레이어 빌드</span><span class="sxs-lookup"><span data-stu-id="dcf14-154">Build .NET for Apache Spark Scala extensions layer</span></span>

<span data-ttu-id="dcf14-155">.NET 애플리케이션을 제출하면 .NET for Apache Spark에서 필요한 논리가 Scala로 작성되어 요청(예: 새 Spark 세션 만들기 요청, .NET 쪽에서 JVM 쪽으로 데이터 전송 요청 등)을 처리하는 방법을 Apache Spark에 알려줍니다.</span><span class="sxs-lookup"><span data-stu-id="dcf14-155">When you submit a .NET application, .NET for Apache Spark has the necessary logic written in Scala that informs Apache Spark how to handle your requests (for example, request to create a new Spark Session, request to transfer data from .NET side to JVM side etc.).</span></span> <span data-ttu-id="dcf14-156">이 논리는 [.NET for Spark Scala 소스 코드](https://github.com/dotnet/spark/tree/master/src/scala)에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcf14-156">This logic can be found in the [.NET for Spark Scala Source Code](https://github.com/dotnet/spark/tree/master/src/scala).</span></span>

<span data-ttu-id="dcf14-157">.NET Framework를 사용하는지 .NET Core를 사용하는지에 상관없이 .NET for Apache Spark Scala 확장 레이어를 빌드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcf14-157">Regardless of whether you are using .NET Framework or .NET Core, you will need to build the .NET for Apache Spark Scala extension layer:</span></span>

```powershell
cd src\scala
mvn clean package 
```

<span data-ttu-id="dcf14-158">지원되는 Spark 버전에 대해 생성된 JAR이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcf14-158">You should see JARs created for the supported Spark versions:</span></span>

* `microsoft-spark-2.3.x\target\microsoft-spark-2.3.x-<version>.jar`
* `microsoft-spark-2.4.x\target\microsoft-spark-2.4.x-<version>.jar`

### <a name="build-the-net-for-spark-sample-applications"></a><span data-ttu-id="dcf14-159">.NET for Spark 샘플 애플리케이션 빌드</span><span class="sxs-lookup"><span data-stu-id="dcf14-159">Build the .NET for Spark sample applications</span></span>

<span data-ttu-id="dcf14-160">이 섹션에서는 .NET for Apache Spark용 [샘플 애플리케이션](https://github.com/dotnet/spark/tree/master/examples)을 빌드하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="dcf14-160">This section explains how to build the [sample applications](https://github.com/dotnet/spark/tree/master/examples) for .NET for Apache Spark.</span></span> <span data-ttu-id="dcf14-161">이러한 단계는 모든 .NET for Spark 애플리케이션의 전체 빌드 프로세스를 이해하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcf14-161">These steps will help in understanding the overall building process for any .NET for Spark application.</span></span>

#### <a name="using-visual-studio-for-net-framework"></a><span data-ttu-id="dcf14-162">.NET Framework 용 Visual Studio 사용</span><span class="sxs-lookup"><span data-stu-id="dcf14-162">Using Visual Studio for .NET Framework</span></span>

  1. <span data-ttu-id="dcf14-163">Visual Studio에서 `src\csharp\Microsoft.Spark.sln`을 열고 `examples` 폴더 아래에 `Microsoft.Spark.CSharp.Examples` 프로젝트를 빌드합니다(그러면 .NET 바인딩 프로젝트도 빌드됨).</span><span class="sxs-lookup"><span data-stu-id="dcf14-163">Open `src\csharp\Microsoft.Spark.sln` in Visual Studio and build the `Microsoft.Spark.CSharp.Examples` project under the `examples` folder (this will in turn build the .NET bindings project as well).</span></span> <span data-ttu-id="dcf14-164">원하는 경우 `Microsoft.Spark.Examples` 프로젝트에서 자체 코드를 작성할 수 있습니다(이 예의 'input_file.json'은 데이터 프레임를 만들 데이터가 포함된 json 파일입니다).</span><span class="sxs-lookup"><span data-stu-id="dcf14-164">If you want, you can write your own code in the `Microsoft.Spark.Examples` project (the 'input_file.json' in this example is a json file with the data you want to create the dataframe with):</span></span>
  
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

     <span data-ttu-id="dcf14-165">빌드가 성공하면 출력 디렉터리에 생성된 적절한 이진 파일이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcf14-165">Once the build is successful, you will see the appropriate binaries produced in the output directory.</span></span>     
     <span data-ttu-id="dcf14-166">샘플 콘솔 출력:</span><span class="sxs-lookup"><span data-stu-id="dcf14-166">Sample console output:</span></span>
     
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

#### <a name="using-net-core-cli-for-net-core"></a><span data-ttu-id="dcf14-167">.NET Core용 .NET Core CLI 사용</span><span class="sxs-lookup"><span data-stu-id="dcf14-167">Using .NET Core CLI for .NET Core</span></span>

> [!NOTE]
> <span data-ttu-id="dcf14-168">현재 Spark .NET을 위한 .NET Core 빌드를 자동화하는 작업을 진행 중입니다.</span><span class="sxs-lookup"><span data-stu-id="dcf14-168">We are currently working on automating .NET Core builds for Spark .NET.</span></span> <span data-ttu-id="dcf14-169">그때까지는 일부 단계를 수동으로 수행하는 것을 감수해 주시면 고맙겠습니다.</span><span class="sxs-lookup"><span data-stu-id="dcf14-169">Until then, we appreciate your patience in performing some of the steps manually.</span></span>

  1. <span data-ttu-id="dcf14-170">작업자 빌드:</span><span class="sxs-lookup"><span data-stu-id="dcf14-170">Build the worker:</span></span>

      ```powershell
      cd C:\github\dotnet-spark\src\csharp\Microsoft.Spark.Worker\
      dotnet publish -f netcoreapp2.1 -r win10-x64
      ```
      
      <span data-ttu-id="dcf14-171">샘플 콘솔 출력:</span><span class="sxs-lookup"><span data-stu-id="dcf14-171">Sample console output:</span></span>

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

  2. <span data-ttu-id="dcf14-172">샘플 빌드:</span><span class="sxs-lookup"><span data-stu-id="dcf14-172">Build the samples:</span></span>

      ```powershell
      cd C:\github\dotnet-spark\examples\Microsoft.Spark.CSharp.Examples\
      dotnet publish -f netcoreapp2.1 -r win10-x64
      ```
   
      <span data-ttu-id="dcf14-173">샘플 콘솔 출력:</span><span class="sxs-lookup"><span data-stu-id="dcf14-173">Sample console output:</span></span>

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

## <a name="run-the-net-for-spark-sample-applications"></a><span data-ttu-id="dcf14-174">.NET for Spark 샘플 애플리케이션 실행</span><span class="sxs-lookup"><span data-stu-id="dcf14-174">Run the .NET for Spark sample applications</span></span>

<span data-ttu-id="dcf14-175">샘플을 빌드한 후에는 .NET Framework 또는 .NET Core를 대상으로 하는지 여부에 관계 없이 `spark-submit`을 통해 샘플이 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcf14-175">Once you build the samples, running them will be through `spark-submit` regardless of whether you are targeting .NET Framework or .NET Core.</span></span> <span data-ttu-id="dcf14-176">[사전 요구 사항](#prerequisites) 섹션에 따라 Apache Spark를 설치했는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="dcf14-176">Make sure you have followed the [prerequisites](#prerequisites) section and installed Apache Spark.</span></span>

  1. <span data-ttu-id="dcf14-177">`Microsoft.Spark.Worker` 이진 파일이 생성된 경로(예: .NET Framework의 경우 *C:\github\dotnet\spark\artifacts\bin\Microsoft.Spark.Worker\Debug\net461*, .NET Core의 경우 *C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.Worker\Debug\netcoreapp2.1\win10-x64\publish*)를 포함하도록 `DOTNET_WORKER_DIR` 또는 `PATH` 환경 변수를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="dcf14-177">Set the `DOTNET_WORKER_DIR` or `PATH` environment variable to include the path where the `Microsoft.Spark.Worker` binary has been generated (for example, *C:\github\dotnet\spark\artifacts\bin\Microsoft.Spark.Worker\Debug\net461* for .NET Framework, *C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.Worker\Debug\netcoreapp2.1\win10-x64\publish* for .NET Core):</span></span>

      ```powershell
      set DOTNET_WORKER_DIR=C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.Worker\Debug\netcoreapp2.1\win10-x64\publish
      ```
  
  2. <span data-ttu-id="dcf14-178">Powershell을 열고 앱 이진 파일이 생성된 디렉터리(예: .NET Framework의 경우 *C:\github\dotnet\spark\artifacts\bin\Microsoft.Spark.CSharp.Examples\Debug\net461*, .NET Core의 경우 *C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.CSharp.Examples\Debug\netcoreapp2.1\win10-x64\publish*)로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="dcf14-178">Open Powershell and go to the directory where your app binary has been generated (for example, *C:\github\dotnet\spark\artifacts\bin\Microsoft.Spark.CSharp.Examples\Debug\net461* for .NET Framework, *C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.CSharp.Examples\Debug\netcoreapp2.1\win10-x64\publish* for .NET Core):</span></span>

      ```powershell
      cd C:\github\dotnet-spark\artifacts\bin\Microsoft.Spark.CSharp.Examples\Debug\netcoreapp2.1\win10-x64\publish
      ```

  3. <span data-ttu-id="dcf14-179">앱 실행은 기본적 구조를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="dcf14-179">Running your app follows the basic structure:</span></span>

     ```powershell
     spark-submit.cmd `
       [--jars <any-jars-your-app-is-dependent-on>] `
       --class org.apache.spark.deploy.dotnet.DotnetRunner `
       --master local `
       <path-to-microsoft-spark-jar> `
       <path-to-your-app-exe> <argument(s)-to-your-app>
     ```

     <span data-ttu-id="dcf14-180">다음은 실행할 수 있는 몇 가지 예입니다.</span><span class="sxs-lookup"><span data-stu-id="dcf14-180">Here are some examples you can run:</span></span>

     - <span data-ttu-id="dcf14-181">**[Microsoft.Spark.Examples.Sql.Batch.Basic](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Batch/Basic.cs)**</span><span class="sxs-lookup"><span data-stu-id="dcf14-181">**[Microsoft.Spark.Examples.Sql.Batch.Basic](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Batch/Basic.cs)**</span></span>

         ```powershell
         spark-submit.cmd `
         --class org.apache.spark.deploy.dotnet.DotnetRunner `
         --master local `
         C:\github\dotnet-spark\src\scala\microsoft-spark-<version>\target\microsoft-spark-<version>.jar `
         Microsoft.Spark.CSharp.Examples.exe Sql.Batch.Basic %SPARK_HOME%\examples\src\main\resources\people.json
         ```

     - <span data-ttu-id="dcf14-182">**[Microsoft.Spark.Examples.Sql.Streaming.StructuredNetworkWordCount](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredNetworkWordCount.cs)**</span><span class="sxs-lookup"><span data-stu-id="dcf14-182">**[Microsoft.Spark.Examples.Sql.Streaming.StructuredNetworkWordCount](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredNetworkWordCount.cs)**</span></span>

         ```powershell
         spark-submit.cmd `
         --class org.apache.spark.deploy.dotnet.DotnetRunner `
         --master local `
         C:\github\dotnet-spark\src\scala\microsoft-spark-<version>\target\microsoft-spark-<version>.jar `
         Microsoft.Spark.CSharp.Examples.exe Sql.Streaming.StructuredNetworkWordCount localhost 9999
         ```

     - <span data-ttu-id="dcf14-183">**[Microsoft.Spark.Examples.Sql.Streaming.StructuredKafkaWordCount(maven 액세스 가능)](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs)**</span><span class="sxs-lookup"><span data-stu-id="dcf14-183">**[Microsoft.Spark.Examples.Sql.Streaming.StructuredKafkaWordCount (maven accessible)](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs)**</span></span>

         ```powershell
         spark-submit.cmd `
         --packages org.apache.spark:spark-sql-kafka-0-10_2.11:2.3.2 `
         --class org.apache.spark.deploy.dotnet.DotnetRunner `
         --master local `
         C:\github\dotnet-spark\src\scala\microsoft-spark-<version>\target\microsoft-spark-<version>.jar `
         Microsoft.Spark.CSharp.Examples.exe Sql.Streaming.StructuredKafkaWordCount localhost:9092 subscribe test
         ```

     - <span data-ttu-id="dcf14-184">**[Microsoft.Spark.Examples.Sql.Streaming.StructuredKafkaWordCount(jars 제공됨)](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs)**</span><span class="sxs-lookup"><span data-stu-id="dcf14-184">**[Microsoft.Spark.Examples.Sql.Streaming.StructuredKafkaWordCount (jars provided)](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/Sql/Streaming/StructuredKafkaWordCount.cs)**</span></span>

         ```powershell
         spark-submit.cmd 
         --jars path\to\net.jpountz.lz4\lz4-1.3.0.jar,path\to\org.apache.kafka\kafka-clients-0.10.0.1.jar,path\to\org.apache.spark\spark-sql-kafka-0-10_2.11-2.3.2.jar,`path\to\org.slf4j\slf4j-api-1.7.6.jar,path\to\org.spark-project.spark\unused-1.0.0.jar,path\to\org.xerial.snappy\snappy-java-1.1.2.6.jar `
         --class org.apache.spark.deploy.dotnet.DotnetRunner `
         --master local `
         C:\github\dotnet-spark\src\scala\microsoft-spark-<version>\target\microsoft-spark-<version>.jar `
         Microsoft.Spark.CSharp.Examples.exe Sql.Streaming.StructuredKafkaWordCount localhost:9092 subscribe test
          ```
