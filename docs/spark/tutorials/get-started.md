---
title: .NET for Apache Spark 시작
description: Windows, macOS, Ubuntu에서 .NET Core를 사용하여 .NET for Apache Spark 앱을 실행하는 방법을 살펴봅니다.
ms.date: 10/09/2020
ms.topic: tutorial
ms.custom: mvc
ms.author: luquinta
author: luisquintanilla
ms.openlocfilehash: 16ccc8f40f290c4bc10f03d1f4d1b296b17f6b11
ms.sourcegitcommit: 34968a61e9bac0f6be23ed6ffb837f52d2390c85
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/17/2020
ms.locfileid: "94687827"
---
# <a name="tutorial-get-started-with-net-for-apache-spark"></a><span data-ttu-id="0162b-103">자습서: .NET for Apache Spark 시작</span><span class="sxs-lookup"><span data-stu-id="0162b-103">Tutorial: Get started with .NET for Apache Spark</span></span>

<span data-ttu-id="0162b-104">이 자습서에서는 Windows, macOS, Ubuntu에서 .NET Core를 사용하여 .NET for Apache Spark 앱을 실행하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0162b-104">This tutorial teaches you how to run a .NET for Apache Spark app using .NET Core on Windows, macOS, and Ubuntu.</span></span>

<span data-ttu-id="0162b-105">이 자습서에서는 다음과 같은 작업을 수행하는 방법을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="0162b-105">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="0162b-106">.NET for Apache Spark를 위한 환경 준비</span><span class="sxs-lookup"><span data-stu-id="0162b-106">Prepare your environment for .NET for Apache Spark</span></span>
> * <span data-ttu-id="0162b-107">첫 번째 .NET for Apache Spark 애플리케이션 작성</span><span class="sxs-lookup"><span data-stu-id="0162b-107">Write your first .NET for Apache Spark application</span></span>
> * <span data-ttu-id="0162b-108">.NET for Apache Spark 애플리케이션 빌드 및 실행</span><span class="sxs-lookup"><span data-stu-id="0162b-108">Build and run your .NET for Apache Spark application</span></span>

## <a name="prepare-your-environment"></a><span data-ttu-id="0162b-109">환경 준비</span><span class="sxs-lookup"><span data-stu-id="0162b-109">Prepare your environment</span></span>

<span data-ttu-id="0162b-110">앱 작성을 시작하기 전에 몇 가지 필수 구성 요소 종속성을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0162b-110">Before you begin writing your app, you need to set up some prerequisite dependencies.</span></span> <span data-ttu-id="0162b-111">명령줄 환경에서 `dotnet`, `java`, `spark-shell`을 실행할 수 있는 경우 환경은 이미 준비된 것이며 다음 섹션으로 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0162b-111">If you can run `dotnet`, `java`, `spark-shell` from your command line environment, then your environment is already prepared and you can skip to the next section.</span></span> <span data-ttu-id="0162b-112">임의 또는 모든 명령을 실행할 수 없는 경우 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="0162b-112">If you cannot run any or all of the commands, do the following steps.</span></span>

### <a name="1-install-net"></a><span data-ttu-id="0162b-113">1. .NET 설치</span><span class="sxs-lookup"><span data-stu-id="0162b-113">1. Install .NET</span></span>

<span data-ttu-id="0162b-114">.NET 앱 빌드를 시작하려면 .NET SDK(소프트웨어 개발 키트)를 다운로드하여 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0162b-114">To start building .NET apps, you need to download and install the .NET SDK (Software Development Kit).</span></span>

<span data-ttu-id="0162b-115">[.NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core/3.1)를 다운로드하여 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="0162b-115">Download and install the [.NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core/3.1).</span></span> <span data-ttu-id="0162b-116">SDK를 설치하면 `dotnet` 도구 체인이 PATH에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="0162b-116">Installing the SDK adds the `dotnet` toolchain to your PATH.</span></span>

<span data-ttu-id="0162b-117">.NET Core SDK를 설치한 후에는 새 명령 프롬프트 또는 터미널을 열고 `dotnet`을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0162b-117">Once you've installed the .NET Core SDK, open a new command prompt or terminal and run `dotnet`.</span></span>

<span data-ttu-id="0162b-118">명령이 실행되고 dotnet 사용 방법에 대한 정보가 출력되면 다음 단계로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0162b-118">If the command runs and prints out information about how to use dotnet, can move to the next step.</span></span> <span data-ttu-id="0162b-119">`'dotnet' is not recognized as an internal or external command` 오류가 표시되면 명령을 실행하기 전에 **새** 명령 프롬프트 또는 터미널을 열어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0162b-119">If you receive a `'dotnet' is not recognized as an internal or external command` error, make sure you opened a **new** command prompt or terminal before running the command.</span></span>

### <a name="2-install-java"></a><span data-ttu-id="0162b-120">2. Java 설치</span><span class="sxs-lookup"><span data-stu-id="0162b-120">2. Install Java</span></span>

<span data-ttu-id="0162b-121">Windows 및 macOS용 [Java 8.1](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html) 또는 Ubuntu용 [OpenJDK 8](https://openjdk.java.net/install/)을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="0162b-121">Install [Java 8.1](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html) for Windows and macOS, or [OpenJDK 8](https://openjdk.java.net/install/) for Ubuntu.</span></span>

<span data-ttu-id="0162b-122">운영 체제에 적합한 버전을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0162b-122">Select the appropriate version for your operating system.</span></span> <span data-ttu-id="0162b-123">예를 들어 Windows x64 머신의 경우 **jdk-8u201-windows-x64.exe**(아래 참조), macOS의 경우 **jdk-8u231-macosx-x64.dmg** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0162b-123">For example, select **jdk-8u201-windows-x64.exe** for a Windows x64 machine (as shown below) or **jdk-8u231-macosx-x64.dmg** for macOS.</span></span> <span data-ttu-id="0162b-124">그런 다음, `java` 명령을 사용하여 설치를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0162b-124">Then, use the command `java` to verify the installation.</span></span>

![Java 다운로드](https://dotnet.microsoft.com/static/images/java-jdk-downloads-windows.png?v=6BbJHoNyDO-PyYVciImr5wzh2AW_YHNcyb3p093AwPA)

### <a name="3-install-compression-software"></a><span data-ttu-id="0162b-126">3. 압축 소프트웨어 설치</span><span class="sxs-lookup"><span data-stu-id="0162b-126">3. Install compression software</span></span>

<span data-ttu-id="0162b-127">Apache Spark는 압축된 .tgz 파일로 다운로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="0162b-127">Apache Spark is downloaded as a compressed .tgz file.</span></span> <span data-ttu-id="0162b-128">[7-Zip](https://www.7-zip.org/) 또는 [WinZip](https://www.winzip.com/)과 같은 압축 풀기 프로그램을 사용하여 파일 압축을 풉니다.</span><span class="sxs-lookup"><span data-stu-id="0162b-128">Use an extraction program, like [7-Zip](https://www.7-zip.org/) or [WinZip](https://www.winzip.com/), to extract the file.</span></span>

### <a name="4-install-apache-spark"></a><span data-ttu-id="0162b-129">4. Apache Spark 설치</span><span class="sxs-lookup"><span data-stu-id="0162b-129">4. Install Apache Spark</span></span>

<span data-ttu-id="0162b-130">[Apache Spark를 다운로드하여 설치](https://spark.apache.org/downloads.html)합니다.</span><span class="sxs-lookup"><span data-stu-id="0162b-130">[Download and install Apache Spark](https://spark.apache.org/downloads.html).</span></span> <span data-ttu-id="0162b-131">버전 2.3.\*, 2.4.0, 2.4.1, 2.4.3, 2.4.4, 2.4.5, 2.4.6, 2.4.7, 3.0.0 또는 3.0.1 중에서 선택해야 합니다(.NET for Apache Spark는 다른 버전의 Apache Spark와 호환되지 않음).</span><span class="sxs-lookup"><span data-stu-id="0162b-131">You'll need to select from version 2.3.\* or 2.4.0, 2.4.1, 2.4.3, 2.4.4, 2.4.5, 2.4.6, 2.4.7, 3.0.0, or 3.0.1 (.NET for Apache Spark is not compatible with other versions of Apache Spark).</span></span>

<span data-ttu-id="0162b-132">다음 단계에서 사용되는 명령에서는 [Apache Spark 3.0.1을 다운로드하여 설치](https://spark.apache.org/downloads.html)했다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="0162b-132">The commands used in the following steps assume you have [downloaded and installed Apache Spark 3.0.1](https://spark.apache.org/downloads.html).</span></span> <span data-ttu-id="0162b-133">다른 버전을 사용하려는 경우 **3.0.1** 을 적절한 버전 번호로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="0162b-133">If you wish to use a different version, replace **3.0.1** with the appropriate version number.</span></span> <span data-ttu-id="0162b-134">그런 다음, **.tar** 파일 및 Apache Spark 파일의 압축을 풉니다.</span><span class="sxs-lookup"><span data-stu-id="0162b-134">Then, extract the **.tar** file and the Apache Spark files.</span></span>

<span data-ttu-id="0162b-135">중첩된 **.tar** 파일의 압축을 풀려면:</span><span class="sxs-lookup"><span data-stu-id="0162b-135">To extract the nested **.tar** file:</span></span>

* <span data-ttu-id="0162b-136">다운로드한 **spark-3.0.1-bin-hadoop2.7.tgz** 파일을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="0162b-136">Locate the **spark-3.0.1-bin-hadoop2.7.tgz** file that you downloaded.</span></span>
* <span data-ttu-id="0162b-137">파일을 마우스 오른쪽 단추로 클릭하고 **7-Zip -> 여기에 압축 풀기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0162b-137">Right click on the file and select **7-Zip -> Extract here**.</span></span>
* <span data-ttu-id="0162b-138">**spark-3.0.1-bin-hadoop2.7.tar** 이 다운로드한 **.tgz** 파일과 함께 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="0162b-138">**spark-3.0.1-bin-hadoop2.7.tar** is created alongside the **.tgz** file you downloaded.</span></span>

<span data-ttu-id="0162b-139">Apache Spark 파일의 압축을 풀려면:</span><span class="sxs-lookup"><span data-stu-id="0162b-139">To extract the Apache Spark files:</span></span>

* <span data-ttu-id="0162b-140">**spark-3.0.1-bin-hadoop2.7.tar** 을 마우스 오른쪽 단추로 클릭하고 **7-Zip -> 압축 풀기...** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0162b-140">Right-click on **spark-3.0.1-bin-hadoop2.7.tar** and select **7-Zip -> Extract files...**</span></span>
* <span data-ttu-id="0162b-141">**압축 풀기** 필드에 **C:\bin** 을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="0162b-141">Enter **C:\bin** in the **Extract to** field.</span></span>
* <span data-ttu-id="0162b-142">**압축 풀기** 필드 아래에 있는 확인란의 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="0162b-142">Uncheck the checkbox below the **Extract to** field.</span></span>
* <span data-ttu-id="0162b-143">**확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0162b-143">Select **OK**.</span></span>
* <span data-ttu-id="0162b-144">Apache Spark 파일이 C:\bin\spark-3.0.1-bin-hadoop2.7\에 추출됩니다.</span><span class="sxs-lookup"><span data-stu-id="0162b-144">The Apache Spark files are extracted to C:\bin\spark-3.0.1-bin-hadoop2.7\</span></span>

![Spark 설치](./media/spark-extract-with-7-zip.png)

<span data-ttu-id="0162b-146">다음 명령을 실행하여 Apache Spark를 찾는 데 사용되는 환경 변수를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0162b-146">Run the following commands to set the environment variables used to locate Apache Spark.</span></span> <span data-ttu-id="0162b-147">Windows에서는 관리자 모드에서 명령 프롬프트를 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0162b-147">On Windows, make sure to run the command prompt in administrator mode.</span></span>

#### <a name="windows"></a>[<span data-ttu-id="0162b-148">Windows</span><span class="sxs-lookup"><span data-stu-id="0162b-148">Windows</span></span>](#tab/windows)

```console
setx /M HADOOP_HOME C:\bin\spark-3.0.1-bin-hadoop2.7\
setx /M SPARK_HOME C:\bin\spark-3.0.1-bin-hadoop2.7\
setx /M PATH "%PATH%;%HADOOP_HOME%;%SPARK_HOME%\bin"
```

#### <a name="maclinux"></a>[<span data-ttu-id="0162b-149">Mac/Linux</span><span class="sxs-lookup"><span data-stu-id="0162b-149">Mac/Linux</span></span>](#tab/linux)

```bash
export SPARK_HOME=~/bin/spark-3.0.1-bin-hadoop2.7/
export PATH="$SPARK_HOME/bin:$PATH"
source ~/.bashrc
```

---

<span data-ttu-id="0162b-150">모든 항목을 설치하고 환경 변수를 설정한 후 **새** 명령 프롬프트 또는 터미널을 열고 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0162b-150">Once you've installed everything and set your environment variables, open a **new** command prompt or terminal and run the following command:</span></span>

```text
spark-submit --version
```

<span data-ttu-id="0162b-151">명령이 실행되고 버전 정보가 출력되면 다음 단계로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0162b-151">If the command runs and prints version information, you can move to the next step.</span></span>

<span data-ttu-id="0162b-152">`'spark-submit' is not recognized as an internal or external command` 오류가 표시되면 **새** 명령 프롬프트를 열었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0162b-152">If you receive a `'spark-submit' is not recognized as an internal or external command` error, make sure you opened a **new** command prompt.</span></span>

### <a name="5-install-net-for-apache-spark"></a><span data-ttu-id="0162b-153">5. .NET for Apache Spark 설치</span><span class="sxs-lookup"><span data-stu-id="0162b-153">5. Install .NET for Apache Spark</span></span>

<span data-ttu-id="0162b-154">.NET for Apache Spark GitHub에서 [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) 릴리스를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="0162b-154">Download the [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) release from the .NET for Apache Spark GitHub.</span></span> <span data-ttu-id="0162b-155">예를 들어 Windows 머신에서 .NET Core를 사용하려는 경우 [Windows x64 netcoreapp3.1 릴리스를 다운로드](https://github.com/dotnet/spark/releases)합니다.</span><span class="sxs-lookup"><span data-stu-id="0162b-155">For example if you're on a Windows machine and plan to use .NET Core, [download the Windows x64 netcoreapp3.1 release](https://github.com/dotnet/spark/releases).</span></span>

<span data-ttu-id="0162b-156">Microsoft.Spark.Worker 압축을 풀려면:</span><span class="sxs-lookup"><span data-stu-id="0162b-156">To extract the Microsoft.Spark.Worker:</span></span>

* <span data-ttu-id="0162b-157">다운로드한 **Microsoft.Spark.Worker.netcoreapp3.1.win-x64-1.0.0.zip** 파일을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="0162b-157">Locate the **Microsoft.Spark.Worker.netcoreapp3.1.win-x64-1.0.0.zip** file that you downloaded.</span></span>
* <span data-ttu-id="0162b-158">마우스 오른쪽 단추를 클릭하고 **7-Zip -> 압축 풀기...** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0162b-158">Right-click and select **7-Zip -> Extract files...**.</span></span>
* <span data-ttu-id="0162b-159">**압축 풀기** 필드에 **C:\bin** 을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="0162b-159">Enter **C:\bin** in the **Extract to** field.</span></span>
* <span data-ttu-id="0162b-160">**압축 풀기** 필드 아래에 있는 확인란의 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="0162b-160">Uncheck the checkbox below the **Extract to** field.</span></span>
* <span data-ttu-id="0162b-161">**확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0162b-161">Select **OK**.</span></span>

### <a name="6-install-winutils-windows-only"></a><span data-ttu-id="0162b-162">6. WinUtils 설치(Windows에만 해당)</span><span class="sxs-lookup"><span data-stu-id="0162b-162">6. Install WinUtils (Windows only)</span></span>

<span data-ttu-id="0162b-163">.NET for Apache Spark를 사용하려면 Apache Spark와 함께 WinUtils를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0162b-163">.NET for Apache Spark requires WinUtils to be installed alongside Apache Spark.</span></span> <span data-ttu-id="0162b-164">[winutils.exe를 다운로드](https://github.com/steveloughran/winutils/blob/master/hadoop-2.7.1/bin/winutils.exe)합니다.</span><span class="sxs-lookup"><span data-stu-id="0162b-164">[Download winutils.exe](https://github.com/steveloughran/winutils/blob/master/hadoop-2.7.1/bin/winutils.exe).</span></span> <span data-ttu-id="0162b-165">그런 다음, WinUtils를 **C:\bin\spark-3.0.1-bin-hadoop2.7\bin** 에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="0162b-165">Then, copy WinUtils into **C:\bin\spark-3.0.1-bin-hadoop2.7\bin**.</span></span>

> [!NOTE]
> <span data-ttu-id="0162b-166">다른 Hadoop 버전을 사용 중인 경우(Spark 설치 폴더 이름 끝에 주석으로 처리되어 있음) 해당 Hadoop 버전과 호환되는 [WinUtils 버전을 선택](https://github.com/steveloughran/winutils)합니다.</span><span class="sxs-lookup"><span data-stu-id="0162b-166">If you are using a different version of Hadoop, which is annotated at the end of your Spark install folder name, [select the version of WinUtils](https://github.com/steveloughran/winutils) that's compatible with your version of Hadoop.</span></span>

### <a name="7-set-dotnet_worker_dir-and-check-dependencies"></a><span data-ttu-id="0162b-167">7. DOTNET_WORKER_DIR 설정 및 종속성 확인</span><span class="sxs-lookup"><span data-stu-id="0162b-167">7. Set DOTNET_WORKER_DIR and check dependencies</span></span>

<span data-ttu-id="0162b-168">다음 명령 중 하나를 실행하여 .NET 앱에서 .NET for Apache Spark 작업자 바이너리를 찾는 데 사용하는 `DOTNET_WORKER_DIR` 환경 변수를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0162b-168">Run one of the following commands to set the `DOTNET_WORKER_DIR` environment variable, which is used by .NET apps to locate .NET for Apache Spark worker binaries.</span></span> <span data-ttu-id="0162b-169">`<PATH-DOTNET_WORKER_DIR>`을 `Microsoft.Spark.Worker`를 다운로드하여 압축을 푼 디렉터리로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="0162b-169">Make sure to replace `<PATH-DOTNET_WORKER_DIR>` with the directory where you downloaded and extracted the `Microsoft.Spark.Worker`.</span></span> <span data-ttu-id="0162b-170">Windows에서는 관리자 모드에서 명령 프롬프트를 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0162b-170">On Windows, make sure to run the command prompt in administrator mode.</span></span>

#### <a name="windows"></a>[<span data-ttu-id="0162b-171">Windows</span><span class="sxs-lookup"><span data-stu-id="0162b-171">Windows</span></span>](#tab/windows)

```console
setx /M DOTNET_WORKER_DIR <PATH-DOTNET-WORKER-DIR>
```

#### <a name="maclinux"></a>[<span data-ttu-id="0162b-172">Mac/Linux</span><span class="sxs-lookup"><span data-stu-id="0162b-172">Mac/Linux</span></span>](#tab/linux)

```bash
export DOTNET_WORKER_DIR=<PATH-DOTNET-WORKER-DIR>
```

---

<span data-ttu-id="0162b-173">마지막으로, 다음 섹션으로 이동하기 전에 명령줄에서 `dotnet`, `java`, `spark-shell`을 실행할 수 있는지 다시 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0162b-173">Finally, double-check that you can run `dotnet`, `java`, `spark-shell` from your command line before you move to the next section.</span></span>

## <a name="write-a-net-for-apache-spark-app"></a><span data-ttu-id="0162b-174">.NET for Apache Spark 앱 작성</span><span class="sxs-lookup"><span data-stu-id="0162b-174">Write a .NET for Apache Spark app</span></span>

### <a name="1-create-a-console-app"></a><span data-ttu-id="0162b-175">1. 콘솔 앱 만들기</span><span class="sxs-lookup"><span data-stu-id="0162b-175">1. Create a console app</span></span>

<span data-ttu-id="0162b-176">명령 프롬프트 또는 터미널에서 다음 명령을 실행하여 새 콘솔 애플리케이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0162b-176">In your command prompt or terminal, run the following commands to create a new console application:</span></span>

```dotnetcli
dotnet new console -o MySparkApp
cd MySparkApp
```

<span data-ttu-id="0162b-177">`dotnet` 명령은 `console` 형식의 `new` 애플리케이션을 자동으로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0162b-177">The `dotnet` command creates a `new` application of type `console` for you.</span></span> <span data-ttu-id="0162b-178">`-o` 매개 변수는 앱이 저장되는 *MySparkApp* 이라는 디렉터리를 만들고 필요한 파일로 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="0162b-178">The `-o` parameter creates a directory named *MySparkApp* where your app is stored and populates it with the required files.</span></span> <span data-ttu-id="0162b-179">`cd MySparkApp` 명령은 디렉터리를 방금 만든 앱 디렉터리로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="0162b-179">The `cd MySparkApp` command changes the directory to the app directory you created.</span></span>

### <a name="2-install-nuget-package"></a><span data-ttu-id="0162b-180">2. NuGet 패키지 설치</span><span class="sxs-lookup"><span data-stu-id="0162b-180">2. Install NuGet package</span></span>

<span data-ttu-id="0162b-181">앱에서 .NET for Apache Spark를 사용하려면 Microsoft.Spark 패키지를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="0162b-181">To use .NET for Apache Spark in an app, install the Microsoft.Spark package.</span></span> <span data-ttu-id="0162b-182">명령 프롬프트 또는 터미널에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0162b-182">In your command prompt or terminal, run the following command:</span></span>

```dotnetcli
dotnet add package Microsoft.Spark
```

> [!NOTE]
> <span data-ttu-id="0162b-183">달리 지정하지 않은 한 이 자습서에서는 `Microsoft.Spark` NuGet 패키지의 최신 버전을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0162b-183">This tutorial uses the latest version of the `Microsoft.Spark` NuGet package unless otherwise specified.</span></span>

### <a name="3-write-your-app"></a><span data-ttu-id="0162b-184">3. 앱 작성</span><span class="sxs-lookup"><span data-stu-id="0162b-184">3. Write your app</span></span>

<span data-ttu-id="0162b-185">Visual Studio Code 또는 텍스트 편집기에서 *Program.cs* 를 열고 모든 코드를 다음으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="0162b-185">Open *Program.cs* in Visual Studio Code, or any text editor, and replace all of the code with the following:</span></span>

```csharp
using Microsoft.Spark.Sql;
using static Microsoft.Spark.Sql.Functions;

namespace MySparkApp
{
    class Program
    {
        static void Main(string[] args)
        {
            // Create Spark session
            SparkSession spark =
                SparkSession
                    .Builder()
                    .AppName("word_count_sample")
                    .GetOrCreate();

            // Create initial DataFrame
            string filePath = args[0];
            DataFrame dataFrame = spark.Read().Text(filePath);

            //Count words
            DataFrame words =
                dataFrame
                    .Select(Split(Col("value")," ").Alias("words"))
                    .Select(Explode(Col("words")).Alias("word"))
                    .GroupBy("word")
                    .Count()
                    .OrderBy(Col("count").Desc());

            // Display results
            words.Show();

            // Stop Spark session
            spark.Stop();
        }
    }
}
```

<span data-ttu-id="0162b-186">[SparkSession](xref:Microsoft.Spark.Sql.SparkSession)은 Apache Spark 애플리케이션의 진입점으로, 애플리케이션의 컨텍스트 및 정보를 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="0162b-186">[SparkSession](xref:Microsoft.Spark.Sql.SparkSession) is the entrypoint of Apache Spark applications, which manages the context and information of your application.</span></span> <span data-ttu-id="0162b-187">[Text](xref:Microsoft.Spark.Sql.DataFrameReader.Text%2A) 메서드를 사용하여 `filePath`에서 지정된 파일의 텍스트 데이터를 [DataFrame](xref:Microsoft.Spark.Sql.DataFrame)으로 읽어옵니다.</span><span class="sxs-lookup"><span data-stu-id="0162b-187">Using the [Text](xref:Microsoft.Spark.Sql.DataFrameReader.Text%2A) method, the text data from the file specified by the `filePath` is read into a [DataFrame](xref:Microsoft.Spark.Sql.DataFrame).</span></span> <span data-ttu-id="0162b-188">DataFrame은 명명된 열의 집합으로 데이터를 구성하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="0162b-188">A DataFrame is a way of organizing data into a set of named columns.</span></span> <span data-ttu-id="0162b-189">그런 다음 일련의 변환을 적용하여 파일의 문장을 분할하고, 각 단어를 그룹화하고, 개수를 계산하고, 내림차순으로 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="0162b-189">Then, a series of transformations is applied to split the sentences in the file, group each of the words, count them and order them in descending order.</span></span> <span data-ttu-id="0162b-190">이러한 작업의 결과는 다른 DataFrame에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="0162b-190">The result of these operations is stored in another DataFrame.</span></span> <span data-ttu-id="0162b-191">이 시점에서는 아무 작업도 수행되지 않습니다. .NET for Apache Spark가 데이터를 지연 계산하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="0162b-191">Note that at this point, no operations have taken place because .NET for Apache Spark lazily evaluates the data.</span></span> <span data-ttu-id="0162b-192">[Show](xref:Microsoft.Spark.Sql.DataFrame.Show%2A) 메서드를 호출하여 콘솔에 `words`로 변환된 DataFrame의 내용을 표시하기 전에는 위의 줄에 정의된 작업이 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0162b-192">It's not until the [Show](xref:Microsoft.Spark.Sql.DataFrame.Show%2A) method is called to display the contents of the `words` transformed DataFrame to the console that the operations defined in the lines above execute.</span></span> <span data-ttu-id="0162b-193">Spark 세션이 더 이상 필요하지 않으면 [Stop](xref:Microsoft.Spark.Sql.SparkSession.Stop%2A) 메서드를 사용하여 세션을 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="0162b-193">Once you no longer need the Spark session, use the [Stop](xref:Microsoft.Spark.Sql.SparkSession.Stop%2A) method to stop your session.</span></span>

### <a name="4-create-data-file"></a><span data-ttu-id="0162b-194">4. 데이터 파일 만들기</span><span class="sxs-lookup"><span data-stu-id="0162b-194">4. Create data file</span></span>

<span data-ttu-id="0162b-195">앱은 텍스트 줄이 포함된 파일을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="0162b-195">Your app processes a file containing lines of text.</span></span> <span data-ttu-id="0162b-196">*MySparkApp* 디렉터리에 다음 텍스트를 포함하는 *input.txt* 라는 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0162b-196">Create a file called *input.txt* file in your *MySparkApp* directory, containing the following text:</span></span>

```text
Hello World
This .NET app uses .NET for Apache Spark
This .NET app counts words with Apache Spark
```

<span data-ttu-id="0162b-197">변경 내용을 저장하고 파일을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="0162b-197">Save the changes and close the file.</span></span>

## <a name="run-your-net-for-apache-spark-app"></a><span data-ttu-id="0162b-198">.NET for Apache Spark 앱 실행</span><span class="sxs-lookup"><span data-stu-id="0162b-198">Run your .NET for Apache Spark app</span></span>

<span data-ttu-id="0162b-199">다음 명령을 실행하여 애플리케이션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="0162b-199">Run the following command to build your application:</span></span>

```dotnetcli
dotnet build
```

<span data-ttu-id="0162b-200">빌드 출력 디렉터리로 이동하고 `spark-submit` 명령을 사용하여 Apache Spark에서 실행할 애플리케이션을 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="0162b-200">Navigate to your build output directory and use the `spark-submit` command to submit your application to run on Apache Spark.</span></span> <span data-ttu-id="0162b-201">`<version>`을 .NET 작업자의 버전으로 바꾸고 `<path-of-input.txt>`를 *input.txt* 파일이 저장된 경로로 바꿔야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0162b-201">Make sure to replace  `<version>` with the version of your .NET worker and `<path-of-input.txt>` with the path of your *input.txt* file is stored.</span></span>

### <a name="windows"></a>[<span data-ttu-id="0162b-202">Windows</span><span class="sxs-lookup"><span data-stu-id="0162b-202">Windows</span></span>](#tab/windows)

```console
spark-submit ^
--class org.apache.spark.deploy.dotnet.DotnetRunner ^
--master local ^
microsoft-spark-3-0_2.12-<version>.jar ^
dotnet MySparkApp.dll <path-of-input.txt>
```

### <a name="maclinux"></a>[<span data-ttu-id="0162b-203">Mac/Linux</span><span class="sxs-lookup"><span data-stu-id="0162b-203">Mac/Linux</span></span>](#tab/linux)

```bash
spark-submit \
--class org.apache.spark.deploy.dotnet.DotnetRunner \
--master local \
microsoft-spark-3-0_2.12-<version>.jar \
dotnet MySparkApp.dll <path-of-input.txt>
```

---

> [!NOTE]
> <span data-ttu-id="0162b-204">이 명령은 Apache Spark를 다운로드한 후 PATH 환경 변수에 추가했으므로 `spark-submit`를 사용할 수 있다고 전제합니다.</span><span class="sxs-lookup"><span data-stu-id="0162b-204">This command assumes you have downloaded Apache Spark and added it to your PATH environment variable to be able to use `spark-submit`.</span></span> <span data-ttu-id="0162b-205">그렇지 않은 경우에는 전체 경로를 사용해야 합니다(예: *C:\bin\apache-spark\bin\spark-submit* 또는 *~/spark/bin/spark-submit*).</span><span class="sxs-lookup"><span data-stu-id="0162b-205">Otherwise, you'd have to use the full path (for example, *C:\bin\apache-spark\bin\spark-submit* or *~/spark/bin/spark-submit*).</span></span>

<span data-ttu-id="0162b-206">앱이 실행되면 *input.txt* 파일의 단어 수 데이터가 콘솔에 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="0162b-206">When your app runs, the word count data of the *input.txt* file is written to the console.</span></span>

```console
+------+-----+
|  word|count|
+------+-----+
|  .NET|    3|
|Apache|    2|
|   app|    2|
|  This|    2|
| Spark|    2|
| World|    1|
|counts|    1|
|   for|    1|
| words|    1|
|  with|    1|
| Hello|    1|
|  uses|    1|
+------+-----+
```

<span data-ttu-id="0162b-207">지금까지</span><span class="sxs-lookup"><span data-stu-id="0162b-207">Congratulations!</span></span> <span data-ttu-id="0162b-208">.NET for Apache Spark 앱을 작성하고 실행했습니다.</span><span class="sxs-lookup"><span data-stu-id="0162b-208">You successfully authored and ran a .NET for Apache Spark app.</span></span>

## <a name="next-steps"></a><span data-ttu-id="0162b-209">다음 단계</span><span class="sxs-lookup"><span data-stu-id="0162b-209">Next steps</span></span>

<span data-ttu-id="0162b-210">이 자습서에서는 다음 작업 방법을 알아보았습니다.</span><span class="sxs-lookup"><span data-stu-id="0162b-210">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> * <span data-ttu-id="0162b-211">.NET for Apache Spark를 위한 환경 준비</span><span class="sxs-lookup"><span data-stu-id="0162b-211">Prepare your environment for .NET for Apache Spark</span></span>
> * <span data-ttu-id="0162b-212">첫 번째 .NET for Apache Spark 애플리케이션 작성</span><span class="sxs-lookup"><span data-stu-id="0162b-212">Write your first .NET for Apache Spark application</span></span>
> * <span data-ttu-id="0162b-213">.NET for Apache Spark 애플리케이션 빌드 및 실행</span><span class="sxs-lookup"><span data-stu-id="0162b-213">Build and run your .NET for Apache Spark application</span></span>

<span data-ttu-id="0162b-214">위의 단계를 설명하는 동영상을 보려면 [.NET for Apache Spark 101 동영상 시리즈](https://channel9.msdn.com/Series/NET-for-Apache-Spark-101/Run-Your-First-NET-for-Apache-Spark-App)를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="0162b-214">To see a video explaining the steps above, check out the [.NET for Apache Spark 101 video series](https://channel9.msdn.com/Series/NET-for-Apache-Spark-101/Run-Your-First-NET-for-Apache-Spark-App).</span></span>

<span data-ttu-id="0162b-215">자세한 내용은 리소스 페이지를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0162b-215">Check out the resources page to learn more.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="0162b-216">.NET for Apache Spark 리소스</span><span class="sxs-lookup"><span data-stu-id="0162b-216">.NET for Apache Spark Resources</span></span>](../resources/index.md)
