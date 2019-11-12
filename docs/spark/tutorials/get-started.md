---
title: .NET for Apache Spark 시작
description: Windows에서 .NET Core를 사용하여 .NET for Apache Spark 앱을 실행하는 방법을 살펴봅니다.
ms.date: 11/04/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 1b736e078eea40e399882c0df020062b6aa758ad
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2019
ms.locfileid: "73740520"
---
# <a name="tutorial-get-started-with-net-for-apache-spark"></a><span data-ttu-id="3266b-103">자습서: .NET for Apache Spark 시작</span><span class="sxs-lookup"><span data-stu-id="3266b-103">Tutorial: Get started with .NET for Apache Spark</span></span>

<span data-ttu-id="3266b-104">이 자습서에서는 Windows에서 .NET Core를 사용하여 .NET for Apache Spark 앱을 실행하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3266b-104">This tutorial teaches you how to run a .NET for Apache Spark app using .NET Core on Windows.</span></span>

<span data-ttu-id="3266b-105">이 자습서에서는 다음과 같은 작업을 수행하는 방법을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="3266b-105">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="3266b-106">.NET for Apache Spark를 위한 Windows 환경 준비</span><span class="sxs-lookup"><span data-stu-id="3266b-106">Prepare your Windows environment for .NET for Apache Spark</span></span>
> * <span data-ttu-id="3266b-107">첫 번째 .NET for Apache Spark 애플리케이션 작성</span><span class="sxs-lookup"><span data-stu-id="3266b-107">Write your first .NET for Apache Spark application</span></span>
> * <span data-ttu-id="3266b-108">간단한 .NET for Apache Spark 애플리케이션 빌드 및 실행</span><span class="sxs-lookup"><span data-stu-id="3266b-108">Build and run your simple .NET for Apache Spark application</span></span>

## <a name="prepare-your-environment"></a><span data-ttu-id="3266b-109">환경 준비</span><span class="sxs-lookup"><span data-stu-id="3266b-109">Prepare your environment</span></span>

<span data-ttu-id="3266b-110">앱 작성을 시작하기 전에 몇 가지 필수 구성 요소 종속성을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3266b-110">Before you begin writing your app, you need to setup some prerequisite dependencies.</span></span> <span data-ttu-id="3266b-111">명령줄 환경에서 `dotnet`, `java`, `mvn`, `spark-shell`을 실행할 수 있는 경우 환경은 이미 준비된 것이며 다음 섹션으로 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3266b-111">If you can run `dotnet`, `java`, `mvn`, `spark-shell` from your command line environment, then your environment is already prepared and you can skip to the next section.</span></span> <span data-ttu-id="3266b-112">임의 또는 모든 명령을 실행할 수 없는 경우 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="3266b-112">If you cannot run any or all of the commands, do the following steps.</span></span>

### <a name="1-install-net"></a><span data-ttu-id="3266b-113">1. .NET 설치</span><span class="sxs-lookup"><span data-stu-id="3266b-113">1. Install .NET</span></span>

<span data-ttu-id="3266b-114">.NET 앱 빌드를 시작하려면 .NET SDK(소프트웨어 개발 키트)를 다운로드하여 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3266b-114">To start building .NET apps, you need to download and install the .NET SDK (Software Development Kit).</span></span>

<span data-ttu-id="3266b-115">[.NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core/3.0)를 다운로드하여 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="3266b-115">Download and install the [.NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core/3.0).</span></span> <span data-ttu-id="3266b-116">SDK를 설치하면 `dotnet` 도구 체인이 PATH에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="3266b-116">Installing the SDK adds the `dotnet` toolchain to your PATH.</span></span> 

<span data-ttu-id="3266b-117">.NET Core SDK를 설치한 후에는 새 명령 프롬프트를 열고 `dotnet`을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3266b-117">Once you've installed the .NET Core SDK, open a new command prompt and run `dotnet`.</span></span>

<span data-ttu-id="3266b-118">명령이 실행되고 dotnet 사용 방법에 대한 정보가 출력되면 다음 단계로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3266b-118">If the command runs and prints out information about how to use dotnet, can move to the next step.</span></span> <span data-ttu-id="3266b-119">`'dotnet' is not recognized as an internal or external command` 오류가 표시되면 명령을 실행하기 전에 **새** 명령 프롬프트를 열어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3266b-119">If you receive a `'dotnet' is not recognized as an internal or external command` error, make sure you opened a **new** command prompt before running the command.</span></span> 

### <a name="2-install-java"></a><span data-ttu-id="3266b-120">2. Java 설치</span><span class="sxs-lookup"><span data-stu-id="3266b-120">2. Install Java</span></span>

<span data-ttu-id="3266b-121">[Java 8.1](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="3266b-121">Install [Java 8.1](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html).</span></span>

<span data-ttu-id="3266b-122">운영 체제에 적합한 버전을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3266b-122">Select the appropriate version for your operating system.</span></span> <span data-ttu-id="3266b-123">예를 들어 Windows x64 머신의 경우 **jdk-8u201-windows-x64.exe**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3266b-123">For example, select **jdk-8u201-windows-x64.exe** for a Windows x64 machine.</span></span> <span data-ttu-id="3266b-124">그런 다음, `java` 명령을 사용하여 설치를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3266b-124">Then, use the command `java` to verify the installation.</span></span>
   
![Java 다운로드](https://dotnet.microsoft.com/static/images/java-jdk-downloads-windows.png?v=6BbJHoNyDO-PyYVciImr5wzh2AW_YHNcyb3p093AwPA)

### <a name="3-install-7-zip"></a><span data-ttu-id="3266b-126">3. 7-zip 설치</span><span class="sxs-lookup"><span data-stu-id="3266b-126">3. Install 7-zip</span></span>

<span data-ttu-id="3266b-127">Apache Spark는 압축된 .tgz 파일로 다운로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="3266b-127">Apache Spark is downloaded as a compressed .tgz file.</span></span> <span data-ttu-id="3266b-128">7-zip 같은 압축 풀기 프로그램을 사용하여 파일 압축을 풉니다.</span><span class="sxs-lookup"><span data-stu-id="3266b-128">Use an extraction program, like 7-zip, to extract the file.</span></span>

* <span data-ttu-id="3266b-129">[7-Zip 다운로드](https://www.7-zip.org/)를 방문합니다.</span><span class="sxs-lookup"><span data-stu-id="3266b-129">Visit [7-Zip downloads](https://www.7-zip.org/).</span></span>
* <span data-ttu-id="3266b-130">페이지의 첫 번째 표에서 운영 체제에 따라 32비트 x86 또는 64비트 x64 다운로드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3266b-130">In the first table on the page, select the 32-bit x86 or 64-bit x64 download, depending on your operating system.</span></span>
* <span data-ttu-id="3266b-131">다운로드가 완료되면 설치 관리자를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3266b-131">When the download completes, run the installer.</span></span>
   
![7Zip 다운로드](https://dotnet.microsoft.com/static/images/7-zip-downloads.png?v=W6qWtFC1tTMKv3YGXz7lBa9F3M22uWyTvkMmunyroNk)

### <a name="4-install-apache-spark"></a><span data-ttu-id="3266b-133">4. Apache Spark 설치</span><span class="sxs-lookup"><span data-stu-id="3266b-133">4. Install Apache Spark</span></span>

<span data-ttu-id="3266b-134">[Apache Spark를 다운로드하여 설치](https://spark.apache.org/downloads.html)합니다.</span><span class="sxs-lookup"><span data-stu-id="3266b-134">[Download and install Apache Spark](https://spark.apache.org/downloads.html).</span></span> <span data-ttu-id="3266b-135">버전 2.3.\* 또는 2.4.0, 2.4.1, 2.4.3, 2.4.4 중에서 선택해야 합니다(.NET for Apache Spark는 다른 버전의 Apache Spark와 호환되지 않음).</span><span class="sxs-lookup"><span data-stu-id="3266b-135">You'll need to select from version 2.3.\* or 2.4.0, 2.4.1, 2.4.3, or 2.4.4 (.NET for Apache Spark is not compatible with other versions of Apache Spark).</span></span>  

<span data-ttu-id="3266b-136">다음 단계에서 사용되는 명령에서는 [Apache Spark 2.4.1을 다운로드하여 설치](https://archive.apache.org/dist/spark/spark-2.4.1/spark-2.4.1-bin-hadoop2.7.tgz)했다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="3266b-136">The commands used in the following steps assume you have [downloaded and installed Apache Spark 2.4.1](https://archive.apache.org/dist/spark/spark-2.4.1/spark-2.4.1-bin-hadoop2.7.tgz).</span></span> <span data-ttu-id="3266b-137">다른 버전을 사용하려는 경우 **2.4.1**을 적절한 버전 번호로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="3266b-137">If you wish to use a different version, replace **2.4.1** with the appropriate version number.</span></span> <span data-ttu-id="3266b-138">그런 다음, **.tar** 파일 및 Apache Spark 파일의 압축을 풉니다.</span><span class="sxs-lookup"><span data-stu-id="3266b-138">Then, extract the **.tar** file and the Apache Spark files.</span></span>

<span data-ttu-id="3266b-139">중첩된 **.tar** 파일의 압축을 풀려면:</span><span class="sxs-lookup"><span data-stu-id="3266b-139">To extract the nested **.tar** file:</span></span>

* <span data-ttu-id="3266b-140">다운로드한 **spark-2.4.1-bin-hadoop2.7.tgz** 파일을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="3266b-140">Locate the **spark-2.4.1-bin-hadoop2.7.tgz** file that you downloaded.</span></span>
* <span data-ttu-id="3266b-141">파일을 마우스 오른쪽 단추로 클릭하고 **7-Zip -> 여기에 압축 풀기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3266b-141">Right click on the file and select **7-Zip -> Extract here**.</span></span>
* <span data-ttu-id="3266b-142">**spark-2.4.1-bin-hadoop2.7.tar**이 다운로드한 **.tgz** 파일과 함께 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="3266b-142">**spark-2.4.1-bin-hadoop2.7.tar** is created alongside the **.tgz** file you downloaded.</span></span>

<span data-ttu-id="3266b-143">Apache Spark 파일의 압축을 풀려면:</span><span class="sxs-lookup"><span data-stu-id="3266b-143">To extract the Apache Spark files:</span></span>

* <span data-ttu-id="3266b-144">**spark-2.4.1-bin-hadoop2.7.tar**을 마우스 오른쪽 단추로 클릭하고 **7-Zip -> 압축 풀기...** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3266b-144">Right click on **spark-2.4.1-bin-hadoop2.7.tar** and select **7-Zip -> Extract files...**</span></span>
* <span data-ttu-id="3266b-145">**압축 풀기** 필드에 **C:\bin**을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="3266b-145">Enter **C:\bin** in the **Extract to** field.</span></span>
* <span data-ttu-id="3266b-146">**압축 풀기** 필드 아래에 있는 확인란의 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="3266b-146">Uncheck the checkbox below the **Extract to** field.</span></span>
* <span data-ttu-id="3266b-147">**확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3266b-147">Select **OK**.</span></span>
* <span data-ttu-id="3266b-148">Apache Spark 파일이 C:\bin\spark-2.4.1-bin-hadoop2.7\에 추출되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3266b-148">The Apache Spark files are extracted to C:\bin\spark-2.4.1-bin-hadoop2.7\</span></span>
      
![Spark 설치](https://dotnet.microsoft.com/static/images/spark-extract-with-7-zip.png?v=YvjUv54LIxI9FbALPC3h8zSQdyMtK2-NKbFOliG-f8M)
    
<span data-ttu-id="3266b-150">다음 명령을 실행하여 Apache Spark를 찾는 데 사용되는 환경 변수를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3266b-150">Run the following commands to set the environment variables used to locate Apache Spark:</span></span>

```console
setx HADOOP_HOME C:\bin\spark-2.4.1-bin-hadoop2.7\
setx SPARK_HOME C:\bin\spark-2.4.1-bin-hadoop2.7\
```

<span data-ttu-id="3266b-151">모든 항목을 설치하고 환경 변수를 설정한 후 **새** 명령 프롬프트를 열고 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3266b-151">Once you've installed everything and set your environment variables, open a **new** command prompt and run the following command:</span></span>

`%SPARK_HOME%\bin\spark-submit --version`

<span data-ttu-id="3266b-152">명령이 실행되고 버전 정보가 출력되면 다음 단계로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3266b-152">If the command runs and prints version information, you can move to the next step.</span></span>

<span data-ttu-id="3266b-153">`'spark-submit' is not recognized as an internal or external command` 오류가 표시되면 **새** 명령 프롬프트를 열었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3266b-153">If you receive a `'spark-submit' is not recognized as an internal or external command` error, make sure you opened a **new** command prompt.</span></span>

### <a name="5-install-net-for-apache-spark"></a><span data-ttu-id="3266b-154">5. .NET for Apache Spark 설치</span><span class="sxs-lookup"><span data-stu-id="3266b-154">5. Install .NET for Apache Spark</span></span>

<span data-ttu-id="3266b-155">.NET for Apache Spark GitHub에서 [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) 릴리스를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="3266b-155">Download the [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) release from the .NET for Apache Spark GitHub.</span></span> <span data-ttu-id="3266b-156">예를 들어 Windows 머신에서 .NET Core를 사용하려는 경우 [Windows x64 netcoreapp2.1 릴리스를 다운로드](https://github.com/dotnet/spark/releases/download/v0.5.0/Microsoft.Spark.Worker.netcoreapp2.1.win-x64-0.6.0.zip)합니다.</span><span class="sxs-lookup"><span data-stu-id="3266b-156">For example if you're on a Windows machine and plan to use .NET Core, [download the Windows x64 netcoreapp2.1 release](https://github.com/dotnet/spark/releases/download/v0.5.0/Microsoft.Spark.Worker.netcoreapp2.1.win-x64-0.6.0.zip).</span></span>

<span data-ttu-id="3266b-157">Microsoft.Spark.Worker 압축을 풀려면:</span><span class="sxs-lookup"><span data-stu-id="3266b-157">To extract the Microsoft.Spark.Worker:</span></span>

* <span data-ttu-id="3266b-158">다운로드한 **Microsoft.Spark.Worker.netcoreapp2.1.win-x64-0.6.0.zip** 파일을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="3266b-158">Locate the **Microsoft.Spark.Worker.netcoreapp2.1.win-x64-0.6.0.zip** file that you downloaded.</span></span>
* <span data-ttu-id="3266b-159">마우스 오른쪽 단추를 클릭하고 **7-Zip -> 압축 풀기...** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3266b-159">Right click and select **7-Zip -> Extract files...**.</span></span>
* <span data-ttu-id="3266b-160">**압축 풀기** 필드에 **C:\bin**을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="3266b-160">Enter **C:\bin** in the **Extract to** field.</span></span>
* <span data-ttu-id="3266b-161">**압축 풀기** 필드 아래에 있는 확인란의 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="3266b-161">Uncheck the checkbox below the **Extract to** field.</span></span>
* <span data-ttu-id="3266b-162">**확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3266b-162">Select **OK**.</span></span>
  
![.NET Spark 설치](https://dotnet.microsoft.com/static/images/dotnet-for-spark-extract-with-7-zip.png?v=jwCyum9mL0mGIi4V5zC7yuvLfcj1_nL-QFFD8TClhZk)

### <a name="6-install-winutils"></a><span data-ttu-id="3266b-164">6. WinUtils 설치</span><span class="sxs-lookup"><span data-stu-id="3266b-164">6. Install WinUtils</span></span>

<span data-ttu-id="3266b-165">.NET for Apache Spark를 사용하려면 Apache Spark와 함께 WinUtils를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3266b-165">.NET for Apache Spark requires WinUtils to be installed alongside Apache Spark.</span></span> <span data-ttu-id="3266b-166">[winutils.exe를 다운로드](https://github.com/steveloughran/winutils/blob/master/hadoop-2.7.1/bin/winutils.exe)합니다.</span><span class="sxs-lookup"><span data-stu-id="3266b-166">[Download winutils.exe](https://github.com/steveloughran/winutils/blob/master/hadoop-2.7.1/bin/winutils.exe).</span></span> <span data-ttu-id="3266b-167">그런 다음, WinUtils를 **C:\bin\spark-2.4.1-bin-hadoop2.7\bin**에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="3266b-167">Then, copy WinUtils into **C:\bin\spark-2.4.1-bin-hadoop2.7\bin**.</span></span>

> [!NOTE]
> <span data-ttu-id="3266b-168">다른 Hadoop 버전을 사용 중인 경우(Spark 설치 폴더 이름 끝에 주석으로 처리되어 있음) 해당 Hadoop 버전과 호환되는 [WinUtils 버전을 선택](https://github.com/steveloughran/winutils)합니다.</span><span class="sxs-lookup"><span data-stu-id="3266b-168">If you are using a different version of Hadoop, which is annotated at the end of your Spark install folder name, [select the version of WinUtils](https://github.com/steveloughran/winutils) that's compatible with your version of Hadoop.</span></span> 

### <a name="7-set-dotnet_worker_dir-and-check-dependencies"></a><span data-ttu-id="3266b-169">7. DOTNET_WORKER_DIR 설정 및 종속성 확인</span><span class="sxs-lookup"><span data-stu-id="3266b-169">7. Set DOTNET_WORKER_DIR and check dependencies</span></span>

<span data-ttu-id="3266b-170">다음 명령을 실행하여 .NET 앱에서 .NET for Apache Spark를 찾는 데 사용하는 `DOTNET_WORKER_DIR` 환경 변수를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3266b-170">Run the following command to set the `DOTNET_WORKER_DIR` Environment Variable, which is used by .NET apps to locate .NET for Apache Spark:</span></span>

`setx DOTNET_WORKER_DIR "C:\bin\Microsoft.Spark.Worker-0.6.0"`

<span data-ttu-id="3266b-171">마지막으로, 다음 섹션으로 이동하기 전에 명령줄에서 `dotnet`, `java`, `mvn`, `spark-shell`을 실행할 수 있는지 다시 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3266b-171">Finally, double-check that you can run `dotnet`, `java`, `mvn`, `spark-shell` from your command line before you move to the next section.</span></span>

## <a name="write-a-net-for-apache-spark-app"></a><span data-ttu-id="3266b-172">.NET for Apache Spark 앱 작성</span><span class="sxs-lookup"><span data-stu-id="3266b-172">Write a .NET for Apache Spark app</span></span>

### <a name="1-create-a-console-app"></a><span data-ttu-id="3266b-173">1. 콘솔 앱 만들기</span><span class="sxs-lookup"><span data-stu-id="3266b-173">1. Create a console app</span></span>

<span data-ttu-id="3266b-174">명령 프롬프트에서 다음 명령을 실행하여 새 콘솔 애플리케이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3266b-174">In your command prompt, run the following commands to create a new console application:</span></span>

```console
dotnet new console -o mySparkApp
cd mySparkApp
```

<span data-ttu-id="3266b-175">`dotnet` 명령은 `console` 형식의 `new` 애플리케이션을 자동으로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3266b-175">The `dotnet` command creates a `new` application of type `console` for you.</span></span> <span data-ttu-id="3266b-176">`-o` 매개 변수는 앱이 저장되는 *mySparkApp*이라는 디렉터리를 만들고 필요한 파일로 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="3266b-176">The `-o` parameter creates a directory named *mySparkApp* where your app is stored and populates it with the required files.</span></span> <span data-ttu-id="3266b-177">`cd mySparkApp` 명령은 디렉터리를 방금 만든 앱 디렉터리로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="3266b-177">The `cd mySparkApp` command changes the directory to the app directory you just created.</span></span>

### <a name="2-install-nuget-package"></a><span data-ttu-id="3266b-178">2. NuGet 패키지 설치</span><span class="sxs-lookup"><span data-stu-id="3266b-178">2. Install NuGet package</span></span>

<span data-ttu-id="3266b-179">앱에서 .NET for Apache Spark를 사용하려면 Microsoft.Spark 패키지를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="3266b-179">To use .NET for Apache Spark in an app, install the Microsoft.Spark package.</span></span> <span data-ttu-id="3266b-180">명령 프롬프트에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3266b-180">In your command prompt, run the following command:</span></span>

`dotnet add package Microsoft.Spark --version 0.6.0`

### <a name="3-code-your-app"></a><span data-ttu-id="3266b-181">3. 앱 코딩</span><span class="sxs-lookup"><span data-stu-id="3266b-181">3. Code your app</span></span>

<span data-ttu-id="3266b-182">Visual Studio Code 또는 텍스트 편집기에서 *Program.cs*를 열고 모든 코드를 다음으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="3266b-182">Open *Program.cs* in Visual Studio Code, or any text editor, and replace all of the code with the following:</span></span>

```csharp
using Microsoft.Spark.Sql;

namespace MySparkApp
{
    class Program
    {
        static void Main(string[] args)
        {
            // Create a Spark session.
            var spark = SparkSession
                .Builder()
                .AppName("word_count_sample")
                .GetOrCreate();

            // Create initial DataFrame.
            DataFrame dataFrame = spark.Read().Text("input.txt");

            // Count words.
            var words = dataFrame
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

### <a name="4-add-data-file"></a><span data-ttu-id="3266b-183">4. 데이터 파일 추가</span><span class="sxs-lookup"><span data-stu-id="3266b-183">4. Add data file</span></span>

<span data-ttu-id="3266b-184">앱은 텍스트 줄이 포함된 파일을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="3266b-184">Your app processes a file containing lines of text.</span></span> <span data-ttu-id="3266b-185">*mySparkApp* 디렉터리에 다음 텍스트를 포함하는 *input.txt* 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3266b-185">Create an *input.txt* file in your *mySparkApp* directory, containing the following text:</span></span>

```text
Hello World
This .NET app uses .NET for Apache Spark
This .NET app counts words with Apache Spark
```

## <a name="run-your-net-for-apache-spark-app"></a><span data-ttu-id="3266b-186">.NET for Apache Spark 앱 실행</span><span class="sxs-lookup"><span data-stu-id="3266b-186">Run your .NET for Apache Spark app</span></span>

1. <span data-ttu-id="3266b-187">다음 명령을 실행하여 애플리케이션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="3266b-187">Run the following command to build your application:</span></span>

   ```dotnetcli
   dotnet build
   ```

2. <span data-ttu-id="3266b-188">다음 명령을 실행하여 Apache Spark에서 실행할 애플리케이션을 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="3266b-188">Run the following command to submit your application to run on Apache Spark:</span></span>

   ```powershell
   %SPARK_HOME%\bin\spark-submit --class org.apache.spark.deploy.dotnet.DotnetRunner --master local bin\Debug\netcoreapp3.0\microsoft-spark-2.4.x-0.6.0.jar dotnet bin\Debug\netcoreapp3.0\mySparkApp.dll
   ```

3. <span data-ttu-id="3266b-189">앱이 실행되면 *input.txt* 파일의 단어 수 데이터가 콘솔에 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="3266b-189">When your app runs, the word count data of the *input.txt* file is written to the console.</span></span>

<span data-ttu-id="3266b-190">지금까지</span><span class="sxs-lookup"><span data-stu-id="3266b-190">Congratulations!</span></span> <span data-ttu-id="3266b-191">.NET for Apache Spark 앱을 작성하고 실행했습니다.</span><span class="sxs-lookup"><span data-stu-id="3266b-191">You successfully authored and ran a .NET for Apache Spark app.</span></span>

## <a name="next-steps"></a><span data-ttu-id="3266b-192">다음 단계</span><span class="sxs-lookup"><span data-stu-id="3266b-192">Next steps</span></span>

<span data-ttu-id="3266b-193">본 자습서에서는 다음 작업에 관한 방법을 학습했습니다.</span><span class="sxs-lookup"><span data-stu-id="3266b-193">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> * <span data-ttu-id="3266b-194">.NET for Apache Spark를 위한 Windows 환경 준비</span><span class="sxs-lookup"><span data-stu-id="3266b-194">Prepare your Windows environment for .NET for Apache Spark</span></span>
> * <span data-ttu-id="3266b-195">첫 번째 .NET for Apache Spark 애플리케이션 작성</span><span class="sxs-lookup"><span data-stu-id="3266b-195">Write your first .NET for Apache Spark application</span></span>
> * <span data-ttu-id="3266b-196">간단한 .NET for Apache Spark 애플리케이션 빌드 및 실행</span><span class="sxs-lookup"><span data-stu-id="3266b-196">Build and run your simple .NET for Apache Spark application</span></span>

<span data-ttu-id="3266b-197">위의 단계를 설명하는 동영상을 보려면 [.NET for Apache Spark 101 동영상 시리즈](https://channel9.msdn.com/Series/NET-for-Apache-Spark-101/Run-Your-First-NET-for-Apache-Spark-App)를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="3266b-197">To see a video explaining the steps above, checkout the [.NET for Apache Spark 101 video series](https://channel9.msdn.com/Series/NET-for-Apache-Spark-101/Run-Your-First-NET-for-Apache-Spark-App).</span></span>

<span data-ttu-id="3266b-198">자세한 내용은 리소스 페이지를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3266b-198">Check out the resources page to learn more.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="3266b-199">.NET for Apache Spark 리소스</span><span class="sxs-lookup"><span data-stu-id="3266b-199">.NET for Apache Spark Resources</span></span>](../resources/index.md)
