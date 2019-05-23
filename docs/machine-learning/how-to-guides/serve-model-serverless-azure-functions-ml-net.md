---
title: Azure Functions에 모델 배포
description: Azure Functions를 사용하여 인터넷을 통해 예측하기 위한 ML.NET 감정 분석 기계 학습 모델 제공
ms.date: 05/03/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc, how-to
ms.openlocfilehash: 9e62d8826227aed07451387cc733d27094327f99
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65645101"
---
# <a name="deploy-a-model-to-azure-functions"></a><span data-ttu-id="a2926-103">Azure Functions에 모델 배포</span><span class="sxs-lookup"><span data-stu-id="a2926-103">Deploy a model to Azure Functions</span></span>

<span data-ttu-id="a2926-104">Azure Functions 서버리스 환경을 통해 HTTP에서의 예측을 위해 미리 학습된 ML.NET 기계 학습 모델을 배포하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-104">Learn how to deploy a pre-trained ML.NET machine learning model for predictions over HTTP through an Azure Functions serverless environment.</span></span>

> [!NOTE]
> <span data-ttu-id="a2926-105">`PredictionEnginePool` 서비스 확장은 현재 미리 보기 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-105">`PredictionEnginePool` service extension is currently in preview.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a2926-106">전제 조건</span><span class="sxs-lookup"><span data-stu-id="a2926-106">Prerequisites</span></span>

- <span data-ttu-id="a2926-107">“.NET Core 플랫폼 간 개발” 워크로드 및 “Azure 개발”이 설치된 [Visual Studio 2017 15.6 이상](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017).</span><span class="sxs-lookup"><span data-stu-id="a2926-107">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload and "Azure development" installed.</span></span>
- [<span data-ttu-id="a2926-108">Azure Functions 도구</span><span class="sxs-lookup"><span data-stu-id="a2926-108">Azure Functions Tools</span></span>](/azure/azure-functions/functions-develop-vs#check-your-tools-version)
- <span data-ttu-id="a2926-109">PowerShell</span><span class="sxs-lookup"><span data-stu-id="a2926-109">Powershell</span></span>
- <span data-ttu-id="a2926-110">미리 학습된 모델입니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-110">Pre-trained model.</span></span> <span data-ttu-id="a2926-111">[ML.NET 감정 분석 자습서](../tutorials/sentiment-analysis.md)를 사용하여 자체 모델을 빌드하거나 이 [미리 학습된 감정 분석 기계 학습 모델](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip) 다운로드</span><span class="sxs-lookup"><span data-stu-id="a2926-111">Use the [ML.NET Sentiment Analysis tutorial](../tutorials/sentiment-analysis.md) to build your own model or download this [pre-trained sentiment analysis machine learning model](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)</span></span>

## <a name="create-azure-functions-project"></a><span data-ttu-id="a2926-112">Azure Functions 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="a2926-112">Create Azure Functions project</span></span>

1. <span data-ttu-id="a2926-113">Visual Studio 2017을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-113">Open Visual Studio 2017.</span></span> <span data-ttu-id="a2926-114">메뉴 모음에서 **파일** > **새로 만들기** > **프로젝트**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-114">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="a2926-115">**새 프로젝트** 대화 상자에서 **Visual C#** 노드와 **Cloud** 노드를 차례로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-115">In the **New Project** dialog, select the **Visual C#** node followed by the **Cloud** node.</span></span> <span data-ttu-id="a2926-116">그런 다음, **Azure Functions** 프로젝트 템플릿을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-116">Then select the **Azure Functions** project template.</span></span> <span data-ttu-id="a2926-117">**이름** 텍스트 상자에 “SentimentAnalysisFunctionsApp”을 입력한 다음, **확인** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-117">In the **Name** text box, type "SentimentAnalysisFunctionsApp" and then select the **OK** button.</span></span>
1. <span data-ttu-id="a2926-118">**새 프로젝트** 대화 상자에서 프로젝트 옵션 위의 드롭다운을 열고 **Azure Functions v2(.NET Core)** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-118">In the **New Project** dialog, open the dropdown above the project options and select **Azure Functions v2 (.NET Core)**.</span></span> <span data-ttu-id="a2926-119">그런 다음, **HTTP 트리거** 프로젝트를 선택한 후 **확인** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-119">Then, select the **Http trigger** project and then select the **OK** button.</span></span>
1. <span data-ttu-id="a2926-120">프로젝트에서 *MLModels* 디렉터리를 만들어 모델을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-120">Create a directory named *MLModels* in your project to save your model:</span></span>

    <span data-ttu-id="a2926-121">**솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가** > **새 폴더**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-121">In **Solution Explorer**, right-click on your project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="a2926-122">“MLModels”를 입력하고 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-122">Type "MLModels" and hit Enter.</span></span>

1. <span data-ttu-id="a2926-123">**Microsoft.ML NuGet 패키지**를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-123">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="a2926-124">솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **NuGet 패키지 관리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-124">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="a2926-125">“nuget.org”를 패키지 소스로 선택하고, [찾아보기] 탭을 선택하고, **Microsoft.ML**을 검색하고, 목록에서 해당 패키지를 선택하고, **설치** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-125">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="a2926-126">**변경 내용 미리 보기** 대화 상자에서 **확인** 단추를 선택한 다음, 나열된 패키지의 사용 조건에 동의하는 경우 **라이선스 승인** 대화 상자에서 **동의함** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-126">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

1. <span data-ttu-id="a2926-127">**Microsoft.Extensions.ML NuGet 패키지**를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-127">Install the **Microsoft.Extensions.ML NuGet Package**:</span></span>

    <span data-ttu-id="a2926-128">솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **NuGet 패키지 관리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-128">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="a2926-129">“nuget.org”를 패키지 원본으로 선택하고, 찾아보기 탭을 선택하고, **Microsoft.Extensions.ML**을 검색하고, 목록에서 해당 패키지를 선택하고, **설치** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-129">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.Extensions.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="a2926-130">**변경 내용 미리 보기** 대화 상자에서 **확인** 단추를 선택한 다음, 나열된 패키지의 사용 조건에 동의하는 경우 **라이선스 승인** 대화 상자에서 **동의함** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-130">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

## <a name="add-pre-trained-model-to-project"></a><span data-ttu-id="a2926-131">프로젝트에 미리 학습된 모델 추가</span><span class="sxs-lookup"><span data-stu-id="a2926-131">Add pre-trained model to project</span></span>

1. <span data-ttu-id="a2926-132">미리 빌드된 모델을 *MLModels* 폴더에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-132">Copy your pre-built model to the *MLModels* folder.</span></span>
1. <span data-ttu-id="a2926-133">솔루션 탐색기에서 미리 빌드된 모델 파일을 마우스 오른쪽 단추로 클릭하고 **속성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-133">In Solution Explorer, right-click your pre-built model file and select **Properties**.</span></span> <span data-ttu-id="a2926-134">**고급** 아래에서 **출력 디렉터리에 복사** 값을 **변경된 내용만 복사**로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-134">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

## <a name="create-azure-function-to-analyze-sentiment"></a><span data-ttu-id="a2926-135">감정을 분석하는 Azure Function 만들기</span><span class="sxs-lookup"><span data-stu-id="a2926-135">Create Azure Function to analyze sentiment</span></span>

<span data-ttu-id="a2926-136">감정을 예측하는 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-136">Create a class to predict sentiment.</span></span> <span data-ttu-id="a2926-137">새 클래스를 프로젝트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-137">Add a new class to your project:</span></span>

1. <span data-ttu-id="a2926-138">**솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가** > **새 항목**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-138">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="a2926-139">**새 항목 추가** 대화 상자에서 **Azure 함수**를 선택하고 **이름** 필드를 *AnalyzeSentiment.cs*로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-139">In the **Add New Item** dialog box, select **Azure Function** and change the **Name** field to *AnalyzeSentiment.cs*.</span></span> <span data-ttu-id="a2926-140">그런 다음, **추가** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-140">Then, select the **Add** button.</span></span>

1. <span data-ttu-id="a2926-141">**새 Azure 함수** 대화 상자에서 **HTTP 트리거**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-141">In the **New Azure Function** dialog box, select **Http Trigger**.</span></span> <span data-ttu-id="a2926-142">그런 다음, **확인** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-142">Then, select the **OK** button.</span></span>

    <span data-ttu-id="a2926-143">*AnalyzeSentiment.cs* 파일이 코드 편집기에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-143">The *AnalyzeSentiment.cs* file opens in the code editor.</span></span> <span data-ttu-id="a2926-144">다음 `using` 문을 *AnalyzeSentiment.cs*의 맨 위에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-144">Add the following `using` statement to the top of *AnalyzeSentiment.cs*:</span></span>

    ```csharp
    using System;
    using System.IO;
    using System.Threading.Tasks;
    using Microsoft.AspNetCore.Mvc;
    using Microsoft.Azure.WebJobs;
    using Microsoft.Azure.WebJobs.Extensions.Http;
    using Microsoft.AspNetCore.Http;
    using Microsoft.Extensions.Logging;
    using Newtonsoft.Json;
    using Microsoft.Extensions.ML;
    using SentimentAnalysisFunctionsApp.DataModels;
    ```

    <span data-ttu-id="a2926-145">기본적으로 `AnalyzeSentiment` 클래스는 `static`입니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-145">By default, the `AnalyzeSentiment` class is `static`.</span></span> <span data-ttu-id="a2926-146">클래스 정의에서 `static` 키워드를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-146">Make sure to remove the `static` keyword from the class definition.</span></span>

    ```csharp
    public class AnalyzeSentiment
    {
    
    }
    ```

## <a name="create-data-models"></a><span data-ttu-id="a2926-147">데이터 모델 만들기</span><span class="sxs-lookup"><span data-stu-id="a2926-147">Create data models</span></span>

<span data-ttu-id="a2926-148">입력 데이터 및 예측에 대한 일부 클래스를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-148">You need to create some classes for your input data and predictions.</span></span> <span data-ttu-id="a2926-149">새 클래스를 프로젝트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-149">Add a new class to your project:</span></span>

1. <span data-ttu-id="a2926-150">프로젝트에서 *DataModels* 디렉터리를 만들어 데이터 모델을 저장합니다. 솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가 > 새 폴더**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-150">Create a directory named *DataModels* in your project to save your data models: In Solution Explorer, right-click on your project and select **Add > New Folder**.</span></span> <span data-ttu-id="a2926-151">“DataModels”를 입력하고 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-151">Type "DataModels" and hit Enter.</span></span>
2. <span data-ttu-id="a2926-152">솔루션 탐색기에서 *DataModels* 디렉터리를 마우스 오른쪽 단추로 클릭하고 **추가 > 새 항목**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-152">In Solution Explorer, right-click the *DataModels* directory, and then select **Add > New Item**.</span></span>
3. <span data-ttu-id="a2926-153">**새 항목 추가** 대화 상자에서 **클래스**를 선택하고 **이름** 필드를 *SentimentData.cs*로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-153">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentData.cs*.</span></span> <span data-ttu-id="a2926-154">그런 다음, **추가** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-154">Then, select the **Add** button.</span></span> 

    <span data-ttu-id="a2926-155">*SentimentData.cs* 파일이 코드 편집기에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-155">The *SentimentData.cs* file opens in the code editor.</span></span> <span data-ttu-id="a2926-156">다음 using 문을 *SentimentData.cs*의 맨 위에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-156">Add the following using statement to the top of *SentimentData.cs*:</span></span>

    ```csharp
    using Microsoft.ML.Data;
    ```

    <span data-ttu-id="a2926-157">기존 클래스 정의를 제거하고 다음 코드를 *SentimentData.cs* 파일에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-157">Remove the existing class definition and add the following code to the *SentimentData.cs* file:</span></span>
    
    ```csharp
    public class SentimentData
    {
        [LoadColumn(0)]
        public string SentimentText;

        [LoadColumn(1)]
        [ColumnName("Label")]
        public bool Sentiment;
    }
    ```

4. <span data-ttu-id="a2926-158">솔루션 탐색기에서 *DataModels* 디렉터리를 마우스 오른쪽 단추로 클릭하고 **추가 > 새 항목**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-158">In Solution Explorer, right-click the *DataModels* directory, and then select **Add > New Item**.</span></span>
5. <span data-ttu-id="a2926-159">**새 항목 추가** 대화 상자에서 **클래스**를 선택하고 **이름** 필드를 *SentimentPrediction.cs*로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-159">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentPrediction.cs*.</span></span> <span data-ttu-id="a2926-160">그런 다음, **추가** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-160">Then, select the **Add** button.</span></span> <span data-ttu-id="a2926-161">*SentimentPrediction.cs* 파일이 코드 편집기에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-161">The *SentimentPrediction.cs* file opens in the code editor.</span></span> <span data-ttu-id="a2926-162">다음 using 문을 *SentimentPrediction.cs*의 맨 위에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-162">Add the following using statement to the top of *SentimentPrediction.cs*:</span></span>

    ```csharp
    using Microsoft.ML.Data;
    ```

    <span data-ttu-id="a2926-163">기존 클래스 정의를 제거하고 다음 코드를 *SentimentPrediction.cs* 파일에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-163">Remove the existing class definition and add the following code to the *SentimentPrediction.cs* file:</span></span>

    ```csharp
    public class SentimentPrediction : SentimentData
    {

        [ColumnName("PredictedLabel")]
        public bool Prediction { get; set; }

        public float Probability { get; set; }

        public float Score { get; set; }
    }
    ```

    <span data-ttu-id="a2926-164">`SentimentPrediction`은 `SentimentText` 속성의 원래 데이터와 모델에서 생성된 출력에 대한 액세스를 제공하는 `SentimentData`에서 상속됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-164">`SentimentPrediction` inherits from `SentimentData` which provides access to the original data in the `SentimentText` property as well as the output generated by the model.</span></span>

## <a name="register-predictionenginepool-service"></a><span data-ttu-id="a2926-165">PredictionEnginePool 서비스 등록</span><span class="sxs-lookup"><span data-stu-id="a2926-165">Register PredictionEnginePool service</span></span>

<span data-ttu-id="a2926-166">단일 예측에 [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-166">To make a single prediction, use [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602).</span></span> <span data-ttu-id="a2926-167">애플리케이션에 [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602)을 사용하려면 필요할 때 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-167">In order to use [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) in your application you must create it when it's needed.</span></span> <span data-ttu-id="a2926-168">이 경우 가장 좋은 방법은 종속성 주입을 고려하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-168">In that case, a best practice to consider is dependency injection.</span></span>

<span data-ttu-id="a2926-169">[종속성 주입](https://en.wikipedia.org/wiki/Dependency_injection)에 대한 자세한 내용은 다음 링크를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a2926-169">The following link provides more information if you want to learn about [dependency injection](https://en.wikipedia.org/wiki/Dependency_injection).</span></span>

1. <span data-ttu-id="a2926-170">**솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가** > **새 항목**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-170">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="a2926-171">**새 항목 추가** 대화 상자에서 **클래스**를 선택하고 **이름** 필드를 *Startup.cs*로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-171">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *Startup.cs*.</span></span> <span data-ttu-id="a2926-172">그런 다음, **추가** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-172">Then, select the **Add** button.</span></span> 

    <span data-ttu-id="a2926-173">*Startup.cs* 파일이 코드 편집기에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-173">The *Startup.cs* file opens in the code editor.</span></span> <span data-ttu-id="a2926-174">다음 using 문을 *Startup.cs*의 맨 위에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-174">Add the following using statement to the top of *Startup.cs*:</span></span>

    ```csharp
    using Microsoft.Azure.WebJobs;
    using Microsoft.Azure.WebJobs.Hosting;
    using Microsoft.Extensions.ML;
    using SentimentAnalysisFunctionsApp;
    using SentimentAnalysisFunctionsApp.DataModels;
    ```

    <span data-ttu-id="a2926-175">using 문 아래의 기존 코드를 제거하고 다음 코드를 *Startup.cs* 파일에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-175">Remove the existing code below the using statements and add the following code to the *Startup.cs* file:</span></span>

    ```csharp
    [assembly: WebJobsStartup(typeof(Startup))]
    namespace SentimentAnalysisFunctionsApp
    {
        class Startup : IWebJobsStartup
        {
            public void Configure(IWebJobsBuilder builder)
            {
                builder.Services.AddPredictionEnginePool<SentimentData, SentimentPrediction>()
                    .FromFile("MLModels/sentiment_model.zip");
            }
        }
    }
    ```

<span data-ttu-id="a2926-176">개략적으로 이 코드는 애플리케이션을 수동으로 초기화하지 않고도 애플리케이션에서 요청할 때 자동으로 개체 및 서비스를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-176">At a high level, this code initializes the objects and services automatically when requested by the application instead of having to manually do it.</span></span>

> [!WARNING]
> <span data-ttu-id="a2926-177">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602)은 스레드로부터 안전하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-177">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) is not thread-safe.</span></span> <span data-ttu-id="a2926-178">성능과 스레드 안전 향상을 위해 애플리케이션용으로 `PredictionEngine` 개체의 [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601)을 만드는 `PredictionEnginePool` 서비스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-178">For improved performance and thread safety, use the `PredictionEnginePool` service, which creates an [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) of `PredictionEngine` objects for application use.</span></span> 

## <a name="register-startup-as-an-azure-functions-extension"></a><span data-ttu-id="a2926-179">Azure Functions 확장으로 시작 등록</span><span class="sxs-lookup"><span data-stu-id="a2926-179">Register Startup as an Azure Functions extension</span></span>

<span data-ttu-id="a2926-180">애플리케이션에서 `Startup`을 사용하려면 Azure Functions 확장으로 등록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-180">In order to use `Startup` in your application, you need to register it as an Azure Functions extension.</span></span> <span data-ttu-id="a2926-181">이름이 *extensions.json*인 새 파일이 없으면 프로젝트에 하나 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-181">Create a new file called *extensions.json* in your project if one does not already exist.</span></span>

1. <span data-ttu-id="a2926-182">**솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가** > **새 항목**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-182">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="a2926-183">**새 항목** 대화에서 **Visual C#** 노드와 **웹** 노드를 차례로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-183">In the **New Item** dialog, select the **Visual C#** node followed by the **Web** node.</span></span> <span data-ttu-id="a2926-184">그런 다음, **Json 파일** 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-184">Then select the **Json File** option.</span></span> <span data-ttu-id="a2926-185">**이름** 텍스트 상자에 "extensions.json"을 입력한 다음, **확인** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-185">In the **Name** text box, type "extensions.json" and then select the **OK** button.</span></span>

    <span data-ttu-id="a2926-186">*extensions.json* 파일이 코드 편집기에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-186">The *extensions.json* file opens in the code editor.</span></span> <span data-ttu-id="a2926-187">*extensions.json*에 다음 콘텐츠를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-187">Add the following content to *extensions.json*:</span></span>
    
    ```json
    {
      "extensions": [
        {
          "name": "Startup",
          "typename": "SentimentAnalysisFunctionsApp.Startup, SentimentAnalysisFunctionsApp, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null"
        }
      ]
    }
    ```

1. <span data-ttu-id="a2926-188">솔루션 탐색기에서 *extensions.json* 파일을 마우스 오른쪽 단추로 클릭하고 **속성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-188">In Solution Explorer, right-click your *extensions.json* file and select **Properties**.</span></span> <span data-ttu-id="a2926-189">**고급** 아래에서 **출력 디렉터리에 복사** 값을 **변경된 내용만 복사**로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-189">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

## <a name="load-the-model-into-the-function"></a><span data-ttu-id="a2926-190">함수에 모델 로드</span><span class="sxs-lookup"><span data-stu-id="a2926-190">Load the model into the function</span></span>

<span data-ttu-id="a2926-191">*AnalyzeSentiment* 클래스 안에 다음 코드를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-191">Insert the following code inside the *AnalyzeSentiment* class:</span></span>

```csharp
private readonly PredictionEnginePool<SentimentData, SentimentPrediction> _predictionEnginePool;

// AnalyzeSentiment class constructor
public AnalyzeSentiment(PredictionEnginePool<SentimentData, SentimentPrediction> predictionEnginePool)
{
    _predictionEnginePool = predictionEnginePool;
}
```

<span data-ttu-id="a2926-192">이 코드는 종속성 주입을 통해 가져오는 함수의 생성자에 `PredictionEnginePool`을 전달하여 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-192">This code assigns the `PredictionEnginePool` by passing it to the function's constructor which you get via dependency injection.</span></span>

## <a name="use-the-model-to-make-predictions"></a><span data-ttu-id="a2926-193">모델을 사용하여 예측하기</span><span class="sxs-lookup"><span data-stu-id="a2926-193">Use the model to make predictions</span></span>

<span data-ttu-id="a2926-194">*AnalyzeSentiment* 클래스에서 *Run* 메서드의 기존 구현을 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-194">Replace the existing implementation of *Run* method in *AnalyzeSentiment* class with the following code:</span></span>

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
    SentimentPrediction prediction = _predictionEnginePool.Predict(data);

    //Convert prediction to string
    string sentiment = Convert.ToBoolean(prediction.Prediction) ? "Positive" : "Negative";

    //Return Prediction
    return (ActionResult)new OkObjectResult(sentiment);
}
```

<span data-ttu-id="a2926-195">`Run` 메서드가 실행되면 HTTP 요청에서 수신되는 데이터가 직렬 해제되어 `PredictionEnginePool`에 대한 입력으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-195">When the `Run` method executes, the incoming data from the HTTP request is deserialized and used as input for the `PredictionEnginePool`.</span></span> <span data-ttu-id="a2926-196">그런 다음, `Predict` 메서드를 호출하여 예측을 생성하고 결과를 사용자에게 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-196">The `Predict` method is then called to generate a prediction and return the result to the user.</span></span> 

## <a name="test-locally"></a><span data-ttu-id="a2926-197">로컬로 테스트</span><span class="sxs-lookup"><span data-stu-id="a2926-197">Test locally</span></span>

<span data-ttu-id="a2926-198">이제 모든 것이 설정되었으므로 애플리케이션을 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-198">Now that everything is set up, it's time to test the application:</span></span>

1. <span data-ttu-id="a2926-199">애플리케이션 실행</span><span class="sxs-lookup"><span data-stu-id="a2926-199">Run the application</span></span>
1. <span data-ttu-id="a2926-200">PowerShell을 열고 PORT가 애플리케이션을 실행 중인 포트인 경우 프롬프트에 코드를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-200">Open PowerShell and enter the code into the prompt where PORT is the port your application is running on.</span></span> <span data-ttu-id="a2926-201">일반적으로 포트는 7071입니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-201">Typically the port is 7071.</span></span>

    ```powershell
    Invoke-RestMethod "http://localhost:<PORT>/api/AnalyzeSentiment" -Method Post -Body (@{SentimentText="This is a very bad steak"} | ConvertTo-Json) -ContentType "application/json"
    ```

    <span data-ttu-id="a2926-202">성공하면 출력이 아래 텍스트와 같이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-202">If successful, the output should look similar to the text below:</span></span>
    
    ```powershell
    Negative
    ```

<span data-ttu-id="a2926-203">지금까지</span><span class="sxs-lookup"><span data-stu-id="a2926-203">Congratulations!</span></span> <span data-ttu-id="a2926-204">Azure 함수를 사용하여 인터넷을 통해 예측을 수행하도록 모델을 제공했습니다.</span><span class="sxs-lookup"><span data-stu-id="a2926-204">You have successfully served your model to make predictions over the internet using an Azure Function.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a2926-205">다음 단계</span><span class="sxs-lookup"><span data-stu-id="a2926-205">Next Steps</span></span>

- [<span data-ttu-id="a2926-206">Azure에 배포</span><span class="sxs-lookup"><span data-stu-id="a2926-206">Deploy to Azure</span></span>](/azure/azure-functions/functions-develop-vs#publish-to-azure)
