---
title: .NET for Apache Spark 시작
description: Windows, MacOS 및 Ubuntu에서 .NET Core를 사용하여 .NET for Apache Spark 앱을 실행하는 방법을 살펴봅니다.
ms.date: 01/31/2020
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 7375c385245a05d7dc29d5df89d875bf6cb4141a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2020
ms.locfileid: "79187548"
---
# <a name="tutorial-get-started-with-net-for-apache-spark"></a><span data-ttu-id="e7bdd-103">자습서: .NET for Apache Spark 시작</span><span class="sxs-lookup"><span data-stu-id="e7bdd-103">Tutorial: Get started with .NET for Apache Spark</span></span>

<span data-ttu-id="e7bdd-104">이 자습서에서는 Windows, MacOS 및 Ubuntu에서 .NET Core를 사용하여 .NET for Apache Spark 앱을 실행하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e7bdd-104">This tutorial teaches you how to run a .NET for Apache Spark app using .NET Core on Windows, MacOS, and Ubuntu.</span></span>

<span data-ttu-id="e7bdd-105">이 자습서에서는 다음과 같은 작업을 수행하는 방법을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="e7bdd-105">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="e7bdd-106">.NET for Apache Spark를 위한 환경 준비</span><span class="sxs-lookup"><span data-stu-id="e7bdd-106">Prepare your environment for .NET for Apache Spark</span></span>
> * <span data-ttu-id="e7bdd-107">첫 번째 .NET for Apache Spark 애플리케이션 작성</span><span class="sxs-lookup"><span data-stu-id="e7bdd-107">Write your first .NET for Apache Spark application</span></span>
> * <span data-ttu-id="e7bdd-108">간단한 .NET for Apache Spark 애플리케이션 빌드 및 실행</span><span class="sxs-lookup"><span data-stu-id="e7bdd-108">Build and run your simple .NET for Apache Spark application</span></span>

## <a name="prepare-your-environment"></a><span data-ttu-id="e7bdd-109">환경 준비</span><span class="sxs-lookup"><span data-stu-id="e7bdd-109">Prepare your environment</span></span>

<span data-ttu-id="e7bdd-110">앱 작성을 시작하기 전에 몇 가지 필수 구성 요소 종속성을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7bdd-110">Before you begin writing your app, you need to set up some prerequisite dependencies.</span></span> <span data-ttu-id="e7bdd-111">명령줄 환경에서 `dotnet`, `java`, `mvn`, `spark-shell`을 실행할 수 있는 경우 환경은 이미 준비된 것이며 다음 섹션으로 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7bdd-111">If you can run `dotnet`, `java`, `mvn`, `spark-shell` from your command line environment, then your environment is already prepared and you can skip to the next section.</span></span> <span data-ttu-id="e7bdd-112">임의 또는 모든 명령을 실행할 수 없는 경우 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="e7bdd-112">If you cannot run any or all of the commands, do the following steps.</span></span>

### <a name="1-install-net"></a><span data-ttu-id="e7bdd-113">1. .NET 설치</span><span class="sxs-lookup"><span data-stu-id="e7bdd-113">1. Install .NET</span></span>

<span data-ttu-id="e7bdd-114">.NET 앱 빌드를 시작하려면 .NET SDK(소프트웨어 개발 키트)를 다운로드하여 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7bdd-114">To start building .NET apps, you need to download and install the .NET SDK (Software Development Kit).</span></span>

<span data-ttu-id="e7bdd-115">[.NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core/3.1)를 다운로드하여 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="e7bdd-115">Download and install the [.NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core/3.1).</span></span> <span data-ttu-id="e7bdd-116">SDK를 설치하면 `dotnet` 도구 체인이 PATH에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7bdd-116">Installing the SDK adds the `dotnet` toolchain to your PATH.</span></span>

<span data-ttu-id="e7bdd-117">.NET Core SDK를 설치한 후에는 새 명령 프롬프트 또는 터미널을 열고 `dotnet`을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e7bdd-117">Once you've installed the .NET Core SDK, open a new command prompt or terminal and run `dotnet`.</span></span>

<span data-ttu-id="e7bdd-118">명령이 실행되고 dotnet 사용 방법에 대한 정보가 출력되면 다음 단계로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7bdd-118">If the command runs and prints out information about how to use dotnet, can move to the next step.</span></span> <span data-ttu-id="e7bdd-119">`'dotnet' is not recognized as an internal or external command` 오류가 표시되면 명령을 실행하기 전에 **새** 명령 프롬프트 또는 터미널을 열어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7bdd-119">If you receive a `'dotnet' is not recognized as an internal or external command` error, make sure you opened a **new** command prompt or terminal before running the command.</span></span>

### <a name="2-install-java"></a><span data-ttu-id="e7bdd-120">2. Java 설치</span><span class="sxs-lookup"><span data-stu-id="e7bdd-120">2. Install Java</span></span>

<span data-ttu-id="e7bdd-121">Windows 및 MacOS용 [Java 8.1](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html) 또는 Ubuntu용 [OpenJDK 8](https://openjdk.java.net/install/)을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="e7bdd-121">Install [Java 8.1](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html) for Windows and MacOS, or [OpenJDK 8](https://openjdk.java.net/install/) for Ubuntu.</span></span>

<span data-ttu-id="e7bdd-122">운영 체제에 적합한 버전을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e7bdd-122">Select the appropriate version for your operating system.</span></span> <span data-ttu-id="e7bdd-123">예를 들어 Windows x64 컴퓨터의 경우 **jdk-8u201-windows-x64.exe**(아래 참조), MacOS의 경우 **jdk-8u231-macosx-x64.dmg**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e7bdd-123">For example, select **jdk-8u201-windows-x64.exe** for a Windows x64 machine (as shown below) or **jdk-8u231-macosx-x64.dmg** for MacOS.</span></span> <span data-ttu-id="e7bdd-124">그런 다음, `java` 명령을 사용하여 설치를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e7bdd-124">Then, use the command `java` to verify the installation.</span></span>

![Java 다운로드](https://dotnet.microsoft.com/static/images/java-jdk-downloads-windows.png?v=6BbJHoNyDO-PyYVciImr5wzh2AW_YHNcyb3p093AwPA)

### <a name="3-install-compression-software"></a><span data-ttu-id="e7bdd-126">3. 압축 소프트웨어 설치</span><span class="sxs-lookup"><span data-stu-id="e7bdd-126">3. Install compression software</span></span>

<span data-ttu-id="e7bdd-127">Apache Spark는 압축된 .tgz 파일로 다운로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7bdd-127">Apache Spark is downloaded as a compressed .tgz file.</span></span> <span data-ttu-id="e7bdd-128">[7-Zip](https://www.7-zip.org/) 또는 [WinZip](https://www.winzip.com/)과 같은 압축 풀기 프로그램을 사용하여 파일 압축을 풉니다.</span><span class="sxs-lookup"><span data-stu-id="e7bdd-128">Use an extraction program, like [7-Zip](https://www.7-zip.org/) or [WinZip](https://www.winzip.com/), to extract the file.</span></span>

### <a name="4-install-apache-spark"></a><span data-ttu-id="e7bdd-129">4. Apache Spark 설치</span><span class="sxs-lookup"><span data-stu-id="e7bdd-129">4. Install Apache Spark</span></span>

<span data-ttu-id="e7bdd-130">[Apache Spark를 다운로드하여 설치](https://spark.apache.org/downloads.html)합니다.</span><span class="sxs-lookup"><span data-stu-id="e7bdd-130">[Download and install Apache Spark](https://spark.apache.org/downloads.html).</span></span> <span data-ttu-id="e7bdd-131">버전 2.3.\* 또는 2.4.0, 2.4.1, 2.4.3, 2.4.4 중에서 선택해야 합니다(.NET for Apache Spark는 다른 버전의 Apache Spark와 호환되지 않음).</span><span class="sxs-lookup"><span data-stu-id="e7bdd-131">You'll need to select from version 2.3.\* or 2.4.0, 2.4.1, 2.4.3, or 2.4.4 (.NET for Apache Spark is not compatible with other versions of Apache Spark).</span></span>

<span data-ttu-id="e7bdd-132">다음 단계에서 사용되는 명령에서는 [Apache Spark 2.4.1을 다운로드하여 설치](https://archive.apache.org/dist/spark/spark-2.4.1/spark-2.4.1-bin-hadoop2.7.tgz)했다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="e7bdd-132">The commands used in the following steps assume you have [downloaded and installed Apache Spark 2.4.1](https://archive.apache.org/dist/spark/spark-2.4.1/spark-2.4.1-bin-hadoop2.7.tgz).</span></span> <span data-ttu-id="e7bdd-133">다른 버전을 사용하려는 경우 **2.4.1**을 적절한 버전 번호로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="e7bdd-133">If you wish to use a different version, replace **2.4.1** with the appropriate version number.</span></span> <span data-ttu-id="e7bdd-134">그런 다음, **.tar** 파일 및 Apache Spark 파일의 압축을 풉니다.</span><span class="sxs-lookup"><span data-stu-id="e7bdd-134">Then, extract the **.tar** file and the Apache Spark files.</span></span>

<span data-ttu-id="e7bdd-135">중첩된 **.tar** 파일의 압축을 풀려면:</span><span class="sxs-lookup"><span data-stu-id="e7bdd-135">To extract the nested **.tar** file:</span></span>

* <span data-ttu-id="e7bdd-136">다운로드한 **spark-2.4.1-bin-hadoop2.7.tgz** 파일을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="e7bdd-136">Locate the **spark-2.4.1-bin-hadoop2.7.tgz** file that you downloaded.</span></span>
* <span data-ttu-id="e7bdd-137">파일을 마우스 오른쪽 단추로 클릭하고 **7-Zip -> 여기에 압축 풀기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e7bdd-137">Right click on the file and select **7-Zip -> Extract here**.</span></span>
* <span data-ttu-id="e7bdd-138">**spark-2.4.1-bin-hadoop2.7.tar**이 다운로드한 **.tgz** 파일과 함께 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7bdd-138">**spark-2.4.1-bin-hadoop2.7.tar** is created alongside the **.tgz** file you downloaded.</span></span>

<span data-ttu-id="e7bdd-139">Apache Spark 파일의 압축을 풀려면:</span><span class="sxs-lookup"><span data-stu-id="e7bdd-139">To extract the Apache Spark files:</span></span>

* <span data-ttu-id="e7bdd-140">**spark-2.4.1-bin-hadoop2.7.tar**을 마우스 오른쪽 단추로 클릭하고 **7-Zip -> 압축 풀기...** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e7bdd-140">Right click on **spark-2.4.1-bin-hadoop2.7.tar** and select **7-Zip -> Extract files...**</span></span>
* <span data-ttu-id="e7bdd-141">**압축 풀기** 필드에 **C:\bin**을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="e7bdd-141">Enter **C:\bin** in the **Extract to** field.</span></span>
* <span data-ttu-id="e7bdd-142">**압축 풀기** 필드 아래에 있는 확인란의 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="e7bdd-142">Uncheck the checkbox below the **Extract to** field.</span></span>
* <span data-ttu-id="e7bdd-143">**확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e7bdd-143">Select **OK**.</span></span>
* <span data-ttu-id="e7bdd-144">Apache Spark 파일이 C:\bin\spark-2.4.1-bin-hadoop2.7\에 추출되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e7bdd-144">The Apache Spark files are extracted to C:\bin\spark-2.4.1-bin-hadoop2.7\</span></span>

![Spark 설치](https://dotnet.microsoft.com/static/images/spark-extract-with-7-zip.png?v=YvjUv54LIxI9FbALPC3h8zSQdyMtK2-NKbFOliG-f8M)

<span data-ttu-id="e7bdd-146">다음 명령을 실행하여 **Windows**에서 Apache Spark를 찾는 데 사용되는 환경 변수를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e7bdd-146">Run the following commands to set the environment variables used to locate Apache Spark on **Windows**:</span></span>

```console
setx HADOOP_HOME C:\bin\spark-2.4.1-bin-hadoop2.7\
setx SPARK_HOME C:\bin\spark-2.4.1-bin-hadoop2.7\
```

<span data-ttu-id="e7bdd-147">다음 명령을 실행하여 **MacOS** 및 **Ubuntu**에서 Apache Spark를 찾는 데 사용되는 환경 변수를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e7bdd-147">Run the following commands to set the environment variables used to locate Apache Spark on **MacOS** and **Ubuntu**:</span></span>

```bash
export SPARK_HOME=~/bin/spark-2.4.1-bin-hadoop2.7/
export PATH="$SPARK_HOME/bin:$PATH"
source ~/.bashrc
```

<span data-ttu-id="e7bdd-148">모든 항목을 설치하고 환경 변수를 설정한 후 **새** 명령 프롬프트 또는 터미널을 열고 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e7bdd-148">Once you've installed everything and set your environment variables, open a **new** command prompt or terminal and run the following command:</span></span>

`%SPARK_HOME%\bin\spark-submit --version`

<span data-ttu-id="e7bdd-149">명령이 실행되고 버전 정보가 출력되면 다음 단계로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7bdd-149">If the command runs and prints version information, you can move to the next step.</span></span>

<span data-ttu-id="e7bdd-150">`'spark-submit' is not recognized as an internal or external command` 오류가 표시되면 **새** 명령 프롬프트를 열었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e7bdd-150">If you receive a `'spark-submit' is not recognized as an internal or external command` error, make sure you opened a **new** command prompt.</span></span>

### <a name="5-install-net-for-apache-spark"></a><span data-ttu-id="e7bdd-151">5. .NET for Apache Spark 설치</span><span class="sxs-lookup"><span data-stu-id="e7bdd-151">5. Install .NET for Apache Spark</span></span>

<span data-ttu-id="e7bdd-152">.NET for Apache Spark GitHub에서 [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) 릴리스를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="e7bdd-152">Download the [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) release from the .NET for Apache Spark GitHub.</span></span> <span data-ttu-id="e7bdd-153">예를 들어 Windows 머신에서 .NET Core를 사용하려는 경우 [Windows x64 netcoreapp3.1 릴리스를 다운로드](https://github.com/dotnet/spark/releases/download/v0.8.0/Microsoft.Spark.Worker.netcoreapp3.1.win-x64-0.8.0.zip)합니다.</span><span class="sxs-lookup"><span data-stu-id="e7bdd-153">For example if you're on a Windows machine and plan to use .NET Core, [download the Windows x64 netcoreapp3.1 release](https://github.com/dotnet/spark/releases/download/v0.8.0/Microsoft.Spark.Worker.netcoreapp3.1.win-x64-0.8.0.zip).</span></span>

<span data-ttu-id="e7bdd-154">Microsoft.Spark.Worker 압축을 풀려면:</span><span class="sxs-lookup"><span data-stu-id="e7bdd-154">To extract the Microsoft.Spark.Worker:</span></span>

* <span data-ttu-id="e7bdd-155">다운로드한 **Microsoft.Spark.Worker.netcoreapp3.1.win-x64-0.8.0.zip** 파일을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="e7bdd-155">Locate the **Microsoft.Spark.Worker.netcoreapp3.1.win-x64-0.8.0.zip** file that you downloaded.</span></span>
* <span data-ttu-id="e7bdd-156">마우스 오른쪽 단추를 클릭하고 **7-Zip -> 압축 풀기...** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e7bdd-156">Right click and select **7-Zip -> Extract files...**.</span></span>
* <span data-ttu-id="e7bdd-157">**압축 풀기** 필드에 **C:\bin**을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="e7bdd-157">Enter **C:\bin** in the **Extract to** field.</span></span>
* <span data-ttu-id="e7bdd-158">**압축 풀기** 필드 아래에 있는 확인란의 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="e7bdd-158">Uncheck the checkbox below the **Extract to** field.</span></span>
* <span data-ttu-id="e7bdd-159">**확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e7bdd-159">Select **OK**.</span></span>

![.NET Spark 설치](https://dotnet.microsoft.com/static/images/dotnet-for-spark-extract-with-7-zip.png?v=jwCyum9mL0mGIi4V5zC7yuvLfcj1_nL-QFFD8TClhZk)

### <a name="6-install-winutils-windows-only"></a><span data-ttu-id="e7bdd-161">6. WinUtils 설치(Windows에만 해당)</span><span class="sxs-lookup"><span data-stu-id="e7bdd-161">6. Install WinUtils (Windows only)</span></span>

<span data-ttu-id="e7bdd-162">.NET for Apache Spark를 사용하려면 Apache Spark와 함께 WinUtils를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7bdd-162">.NET for Apache Spark requires WinUtils to be installed alongside Apache Spark.</span></span> <span data-ttu-id="e7bdd-163">[winutils.exe를 다운로드](https://github.com/steveloughran/winutils/blob/master/hadoop-2.7.1/bin/winutils.exe)합니다.</span><span class="sxs-lookup"><span data-stu-id="e7bdd-163">[Download winutils.exe](https://github.com/steveloughran/winutils/blob/master/hadoop-2.7.1/bin/winutils.exe).</span></span> <span data-ttu-id="e7bdd-164">그런 다음, WinUtils를 **C:\bin\spark-2.4.1-bin-hadoop2.7\bin**에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="e7bdd-164">Then, copy WinUtils into **C:\bin\spark-2.4.1-bin-hadoop2.7\bin**.</span></span>

> [!NOTE]
> <span data-ttu-id="e7bdd-165">다른 Hadoop 버전을 사용 중인 경우(Spark 설치 폴더 이름 끝에 주석으로 처리되어 있음) 해당 Hadoop 버전과 호환되는 [WinUtils 버전을 선택](https://github.com/steveloughran/winutils)합니다.</span><span class="sxs-lookup"><span data-stu-id="e7bdd-165">If you are using a different version of Hadoop, which is annotated at the end of your Spark install folder name, [select the version of WinUtils](https://github.com/steveloughran/winutils) that's compatible with your version of Hadoop.</span></span>

### <a name="7-set-dotnet_worker_dir-and-check-dependencies"></a><span data-ttu-id="e7bdd-166">7. DOTNET_WORKER_DIR 설정 및 종속성 확인</span><span class="sxs-lookup"><span data-stu-id="e7bdd-166">7. Set DOTNET_WORKER_DIR and check dependencies</span></span>

<span data-ttu-id="e7bdd-167">다음 명령 중 하나를 실행하여 .NET 앱에서 .NET for Apache Spark를 찾는 데 사용하는 `DOTNET_WORKER_DIR` 환경 변수를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e7bdd-167">Run one of the following commands to set the `DOTNET_WORKER_DIR` Environment Variable, which is used by .NET apps to locate .NET for Apache Spark.</span></span>

<span data-ttu-id="e7bdd-168">**Windows**에서 [새 환경 변수](https://www.java.com/en/download/help/path.xml) `DOTNET_WORKER_DIR`을 만들고 Microsoft.Spark.Worker(예: `C:\bin\Microsoft.Spark.Worker\`)를 다운로드하여 추출한 디렉터리로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e7bdd-168">On **Windows**, create a [new environment variable](https://www.java.com/en/download/help/path.xml) `DOTNET_WORKER_DIR` and set it to the directory where you downloaded and extracted the Microsoft.Spark.Worker (for example, `C:\bin\Microsoft.Spark.Worker\`).</span></span>

<span data-ttu-id="e7bdd-169">**MacOS**에서 `export DOTNET_WORKER_DIR <your_path>`을 사용하여 새 환경 변수를 만들고 Microsoft.Spark.Worker(예: *~/bin/Microsoft.Spark.Worker/* )를 다운로드하여 추출한 디렉터리로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e7bdd-169">On **MacOS**, create a new environment variable using `export DOTNET_WORKER_DIR <your_path>` and set it to the directory where you downloaded and extracted the Microsoft.Spark.Worker (for example, *~/bin/Microsoft.Spark.Worker/*).</span></span>

<span data-ttu-id="e7bdd-170">**Ubuntu**에서 [새 환경 변수](https://help.ubuntu.com/community/EnvironmentVariables) `DOTNET_WORKER_DIR`을 만들고 Microsoft.Spark.Worker(예: *~/bin/Microsoft.Spark.Worker*)를 다운로드하여 추출한 디렉터리로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e7bdd-170">On **Ubuntu**, create a [new environment variable](https://help.ubuntu.com/community/EnvironmentVariables) `DOTNET_WORKER_DIR` and set it to the directory where you downloaded and extracted the Microsoft.Spark.Worker (for example, *~/bin/Microsoft.Spark.Worker*).</span></span>

<span data-ttu-id="e7bdd-171">마지막으로, 다음 섹션으로 이동하기 전에 명령줄에서 `dotnet`, `java`, `mvn`, `spark-shell`을 실행할 수 있는지 다시 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e7bdd-171">Finally, double-check that you can run `dotnet`, `java`, `mvn`, `spark-shell` from your command line before you move to the next section.</span></span>

## <a name="write-a-net-for-apache-spark-app"></a><span data-ttu-id="e7bdd-172">.NET for Apache Spark 앱 작성</span><span class="sxs-lookup"><span data-stu-id="e7bdd-172">Write a .NET for Apache Spark app</span></span>

### <a name="1-create-a-console-app"></a><span data-ttu-id="e7bdd-173">1. 콘솔 앱 만들기</span><span class="sxs-lookup"><span data-stu-id="e7bdd-173">1. Create a console app</span></span>

<span data-ttu-id="e7bdd-174">명령 프롬프트 또는 터미널에서 다음 명령을 실행하여 새 콘솔 애플리케이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e7bdd-174">In your command prompt or terminal, run the following commands to create a new console application:</span></span>

```dotnetcli
dotnet new console -o mySparkApp
cd mySparkApp
```

<span data-ttu-id="e7bdd-175">`dotnet` 명령은 `console` 형식의 `new` 애플리케이션을 자동으로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e7bdd-175">The `dotnet` command creates a `new` application of type `console` for you.</span></span> <span data-ttu-id="e7bdd-176">`-o` 매개 변수는 앱이 저장되는 *mySparkApp*이라는 디렉터리를 만들고 필요한 파일로 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="e7bdd-176">The `-o` parameter creates a directory named *mySparkApp* where your app is stored and populates it with the required files.</span></span> <span data-ttu-id="e7bdd-177">`cd mySparkApp` 명령은 디렉터리를 방금 만든 앱 디렉터리로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="e7bdd-177">The `cd mySparkApp` command changes the directory to the app directory you just created.</span></span>

### <a name="2-install-nuget-package"></a><span data-ttu-id="e7bdd-178">2. NuGet 패키지 설치</span><span class="sxs-lookup"><span data-stu-id="e7bdd-178">2. Install NuGet package</span></span>

<span data-ttu-id="e7bdd-179">앱에서 .NET for Apache Spark를 사용하려면 Microsoft.Spark 패키지를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="e7bdd-179">To use .NET for Apache Spark in an app, install the Microsoft.Spark package.</span></span> <span data-ttu-id="e7bdd-180">명령 프롬프트 또는 터미널에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e7bdd-180">In your command prompt or terminal, run the following command:</span></span>

`dotnet add package Microsoft.Spark --version 0.8.0`

### <a name="3-code-your-app"></a><span data-ttu-id="e7bdd-181">3. 앱 코딩</span><span class="sxs-lookup"><span data-stu-id="e7bdd-181">3. Code your app</span></span>

<span data-ttu-id="e7bdd-182">Visual Studio Code 또는 텍스트 편집기에서 *Program.cs*를 열고 모든 코드를 다음으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="e7bdd-182">Open *Program.cs* in Visual Studio Code, or any text editor, and replace all of the code with the following:</span></span>

```csharp
using Microsoft.Spark.Sql;

namespace MySparkApp
{
    class Program
    {
        static void Main(string[] args)
        {
            // Create a Spark session.
            SparkSession spark = SparkSession
                .Builder()
                .AppName("word_count_sample")
                .GetOrCreate();

            // Create initial DataFrame.
            DataFrame dataFrame = spark.Read().Text("input.txt");

            // Count words.
            DataFrame words = dataFrame
                .Select(Functions.Split(Functions.Col("value"), " ").Alias("words"))
                .Select(Functions.Explode(Functions.Col("words"))
                .Alias("word"))
                .GroupBy("word")
                .Count()
                .OrderBy(Functions.Col("count").Desc());

            // Show results.
            words.Show();

            // Stop Spark session.
            spark.Stop();
        }
    }
}
```

### <a name="4-create-and-add-a-data-file"></a><span data-ttu-id="e7bdd-183">4. 데이터 파일 만들기 및 추가</span><span class="sxs-lookup"><span data-stu-id="e7bdd-183">4. Create and add a data file</span></span>

<span data-ttu-id="e7bdd-184">명령 프롬프트 또는 터미널을 열고 앱 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="e7bdd-184">Open your command prompt or terminal and navigate into your app folder.</span></span>

```bash
cd <your-app-output-directory>
```

<span data-ttu-id="e7bdd-185">앱은 텍스트 줄이 포함된 파일을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="e7bdd-185">Your app processes a file containing lines of text.</span></span> <span data-ttu-id="e7bdd-186">*mySparkApp* 디렉터리에 다음 텍스트를 포함하는 *input.txt* 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e7bdd-186">Create an *input.txt* file in your *mySparkApp* directory, containing the following text:</span></span>

```text
Hello World
This .NET app uses .NET for Apache Spark
This .NET app counts words with Apache Spark
```

## <a name="run-your-net-for-apache-spark-app"></a><span data-ttu-id="e7bdd-187">.NET for Apache Spark 앱 실행</span><span class="sxs-lookup"><span data-stu-id="e7bdd-187">Run your .NET for Apache Spark app</span></span>

1. <span data-ttu-id="e7bdd-188">다음 명령을 실행하여 애플리케이션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="e7bdd-188">Run the following command to build your application:</span></span>

   ```dotnetcli
   dotnet build
   ```

2. <span data-ttu-id="e7bdd-189">다음 명령을 실행하여 Apache Spark에서 실행할 애플리케이션을 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="e7bdd-189">Run the following command to submit your application to run on Apache Spark:</span></span>

   ```console
   spark-submit \
   --class org.apache.spark.deploy.dotnet.DotnetRunner \
   --master local \
   microsoft-spark-2.4.x-<version>.jar \
   dotnet HelloSpark.dll
   ```

   > [!NOTE]
   > <span data-ttu-id="e7bdd-190">이 명령은 Apache Spark를 다운로드한 후 PATH 환경 변수에 추가했으므로 `spark-submit`를 사용할 수 있다고 전제합니다.</span><span class="sxs-lookup"><span data-stu-id="e7bdd-190">This command assumes you have downloaded Apache Spark and added it to your PATH environment variable to be able to use `spark-submit`.</span></span> <span data-ttu-id="e7bdd-191">그렇지 않은 경우에는 전체 경로를 사용해야 합니다(예: *C:\bin\apache-spark\bin\spark-submit* 또는 *~/spark/bin/spark-submit*).</span><span class="sxs-lookup"><span data-stu-id="e7bdd-191">Otherwise, you'd have to use the full path (for example, *C:\bin\apache-spark\bin\spark-submit* or *~/spark/bin/spark-submit*).</span></span>

3. <span data-ttu-id="e7bdd-192">앱이 실행되면 *input.txt* 파일의 단어 수 데이터가 콘솔에 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7bdd-192">When your app runs, the word count data of the *input.txt* file is written to the console.</span></span>

<span data-ttu-id="e7bdd-193">지금까지</span><span class="sxs-lookup"><span data-stu-id="e7bdd-193">Congratulations!</span></span> <span data-ttu-id="e7bdd-194">.NET for Apache Spark 앱을 작성하고 실행했습니다.</span><span class="sxs-lookup"><span data-stu-id="e7bdd-194">You successfully authored and ran a .NET for Apache Spark app.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e7bdd-195">다음 단계</span><span class="sxs-lookup"><span data-stu-id="e7bdd-195">Next steps</span></span>

<span data-ttu-id="e7bdd-196">본 자습서에서는 다음 작업에 관한 방법을 학습했습니다.</span><span class="sxs-lookup"><span data-stu-id="e7bdd-196">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> * <span data-ttu-id="e7bdd-197">.NET for Apache Spark를 위한 Windows 환경 준비</span><span class="sxs-lookup"><span data-stu-id="e7bdd-197">Prepare your Windows environment for .NET for Apache Spark</span></span>
> * <span data-ttu-id="e7bdd-198">첫 번째 .NET for Apache Spark 애플리케이션 작성</span><span class="sxs-lookup"><span data-stu-id="e7bdd-198">Write your first .NET for Apache Spark application</span></span>
> * <span data-ttu-id="e7bdd-199">간단한 .NET for Apache Spark 애플리케이션 빌드 및 실행</span><span class="sxs-lookup"><span data-stu-id="e7bdd-199">Build and run your simple .NET for Apache Spark application</span></span>

<span data-ttu-id="e7bdd-200">위의 단계를 설명하는 동영상을 보려면 [.NET for Apache Spark 101 동영상 시리즈](https://channel9.msdn.com/Series/NET-for-Apache-Spark-101/Run-Your-First-NET-for-Apache-Spark-App)를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="e7bdd-200">To see a video explaining the steps above, checkout the [.NET for Apache Spark 101 video series](https://channel9.msdn.com/Series/NET-for-Apache-Spark-101/Run-Your-First-NET-for-Apache-Spark-App).</span></span>

<span data-ttu-id="e7bdd-201">자세한 내용은 리소스 페이지를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e7bdd-201">Check out the resources page to learn more.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="e7bdd-202">.NET for Apache Spark 리소스</span><span class="sxs-lookup"><span data-stu-id="e7bdd-202">.NET for Apache Spark Resources</span></span>](../resources/index.md)
