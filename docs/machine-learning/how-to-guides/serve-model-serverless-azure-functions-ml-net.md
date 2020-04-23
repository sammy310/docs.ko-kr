---
title: Azure Functions에 모델 배포
description: Azure Functions를 사용하여 인터넷을 통해 예측하기 위한 ML.NET 감정 분석 기계 학습 모델 제공
ms.date: 02/21/2020
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc, how-to
ms.openlocfilehash: 2f340805200a14e0e145ffe1bf20f8059df63555
ms.sourcegitcommit: d9470d8b2278b33108332c05224d86049cb9484b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/17/2020
ms.locfileid: "81608051"
---
# <a name="deploy-a-model-to-azure-functions"></a><span data-ttu-id="a32c6-103">Azure Functions에 모델 배포</span><span class="sxs-lookup"><span data-stu-id="a32c6-103">Deploy a model to Azure Functions</span></span>

<span data-ttu-id="a32c6-104">Azure Functions 서버리스 환경을 통해 HTTP에서의 예측을 위해 미리 학습된 ML.NET 기계 학습 모델을 배포하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-104">Learn how to deploy a pre-trained ML.NET machine learning model for predictions over HTTP through an Azure Functions serverless environment.</span></span>

> [!NOTE]
> <span data-ttu-id="a32c6-105">이 샘플은 `PredictionEnginePool` 서비스의 미리 보기 버전을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-105">This sample runs a preview version of the `PredictionEnginePool` service.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a32c6-106">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="a32c6-106">Prerequisites</span></span>

- <span data-ttu-id="a32c6-107">“.NET Core 플랫폼 간 개발” 및 “Azure 개발” 워크로드가 설치된 [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) 이상 또는 Visual Studio 2017 버전 15.6 이상.</span><span class="sxs-lookup"><span data-stu-id="a32c6-107">[Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) or later or Visual Studio 2017 version 15.6 or later with the ".NET Core cross-platform development" and "Azure development" workloads installed.</span></span>
- [<span data-ttu-id="a32c6-108">Azure Functions 도구</span><span class="sxs-lookup"><span data-stu-id="a32c6-108">Azure Functions Tools</span></span>](/azure/azure-functions/functions-develop-vs#check-your-tools-version)
- <span data-ttu-id="a32c6-109">PowerShell</span><span class="sxs-lookup"><span data-stu-id="a32c6-109">Powershell</span></span>
- <span data-ttu-id="a32c6-110">미리 학습된 모델입니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-110">Pre-trained model.</span></span> <span data-ttu-id="a32c6-111">[ML.NET 감정 분석 자습서](../tutorials/sentiment-analysis.md)를 사용하여 자체 모델을 빌드하거나 이 [미리 학습된 감정 분석 기계 학습 모델](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip) 다운로드</span><span class="sxs-lookup"><span data-stu-id="a32c6-111">Use the [ML.NET Sentiment Analysis tutorial](../tutorials/sentiment-analysis.md) to build your own model or download this [pre-trained sentiment analysis machine learning model](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)</span></span>

## <a name="azure-functions-sample-overview"></a><span data-ttu-id="a32c6-112">Azure Functions 샘플 개요</span><span class="sxs-lookup"><span data-stu-id="a32c6-112">Azure Functions sample overview</span></span>

<span data-ttu-id="a32c6-113">이 샘플은 미리 학습된 이진 분류 모델을 사용하여 텍스트의 감정을 긍정 또는 부정으로 분류하는 **C# HTTP 트리거 Azure Functions 애플리케이션**입니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-113">This sample is a **C# HTTP Trigger Azure Functions application** that uses a pretrained binary classification model to categorize the sentiment of text as positive or negative.</span></span> <span data-ttu-id="a32c6-114">Azure Functions는 클라우드의 관리되는 서버리스 환경에서 작은 코드를 대규모로 실행하는 간편한 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-114">Azure Functions provides an easy way to run small pieces of code at scale on a managed serverless environment in the cloud.</span></span> <span data-ttu-id="a32c6-115">이 샘플의 코드는 GitHub의 [dotnet/machinelearning-samples repository](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/end-to-end-apps/ScalableMLModelOnAzureFunction)에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-115">The code for this sample can be found on the [dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/end-to-end-apps/ScalableMLModelOnAzureFunction) repository on GitHub.</span></span>

## <a name="create-azure-functions-project"></a><span data-ttu-id="a32c6-116">Azure Functions 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="a32c6-116">Create Azure Functions project</span></span>

1. <span data-ttu-id="a32c6-117">Visual Studio 2017을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-117">Open Visual Studio 2017.</span></span> <span data-ttu-id="a32c6-118">메뉴 모음에서 **파일** > **새로 만들기** > **프로젝트**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-118">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="a32c6-119">**새 프로젝트** 대화 상자에서 **Visual C#** 노드와 **Cloud** 노드를 차례로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-119">In the **New Project** dialog, select the **Visual C#** node followed by the **Cloud** node.</span></span> <span data-ttu-id="a32c6-120">그런 다음, **Azure Functions** 프로젝트 템플릿을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-120">Then select the **Azure Functions** project template.</span></span> <span data-ttu-id="a32c6-121">**이름** 텍스트 상자에 “SentimentAnalysisFunctionsApp”을 입력한 다음, **확인** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-121">In the **Name** text box, type "SentimentAnalysisFunctionsApp" and then select the **OK** button.</span></span>
1. <span data-ttu-id="a32c6-122">**새 프로젝트** 대화 상자에서 프로젝트 옵션 위의 드롭다운을 열고 **Azure Functions v2(.NET Core)** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-122">In the **New Project** dialog, open the dropdown above the project options and select **Azure Functions v2 (.NET Core)**.</span></span> <span data-ttu-id="a32c6-123">그런 다음, **HTTP 트리거** 프로젝트를 선택한 후 **확인** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-123">Then, select the **Http trigger** project and then select the **OK** button.</span></span>
1. <span data-ttu-id="a32c6-124">프로젝트에서 *MLModels* 디렉터리를 만들어 모델을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-124">Create a directory named *MLModels* in your project to save your model:</span></span>

    <span data-ttu-id="a32c6-125">**솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가** > **새 폴더**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-125">In **Solution Explorer**, right-click on your project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="a32c6-126">“MLModels”를 입력하고 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-126">Type "MLModels" and hit Enter.</span></span>

1. <span data-ttu-id="a32c6-127">**Microsoft.ML NuGet 패키지** 버전 **1.3.1**을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-127">Install the **Microsoft.ML NuGet Package** version **1.3.1**:</span></span>

    <span data-ttu-id="a32c6-128">솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **NuGet 패키지 관리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-128">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="a32c6-129">“nuget.org”를 패키지 소스로 선택하고, [찾아보기] 탭을 선택하고, **Microsoft.ML**을 검색하고, 목록에서 해당 패키지를 선택하고, **설치** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-129">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="a32c6-130">**변경 내용 미리 보기** 대화 상자에서 **확인** 단추를 선택한 다음, 나열된 패키지의 사용 조건에 동의하는 경우 **라이선스 승인** 대화 상자에서 **동의함** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-130">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

1. <span data-ttu-id="a32c6-131">**Microsoft.Azure.Functions.Extensions NuGet 패키지**를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-131">Install the **Microsoft.Azure.Functions.Extensions NuGet Package**:</span></span>

    <span data-ttu-id="a32c6-132">솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **NuGet 패키지 관리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-132">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="a32c6-133">“nuget.org”를 패키지 소스로 선택하고 찾아보기 탭을 선택합니다. **Microsoft.Azure.Functions.Extensions**를 검색하고 목록에서 해당 패키지를 선택한 다음, **설치** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-133">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.Azure.Functions.Extensions**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="a32c6-134">**변경 내용 미리 보기** 대화 상자에서 **확인** 단추를 선택한 다음, 나열된 패키지의 사용 조건에 동의하는 경우 **라이선스 승인** 대화 상자에서 **동의함** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-134">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

1. <span data-ttu-id="a32c6-135">**Microsoft.Extensions.ML NuGet 패키지** 버전 **0.15.1**을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-135">Install the **Microsoft.Extensions.ML NuGet Package** version **0.15.1**:</span></span>

    <span data-ttu-id="a32c6-136">솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **NuGet 패키지 관리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-136">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="a32c6-137">“nuget.org”를 패키지 원본으로 선택하고, 찾아보기 탭을 선택하고, **Microsoft.Extensions.ML**을 검색하고, 목록에서 해당 패키지를 선택하고, **설치** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-137">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.Extensions.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="a32c6-138">**변경 내용 미리 보기** 대화 상자에서 **확인** 단추를 선택한 다음, 나열된 패키지의 사용 조건에 동의하는 경우 **라이선스 승인** 대화 상자에서 **동의함** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-138">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

1. <span data-ttu-id="a32c6-139">**Microsoft.NET.Sdk.Functions NuGet 패키지** 버전 **1.0.31**을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-139">Install the **Microsoft.NET.Sdk.Functions NuGet Package** version **1.0.31**:</span></span>

    <span data-ttu-id="a32c6-140">솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **NuGet 패키지 관리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-140">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="a32c6-141">“nuget.org”를 패키지 소스로 선택하고 설치됨 탭을 선택합니다. **Microsoft.NET.Sdk.Functions**를 검색하고 목록에서 해당 패키지를 선택한 후 버전 드롭다운에서 **1.0.31**을 선택하고 **업데이트** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-141">Choose "nuget.org" as the Package source, select the Installed tab, search for **Microsoft.NET.Sdk.Functions**, select that package in the list, select **1.0.31** from the Version dropdown, and select the **Update** button.</span></span> <span data-ttu-id="a32c6-142">**변경 내용 미리 보기** 대화 상자에서 **확인** 단추를 선택한 다음, 나열된 패키지의 사용 조건에 동의하는 경우 **라이선스 승인** 대화 상자에서 **동의함** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-142">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

## <a name="add-pre-trained-model-to-project"></a><span data-ttu-id="a32c6-143">프로젝트에 미리 학습된 모델 추가</span><span class="sxs-lookup"><span data-stu-id="a32c6-143">Add pre-trained model to project</span></span>

1. <span data-ttu-id="a32c6-144">미리 빌드된 모델을 *MLModels* 폴더에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-144">Copy your pre-built model to the *MLModels* folder.</span></span>
1. <span data-ttu-id="a32c6-145">솔루션 탐색기에서 미리 빌드된 모델 파일을 마우스 오른쪽 단추로 클릭하고 **속성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-145">In Solution Explorer, right-click your pre-built model file and select **Properties**.</span></span> <span data-ttu-id="a32c6-146">**고급** 아래에서 **출력 디렉터리에 복사** 값을 **변경된 내용만 복사**로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-146">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

## <a name="create-azure-function-to-analyze-sentiment"></a><span data-ttu-id="a32c6-147">감정을 분석하는 Azure Function 만들기</span><span class="sxs-lookup"><span data-stu-id="a32c6-147">Create Azure Function to analyze sentiment</span></span>

<span data-ttu-id="a32c6-148">감정을 예측하는 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-148">Create a class to predict sentiment.</span></span> <span data-ttu-id="a32c6-149">새 클래스를 프로젝트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-149">Add a new class to your project:</span></span>

1. <span data-ttu-id="a32c6-150">**솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가** > **새 항목**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-150">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="a32c6-151">**새 항목 추가** 대화 상자에서 **Azure 함수**를 선택하고 **이름** 필드를 *AnalyzeSentiment.cs*로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-151">In the **Add New Item** dialog box, select **Azure Function** and change the **Name** field to *AnalyzeSentiment.cs*.</span></span> <span data-ttu-id="a32c6-152">그런 다음, **추가** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-152">Then, select the **Add** button.</span></span>

1. <span data-ttu-id="a32c6-153">**새 Azure 함수** 대화 상자에서 **HTTP 트리거**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-153">In the **New Azure Function** dialog box, select **Http Trigger**.</span></span> <span data-ttu-id="a32c6-154">그런 다음, **확인** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-154">Then, select the **OK** button.</span></span>

    <span data-ttu-id="a32c6-155">*AnalyzeSentiment.cs* 파일이 코드 편집기에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-155">The *AnalyzeSentiment.cs* file opens in the code editor.</span></span> <span data-ttu-id="a32c6-156">다음 `using` 문을 *AnalyzeSentiment.cs*의 맨 위에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-156">Add the following `using` statement to the top of *AnalyzeSentiment.cs*:</span></span>

    [!code-csharp [AnalyzeUsings](~/machinelearning-samples/samples/csharp/end-to-end-apps/ScalableMLModelOnAzureFunction/SentimentAnalysisFunctionsApp/AnalyzeSentiment.cs#L1-L11)]

    <span data-ttu-id="a32c6-157">기본적으로 `AnalyzeSentiment` 클래스는 `static`입니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-157">By default, the `AnalyzeSentiment` class is `static`.</span></span> <span data-ttu-id="a32c6-158">클래스 정의에서 `static` 키워드를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-158">Make sure to remove the `static` keyword from the class definition.</span></span>

    ```csharp
    public class AnalyzeSentiment
    {

    }
    ```

## <a name="create-data-models"></a><span data-ttu-id="a32c6-159">데이터 모델 만들기</span><span class="sxs-lookup"><span data-stu-id="a32c6-159">Create data models</span></span>

<span data-ttu-id="a32c6-160">입력 데이터 및 예측에 대한 일부 클래스를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-160">You need to create some classes for your input data and predictions.</span></span> <span data-ttu-id="a32c6-161">새 클래스를 프로젝트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-161">Add a new class to your project:</span></span>

1. <span data-ttu-id="a32c6-162">프로젝트에서 *DataModels* 디렉터리를 만들어 데이터 모델을 저장합니다. 솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가 > 새 폴더**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-162">Create a directory named *DataModels* in your project to save your data models: In Solution Explorer, right-click on your project and select **Add > New Folder**.</span></span> <span data-ttu-id="a32c6-163">“DataModels”를 입력하고 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-163">Type "DataModels" and hit Enter.</span></span>
2. <span data-ttu-id="a32c6-164">솔루션 탐색기에서 *DataModels* 디렉터리를 마우스 오른쪽 단추로 클릭하고 **추가 > 새 항목**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-164">In Solution Explorer, right-click the *DataModels* directory, and then select **Add > New Item**.</span></span>
3. <span data-ttu-id="a32c6-165">**새 항목 추가** 대화 상자에서 **클래스**를 선택하고 **이름** 필드를 *SentimentData.cs*로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-165">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentData.cs*.</span></span> <span data-ttu-id="a32c6-166">그런 다음, **추가** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-166">Then, select the **Add** button.</span></span>

    <span data-ttu-id="a32c6-167">*SentimentData.cs* 파일이 코드 편집기에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-167">The *SentimentData.cs* file opens in the code editor.</span></span> <span data-ttu-id="a32c6-168">다음 using 문을 *SentimentData.cs*의 맨 위에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-168">Add the following using statement to the top of *SentimentData.cs*:</span></span>

    [!code-csharp [SentimentDataUsings](~/machinelearning-samples/samples/csharp/end-to-end-apps/ScalableMLModelOnAzureFunction/SentimentAnalysisFunctionsApp/DataModels/SentimentData.cs#L1)]

    <span data-ttu-id="a32c6-169">기존 클래스 정의를 제거하고 다음 코드를 *SentimentData.cs* 파일에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-169">Remove the existing class definition and add the following code to the *SentimentData.cs* file:</span></span>

    [!code-csharp [SentimentData](~/machinelearning-samples/samples/csharp/end-to-end-apps/ScalableMLModelOnAzureFunction/SentimentAnalysisFunctionsApp/DataModels/SentimentData.cs#L5-L13)]

4. <span data-ttu-id="a32c6-170">솔루션 탐색기에서 *DataModels* 디렉터리를 마우스 오른쪽 단추로 클릭하고 **추가 > 새 항목**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-170">In Solution Explorer, right-click the *DataModels* directory, and then select **Add > New Item**.</span></span>
5. <span data-ttu-id="a32c6-171">**새 항목 추가** 대화 상자에서 **클래스**를 선택하고 **이름** 필드를 *SentimentPrediction.cs*로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-171">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentPrediction.cs*.</span></span> <span data-ttu-id="a32c6-172">그런 다음, **추가** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-172">Then, select the **Add** button.</span></span> <span data-ttu-id="a32c6-173">*SentimentPrediction.cs* 파일이 코드 편집기에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-173">The *SentimentPrediction.cs* file opens in the code editor.</span></span> <span data-ttu-id="a32c6-174">다음 using 문을 *SentimentPrediction.cs*의 맨 위에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-174">Add the following using statement to the top of *SentimentPrediction.cs*:</span></span>

    [!code-csharp [SentimentPredictionUsings](~/machinelearning-samples/samples/csharp/end-to-end-apps/ScalableMLModelOnAzureFunction/SentimentAnalysisFunctionsApp/DataModels/SentimentPrediction.cs#L1)]

    <span data-ttu-id="a32c6-175">기존 클래스 정의를 제거하고 다음 코드를 *SentimentPrediction.cs* 파일에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-175">Remove the existing class definition and add the following code to the *SentimentPrediction.cs* file:</span></span>

    [!code-csharp [SentimentPrediction](~/machinelearning-samples/samples/csharp/end-to-end-apps/ScalableMLModelOnAzureFunction/SentimentAnalysisFunctionsApp/DataModels/SentimentPrediction.cs#L5-L14)]

    <span data-ttu-id="a32c6-176">`SentimentPrediction`은 `SentimentText` 속성의 원래 데이터와 모델에서 생성된 출력에 대한 액세스를 제공하는 `SentimentData`에서 상속됩니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-176">`SentimentPrediction` inherits from `SentimentData` which provides access to the original data in the `SentimentText` property as well as the output generated by the model.</span></span>

## <a name="register-predictionenginepool-service"></a><span data-ttu-id="a32c6-177">PredictionEnginePool 서비스 등록</span><span class="sxs-lookup"><span data-stu-id="a32c6-177">Register PredictionEnginePool service</span></span>

<span data-ttu-id="a32c6-178">단일 예측을 수행하려면 [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602)을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-178">To make a single prediction, you have to create a [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602).</span></span> <span data-ttu-id="a32c6-179">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602)은 스레드로부터 안전하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-179">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) is not thread-safe.</span></span> <span data-ttu-id="a32c6-180">또한 애플리케이션 내에서 필요한 모든 위치에서 인스턴스를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-180">Additionally, you have to create an instance of it everywhere it is needed within your application.</span></span> <span data-ttu-id="a32c6-181">애플리케이션이 커지면 이 프로세스를 관리할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-181">As your application grows, this process can become unmanageable.</span></span> <span data-ttu-id="a32c6-182">성능 및 스레드 보안을 개선하려면 종속성 주입과 `PredictionEnginePool` 서비스를 함께 사용합니다. 이 서비스는 애플리케이션 전체에서 사용할 [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) 개체의 [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601)을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-182">For improved performance and thread safety, use a combination of dependency injection and the `PredictionEnginePool` service, which creates an [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) of [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) objects for use throughout your application.</span></span>

<span data-ttu-id="a32c6-183">[종속성 주입](https://en.wikipedia.org/wiki/Dependency_injection)에 대한 자세한 내용은 다음 링크를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a32c6-183">The following link provides more information if you want to learn more about [dependency injection](https://en.wikipedia.org/wiki/Dependency_injection).</span></span>

1. <span data-ttu-id="a32c6-184">**솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가** > **새 항목**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-184">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="a32c6-185">**새 항목 추가** 대화 상자에서 **클래스**를 선택하고 **이름** 필드를 *Startup.cs*로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-185">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *Startup.cs*.</span></span> <span data-ttu-id="a32c6-186">그런 다음, **추가** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-186">Then, select the **Add** button.</span></span>
1. <span data-ttu-id="a32c6-187">다음 using 문을 *Startup.cs*의 맨 위에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-187">Add the following using statements to the top of *Startup.cs*:</span></span>

    [!code-csharp [StartupUsings](~/machinelearning-samples/samples/csharp/end-to-end-apps/ScalableMLModelOnAzureFunction/SentimentAnalysisFunctionsApp/Startup.cs#L1-L6)]

1. <span data-ttu-id="a32c6-188">using 문 아래의 기존 코드를 제거하고 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-188">Remove the existing code below the using statements and add the following code:</span></span>

    ```csharp
    [assembly: FunctionsStartup(typeof(Startup))]
    namespace SentimentAnalysisFunctionsApp
    {
        public class Startup : FunctionsStartup
        {

        }
    }
    ```

1. <span data-ttu-id="a32c6-189">앱이 실행되는 환경 및 모델이 `Startup` 클래스 내에 있는 파일 경로를 저장할 변수를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-189">Define variables to store the environment the app is running in and the file path where the model is located inside the `Startup` class</span></span>

    [!code-csharp [DefineStartupVars](~/machinelearning-samples/samples/csharp/end-to-end-apps/ScalableMLModelOnAzureFunction/SentimentAnalysisFunctionsApp/Startup.cs#L13-L14)]

1. <span data-ttu-id="a32c6-190">그런 다음 `_environment` 및 `_modelPath` 변수 값을 설정하는 생성자를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-190">Below that, create a constructor to set the values of the `_environment` and `_modelPath` variables.</span></span> <span data-ttu-id="a32c6-191">애플리케이션을 로컬로 실행하는 경우 기본 환경은 *개발*입니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-191">When the application is running locally, the default environment is *Development*.</span></span>

    [!code-csharp [StartupCtor](~/machinelearning-samples/samples/csharp/end-to-end-apps/ScalableMLModelOnAzureFunction/SentimentAnalysisFunctionsApp/Startup.cs#L16-L29)]

1. <span data-ttu-id="a32c6-192">그런 다음 `Configure`라는 새 메서드를 추가하여 생성자 아래에 `PredictionEnginePool` 서비스를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-192">Then, add a new method called `Configure` to register the `PredictionEnginePool` service below the constructor.</span></span>

    [!code-csharp [ConfigureServices](~/machinelearning-samples/samples/csharp/end-to-end-apps/ScalableMLModelOnAzureFunction/SentimentAnalysisFunctionsApp/Startup.cs#L31-L35)]

<span data-ttu-id="a32c6-193">개략적으로 이 코드는 애플리케이션을 수동으로 초기화하지 않고도 애플리케이션에서 요청할 때 나중에 사용할 수 있도록 자동으로 개체 및 서비스를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-193">At a high level, this code initializes the objects and services automatically for later use when requested by the application instead of having to manually do it.</span></span>

<span data-ttu-id="a32c6-194">기계 학습 모델은 정적이지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-194">Machine learning models are not static.</span></span> <span data-ttu-id="a32c6-195">새 학습 데이터를 사용할 수 있게 되면 모델을 다시 학습하고 다시 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-195">As new training data becomes available, the model is retrained and redeployed.</span></span> <span data-ttu-id="a32c6-196">최신 버전의 모델을 애플리케이션으로 가져오는 한 가지 방법은 전체 애플리케이션을 다시 배포하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-196">One way to get the latest version of the model into your application is to redeploy the entire application.</span></span> <span data-ttu-id="a32c6-197">그러나 이 경우 애플리케이션 가동 중지 시간이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-197">However, this introduces application downtime.</span></span> <span data-ttu-id="a32c6-198">`PredictionEnginePool` 서비스는 애플리케이션을 가동 중지하지 않으면서 업데이트된 모델을 다시 로드하는 메커니즘을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-198">The `PredictionEnginePool` service provides a mechanism to reload an updated model without taking your application down.</span></span>

<span data-ttu-id="a32c6-199">`watchForChanges` 매개 변수를 `true`로 설정하면 `PredictionEnginePool`은 파일 시스템 변경 알림을 수신 대기하고 파일이 변경될 때 이벤트를 발생시키는 [`FileSystemWatcher`](xref:System.IO.FileSystemWatcher)를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-199">Set the `watchForChanges` parameter to `true`, and the `PredictionEnginePool` starts a [`FileSystemWatcher`](xref:System.IO.FileSystemWatcher) that listens to the file system change notifications and raises events when there is a change to the file.</span></span> <span data-ttu-id="a32c6-200">그러면 `PredictionEnginePool`에서 모델을 자동으로 다시 로드하도록 지정할 수 있는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-200">This prompts the `PredictionEnginePool` to automatically reload the model.</span></span>

<span data-ttu-id="a32c6-201">모델은 `modelName` 매개 변수로 식별되므로 변경 시, 애플리케이션당 두 개 이상의 모델이 다시 로드될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-201">The model is identified by the `modelName` parameter so that more than one model per application can be reloaded upon change.</span></span>

> [!TIP]
> <span data-ttu-id="a32c6-202">또는 원격으로 저장된 모델을 사용하는 경우 `FromUri` 메서드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-202">Alternatively, you can use the `FromUri` method when working with models stored remotely.</span></span> <span data-ttu-id="a32c6-203">`FromUri`는 파일 변경 이벤트를 감시하지 않고, 원격 위치에서 변경 내용을 폴링합니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-203">Rather than watching for file changed events, `FromUri` polls the remote location for changes.</span></span> <span data-ttu-id="a32c6-204">폴링 간격의 기본값은 5분입니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-204">The polling interval defaults to 5 minutes.</span></span> <span data-ttu-id="a32c6-205">애플리케이션의 요구 사항에 따라 폴링 간격을 늘리거나 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-205">You can increase or decrease the polling interval based on your application's requirements.</span></span> <span data-ttu-id="a32c6-206">아래 코드 샘플에서 `PredictionEnginePool`은 1분마다 지정된 URI에 저장된 모델을 폴링합니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-206">In the code sample below, the `PredictionEnginePool` polls the model stored at the specified URI every minute.</span></span>
>
>```csharp
>builder.Services.AddPredictionEnginePool<SentimentData, SentimentPrediction>()
>   .FromUri(
>       modelName: "SentimentAnalysisModel",
>       uri:"https://github.com/dotnet/samples/raw/master/machine-learning/models/sentimentanalysis/sentiment_model.zip",
>       period: TimeSpan.FromMinutes(1));
>```

## <a name="load-the-model-into-the-function"></a><span data-ttu-id="a32c6-207">함수에 모델 로드</span><span class="sxs-lookup"><span data-stu-id="a32c6-207">Load the model into the function</span></span>

<span data-ttu-id="a32c6-208">*AnalyzeSentiment* 클래스 안에 다음 코드를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-208">Insert the following code inside the *AnalyzeSentiment* class:</span></span>

[!code-csharp [AnalyzeCtor](~/machinelearning-samples/samples/csharp/end-to-end-apps/ScalableMLModelOnAzureFunction/SentimentAnalysisFunctionsApp/AnalyzeSentiment.cs#L18-L24)]

<span data-ttu-id="a32c6-209">이 코드는 종속성 주입을 통해 가져오는 함수의 생성자에 `PredictionEnginePool`을 전달하여 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-209">This code assigns the `PredictionEnginePool` by passing it to the function's constructor which you get via dependency injection.</span></span>

## <a name="use-the-model-to-make-predictions"></a><span data-ttu-id="a32c6-210">모델을 사용하여 예측하기</span><span class="sxs-lookup"><span data-stu-id="a32c6-210">Use the model to make predictions</span></span>

<span data-ttu-id="a32c6-211">*AnalyzeSentiment* 클래스에서 *Run* 메서드의 기존 구현을 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-211">Replace the existing implementation of *Run* method in *AnalyzeSentiment* class with the following code:</span></span>

[!code-csharp [AnalyzeRunMethod](~/machinelearning-samples/samples/csharp/end-to-end-apps/ScalableMLModelOnAzureFunction/SentimentAnalysisFunctionsApp/AnalyzeSentiment.cs#L26-L45)]

<span data-ttu-id="a32c6-212">`Run` 메서드가 실행되면 HTTP 요청에서 수신되는 데이터가 역직렬화되어 `PredictionEnginePool`에 대한 입력으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-212">When the `Run` method executes, the incoming data from the HTTP request is deserialized and used as input for the `PredictionEnginePool`.</span></span> <span data-ttu-id="a32c6-213">그런 다음, `Predict` 메서드가 `Startup` 클래스에 등록된 `SentimentAnalysisModel`을 사용하여 예측을 수행하고 성공하면 결과를 사용자에게 다시 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-213">The `Predict` method is then called to make predictions using the `SentimentAnalysisModel` registered in the `Startup` class and returns the results back to the user if successful.</span></span>

## <a name="test-locally"></a><span data-ttu-id="a32c6-214">로컬로 테스트</span><span class="sxs-lookup"><span data-stu-id="a32c6-214">Test locally</span></span>

<span data-ttu-id="a32c6-215">이제 모든 것이 설정되었으므로 애플리케이션을 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-215">Now that everything is set up, it's time to test the application:</span></span>

1. <span data-ttu-id="a32c6-216">애플리케이션 실행</span><span class="sxs-lookup"><span data-stu-id="a32c6-216">Run the application</span></span>
1. <span data-ttu-id="a32c6-217">PowerShell을 열고 PORT가 애플리케이션을 실행 중인 포트인 경우 프롬프트에 코드를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-217">Open PowerShell and enter the code into the prompt where PORT is the port your application is running on.</span></span> <span data-ttu-id="a32c6-218">일반적으로 포트는 7071입니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-218">Typically the port is 7071.</span></span>

    ```powershell
    Invoke-RestMethod "http://localhost:<PORT>/api/AnalyzeSentiment" -Method Post -Body (@{SentimentText="This is a very bad steak"} | ConvertTo-Json) -ContentType "application/json"
    ```

    <span data-ttu-id="a32c6-219">성공하면 출력이 아래 텍스트와 같이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-219">If successful, the output should look similar to the text below:</span></span>

    ```powershell
    Negative
    ```

<span data-ttu-id="a32c6-220">지금까지</span><span class="sxs-lookup"><span data-stu-id="a32c6-220">Congratulations!</span></span> <span data-ttu-id="a32c6-221">Azure 함수를 사용하여 인터넷을 통해 예측을 수행하도록 모델을 제공했습니다.</span><span class="sxs-lookup"><span data-stu-id="a32c6-221">You have successfully served your model to make predictions over the internet using an Azure Function.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a32c6-222">다음 단계</span><span class="sxs-lookup"><span data-stu-id="a32c6-222">Next Steps</span></span>

- [<span data-ttu-id="a32c6-223">Azure에 배포</span><span class="sxs-lookup"><span data-stu-id="a32c6-223">Deploy to Azure</span></span>](/azure/azure-functions/functions-develop-vs#publish-to-azure)
