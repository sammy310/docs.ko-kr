---
title: Jupyter Notebook 사용
titleSuffix: .NET for Apache Spark
description: Jupyter Notebook, Jupyter Lab 또는 VS Code(Visual Studio Code)와 같은 대화형 환경에서 .NET for Apache Spark 사용
ms.author: luquinta
author: luisquintanilla
ms.date: 10/09/2020
ms.topic: conceptual
ms.custom: mvc, how-to
ms.openlocfilehash: 9c0e713731b5e2ad742bdd257a99f9029f244363
ms.sourcegitcommit: 3a8f1979a98c6c19217a1930e0af5908988eb8ba
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2021
ms.locfileid: "98536114"
---
# <a name="use-net-for-apache-spark-in-jupyter-notebooks"></a><span data-ttu-id="51597-103">Jupyter Notebook에서 .NET for Apache Spark 사용</span><span class="sxs-lookup"><span data-stu-id="51597-103">Use .NET for Apache Spark in Jupyter Notebooks</span></span>

<span data-ttu-id="51597-104">이 문서에서는 .NET Interactive를 사용하여 Jupyter Notebook 및 VS Code(Visual Studio Code)에서 .NET for Apache Spark 작업을 대화형으로 실행하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="51597-104">In this article, you learn how to run .NET for Apache Spark jobs interactively in Jupyter Notebook and Visual Studio Code (VS Code) with .NET Interactive.</span></span>

## <a name="about-jupyter"></a><span data-ttu-id="51597-105">Jupyter 정보</span><span class="sxs-lookup"><span data-stu-id="51597-105">About Jupyter</span></span>

<span data-ttu-id="51597-106">[Jupyter](https://jupyter.org/)는 사용자가 대화형으로 애플리케이션 프로토타입을 작성하고 개발할 수 있는 방법을 제공하는 오픈 소스 플랫폼 간 컴퓨팅 환경입니다.</span><span class="sxs-lookup"><span data-stu-id="51597-106">[Jupyter](https://jupyter.org/) is an open-source, cross-platform computing environment that provides a way for users to prototype and develop applications interactively.</span></span> <span data-ttu-id="51597-107">Jupyter Notebook, Jupyter Lab, VS Code 등의 다양한 인터페이스를 통해 Jupyter를 조작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51597-107">You can interact with Jupyter through a wide variety of interfaces such as Jupyter Notebook, Jupyter Lab, and VS Code.</span></span>

<span data-ttu-id="51597-108">.NET 컨텍스트에서 .NET Core 전역 도구인 [.NET Interactive](https://github.com/dotnet/interactive)는 Jupyter Notebook과 같은 대화형 컴퓨팅 환경에서 .NET 코드(C#/F#)를 작성하기 위한 커널을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="51597-108">In the context of .NET, [.NET Interactive](https://github.com/dotnet/interactive), a .NET Core global tool, provides a kernel for writing .NET code (C#/F#) in interactive computing environments such as Jupyter Notebook.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="51597-109">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="51597-109">Prerequisites</span></span>

- [<span data-ttu-id="51597-110">.NET Core 3.1 SDK</span><span class="sxs-lookup"><span data-stu-id="51597-110">.NET Core 3.1 SDK</span></span>](../../core/install/index.yml)
- [<span data-ttu-id="51597-111">Apache Spark</span><span class="sxs-lookup"><span data-stu-id="51597-111">Apache Spark</span></span>](https://spark.apache.org/downloads.html)
- [<span data-ttu-id="51597-112">Apache Spark .NET Worker</span><span class="sxs-lookup"><span data-stu-id="51597-112">Apache Spark .NET Worker</span></span>](https://github.com/dotnet/spark/releases)

<span data-ttu-id="51597-113">.NET for Apache Spark 환경을 설정하는 방법에 대한 자세한 내용은 [시작하기 자습서](../tutorials/get-started.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="51597-113">See the [getting started tutorial](../tutorials/get-started.md) for more information on setting up your .NET for Apache Spark environment.</span></span>

## <a name="prepare-environment"></a><span data-ttu-id="51597-114">환경 준비</span><span class="sxs-lookup"><span data-stu-id="51597-114">Prepare environment</span></span>

<span data-ttu-id="51597-115">Jupyter Notebook을 사용하려면 두 가지 항목이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="51597-115">To work with Jupyter Notebooks, you'll need two things.</span></span>

1. <span data-ttu-id="51597-116">[.NET Interactive 전역 .NET 도구](https://github.com/dotnet/interactive/blob/main/docs/NotebooksLocalExperience.md)를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="51597-116">Install the [.NET Interactive global .NET tool](https://github.com/dotnet/interactive/blob/main/docs/NotebooksLocalExperience.md)</span></span>
1. <span data-ttu-id="51597-117">`Microsoft.Spark` NuGet 패키지를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="51597-117">Download the `Microsoft.Spark` NuGet package.</span></span>
    1. <span data-ttu-id="51597-118">[Microsoft.Spark](https://www.nuget.org/packages/Microsoft.Spark/) NuGet 패키지 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="51597-118">Navigate to the [Microsoft.Spark](https://www.nuget.org/packages/Microsoft.Spark/) NuGet package page.</span></span>

        > [!IMPORTANT]
        > <span data-ttu-id="51597-119">기본적으로 최신 버전의 패키지가 다운로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="51597-119">By default, the latest version of the package is downloaded.</span></span> <span data-ttu-id="51597-120">**다운로드한 버전이 Apache Spark .NET Worker와 동일한지 확인합니다.**</span><span class="sxs-lookup"><span data-stu-id="51597-120">**Make sure that the version you download is the same as your Apache Spark .NET Worker.**</span></span>

    1. <span data-ttu-id="51597-121">**정보** 창에서 **패키지 다운로드** 를 선택하여 최신 버전의 패키지를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="51597-121">In the **Info** pane, select **Download package** to download the latest version of the package.</span></span> <span data-ttu-id="51597-122">패키지 이름은 *microsoft.spark.[PACKAGE-VERSION].nupkg* 와 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="51597-122">The name of the package is similar to  *microsoft.spark.[PACKAGE-VERSION].nupkg*.</span></span>
    1. <span data-ttu-id="51597-123">다운로드한 패키지의 압축을 풉니다.</span><span class="sxs-lookup"><span data-stu-id="51597-123">Unzip the downloaded package.</span></span> <span data-ttu-id="51597-124">압축을 푼 디렉터리에 *jars* 라는 하위 디렉터리가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51597-124">The unzipped directory should contain a subdirectory called *jars*.</span></span> <span data-ttu-id="51597-125">나중에 사용되므로 경로를 기록해 둡니다.</span><span class="sxs-lookup"><span data-stu-id="51597-125">Take note of the path since it's used at a later time.</span></span>

## <a name="start-net-for-apache-spark"></a><span data-ttu-id="51597-126">.NET for Apache Spark 시작</span><span class="sxs-lookup"><span data-stu-id="51597-126">Start .NET for Apache Spark</span></span>

<span data-ttu-id="51597-127">다음 명령을 실행하여 .NET for Apache Spark를 디버그 모드로 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="51597-127">Run the following command to start .NET for Apache Spark in debug mode.</span></span> <span data-ttu-id="51597-128">`spark-submit` 명령은 프로세스를 시작하고 [SparkSession](xref:Microsoft.Spark.Sql.SparkSession)의 연결을 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="51597-128">This `spark-submit` command starts a process and waits for connections from a [SparkSession](xref:Microsoft.Spark.Sql.SparkSession).</span></span> <span data-ttu-id="51597-129">사용 중인 .NET for Apache Spark 버전에 해당하는 `microsoft-spark-<spark_majorversion-spark_minorversion>_<scala_majorversion.scala_minorversion>-<spark_dotnet_version>.jar` 경로를 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="51597-129">Make sure to provide the path to the `microsoft-spark-<spark_majorversion-spark_minorversion>_<scala_majorversion.scala_minorversion>-<spark_dotnet_version>.jar` for the respective version of .NET for Apache Spark you're using.</span></span>

<span data-ttu-id="51597-130">**Ubuntu**</span><span class="sxs-lookup"><span data-stu-id="51597-130">**Ubuntu**</span></span>

```bash
spark-submit \
    --class org.apache.spark.deploy.dotnet.DotnetRunner \
    --master local \
    <path-to-microsoft-spark-jar> \
    debug
```

<span data-ttu-id="51597-131">**Windows**</span><span class="sxs-lookup"><span data-stu-id="51597-131">**Windows**</span></span>

```cmd
spark-submit ^
    --class org.apache.spark.deploy.dotnet.DotnetRunner ^
    --master local ^
    <path-to-microsoft-spark-jar> ^
    debug
```

## <a name="create-a-notebook"></a><span data-ttu-id="51597-132">Notebook 만들기</span><span class="sxs-lookup"><span data-stu-id="51597-132">Create a notebook</span></span>

<span data-ttu-id="51597-133">다른 인터페이스를 사용하여 Jupyter를 조작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51597-133">You can use different interfaces to interact with Jupyter.</span></span> <span data-ttu-id="51597-134">브라우저 기반 인터페이스가 필요하면 Jupyter Notebook 또는 Jupyter Lab을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="51597-134">For a browser-based interface, use Jupyter Notebooks or Jupyter Lab.</span></span> <span data-ttu-id="51597-135">로컬 편집기 환경이 필요하면 VS Code를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="51597-135">For a local editor experience, use VS Code.</span></span>

### <a name="jupyter-notebooks--jupyter-lab"></a><span data-ttu-id="51597-136">Jupyter Notebook 및 Jupyter Lab</span><span class="sxs-lookup"><span data-stu-id="51597-136">Jupyter Notebooks & Jupyter Lab</span></span>

1. <span data-ttu-id="51597-137">다른 명령 프롬프트에서 아래 명령 중 하나를 사용하여 Jupyter Notebook 또는 Jupyter Lab을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="51597-137">In another command prompt, start Jupyter Notebook or Jupyter Lab using one of the commands below:</span></span>

    <span data-ttu-id="51597-138">**Jupyter Notebook**</span><span class="sxs-lookup"><span data-stu-id="51597-138">**Jupyter Notebook**</span></span>

    ```bash
    jupyter notebook
    ```

    <span data-ttu-id="51597-139">**Jupyter Lab**</span><span class="sxs-lookup"><span data-stu-id="51597-139">**Jupyter Lab**</span></span>

    ```bash
    jupyter lab
    ```

    <span data-ttu-id="51597-140">위 명령은 Jupyter Notebook 또는 Jupyter Lab 인터페이스를 사용하여 브라우저 창을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="51597-140">These commands launch a browser window with the Jupyter Notebook or Jupyter Lab interface.</span></span>

1. <span data-ttu-id="51597-141">브라우저에서 새 Notebook을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="51597-141">In the browser, create a new notebook.</span></span>

    <span data-ttu-id="51597-142">**Jupyter Notebook**</span><span class="sxs-lookup"><span data-stu-id="51597-142">**Jupyter Notebook**</span></span>

    <span data-ttu-id="51597-143">**새로 만들기 > .NET(C#)** 또는 **새로 만들기 > .NET(F#)** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="51597-143">Select **New > .NET (C#)** or **New > .NET (F#)**</span></span>

    <span data-ttu-id="51597-144">**Jupyter Lab**</span><span class="sxs-lookup"><span data-stu-id="51597-144">**Jupyter Lab**</span></span>

    <span data-ttu-id="51597-145">시작 관리자 창에서 **.NET(C#)** 또는 **.NET(F#)** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="51597-145">In the Launcher window, select **.NET (C#)** or **.NET (F#)**</span></span>

### <a name="visual-studio-code-preview"></a><span data-ttu-id="51597-146">Visual Studio Code(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="51597-146">Visual Studio Code (preview)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="51597-147">VS Code에서 Jupyter Notebook을 사용하려면 다음을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="51597-147">To use Jupyter Notebooks in VS Code, you have to install:</span></span>
>
>- [<span data-ttu-id="51597-148">VS Code Insiders</span><span class="sxs-lookup"><span data-stu-id="51597-148">VS Code Insiders</span></span>](https://code.visualstudio.com/insiders/)
>- [<span data-ttu-id="51597-149">.NET Interactive Notebook 확장</span><span class="sxs-lookup"><span data-stu-id="51597-149">.NET Interactive Notebooks extension</span></span>](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.dotnet-interactive-vscode)

1. <span data-ttu-id="51597-150">VS Code를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="51597-150">Open VS Code.</span></span>
1. <span data-ttu-id="51597-151">명령 팔레트를 엽니다(**보기 > 명령 팔레트**).</span><span class="sxs-lookup"><span data-stu-id="51597-151">Open the command palette **View > Command Palette**.</span></span>

    <span data-ttu-id="51597-152">명령 팔레트가 표시되면 다음 명령을 입력하여 새 .NET Interactive Notebook을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="51597-152">When the command palette appears, enter the following command to create a new .NET Interactive notebook:</span></span>

    ```text
    >.NET Interactive: Create new blank notebook
    ```

    <span data-ttu-id="51597-153">또는 *.ipynb* 확장을 사용하여 기존 .NET Interactive Notebook을 열려면 다음 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="51597-153">Alternatively, if you want to open an existing .NET Interactive notebook with the *.ipynb* extension, use the following command:</span></span>

    ```text
    >.NET Interactive: Open notebook
    ```

## <a name="initialize-a-spark-session"></a><span data-ttu-id="51597-154">Spark 세션 초기화</span><span class="sxs-lookup"><span data-stu-id="51597-154">Initialize a Spark Session</span></span>

1. <span data-ttu-id="51597-155">Notebook이 열리면 `Microsoft.Spark` NuGet 패키지를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="51597-155">When the notebook opens, install the `Microsoft.Spark` NuGet package.</span></span> <span data-ttu-id="51597-156">설치한 버전이 .NET Worker와 동일한지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="51597-156">Make sure the version you install is the same as the .NET Worker.</span></span>

    ```text
    #r "nuget:Microsoft.Spark, 1.0.0"
    ```

1. <span data-ttu-id="51597-157">다음 using 문을 Notebook에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="51597-157">Add the following using statement to the notebook.</span></span>

    ```csharp
    using Microsoft.Spark.Sql;
    ```

1. <span data-ttu-id="51597-158">[SparkSession](xref:Microsoft.Spark.Sql.SparkSession)을 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="51597-158">Initialize your [SparkSession](xref:Microsoft.Spark.Sql.SparkSession).</span></span>

    ```csharp
    var sparkSession =
    SparkSession
        .Builder()
        .AppName("dotnet-interactive-spark")
        .GetOrCreate();
    ```

<span data-ttu-id="51597-159">Notebook이 다음 이미지와 같이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="51597-159">The notebook should look similar to the one in the following image.</span></span> <span data-ttu-id="51597-160">예제에서는 VS Code를 사용하지만 Jupyter Notebook과 Jupyter Lab도 거의 동일하게 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="51597-160">This example uses VS Code, but Jupyter Notebook and Jupyter Lab should look about the same.</span></span>

> [!div class="mx-imgBorder"]
<span data-ttu-id="51597-161">![.NET for Apache Spark Jupyter Notebook VS Code](media/dotnet-spark-jupyter-notebooks/jupyter-notebooks-dotnet-spark-vscode.png)</span><span class="sxs-lookup"><span data-stu-id="51597-161">![.NET for Apache Spark Jupyter Notebook VS Code](media/dotnet-spark-jupyter-notebooks/jupyter-notebooks-dotnet-spark-vscode.png)</span></span>

## <a name="next-steps"></a><span data-ttu-id="51597-162">다음 단계</span><span class="sxs-lookup"><span data-stu-id="51597-162">Next Steps</span></span>

- [<span data-ttu-id="51597-163">.NET for Apache Spark 시작</span><span class="sxs-lookup"><span data-stu-id="51597-163">Get started with .NET for Apache Spark</span></span>](../tutorials/get-started.md)
- [<span data-ttu-id="51597-164">.NET for Apache Spark 및 ML.NET을 사용하여 감정 예측</span><span class="sxs-lookup"><span data-stu-id="51597-164">Predict sentiment using .NET for Apache Spark and ML.NET</span></span>](../tutorials/ml-sentiment-analysis.md)
- <span data-ttu-id="51597-165">.NET Interactive에 대한 자세한 내용은 [.NET Interactive 설명서](https://github.com/dotnet/interactive/blob/main/docs/README.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="51597-165">For more information on .NET Interactive, see the [.NET Interactive documentation](https://github.com/dotnet/interactive/blob/main/docs/README.md).</span></span>
