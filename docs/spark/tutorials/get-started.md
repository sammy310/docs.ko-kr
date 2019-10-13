---
title: .NET for Apache Spark 시작
description: Windows에서 .NET Core를 사용하여 .NET for Apache Spark 앱을 실행하는 방법을 살펴봅니다.
ms.date: 06/27/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: c4dbce74d0d8c0a682250a8021d983ef2990971f
ms.sourcegitcommit: d7c298f6c2e3aab0c7498bfafc0a0a94ea1fe23e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/10/2019
ms.locfileid: "72250318"
---
# <a name="tutorial-get-started-with-net-for-apache-spark"></a><span data-ttu-id="0c125-103">자습서: .NET for Apache Spark 시작</span><span class="sxs-lookup"><span data-stu-id="0c125-103">Tutorial: Get started with .NET for Apache Spark</span></span>

<span data-ttu-id="0c125-104">이 자습서에서는 Windows에서 .NET Core를 사용하여 .NET for Apache Spark 앱을 실행하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0c125-104">This tutorial teaches you how to run a .NET for Apache Spark app using .NET Core on Windows.</span></span>

<span data-ttu-id="0c125-105">이 자습서에서는 다음과 같은 작업을 수행하는 방법을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="0c125-105">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="0c125-106">.NET for Apache Spark를 위한 Windows 환경 준비</span><span class="sxs-lookup"><span data-stu-id="0c125-106">Prepare your Windows environment for .NET for Apache Spark</span></span>
> * <span data-ttu-id="0c125-107">**Microsoft.Spark.Worker** 다운로드</span><span class="sxs-lookup"><span data-stu-id="0c125-107">Download the **Microsoft.Spark.Worker**</span></span>
> * <span data-ttu-id="0c125-108">간단한 .NET for Apache Spark 애플리케이션 빌드 및 실행</span><span class="sxs-lookup"><span data-stu-id="0c125-108">Build and run a simple .NET for Apache Spark application</span></span>

## <a name="prepare-your-environment"></a><span data-ttu-id="0c125-109">환경 준비</span><span class="sxs-lookup"><span data-stu-id="0c125-109">Prepare your environment</span></span>

<span data-ttu-id="0c125-110">시작하기 전에 명령줄에서 `dotnet`, `java`, `mvn`, `spark-shell`을 실행할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0c125-110">Before you begin, make sure you can run `dotnet`, `java`, `mvn`, `spark-shell` from your command line.</span></span> <span data-ttu-id="0c125-111">환경이 이미 준비된 경우 다음 섹션으로 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c125-111">If your environment is already prepared, you can skip to the next section.</span></span> <span data-ttu-id="0c125-112">임의 또는 모든 명령을 실행할 수 없는 경우 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="0c125-112">If you cannot run any or all of the commands, follow the steps below.</span></span>

1. <span data-ttu-id="0c125-113">[.NET Core 2.1x SDK](https://dotnet.microsoft.com/download/dotnet-core/2.1)를 다운로드하여 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="0c125-113">Download and install the [.NET Core 2.1x SDK](https://dotnet.microsoft.com/download/dotnet-core/2.1).</span></span> <span data-ttu-id="0c125-114">SDK를 설치하면 `dotnet` 도구 체인이 PATH에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c125-114">Installing the SDK adds the `dotnet` toolchain to your PATH.</span></span> <span data-ttu-id="0c125-115">PowerShell 명령 `dotnet --version`을 사용하여 설치를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0c125-115">Use the PowerShell command `dotnet --version` to verify the installation.</span></span>

2. <span data-ttu-id="0c125-116">최신 업데이트와 함께 [Visual Studio 2017](https://www.visualstudio.com/downloads/) 또는 [Visual Studio 2019](https://visualstudio.microsoft.com/vs/preview/)를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="0c125-116">Install [Visual Studio 2017](https://www.visualstudio.com/downloads/) or [Visual Studio 2019](https://visualstudio.microsoft.com/vs/preview/) with the latest updates.</span></span> <span data-ttu-id="0c125-117">Community, Professional 또는 Enterprise를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c125-117">You can use Community, Professional, or Enterprise.</span></span> <span data-ttu-id="0c125-118">Community 버전은 무료입니다.</span><span class="sxs-lookup"><span data-stu-id="0c125-118">The Community version is free.</span></span>

   <span data-ttu-id="0c125-119">설치 중에 다음 워크로드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0c125-119">Choose the following workloads during installation:</span></span>
      * <span data-ttu-id="0c125-120">.NET 데스크톱 개발</span><span class="sxs-lookup"><span data-stu-id="0c125-120">.NET desktop development</span></span>
          * <span data-ttu-id="0c125-121">필요한 모든 구성 요소</span><span class="sxs-lookup"><span data-stu-id="0c125-121">All required components</span></span>
          * <span data-ttu-id="0c125-122">.NET Framework 4.6.1 개발 도구</span><span class="sxs-lookup"><span data-stu-id="0c125-122">.NET Framework 4.6.1 Development Tools</span></span>
      * <span data-ttu-id="0c125-123">.NET Core 플랫폼 간 개발</span><span class="sxs-lookup"><span data-stu-id="0c125-123">.NET Core cross-platform development</span></span>
          * <span data-ttu-id="0c125-124">필요한 모든 구성 요소</span><span class="sxs-lookup"><span data-stu-id="0c125-124">All required components</span></span>

3. <span data-ttu-id="0c125-125">[Java 1.8](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="0c125-125">Install [Java 1.8](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html).</span></span>

    * <span data-ttu-id="0c125-126">운영 체제에 적합한 버전을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0c125-126">Select the appropriate version for your operating system.</span></span> <span data-ttu-id="0c125-127">예를 들어 Windows x64 머신의 경우 **jdk-8u201-windows-x64.exe**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0c125-127">For example, select **jdk-8u201-windows-x64.exe** for a Windows x64 machine.</span></span>
    * <span data-ttu-id="0c125-128">PowerShell 명령 `java -version`을 사용하여 설치를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0c125-128">Use the PowerShell command `java -version` to verify the installation.</span></span>

4. <span data-ttu-id="0c125-129">[Apache Maven 3.6.0+](https://maven.apache.org/download.cgi)를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="0c125-129">Install [Apache Maven 3.6.0+](https://maven.apache.org/download.cgi).</span></span>
    * <span data-ttu-id="0c125-130">[Apache Maven 3.6.0](http://mirror.metrocast.net/apache/maven/maven-3/3.6.0/binaries/apache-maven-3.6.0-bin.zip)을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="0c125-130">Download [Apache Maven 3.6.0](http://mirror.metrocast.net/apache/maven/maven-3/3.6.0/binaries/apache-maven-3.6.0-bin.zip).</span></span>
    * <span data-ttu-id="0c125-131">로컬 디렉터리로 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="0c125-131">Extract to a local directory.</span></span> <span data-ttu-id="0c125-132">예: `c:\bin\apache-maven-3.6.0\`.</span><span class="sxs-lookup"><span data-stu-id="0c125-132">For example, `c:\bin\apache-maven-3.6.0\`.</span></span>
    * <span data-ttu-id="0c125-133">Apache Maven을 [PATH 환경 변수](https://www.java.com/en/download/help/path.xml)에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0c125-133">Add Apache Maven to your [PATH environment variable](https://www.java.com/en/download/help/path.xml).</span></span> <span data-ttu-id="0c125-134">`c:\bin\apache-maven-3.6.0\`으로 추출한 경우 `c:\bin\apache-maven-3.6.0\bin`을 PATH에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0c125-134">If you extracted to `c:\bin\apache-maven-3.6.0\`, you would add `c:\bin\apache-maven-3.6.0\bin` to your PATH.</span></span>
    * <span data-ttu-id="0c125-135">PowerShell 명령 `mvn -version`을 사용하여 설치를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0c125-135">Use the PowerShell command `mvn -version` to verify the installation.</span></span>

5. <span data-ttu-id="0c125-136">[Apache Spark 2.3 이상](https://spark.apache.org/downloads.html)을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="0c125-136">Install [Apache Spark 2.3+](https://spark.apache.org/downloads.html).</span></span> <span data-ttu-id="0c125-137">Apache Spark 2.4 이상은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0c125-137">Apache Spark 2.4+ isn't supported.</span></span>
    * <span data-ttu-id="0c125-138">[Apache Spark 2.3 이상](https://spark.apache.org/downloads.html)을 다운로드하여 [7-zip](https://www.7-zip.org/) 또는 [WinZip](https://www.winzip.com/)과 같은 도구를 사용하여 로컬 폴더에 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="0c125-138">Download [Apache Spark 2.3+](https://spark.apache.org/downloads.html) and extract it into a local folder using a tool like [7-zip](https://www.7-zip.org/) or [WinZip](https://www.winzip.com/).</span></span> <span data-ttu-id="0c125-139">예를 들어 `c:\bin\spark-2.3.2-bin-hadoop2.7\`로 추출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c125-139">For example, you might extract it to `c:\bin\spark-2.3.2-bin-hadoop2.7\`.</span></span>
    * <span data-ttu-id="0c125-140">Apache Spark를 [PATH 환경 변수](https://www.java.com/en/download/help/path.xml)에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0c125-140">Add Apache Spark to your [PATH environment variable](https://www.java.com/en/download/help/path.xml).</span></span> <span data-ttu-id="0c125-141">`c:\bin\spark-2.3.2-bin-hadoop2.7\`로 추출한 경우 `c:\bin\spark-2.3.2-bin-hadoop2.7\bin`을 PATH에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0c125-141">If you extracted to `c:\bin\spark-2.3.2-bin-hadoop2.7\`, you would add `c:\bin\spark-2.3.2-bin-hadoop2.7\bin` to your PATH.</span></span>
    * <span data-ttu-id="0c125-142">`SPARK_HOME`이라는 [새 환경 변수](https://www.java.com/en/download/help/path.xml)를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0c125-142">Add a [new environment variable](https://www.java.com/en/download/help/path.xml) called `SPARK_HOME`.</span></span> <span data-ttu-id="0c125-143">`C:\bin\spark-2.3.2-bin-hadoop2.7\`로 추출한 경우 **변수 값**에 `C:\bin\spark-2.3.2-bin-hadoop2.7\`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0c125-143">If you extracted to `C:\bin\spark-2.3.2-bin-hadoop2.7\`, use  `C:\bin\spark-2.3.2-bin-hadoop2.7\` for the **Variable value**.</span></span>
    * <span data-ttu-id="0c125-144">명령줄에서 `spark-shell`을 실행할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0c125-144">Verify you are able to run `spark-shell` from your command line.</span></span>

6. <span data-ttu-id="0c125-145">[WinUtils](https://github.com/steveloughran/winutils)를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0c125-145">Set up [WinUtils](https://github.com/steveloughran/winutils).</span></span>
    * <span data-ttu-id="0c125-146">[WinUtils 리포지토리](https://github.com/steveloughran/winutils)에서 **winutils.exe** 이진 파일을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="0c125-146">Download the **winutils.exe** binary from [WinUtils repository](https://github.com/steveloughran/winutils).</span></span> <span data-ttu-id="0c125-147">Spark 배포의 컴파일에 사용된 Hadoop 버전을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0c125-147">Select the version of Hadoop the Spark distribution was compiled with.</span></span> <span data-ttu-id="0c125-148">예를 들어 **Spark 2.3.2**에 **hadoop-2.7.1**을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0c125-148">For example, you use **hadoop-2.7.1** for **Spark 2.3.2**.</span></span> <span data-ttu-id="0c125-149">Hadoop 버전은 Spark 설치 폴더 이름의 끝에 주석으로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c125-149">The Hadoop version is annotated at the end of your Spark install folder name.</span></span>
    * <span data-ttu-id="0c125-150">**winutils.exe** 이진 파일을 선택한 디렉터리에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="0c125-150">Save the **winutils.exe** binary to a directory of your choice.</span></span> <span data-ttu-id="0c125-151">예: `c:\hadoop\bin`.</span><span class="sxs-lookup"><span data-stu-id="0c125-151">For example, `c:\hadoop\bin`.</span></span>
    * <span data-ttu-id="0c125-152">`bin` 없이 **winutils.exe**가 있는 디렉터리를 반영하도록 `HADOOP_HOME`을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0c125-152">Set `HADOOP_HOME` to reflect the directory with **winutils.exe** without `bin`.</span></span> <span data-ttu-id="0c125-153">예: `c:\hadoop`.</span><span class="sxs-lookup"><span data-stu-id="0c125-153">For example, `c:\hadoop`.</span></span>
    * <span data-ttu-id="0c125-154">`%HADOOP_HOME%\bin`을 포함하도록 PATH 환경 변수를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0c125-154">Set the PATH environment variable to include `%HADOOP_HOME%\bin`.</span></span>

<span data-ttu-id="0c125-155">다음 섹션으로 이동하기 전에 명령줄에서 `dotnet`, `java`, `mvn`, `spark-shell`을 실행할 수 있는지 다시 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0c125-155">Double check that you can run `dotnet`, `java`, `mvn`, `spark-shell` from your command line before you move to the next section.</span></span>

## <a name="download-the-microsoftsparkworker-release"></a><span data-ttu-id="0c125-156">Microsoft.Spark.Worker 릴리스 다운로드</span><span class="sxs-lookup"><span data-stu-id="0c125-156">Download the Microsoft.Spark.Worker release</span></span>

1. <span data-ttu-id="0c125-157">.NET for Apache Spark GitHub 릴리스 페이지에서 로컬 머신으로 [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) 릴리스를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="0c125-157">Download the [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) release from the .NET for Apache Spark GitHub Releases page to your local machine.</span></span> <span data-ttu-id="0c125-158">예를 들어 `c:\bin\Microsoft.Spark.Worker\` 경로에 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c125-158">For example, you might download it to the path, `c:\bin\Microsoft.Spark.Worker\`.</span></span>

2. <span data-ttu-id="0c125-159">`DOTNET_WORKER_DIR`라는 [새 환경 변수](https://www.java.com/en/download/help/path.xml)를 만들고 **Microsoft.Spark.Worker**를 다운로드하여 추출한 디렉터리로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0c125-159">Create a [new environment variable](https://www.java.com/en/download/help/path.xml) called `DOTNET_WORKER_DIR` and set it to the directory where you downloaded and extracted the **Microsoft.Spark.Worker**.</span></span> <span data-ttu-id="0c125-160">예: `c:\bin\Microsoft.Spark.Worker`.</span><span class="sxs-lookup"><span data-stu-id="0c125-160">For example, `c:\bin\Microsoft.Spark.Worker`.</span></span>

## <a name="clone-the-net-for-apache-spark-github-repo"></a><span data-ttu-id="0c125-161">.NET for Apache Spark GitHub 리포지토리 복제</span><span class="sxs-lookup"><span data-stu-id="0c125-161">Clone the .NET for Apache Spark GitHub repo</span></span>

<span data-ttu-id="0c125-162">다음 [GitBash](https://gitforwindows.org/) 명령을 사용하여 머신에 .NET for Apache Spark 리포지토리를 복제합니다.</span><span class="sxs-lookup"><span data-stu-id="0c125-162">Use the following [GitBash](https://gitforwindows.org/) command to clone the .NET for Apache Spark repo to your machine.</span></span>

```bash
git clone https://github.com/dotnet/spark.git c:\github\dotnet-spark
```

## <a name="write-a-net-for-apache-spark-app"></a><span data-ttu-id="0c125-163">.NET for Apache Spark 앱 작성</span><span class="sxs-lookup"><span data-stu-id="0c125-163">Write a .NET for Apache Spark app</span></span>

1. <span data-ttu-id="0c125-164">**Visual Studio**를 열고 **파일 > 새 프로젝트 만들기 > 콘솔 앱(.NET Core)** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="0c125-164">Open **Visual Studio** and navigate to **File > Create New Project > Console App (.NET Core)**.</span></span> <span data-ttu-id="0c125-165">애플리케이션 이름을 **HelloSpark**로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0c125-165">Name the application **HelloSpark**.</span></span>

2. <span data-ttu-id="0c125-166">[Microsoft.Spark NuGet 패키지](https://www.nuget.org/profiles/spark)를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="0c125-166">Install the [Microsoft.Spark NuGet package](https://www.nuget.org/profiles/spark).</span></span> <span data-ttu-id="0c125-167">NuGet 패키지 설치에 대한 자세한 내용은 [NuGet 패키지를 설치하는 다양한 방법](https://docs.microsoft.com/nuget/consume-packages/ways-to-install-a-package)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0c125-167">For more information on installing NuGet packages, see [Different ways to install a NuGet Package](https://docs.microsoft.com/nuget/consume-packages/ways-to-install-a-package).</span></span>

3. <span data-ttu-id="0c125-168">**솔루션 탐색기**에서 **Program.cs**를 열고 다음 C# 코드를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="0c125-168">In **Solution Explorer**, open **Program.cs** and write the following C# code:</span></span>

   ```csharp
     var spark = SparkSession.Builder().GetOrCreate();
     var df = spark.Read().Json("people.json");
     df.Show();
   ```

4. <span data-ttu-id="0c125-169">솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="0c125-169">Build the solution.</span></span>

## <a name="run-your-net-for-apache-spark-app"></a><span data-ttu-id="0c125-170">.NET for Apache Spark 앱 실행</span><span class="sxs-lookup"><span data-stu-id="0c125-170">Run your .NET for Apache Spark app</span></span>

1. <span data-ttu-id="0c125-171">**PowerShell**을 열고 앱이 저장된 폴더로 디렉터리를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="0c125-171">Open **PowerShell** and change the directory to the folder where your app is stored.</span></span>

   ```powershell
   cd <your-app-output-directory>
   ```

2. <span data-ttu-id="0c125-172">다음 콘텐츠를 사용하여 **people.json** 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0c125-172">Create a file called **people.json** with the following content:</span></span>

   ```json
   {"name":"Michael"}
   {"name":"Andy", "age":30}
   {"name":"Justin", "age":19}
   ```

3. <span data-ttu-id="0c125-173">다음 PowerShell 명령을 사용하여 앱을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0c125-173">Use the following PowerShell command to run your app:</span></span>

   ```powershell
    spark-submit `
    --class org.apache.spark.deploy.dotnet.DotnetRunner `
    --master local `
    microsoft-spark-2.4.x-<version>.jar `
    dotnet HelloSpark.dll
    ```

<span data-ttu-id="0c125-174">지금까지</span><span class="sxs-lookup"><span data-stu-id="0c125-174">Congratulations!</span></span> <span data-ttu-id="0c125-175">.NET for Apache Spark 앱을 작성하고 실행했습니다.</span><span class="sxs-lookup"><span data-stu-id="0c125-175">You successfully authored and ran a .NET for Apache Spark app.</span></span>

## <a name="next-steps"></a><span data-ttu-id="0c125-176">다음 단계</span><span class="sxs-lookup"><span data-stu-id="0c125-176">Next steps</span></span>

<span data-ttu-id="0c125-177">본 자습서에서는 다음 작업에 관한 방법을 학습했습니다.</span><span class="sxs-lookup"><span data-stu-id="0c125-177">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> * <span data-ttu-id="0c125-178">.NET for Apache Spark를 위한 Windows 환경 준비</span><span class="sxs-lookup"><span data-stu-id="0c125-178">Prepare your Windows environment for .NET for Apache Spark</span></span>
> * <span data-ttu-id="0c125-179">**Microsoft.Spark.Worker** 다운로드</span><span class="sxs-lookup"><span data-stu-id="0c125-179">Download the **Microsoft.Spark.Worker**</span></span>
> * <span data-ttu-id="0c125-180">간단한 .NET for Apache Spark 애플리케이션 빌드 및 실행</span><span class="sxs-lookup"><span data-stu-id="0c125-180">Build and run a simple .NET for Apache Spark application</span></span>

<span data-ttu-id="0c125-181">자세한 내용은 리소스 페이지를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0c125-181">Check out the resources page to learn more.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="0c125-182">.NET for Apache Spark 리소스</span><span class="sxs-lookup"><span data-stu-id="0c125-182">.NET for Apache Spark Resources</span></span>](../resources/index.md)
