---
title: Azure Functions에 모델 배포
description: Azure Functions를 사용하여 인터넷을 통해 예측하기 위한 ML.NET 감정 분석 기계 학습 모델 제공
ms.date: 09/12/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc, how-to
ms.openlocfilehash: 2abd8588aa314b630c995e0c78b5869ec00a89df
ms.sourcegitcommit: dfd612ba454ce775a766bcc6fe93bc1d43dfda47
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/09/2019
ms.locfileid: "72179368"
---
# <a name="deploy-a-model-to-azure-functions"></a><span data-ttu-id="d2d63-103">Azure Functions에 모델 배포</span><span class="sxs-lookup"><span data-stu-id="d2d63-103">Deploy a model to Azure Functions</span></span>

<span data-ttu-id="d2d63-104">Azure Functions 서버리스 환경을 통해 HTTP에서의 예측을 위해 미리 학습된 ML.NET 기계 학습 모델을 배포하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-104">Learn how to deploy a pre-trained ML.NET machine learning model for predictions over HTTP through an Azure Functions serverless environment.</span></span>

> [!NOTE]
> <span data-ttu-id="d2d63-105">`PredictionEnginePool` 서비스 확장은 현재 미리 보기 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-105">`PredictionEnginePool` service extension is currently in preview.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d2d63-106">전제 조건</span><span class="sxs-lookup"><span data-stu-id="d2d63-106">Prerequisites</span></span>

- <span data-ttu-id="d2d63-107">“.NET Core 플랫폼 간 개발” 워크로드 및 “Azure 개발”이 설치된 [Visual Studio 2017 15.6 이상](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017).</span><span class="sxs-lookup"><span data-stu-id="d2d63-107">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload and "Azure development" installed.</span></span>
- <span data-ttu-id="d2d63-108">Microsoft.NET.Sdk.Functions NuGet 패키지 버전 1.0.28 이상</span><span class="sxs-lookup"><span data-stu-id="d2d63-108">Microsoft.NET.Sdk.Functions NuGet Package version 1.0.28+.</span></span>
- [<span data-ttu-id="d2d63-109">Azure Functions 도구</span><span class="sxs-lookup"><span data-stu-id="d2d63-109">Azure Functions Tools</span></span>](/azure/azure-functions/functions-develop-vs#check-your-tools-version)
- <span data-ttu-id="d2d63-110">PowerShell</span><span class="sxs-lookup"><span data-stu-id="d2d63-110">Powershell</span></span>
- <span data-ttu-id="d2d63-111">미리 학습된 모델입니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-111">Pre-trained model.</span></span> <span data-ttu-id="d2d63-112">[ML.NET 감정 분석 자습서](../tutorials/sentiment-analysis.md)를 사용하여 자체 모델을 빌드하거나 이 [미리 학습된 감정 분석 기계 학습 모델](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip) 다운로드</span><span class="sxs-lookup"><span data-stu-id="d2d63-112">Use the [ML.NET Sentiment Analysis tutorial](../tutorials/sentiment-analysis.md) to build your own model or download this [pre-trained sentiment analysis machine learning model](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)</span></span>

## <a name="create-azure-functions-project"></a><span data-ttu-id="d2d63-113">Azure Functions 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="d2d63-113">Create Azure Functions project</span></span>

1. <span data-ttu-id="d2d63-114">Visual Studio 2017을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-114">Open Visual Studio 2017.</span></span> <span data-ttu-id="d2d63-115">메뉴 모음에서 **파일** > **새로 만들기** > **프로젝트**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-115">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="d2d63-116">**새 프로젝트** 대화 상자에서 **Visual C#** 노드와 **Cloud** 노드를 차례로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-116">In the **New Project** dialog, select the **Visual C#** node followed by the **Cloud** node.</span></span> <span data-ttu-id="d2d63-117">그런 다음, **Azure Functions** 프로젝트 템플릿을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-117">Then select the **Azure Functions** project template.</span></span> <span data-ttu-id="d2d63-118">**이름** 텍스트 상자에 “SentimentAnalysisFunctionsApp”을 입력한 다음, **확인** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-118">In the **Name** text box, type "SentimentAnalysisFunctionsApp" and then select the **OK** button.</span></span>
1. <span data-ttu-id="d2d63-119">**새 프로젝트** 대화 상자에서 프로젝트 옵션 위의 드롭다운을 열고 **Azure Functions v2(.NET Core)** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-119">In the **New Project** dialog, open the dropdown above the project options and select **Azure Functions v2 (.NET Core)**.</span></span> <span data-ttu-id="d2d63-120">그런 다음, **HTTP 트리거** 프로젝트를 선택한 후 **확인** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-120">Then, select the **Http trigger** project and then select the **OK** button.</span></span>
1. <span data-ttu-id="d2d63-121">프로젝트에서 *MLModels* 디렉터리를 만들어 모델을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-121">Create a directory named *MLModels* in your project to save your model:</span></span>

    <span data-ttu-id="d2d63-122">**솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가** > **새 폴더**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-122">In **Solution Explorer**, right-click on your project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="d2d63-123">“MLModels”를 입력하고 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-123">Type "MLModels" and hit Enter.</span></span>

1. <span data-ttu-id="d2d63-124">**Microsoft.ML NuGet 패키지**를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-124">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="d2d63-125">솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **NuGet 패키지 관리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-125">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="d2d63-126">“nuget.org”를 패키지 소스로 선택하고, [찾아보기] 탭을 선택하고, **Microsoft.ML**을 검색하고, 목록에서 해당 패키지를 선택하고, **설치** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-126">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="d2d63-127">**변경 내용 미리 보기** 대화 상자에서 **확인** 단추를 선택한 다음, 나열된 패키지의 사용 조건에 동의하는 경우 **라이선스 승인** 대화 상자에서 **동의함** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-127">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

1. <span data-ttu-id="d2d63-128">**Microsoft.Azure.Functions.Extensions NuGet 패키지**를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-128">Install the **Microsoft.Azure.Functions.Extensions NuGet Package**:</span></span>

    <span data-ttu-id="d2d63-129">솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **NuGet 패키지 관리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-129">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="d2d63-130">“nuget.org”를 패키지 소스로 선택하고 찾아보기 탭을 선택합니다. **Microsoft.Azure.Functions.Extensions**를 검색하고 목록에서 해당 패키지를 선택한 다음, **설치** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-130">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.Azure.Functions.Extensions**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="d2d63-131">**변경 내용 미리 보기** 대화 상자에서 **확인** 단추를 선택한 다음, 나열된 패키지의 사용 조건에 동의하는 경우 **라이선스 승인** 대화 상자에서 **동의함** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-131">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

1. <span data-ttu-id="d2d63-132">**Microsoft.Extensions.ML NuGet 패키지**를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-132">Install the **Microsoft.Extensions.ML NuGet Package**:</span></span>

    <span data-ttu-id="d2d63-133">솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **NuGet 패키지 관리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-133">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="d2d63-134">“nuget.org”를 패키지 원본으로 선택하고, 찾아보기 탭을 선택하고, **Microsoft.Extensions.ML**을 검색하고, 목록에서 해당 패키지를 선택하고, **설치** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-134">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.Extensions.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="d2d63-135">**변경 내용 미리 보기** 대화 상자에서 **확인** 단추를 선택한 다음, 나열된 패키지의 사용 조건에 동의하는 경우 **라이선스 승인** 대화 상자에서 **동의함** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-135">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

1. <span data-ttu-id="d2d63-136">**Microsoft.NET.Sdk.Functions NuGet 패키지**를 버전 1.0.28 이상으로 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-136">Update the **Microsoft.NET.Sdk.Functions NuGet Package** to version 1.0.28+:</span></span>

    <span data-ttu-id="d2d63-137">솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **NuGet 패키지 관리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-137">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="d2d63-138">“nuget.org”를 패키지 소스로 선택하고 설치 탭을 선택합니다. **Microsoft.NET.Sdk.Functions**를 검색하고 목록에서 해당 패키지를 선택한 다음, 버전 드롭다운에서 1.0.28 이상을 선택하고 **업데이트** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-138">Choose "nuget.org" as the Package source, select the Installed tab, search for **Microsoft.NET.Sdk.Functions**, select that package in the list, select 1.0.28 or later from the Version dropdown, and select the **Update** button.</span></span> <span data-ttu-id="d2d63-139">**변경 내용 미리 보기** 대화 상자에서 **확인** 단추를 선택한 다음, 나열된 패키지의 사용 조건에 동의하는 경우 **라이선스 승인** 대화 상자에서 **동의함** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-139">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

## <a name="add-pre-trained-model-to-project"></a><span data-ttu-id="d2d63-140">프로젝트에 미리 학습된 모델 추가</span><span class="sxs-lookup"><span data-stu-id="d2d63-140">Add pre-trained model to project</span></span>

1. <span data-ttu-id="d2d63-141">미리 빌드된 모델을 *MLModels* 폴더에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-141">Copy your pre-built model to the *MLModels* folder.</span></span>
1. <span data-ttu-id="d2d63-142">솔루션 탐색기에서 미리 빌드된 모델 파일을 마우스 오른쪽 단추로 클릭하고 **속성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-142">In Solution Explorer, right-click your pre-built model file and select **Properties**.</span></span> <span data-ttu-id="d2d63-143">**고급** 아래에서 **출력 디렉터리에 복사** 값을 **변경된 내용만 복사**로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-143">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

## <a name="create-azure-function-to-analyze-sentiment"></a><span data-ttu-id="d2d63-144">감정을 분석하는 Azure Function 만들기</span><span class="sxs-lookup"><span data-stu-id="d2d63-144">Create Azure Function to analyze sentiment</span></span>

<span data-ttu-id="d2d63-145">감정을 예측하는 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-145">Create a class to predict sentiment.</span></span> <span data-ttu-id="d2d63-146">새 클래스를 프로젝트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-146">Add a new class to your project:</span></span>

1. <span data-ttu-id="d2d63-147">**솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가** > **새 항목**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-147">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="d2d63-148">**새 항목 추가** 대화 상자에서 **Azure 함수**를 선택하고 **이름** 필드를 *AnalyzeSentiment.cs*로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-148">In the **Add New Item** dialog box, select **Azure Function** and change the **Name** field to *AnalyzeSentiment.cs*.</span></span> <span data-ttu-id="d2d63-149">그런 다음, **추가** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-149">Then, select the **Add** button.</span></span>

1. <span data-ttu-id="d2d63-150">**새 Azure 함수** 대화 상자에서 **HTTP 트리거**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-150">In the **New Azure Function** dialog box, select **Http Trigger**.</span></span> <span data-ttu-id="d2d63-151">그런 다음, **확인** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-151">Then, select the **OK** button.</span></span>

    <span data-ttu-id="d2d63-152">*AnalyzeSentiment.cs* 파일이 코드 편집기에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-152">The *AnalyzeSentiment.cs* file opens in the code editor.</span></span> <span data-ttu-id="d2d63-153">다음 `using` 문을 *AnalyzeSentiment.cs*의 맨 위에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-153">Add the following `using` statement to the top of *AnalyzeSentiment.cs*:</span></span>

    [!code-csharp [AnalyzeUsings](~/machinelearning-samples/samples/csharp/end-to-end-apps/ScalableMLModelOnAzureFunction/SentimentAnalysisFunctionsApp/AnalyzeSentiment.cs#L1-L11)]

    <span data-ttu-id="d2d63-154">기본적으로 `AnalyzeSentiment` 클래스는 `static`입니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-154">By default, the `AnalyzeSentiment` class is `static`.</span></span> <span data-ttu-id="d2d63-155">클래스 정의에서 `static` 키워드를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-155">Make sure to remove the `static` keyword from the class definition.</span></span>

    ```csharp
    public class AnalyzeSentiment
    {
    
    }
    ```

## <a name="create-data-models"></a><span data-ttu-id="d2d63-156">데이터 모델 만들기</span><span class="sxs-lookup"><span data-stu-id="d2d63-156">Create data models</span></span>

<span data-ttu-id="d2d63-157">입력 데이터 및 예측에 대한 일부 클래스를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-157">You need to create some classes for your input data and predictions.</span></span> <span data-ttu-id="d2d63-158">새 클래스를 프로젝트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-158">Add a new class to your project:</span></span>

1. <span data-ttu-id="d2d63-159">프로젝트에서 *DataModels* 디렉터리를 만들어 데이터 모델을 저장합니다. 솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가 > 새 폴더**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-159">Create a directory named *DataModels* in your project to save your data models: In Solution Explorer, right-click on your project and select **Add > New Folder**.</span></span> <span data-ttu-id="d2d63-160">“DataModels”를 입력하고 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-160">Type "DataModels" and hit Enter.</span></span>
2. <span data-ttu-id="d2d63-161">솔루션 탐색기에서 *DataModels* 디렉터리를 마우스 오른쪽 단추로 클릭하고 **추가 > 새 항목**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-161">In Solution Explorer, right-click the *DataModels* directory, and then select **Add > New Item**.</span></span>
3. <span data-ttu-id="d2d63-162">**새 항목 추가** 대화 상자에서 **클래스**를 선택하고 **이름** 필드를 *SentimentData.cs*로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-162">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentData.cs*.</span></span> <span data-ttu-id="d2d63-163">그런 다음, **추가** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-163">Then, select the **Add** button.</span></span> 

    <span data-ttu-id="d2d63-164">*SentimentData.cs* 파일이 코드 편집기에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-164">The *SentimentData.cs* file opens in the code editor.</span></span> <span data-ttu-id="d2d63-165">다음 using 문을 *SentimentData.cs*의 맨 위에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-165">Add the following using statement to the top of *SentimentData.cs*:</span></span>

    [!code-csharp [SentimentDataUsings](~/machinelearning-samples/samples/csharp/end-to-end-apps/ScalableMLModelOnAzureFunction/SentimentAnalysisFunctionsApp/DataModels/SentimentData.cs#L1)]

    <span data-ttu-id="d2d63-166">기존 클래스 정의를 제거하고 다음 코드를 *SentimentData.cs* 파일에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-166">Remove the existing class definition and add the following code to the *SentimentData.cs* file:</span></span>

    [!code-csharp [SentimentData](~/machinelearning-samples/samples/csharp/end-to-end-apps/ScalableMLModelOnAzureFunction/SentimentAnalysisFunctionsApp/DataModels/SentimentData.cs#L5-L13)]

4. <span data-ttu-id="d2d63-167">솔루션 탐색기에서 *DataModels* 디렉터리를 마우스 오른쪽 단추로 클릭하고 **추가 > 새 항목**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-167">In Solution Explorer, right-click the *DataModels* directory, and then select **Add > New Item**.</span></span>
5. <span data-ttu-id="d2d63-168">**새 항목 추가** 대화 상자에서 **클래스**를 선택하고 **이름** 필드를 *SentimentPrediction.cs*로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-168">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentPrediction.cs*.</span></span> <span data-ttu-id="d2d63-169">그런 다음, **추가** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-169">Then, select the **Add** button.</span></span> <span data-ttu-id="d2d63-170">*SentimentPrediction.cs* 파일이 코드 편집기에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-170">The *SentimentPrediction.cs* file opens in the code editor.</span></span> <span data-ttu-id="d2d63-171">다음 using 문을 *SentimentPrediction.cs*의 맨 위에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-171">Add the following using statement to the top of *SentimentPrediction.cs*:</span></span>

    [!code-csharp [SentimentPredictionUsings](~/machinelearning-samples/samples/csharp/end-to-end-apps/ScalableMLModelOnAzureFunction/SentimentAnalysisFunctionsApp/DataModels/SentimentPrediction.cs#L1)]

    <span data-ttu-id="d2d63-172">기존 클래스 정의를 제거하고 다음 코드를 *SentimentPrediction.cs* 파일에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-172">Remove the existing class definition and add the following code to the *SentimentPrediction.cs* file:</span></span>

    [!code-csharp [SentimentPrediction](~/machinelearning-samples/samples/csharp/end-to-end-apps/ScalableMLModelOnAzureFunction/SentimentAnalysisFunctionsApp/DataModels/SentimentPrediction.cs#L5-L14)]

    <span data-ttu-id="d2d63-173">`SentimentPrediction`은 `SentimentText` 속성의 원래 데이터와 모델에서 생성된 출력에 대한 액세스를 제공하는 `SentimentData`에서 상속됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-173">`SentimentPrediction` inherits from `SentimentData` which provides access to the original data in the `SentimentText` property as well as the output generated by the model.</span></span>

## <a name="register-predictionenginepool-service"></a><span data-ttu-id="d2d63-174">PredictionEnginePool 서비스 등록</span><span class="sxs-lookup"><span data-stu-id="d2d63-174">Register PredictionEnginePool service</span></span>

<span data-ttu-id="d2d63-175">단일 예측을 수행하려면 [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602)을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-175">To make a single prediction, you have to create a [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602).</span></span> <span data-ttu-id="d2d63-176">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602)은 스레드로부터 안전하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-176">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) is not thread-safe.</span></span> <span data-ttu-id="d2d63-177">또한 애플리케이션 내에서 필요한 모든 위치에서 인스턴스를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-177">Additionally, you have to create an instance of it everywhere it is needed within your application.</span></span> <span data-ttu-id="d2d63-178">애플리케이션이 커지면 이 프로세스를 관리할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-178">As your application grows, this process can become unmanageable.</span></span> <span data-ttu-id="d2d63-179">성능 및 스레드 보안을 개선하려면 종속성 주입과 `PredictionEnginePool` 서비스를 함께 사용합니다. 이 서비스는 애플리케이션 전체에서 사용할 [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) 개체의 [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601)을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-179">For improved performance and thread safety, use a combination of dependency injection and the `PredictionEnginePool` service, which creates an [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) of [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) objects for use throughout your application.</span></span>

<span data-ttu-id="d2d63-180">[종속성 주입](https://en.wikipedia.org/wiki/Dependency_injection)에 대한 자세한 내용은 다음 링크를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d2d63-180">The following link provides more information if you want to learn more about [dependency injection](https://en.wikipedia.org/wiki/Dependency_injection).</span></span>

1. <span data-ttu-id="d2d63-181">**솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가** > **새 항목**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-181">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="d2d63-182">**새 항목 추가** 대화 상자에서 **클래스**를 선택하고 **이름** 필드를 *Startup.cs*로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-182">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *Startup.cs*.</span></span> <span data-ttu-id="d2d63-183">그런 다음, **추가** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-183">Then, select the **Add** button.</span></span> 

    <span data-ttu-id="d2d63-184">*Startup.cs* 파일이 코드 편집기에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-184">The *Startup.cs* file opens in the code editor.</span></span> <span data-ttu-id="d2d63-185">다음 using 문을 *Startup.cs*의 맨 위에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-185">Add the following using statement to the top of *Startup.cs*:</span></span>

    ```csharp
    using Microsoft.Azure.Functions.Extensions.DependencyInjection;
    using Microsoft.Extensions.ML;
    using SentimentAnalysisFunctionsApp;
    using SentimentAnalysisFunctionsApp.DataModels;
    ```

    <span data-ttu-id="d2d63-186">using 문 아래의 기존 코드를 제거하고 다음 코드를 *Startup.cs* 파일에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-186">Remove the existing code below the using statements and add the following code to the *Startup.cs* file:</span></span>

    ```csharp
    [assembly: FunctionsStartup(typeof(Startup))]
    namespace SentimentAnalysisFunctionsApp
    {
        public class Startup : FunctionsStartup
        {
            public override void Configure(IFunctionsHostBuilder builder)
            {
                builder.Services.AddPredictionEnginePool<SentimentData, SentimentPrediction>()
                    .FromFile(modelName: "SentimentAnalysisModel", filePath:"MLModels/sentiment_model.zip", watchForChanges: true);
            }
        }
    }
    ```

<span data-ttu-id="d2d63-187">개략적으로 이 코드는 애플리케이션을 수동으로 초기화하지 않고도 애플리케이션에서 요청할 때 나중에 사용할 수 있도록 자동으로 개체 및 서비스를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-187">At a high level, this code initializes the objects and services automatically for later use when requested by the application instead of having to manually do it.</span></span> 

<span data-ttu-id="d2d63-188">기계 학습 모델은 정적이지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-188">Machine learning models are not static.</span></span> <span data-ttu-id="d2d63-189">새 학습 데이터를 사용할 수 있게 되면 모델을 다시 학습하고 다시 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-189">As new training data becomes available, the model is retrained and redeployed.</span></span> <span data-ttu-id="d2d63-190">최신 버전의 모델을 애플리케이션으로 가져오는 한 가지 방법은 전체 애플리케이션을 다시 배포하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-190">One way to get the latest version of the model into your application is to redeploy the entire application.</span></span> <span data-ttu-id="d2d63-191">그러나 이 경우 애플리케이션 가동 중지 시간이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-191">However, this introduces application downtime.</span></span> <span data-ttu-id="d2d63-192">`PredictionEnginePool` 서비스는 애플리케이션을 가동 중지하지 않으면서 업데이트된 모델을 다시 로드하는 메커니즘을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-192">The `PredictionEnginePool` service provides a mechanism to reload an updated model without taking your application down.</span></span> 

<span data-ttu-id="d2d63-193">`watchForChanges` 매개 변수를 `true`로 설정하면 `PredictionEnginePool`은 파일 시스템 변경 알림을 수신 대기하고 파일이 변경될 때 이벤트를 발생시키는 [`FileSystemWatcher`](xref:System.IO.FileSystemWatcher)를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-193">Set the `watchForChanges` parameter to `true`, and the `PredictionEnginePool` starts a [`FileSystemWatcher`](xref:System.IO.FileSystemWatcher) that listens to the file system change notifications and raises events when there is a change to the file.</span></span> <span data-ttu-id="d2d63-194">그러면 `PredictionEnginePool`에서 모델을 자동으로 다시 로드하도록 지정할 수 있는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-194">This prompts the `PredictionEnginePool` to automatically reload the model.</span></span>

<span data-ttu-id="d2d63-195">모델은 `modelName` 매개 변수로 식별되므로 변경 시, 애플리케이션당 두 개 이상의 모델이 다시 로드될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-195">The model is identified by the `modelName` parameter so that more than one model per application can be reloaded upon change.</span></span> 

> [!TIP]
> <span data-ttu-id="d2d63-196">또는 원격으로 저장된 모델을 사용하는 경우 `FromUri` 메서드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-196">Alternatively, you can use the `FromUri` method when working with models stored remotely.</span></span> <span data-ttu-id="d2d63-197">`FromUri`는 파일 변경 이벤트를 감시하지 않고, 원격 위치에서 변경 내용을 폴링합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-197">Rather than watching for file changed events, `FromUri` polls the remote location for changes.</span></span> <span data-ttu-id="d2d63-198">폴링 간격의 기본값은 5분입니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-198">The polling interval defaults to 5 minutes.</span></span> <span data-ttu-id="d2d63-199">애플리케이션의 요구 사항에 따라 폴링 간격을 늘리거나 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-199">You can increase or decrease the polling interval based on your application's requirements.</span></span> <span data-ttu-id="d2d63-200">아래 코드 샘플에서 `PredictionEnginePool`은 1분마다 지정된 URI에 저장된 모델을 폴링합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-200">In the code sample below, the `PredictionEnginePool` polls the model stored at the specified URI every minute.</span></span>
>    
>```csharp
>builder.Services.AddPredictionEnginePool<SentimentData, SentimentPrediction>()
>   .FromUri(
>       modelName: "SentimentAnalysisModel", 
>       uri:"https://github.com/dotnet/samples/raw/master/machine-learning/models/sentimentanalysis/sentiment_model.zip", 
>       period: TimeSpan.FromMinutes(1));
>```

## <a name="load-the-model-into-the-function"></a><span data-ttu-id="d2d63-201">함수에 모델 로드</span><span class="sxs-lookup"><span data-stu-id="d2d63-201">Load the model into the function</span></span>

<span data-ttu-id="d2d63-202">*AnalyzeSentiment* 클래스 안에 다음 코드를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-202">Insert the following code inside the *AnalyzeSentiment* class:</span></span>

[!code-csharp [AnalyzeCtor](~/machinelearning-samples/samples/csharp/end-to-end-apps/ScalableMLModelOnAzureFunction/SentimentAnalysisFunctionsApp/AnalyzeSentiment.cs#L18-L24)]

<span data-ttu-id="d2d63-203">이 코드는 종속성 주입을 통해 가져오는 함수의 생성자에 `PredictionEnginePool`을 전달하여 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-203">This code assigns the `PredictionEnginePool` by passing it to the function's constructor which you get via dependency injection.</span></span>

## <a name="use-the-model-to-make-predictions"></a><span data-ttu-id="d2d63-204">모델을 사용하여 예측하기</span><span class="sxs-lookup"><span data-stu-id="d2d63-204">Use the model to make predictions</span></span>

<span data-ttu-id="d2d63-205">*AnalyzeSentiment* 클래스에서 *Run* 메서드의 기존 구현을 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-205">Replace the existing implementation of *Run* method in *AnalyzeSentiment* class with the following code:</span></span>

```csharp
[FunctionName("AnalyzeSentiment")]
public async Task<IActionResult> Run(
[HttpTrigger(AuthorizationLevel.Function, "post", Route = null)] HttpRequest req,
ILogger log)
{
    log.LogInformation("C# HTTP trigger function processed a request.");

    //Parse HTTP Request Body
    string requestBody = await new StreamReader(req.Body).ReadToEndAsync();
    SentimentData data = JsonConvert.DeserializeObject<SentimentData>(requestBody);

    //Make Prediction
    SentimentPrediction prediction = _predictionEnginePool.Predict(modelName: "SentimentAnalysisModel", example: data);

    //Convert prediction to string
    string sentiment = Convert.ToBoolean(prediction.Prediction) ? "Positive" : "Negative";

    //Return Prediction
    return (ActionResult)new OkObjectResult(sentiment);
}
```

<span data-ttu-id="d2d63-206">`Run` 메서드가 실행되면 HTTP 요청에서 수신되는 데이터가 직렬 해제되어 `PredictionEnginePool`에 대한 입력으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-206">When the `Run` method executes, the incoming data from the HTTP request is deserialized and used as input for the `PredictionEnginePool`.</span></span> <span data-ttu-id="d2d63-207">그런 다음, `Predict` 메서드가 `Startup` 클래스에 등록된 `SentimentAnalysisModel`을 사용하여 예측을 수행하고 성공하면 결과를 사용자에게 다시 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-207">The `Predict` method is then called to to make predictions using the `SentimentAnalysisModel` registered in the `Startup` class and returns the results back to the user if successful.</span></span>

## <a name="test-locally"></a><span data-ttu-id="d2d63-208">로컬로 테스트</span><span class="sxs-lookup"><span data-stu-id="d2d63-208">Test locally</span></span>

<span data-ttu-id="d2d63-209">이제 모든 것이 설정되었으므로 애플리케이션을 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-209">Now that everything is set up, it's time to test the application:</span></span>

1. <span data-ttu-id="d2d63-210">애플리케이션 실행</span><span class="sxs-lookup"><span data-stu-id="d2d63-210">Run the application</span></span>
1. <span data-ttu-id="d2d63-211">PowerShell을 열고 PORT가 애플리케이션을 실행 중인 포트인 경우 프롬프트에 코드를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-211">Open PowerShell and enter the code into the prompt where PORT is the port your application is running on.</span></span> <span data-ttu-id="d2d63-212">일반적으로 포트는 7071입니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-212">Typically the port is 7071.</span></span>

    ```powershell
    Invoke-RestMethod "http://localhost:<PORT>/api/AnalyzeSentiment" -Method Post -Body (@{SentimentText="This is a very bad steak"} | ConvertTo-Json) -ContentType "application/json"
    ```

    <span data-ttu-id="d2d63-213">성공하면 출력이 아래 텍스트와 같이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-213">If successful, the output should look similar to the text below:</span></span>
    
    ```powershell
    Negative
    ```

<span data-ttu-id="d2d63-214">지금까지</span><span class="sxs-lookup"><span data-stu-id="d2d63-214">Congratulations!</span></span> <span data-ttu-id="d2d63-215">Azure 함수를 사용하여 인터넷을 통해 예측을 수행하도록 모델을 제공했습니다.</span><span class="sxs-lookup"><span data-stu-id="d2d63-215">You have successfully served your model to make predictions over the internet using an Azure Function.</span></span>

## <a name="next-steps"></a><span data-ttu-id="d2d63-216">다음 단계</span><span class="sxs-lookup"><span data-stu-id="d2d63-216">Next Steps</span></span>

- [<span data-ttu-id="d2d63-217">Azure에 배포</span><span class="sxs-lookup"><span data-stu-id="d2d63-217">Deploy to Azure</span></span>](/azure/azure-functions/functions-develop-vs#publish-to-azure)
