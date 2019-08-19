---
title: Apache Spark 용 .NET 시작
description: Windows에서 .NET Core를 사용 하 여 Apache Spark 앱 용 .NET을 실행 하는 방법을 알아봅니다.
ms.date: 06/27/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 7ce7d7aec6c15385d3d797d5a548519eea33b764
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/13/2019
ms.locfileid: "69577010"
---
# <a name="tutorial-get-started-with-net-for-apache-spark"></a><span data-ttu-id="0ef7d-103">자습서: Apache Spark 용 .NET 시작</span><span class="sxs-lookup"><span data-stu-id="0ef7d-103">Tutorial: Get started with .NET for Apache Spark</span></span>

<span data-ttu-id="0ef7d-104">이 자습서에서는 Windows에서 .NET Core를 사용 하 여 Apache Spark 앱 용 .NET을 실행 하는 방법을 배웁니다.</span><span class="sxs-lookup"><span data-stu-id="0ef7d-104">This tutorial teaches you how to run a .NET for Apache Spark app using .NET Core on Windows.</span></span>

<span data-ttu-id="0ef7d-105">이 자습서에서는 다음 작업을 수행하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="0ef7d-105">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="0ef7d-106">Apache Spark 용 .NET 용 Windows 환경 준비</span><span class="sxs-lookup"><span data-stu-id="0ef7d-106">Prepare your Windows environment for .NET for Apache Spark</span></span>
> * <span data-ttu-id="0ef7d-107">**Microsoft Spark Worker** 를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ef7d-107">Download the **Microsoft.Spark.Worker**</span></span>
> * <span data-ttu-id="0ef7d-108">Apache Spark 응용 프로그램에 대 한 간단한 .NET 빌드 및 실행</span><span class="sxs-lookup"><span data-stu-id="0ef7d-108">Build and run a simple .NET for Apache Spark application</span></span>

## <a name="prepare-your-environment"></a><span data-ttu-id="0ef7d-109">환경 준비</span><span class="sxs-lookup"><span data-stu-id="0ef7d-109">Prepare your environment</span></span>

<span data-ttu-id="0ef7d-110">시작 하기 `dotnet`전에 명령줄 `spark-shell` 에서,,를 실행할 `java` `mvn`수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ef7d-110">Before you begin, make sure you can run `dotnet`, `java`, `mvn`, `spark-shell` from your command line.</span></span> <span data-ttu-id="0ef7d-111">사용자 환경이 이미 준비 된 경우 다음 섹션으로 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ef7d-111">If your environment is already prepared, you can skip to the next section.</span></span> <span data-ttu-id="0ef7d-112">일부 또는 모든 명령을 실행할 수 없는 경우 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ef7d-112">If you cannot run any or all of the commands, follow the steps below.</span></span>

1. <span data-ttu-id="0ef7d-113">[.Net Core 2.1 x SDK](https://dotnet.microsoft.com/download/dotnet-core/2.1)를 다운로드 하 여 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ef7d-113">Download and install the [.NET Core 2.1x SDK](https://dotnet.microsoft.com/download/dotnet-core/2.1).</span></span> <span data-ttu-id="0ef7d-114">SDK를 설치 하면 도구 체인 `dotnet` 가 경로에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ef7d-114">Installing the SDK adds the `dotnet` toolchain to your PATH.</span></span> <span data-ttu-id="0ef7d-115">PowerShell 명령을 `dotnet --version` 사용 하 여 설치를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ef7d-115">Use the PowerShell command `dotnet --version` to verify the installation.</span></span>

2. <span data-ttu-id="0ef7d-116">최신 업데이트를 사용 하 여 [Visual studio 2017](https://www.visualstudio.com/downloads/) 또는 [visual studio 2019](https://visualstudio.microsoft.com/vs/preview/) 를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ef7d-116">Install [Visual Studio 2017](https://www.visualstudio.com/downloads/) or [Visual Studio 2019](https://visualstudio.microsoft.com/vs/preview/) with the latest updates.</span></span> <span data-ttu-id="0ef7d-117">Community, Professional 또는 Enterprise를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ef7d-117">You can use Community, Professional, or Enterprise.</span></span> <span data-ttu-id="0ef7d-118">커뮤니티 버전은 무료입니다.</span><span class="sxs-lookup"><span data-stu-id="0ef7d-118">The Community version is free.</span></span>

   <span data-ttu-id="0ef7d-119">설치 하는 동안 다음 작업을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ef7d-119">Choose the following workloads during installation:</span></span>
      * <span data-ttu-id="0ef7d-120">.NET 데스크톱 개발</span><span class="sxs-lookup"><span data-stu-id="0ef7d-120">.NET desktop development</span></span>
          * <span data-ttu-id="0ef7d-121">모든 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="0ef7d-121">All required components</span></span>
          * <span data-ttu-id="0ef7d-122">.NET Framework 4.6.1 개발 도구</span><span class="sxs-lookup"><span data-stu-id="0ef7d-122">.NET Framework 4.6.1 Development Tools</span></span>
      * <span data-ttu-id="0ef7d-123">.NET Core 플랫폼 간 개발</span><span class="sxs-lookup"><span data-stu-id="0ef7d-123">.NET Core cross-platform development</span></span>
          * <span data-ttu-id="0ef7d-124">모든 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="0ef7d-124">All required components</span></span>

3. <span data-ttu-id="0ef7d-125">[Java 1.8](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ef7d-125">Install [Java 1.8](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html).</span></span>

    * <span data-ttu-id="0ef7d-126">운영 체제에 적합 한 버전을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ef7d-126">Select the appropriate version for your operating system.</span></span> <span data-ttu-id="0ef7d-127">예를 들어 Windows x64 컴퓨터에 대해 **jdk-8u201-windows-x64** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ef7d-127">For example, select **jdk-8u201-windows-x64.exe** for a Windows x64 machine.</span></span>
    * <span data-ttu-id="0ef7d-128">PowerShell 명령을 `java -version` 사용 하 여 설치를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ef7d-128">Use the PowerShell command `java -version` to verify the installation.</span></span>

4. <span data-ttu-id="0ef7d-129">[Apache Maven 3.6.0 +](https://maven.apache.org/download.cgi)를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ef7d-129">Install [Apache Maven 3.6.0+](https://maven.apache.org/download.cgi).</span></span>
    * <span data-ttu-id="0ef7d-130">[Apache Maven 3.6.0](http://mirror.metrocast.net/apache/maven/maven-3/3.6.0/binaries/apache-maven-3.6.0-bin.zip)를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ef7d-130">Download [Apache Maven 3.6.0](http://mirror.metrocast.net/apache/maven/maven-3/3.6.0/binaries/apache-maven-3.6.0-bin.zip).</span></span>
    * <span data-ttu-id="0ef7d-131">로컬 디렉터리로 추출 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ef7d-131">Extract to a local directory.</span></span> <span data-ttu-id="0ef7d-132">`c:\bin\apache-maven-3.6.0\` )을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="0ef7d-132">For example, `c:\bin\apache-maven-3.6.0\`.</span></span>
    * <span data-ttu-id="0ef7d-133">[PATH 환경 변수에](https://www.java.com/en/download/help/path.xml)Apache Maven를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ef7d-133">Add Apache Maven to your [PATH environment variable](https://www.java.com/en/download/help/path.xml).</span></span> <span data-ttu-id="0ef7d-134">로 `c:\bin\apache-maven-3.6.0\`압축을 푼 경우 경로에를 `c:\bin\apache-maven-3.6.0\bin` 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ef7d-134">If you extracted to `c:\bin\apache-maven-3.6.0\`, you would add `c:\bin\apache-maven-3.6.0\bin` to your PATH.</span></span>
    * <span data-ttu-id="0ef7d-135">PowerShell 명령을 `mvn -version` 사용 하 여 설치를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ef7d-135">Use the PowerShell command `mvn -version` to verify the installation.</span></span>

5. <span data-ttu-id="0ef7d-136">[Apache Spark 2.3 이상](https://spark.apache.org/downloads.html)을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ef7d-136">Install [Apache Spark 2.3+](https://spark.apache.org/downloads.html).</span></span> <span data-ttu-id="0ef7d-137">Apache Spark 2.4 +는 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0ef7d-137">Apache Spark 2.4+ isn't supported.</span></span>
    * <span data-ttu-id="0ef7d-138">[2.3 이상 Apache Spark](https://spark.apache.org/downloads.html) 를 다운로드 하 고 [7-zip](https://www.7-zip.org/) 또는 [WinZip](https://www.winzip.com/)과 같은 도구를 사용 하 여 로컬 폴더에 추출 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ef7d-138">Download [Apache Spark 2.3+](https://spark.apache.org/downloads.html) and extract it into a local folder using a tool like [7-zip](https://www.7-zip.org/) or [WinZip](https://www.winzip.com/).</span></span> <span data-ttu-id="0ef7d-139">예를 들어로 `c:\bin\spark-2.3.2-bin-hadoop2.7\`추출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ef7d-139">For example, you might extract it to `c:\bin\spark-2.3.2-bin-hadoop2.7\`.</span></span>
    * <span data-ttu-id="0ef7d-140">[PATH 환경 변수에](https://www.java.com/en/download/help/path.xml)Apache Spark를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ef7d-140">Add Apache Spark to your [PATH environment variable](https://www.java.com/en/download/help/path.xml).</span></span> <span data-ttu-id="0ef7d-141">로 `c:\bin\spark-2.3.2-bin-hadoop2.7\`압축을 푼 경우 경로에를 `c:\bin\spark-2.3.2-bin-hadoop2.7\bin` 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ef7d-141">If you extracted to `c:\bin\spark-2.3.2-bin-hadoop2.7\`, you would add `c:\bin\spark-2.3.2-bin-hadoop2.7\bin` to your PATH.</span></span>
    * <span data-ttu-id="0ef7d-142">이라는`SPARK_HOME` [새 환경 변수](https://www.java.com/en/download/help/path.xml) 를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ef7d-142">Add a [new environment variable](https://www.java.com/en/download/help/path.xml) called `SPARK_HOME`.</span></span> <span data-ttu-id="0ef7d-143">로 `C:\bin\spark-2.3.2-bin-hadoop2.7\`압축을 푼 경우 **변수 값**에을 사용 `C:\bin\spark-2.3.2-bin-hadoop2.7\` 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ef7d-143">If you extracted to `C:\bin\spark-2.3.2-bin-hadoop2.7\`, use  `C:\bin\spark-2.3.2-bin-hadoop2.7\` for the **Variable value**.</span></span>
    * <span data-ttu-id="0ef7d-144">명령줄에서를 실행할 `spark-shell` 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ef7d-144">Verify you are able to run `spark-shell` from your command line.</span></span>

6. <span data-ttu-id="0ef7d-145">[Winutils.exe](https://github.com/steveloughran/winutils)를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ef7d-145">Set up [WinUtils](https://github.com/steveloughran/winutils).</span></span>
    * <span data-ttu-id="0ef7d-146">[Winutils.exe 리포지토리에서](https://github.com/steveloughran/winutils) **winutils.exe** binary를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ef7d-146">Download the **winutils.exe** binary from [WinUtils repository](https://github.com/steveloughran/winutils).</span></span> <span data-ttu-id="0ef7d-147">Spark 배포가 컴파일된 Hadoop의 버전을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ef7d-147">Select the version of Hadoop the Spark distribution was compiled with.</span></span> <span data-ttu-id="0ef7d-148">예를 들어 **Spark 2.3.2**에 **hadoop-2.7.1** 를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ef7d-148">For example, you use **hadoop-2.7.1** for **Spark 2.3.2**.</span></span> <span data-ttu-id="0ef7d-149">Hadoop 버전은 Spark 설치 폴더 이름의 끝에 주석이 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ef7d-149">The Hadoop version is annotated at the end of your Spark install folder name.</span></span>
    * <span data-ttu-id="0ef7d-150">원하는 디렉터리에 **winutils.exe** binary를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ef7d-150">Save the **winutils.exe** binary to a directory of your choice.</span></span> <span data-ttu-id="0ef7d-151">`c:\hadoop\bin` )을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="0ef7d-151">For example, `c:\hadoop\bin`.</span></span>
    * <span data-ttu-id="0ef7d-152">를 `HADOOP_HOME` 사용 하지 않고 `bin` **winutils.exe** 를 사용 하 여 디렉터리를 반영 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ef7d-152">Set `HADOOP_HOME` to reflect the directory with **winutils.exe** without `bin`.</span></span> <span data-ttu-id="0ef7d-153">`c:\hadoop` )을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="0ef7d-153">For example, `c:\hadoop`.</span></span>
    * <span data-ttu-id="0ef7d-154">PATH 환경 변수를 포함 `%HADOOP_HOME%\bin`하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ef7d-154">Set the PATH environment variable to include `%HADOOP_HOME%\bin`.</span></span>

<span data-ttu-id="0ef7d-155">다음 섹션으로 이동 하기 전에 `dotnet`명령줄 `java`에서 `mvn`, `spark-shell` ,를 실행할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ef7d-155">Double check that you can run `dotnet`, `java`, `mvn`, `spark-shell` from your command line before you move to the next section.</span></span>

## <a name="download-the-microsoftsparkworker-release"></a><span data-ttu-id="0ef7d-156">Microsoft Spark Worker 릴리스를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ef7d-156">Download the Microsoft.Spark.Worker release</span></span>

1. <span data-ttu-id="0ef7d-157">Apache Spark GitHub 릴리스 페이지의 .NET에서 로컬 컴퓨터로 [Microsoft Spark Worker](https://github.com/dotnet/spark/releases) 릴리스를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ef7d-157">Download the [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) release from the .NET for Apache Spark GitHub Releases page to your local machine.</span></span> <span data-ttu-id="0ef7d-158">예를 들어, `c:\bin\Microsoft.Spark.Worker\`경로에 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ef7d-158">For example, you might download it to the path, `c:\bin\Microsoft.Spark.Worker\`.</span></span>

2. <span data-ttu-id="0ef7d-159">이라는 `DotnetWorkerPath` [새 환경 변수](https://www.java.com/en/download/help/path.xml) 를 만들어이를 다운로드 하 고 압축을 푼 디렉터리로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ef7d-159">Create a [new environment variable](https://www.java.com/en/download/help/path.xml) called `DotnetWorkerPath` and set it to the directory where you downloaded and extracted the **Microsoft.Spark.Worker**.</span></span> <span data-ttu-id="0ef7d-160">`c:\bin\Microsoft.Spark.Worker` )을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="0ef7d-160">For example, `c:\bin\Microsoft.Spark.Worker`.</span></span>

## <a name="clone-the-net-for-apache-spark-github-repo"></a><span data-ttu-id="0ef7d-161">Apache Spark GitHub 리포지토리의 .NET 복제</span><span class="sxs-lookup"><span data-stu-id="0ef7d-161">Clone the .NET for Apache Spark GitHub repo</span></span>

<span data-ttu-id="0ef7d-162">다음 [Gitbash](https://gitforwindows.org/) 명령을 사용 하 여 Apache Spark 리포지토리의 .net을 컴퓨터에 복제 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ef7d-162">Use the following [GitBash](https://gitforwindows.org/) command to clone the .NET for Apache Spark repo to your machine.</span></span>

```bash
git clone https://github.com/dotnet/spark.git c:\github\dotnet-spark
```

## <a name="write-a-net-for-apache-spark-app"></a><span data-ttu-id="0ef7d-163">Apache Spark 앱에 대 한 .NET 작성</span><span class="sxs-lookup"><span data-stu-id="0ef7d-163">Write a .NET for Apache Spark app</span></span>

1. <span data-ttu-id="0ef7d-164">**Visual Studio** 를 열고 **파일 > 새 프로젝트 만들기 > 콘솔 앱 (.net Core)** 으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ef7d-164">Open **Visual Studio** and navigate to **File > Create New Project > Console App (.NET Core)**.</span></span> <span data-ttu-id="0ef7d-165">응용 프로그램 이름을 **HelloSpark**로 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ef7d-165">Name the application **HelloSpark**.</span></span>

2. <span data-ttu-id="0ef7d-166">[Microsoft Spark NuGet 패키지](https://www.nuget.org/profiles/spark)를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ef7d-166">Install the [Microsoft.Spark NuGet package](https://www.nuget.org/profiles/spark).</span></span> <span data-ttu-id="0ef7d-167">NuGet 패키지를 설치 하는 방법에 대 한 자세한 내용은 [Nuget 패키지를 설치 하는 다양 한 방법](https://docs.microsoft.com/nuget/consume-packages/ways-to-install-a-package)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0ef7d-167">For more information on installing NuGet packages, see [Different ways to install a NuGet Package](https://docs.microsoft.com/nuget/consume-packages/ways-to-install-a-package).</span></span>

3. <span data-ttu-id="0ef7d-168">**솔루션 탐색기**에서 **Program.cs** 을 열고 다음 C# 코드를 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ef7d-168">In **Solution Explorer**, open **Program.cs** and write the following C# code:</span></span>

   ```csharp
     var spark = SparkSession.Builder().GetOrCreate();
     var df = spark.Read().Json("people.json");
     df.Show();
   ```

4. <span data-ttu-id="0ef7d-169">솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="0ef7d-169">Build the solution.</span></span>

## <a name="run-your-net-for-apache-spark-app"></a><span data-ttu-id="0ef7d-170">Apache Spark 앱에 대 한 .NET 실행</span><span class="sxs-lookup"><span data-stu-id="0ef7d-170">Run your .NET for Apache Spark app</span></span>

1. <span data-ttu-id="0ef7d-171">**PowerShell** 을 열고 디렉터리를 앱이 저장 된 폴더로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ef7d-171">Open **PowerShell** and change the directory to the folder where your app is stored.</span></span>

   ```powershell
   cd <your-app-output-directory>
   ```

2. <span data-ttu-id="0ef7d-172">다음 콘텐츠를 사용 하 여 **사용자: json** 이라는 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0ef7d-172">Create a file called **people.json** with the following content:</span></span>

   ```json
   {"name":"Michael"}
   {"name":"Andy", "age":30}
   {"name":"Justin", "age":19}
   ```

3. <span data-ttu-id="0ef7d-173">다음 PowerShell 명령을 사용 하 여 앱을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ef7d-173">Use the following PowerShell command to run your app:</span></span>

   ```powershell
    spark-submit `
    --class org.apache.spark.deploy.dotnet.DotnetRunner `
    --master local `
    microsoft-spark-2.4.x-<version>.jar `
    dotnet HelloSpark.dll
    ```

<span data-ttu-id="0ef7d-174">축하합니다.</span><span class="sxs-lookup"><span data-stu-id="0ef7d-174">Congratulations!</span></span> <span data-ttu-id="0ef7d-175">Apache Spark 앱에 대 한 .NET을 작성 하 고 실행 했습니다.</span><span class="sxs-lookup"><span data-stu-id="0ef7d-175">You successfully authored and ran a .NET for Apache Spark app.</span></span>

## <a name="next-steps"></a><span data-ttu-id="0ef7d-176">다음 단계</span><span class="sxs-lookup"><span data-stu-id="0ef7d-176">Next steps</span></span>

<span data-ttu-id="0ef7d-177">이 자습서에서는 다음 작업을 수행하는 방법을 알아보았습니다.</span><span class="sxs-lookup"><span data-stu-id="0ef7d-177">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="0ef7d-178">Apache Spark 용 .NET 용 Windows 환경 준비</span><span class="sxs-lookup"><span data-stu-id="0ef7d-178">Prepare your Windows environment for .NET for Apache Spark</span></span>
> * <span data-ttu-id="0ef7d-179">**Microsoft Spark Worker** 를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ef7d-179">Download the **Microsoft.Spark.Worker**</span></span>
> * <span data-ttu-id="0ef7d-180">Apache Spark 응용 프로그램에 대 한 간단한 .NET 빌드 및 실행</span><span class="sxs-lookup"><span data-stu-id="0ef7d-180">Build and run a simple .NET for Apache Spark application</span></span>

<span data-ttu-id="0ef7d-181">자세한 내용은 리소스 페이지를 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="0ef7d-181">Check out the resources page to learn more.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="0ef7d-182">Apache Spark 리소스에 대 한 .NET</span><span class="sxs-lookup"><span data-stu-id="0ef7d-182">.NET for Apache Spark Resources</span></span>](../resources/index.md)
