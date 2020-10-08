---
title: ASP.NET Core Web API에 모델 배포
description: ASP.NET Core Web API를 사용하여 인터넷을 통해 ML.NET 감정 분석 기계 학습 모델 제공
ms.date: 11/07/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc,how-to
ms.openlocfilehash: f588d4681ee277ad15b50d5553473b1c9e84d578
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2020
ms.locfileid: "91608766"
---
# <a name="deploy-a-model-in-an-aspnet-core-web-api"></a><span data-ttu-id="5a3bf-103">ASP.NET Core Web API에 모델 배포</span><span class="sxs-lookup"><span data-stu-id="5a3bf-103">Deploy a model in an ASP.NET Core Web API</span></span>

<span data-ttu-id="5a3bf-104">ASP.NET Core Web API를 사용하여 웹에서 미리 학습된 ML.NET 기계 학습 모델을 서비스하는 방법을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="5a3bf-104">Learn how to serve a pre-trained ML.NET machine learning model on the web using an ASP.NET Core Web API.</span></span> <span data-ttu-id="5a3bf-105">웹 API를 통해 모델을 서비스하면 표준 HTTP 메서드를 통한 예측을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a3bf-105">Serving a model over a web API enables predictions via standard HTTP methods.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5a3bf-106">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="5a3bf-106">Prerequisites</span></span>

- <span data-ttu-id="5a3bf-107">“.NET Core 플랫폼 간 개발” 워크로드가 설치된 [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) 이상 또는 Visual Studio 2017 버전 15.6 이상.</span><span class="sxs-lookup"><span data-stu-id="5a3bf-107">[Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) or later or Visual Studio 2017 version 15.6 or later with the ".NET Core cross-platform development" workload installed.</span></span>
- <span data-ttu-id="5a3bf-108">PowerShell을 사용하여 키 백업 파일 복원</span><span class="sxs-lookup"><span data-stu-id="5a3bf-108">PowerShell.</span></span>
- <span data-ttu-id="5a3bf-109">미리 학습된 모델입니다.</span><span class="sxs-lookup"><span data-stu-id="5a3bf-109">Pre-trained model.</span></span> <span data-ttu-id="5a3bf-110">[ML.NET 감정 분석 자습서](../tutorials/sentiment-analysis.md)를 사용하여 자체 모델을 빌드하거나 이 [미리 학습된 감정 분석 기계 학습 모델](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip) 다운로드</span><span class="sxs-lookup"><span data-stu-id="5a3bf-110">Use the [ML.NET Sentiment Analysis tutorial](../tutorials/sentiment-analysis.md) to build your own model or download this [pre-trained sentiment analysis machine learning model](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)</span></span>

## <a name="create-aspnet-core-web-api-project"></a><span data-ttu-id="5a3bf-111">ASP.NET Core Web API 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="5a3bf-111">Create ASP.NET Core Web API project</span></span>

1. <span data-ttu-id="5a3bf-112">Visual Studio 2017을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5a3bf-112">Open Visual Studio 2017.</span></span> <span data-ttu-id="5a3bf-113">메뉴 모음에서 **파일 > 새로 만들기 > 프로젝트**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5a3bf-113">Select **File > New > Project** from the menu bar.</span></span> <span data-ttu-id="5a3bf-114">[새 프로젝트] 대화 상자에서 **Visual C#** 노드와 **Web** 노드를 차례로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5a3bf-114">In the New Project dialog, select the **Visual C#** node followed by the **Web** node.</span></span> <span data-ttu-id="5a3bf-115">그런 다음, **ASP.NET Core 웹 애플리케이션** 프로젝트 템플릿을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5a3bf-115">Then select the **ASP.NET Core Web Application** project template.</span></span> <span data-ttu-id="5a3bf-116">**이름** 텍스트 상자에 “SentimentAnalysisWebAPI”를 입력한 다음, **확인** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5a3bf-116">In the **Name** text box, type "SentimentAnalysisWebAPI" and then select the **OK** button.</span></span>

1. <span data-ttu-id="5a3bf-117">다른 유형의 ASP.NET Core 프로젝트를 표시하는 창에서 **API**를 선택하고 **확인** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5a3bf-117">In the window that displays the different types of ASP.NET Core Projects, select **API** and the select the **OK** button.</span></span>

1. <span data-ttu-id="5a3bf-118">프로젝트에서 *MLModels* 디렉터리를 만들어 미리 빌드된 기계 학습 모델 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="5a3bf-118">Create a directory named *MLModels* in your project to save your pre-built machine learning model files:</span></span>

    <span data-ttu-id="5a3bf-119">솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 [추가] > [새 폴더]를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5a3bf-119">In Solution Explorer, right-click on your project and select Add > New Folder.</span></span> <span data-ttu-id="5a3bf-120">“MLModels”를 입력하고 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="5a3bf-120">Type "MLModels" and hit Enter.</span></span>

1. <span data-ttu-id="5a3bf-121">**Microsoft.ML NuGet 패키지**를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="5a3bf-121">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="5a3bf-122">솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **NuGet 패키지 관리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5a3bf-122">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="5a3bf-123">“nuget.org”를 패키지 소스로 선택하고, [찾아보기] 탭을 선택하고, **Microsoft.ML**을 검색하고, 목록에서 해당 패키지를 선택하고, [설치] 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5a3bf-123">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the Install button.</span></span> <span data-ttu-id="5a3bf-124">**변경 내용 미리 보기** 대화 상자에서 **확인** 단추를 선택한 다음, 나열된 패키지의 사용 조건에 동의하는 경우 [라이선스 승인] 대화 상자에서 **동의함** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5a3bf-124">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the License Acceptance dialog if you agree with the license terms for the packages listed.</span></span>

1. <span data-ttu-id="5a3bf-125">**Microsoft.Extensions.ML NuGet 패키지**를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="5a3bf-125">Install the **Microsoft.Extensions.ML Nuget Package**:</span></span>

    <span data-ttu-id="5a3bf-126">솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **NuGet 패키지 관리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5a3bf-126">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="5a3bf-127">“nuget.org”를 패키지 원본으로 선택하고, 찾아보기 탭을 선택하고, **Microsoft.Extensions.ML**을 검색하고, 목록에서 해당 패키지를 선택하고, 설치 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5a3bf-127">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.Extensions.ML**, select that package in the list, and select the Install button.</span></span> <span data-ttu-id="5a3bf-128">**변경 내용 미리 보기** 대화 상자에서 **확인** 단추를 선택한 다음, 나열된 패키지의 사용 조건에 동의하는 경우 [라이선스 승인] 대화 상자에서 **동의함** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5a3bf-128">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the License Acceptance dialog if you agree with the license terms for the packages listed.</span></span>

### <a name="add-model-to-aspnet-core-web-api-project"></a><span data-ttu-id="5a3bf-129">ASP.NET Core Web API 프로젝트에 모델 추가</span><span class="sxs-lookup"><span data-stu-id="5a3bf-129">Add model to ASP.NET Core Web API project</span></span>

1. <span data-ttu-id="5a3bf-130">미리 빌드된 모델을 *MLModels* 디렉터리에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="5a3bf-130">Copy your pre-built model to the *MLModels* directory</span></span>
1. <span data-ttu-id="5a3bf-131">솔루션 탐색기에서 모델 zip 파일을 마우스 오른쪽 단추로 클릭하고 [속성]을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5a3bf-131">In Solution Explorer, right-click the model zip file and select Properties.</span></span> <span data-ttu-id="5a3bf-132">[고급] 아래에서 [출력 디렉터리에 복사] 값을 [변경된 내용만 복사]로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="5a3bf-132">Under Advanced, change the value of Copy to Output Directory to Copy if newer.</span></span>

## <a name="create-data-models"></a><span data-ttu-id="5a3bf-133">데이터 모델 만들기</span><span class="sxs-lookup"><span data-stu-id="5a3bf-133">Create data models</span></span>

<span data-ttu-id="5a3bf-134">입력 데이터 및 예측에 대한 일부 클래스를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a3bf-134">You need to create some classes for your input data and predictions.</span></span> <span data-ttu-id="5a3bf-135">새 클래스를 프로젝트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5a3bf-135">Add a new class to your project:</span></span>

1. <span data-ttu-id="5a3bf-136">프로젝트에서 *DataModels* 디렉터리를 만들어 데이터 모델을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="5a3bf-136">Create a directory named *DataModels* in your project to save your data models:</span></span>

    <span data-ttu-id="5a3bf-137">솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 [추가] > [새 폴더]를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5a3bf-137">In Solution Explorer, right-click on your project and select Add > New Folder.</span></span> <span data-ttu-id="5a3bf-138">“DataModels”를 입력하고 **Enter** 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="5a3bf-138">Type "DataModels" and hit **Enter**.</span></span>

2. <span data-ttu-id="5a3bf-139">솔루션 탐색기에서 *DataModels* 디렉터리를 마우스 오른쪽 단추로 클릭하고 [추가] > [새 항목]을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5a3bf-139">In Solution Explorer, right-click the *DataModels* directory, and then select Add > New Item.</span></span>
3. <span data-ttu-id="5a3bf-140">**새 항목 추가** 대화 상자에서 **클래스**를 선택하고 **이름** 필드를 *SentimentData.cs*로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="5a3bf-140">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentData.cs*.</span></span> <span data-ttu-id="5a3bf-141">그런 다음, **추가** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5a3bf-141">Then, select the **Add** button.</span></span> <span data-ttu-id="5a3bf-142">*SentimentData.cs* 파일이 코드 편집기에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="5a3bf-142">The *SentimentData.cs* file opens in the code editor.</span></span> <span data-ttu-id="5a3bf-143">다음 using 문을 *SentimentData.cs*의 맨 위에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5a3bf-143">Add the following using statement to the top of *SentimentData.cs*:</span></span>

    ```csharp
    using Microsoft.ML.Data;
    ```

    <span data-ttu-id="5a3bf-144">기존 클래스 정의를 제거하고 다음 코드를 **SentimentData.cs** 파일에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5a3bf-144">Remove the existing class definition and add the following code to the **SentimentData.cs** file:</span></span>

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

4. <span data-ttu-id="5a3bf-145">솔루션 탐색기에서 *DataModels* 디렉터리를 마우스 오른쪽 단추로 클릭하고 **추가 > 새 항목**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5a3bf-145">In Solution Explorer, right-click the *DataModels* directory, and then select **Add > New Item**.</span></span>
5. <span data-ttu-id="5a3bf-146">**새 항목 추가** 대화 상자에서 **클래스**를 선택하고 **이름** 필드를 *SentimentPrediction.cs*로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="5a3bf-146">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentPrediction.cs*.</span></span> <span data-ttu-id="5a3bf-147">그런 다음, [추가] 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5a3bf-147">Then, select the Add button.</span></span> <span data-ttu-id="5a3bf-148">*SentimentPrediction.cs* 파일이 코드 편집기에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="5a3bf-148">The *SentimentPrediction.cs* file opens in the code editor.</span></span> <span data-ttu-id="5a3bf-149">다음 using 문을 *SentimentPrediction.cs*의 맨 위에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5a3bf-149">Add the following using statement to the top of *SentimentPrediction.cs*:</span></span>

    ```csharp
    using Microsoft.ML.Data;
    ```

    <span data-ttu-id="5a3bf-150">기존 클래스 정의를 제거하고 다음 코드를 *SentimentPrediction.cs* 파일에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5a3bf-150">Remove the existing class definition and add the following code to the *SentimentPrediction.cs* file:</span></span>

    ```csharp
    public class SentimentPrediction : SentimentData
    {

        [ColumnName("PredictedLabel")]
        public bool Prediction { get; set; }

        public float Probability { get; set; }

        public float Score { get; set; }
    }
    ```

    <span data-ttu-id="5a3bf-151">`SentimentPrediction`는 `SentimentData`에서 상속됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a3bf-151">`SentimentPrediction` inherits from `SentimentData`.</span></span> <span data-ttu-id="5a3bf-152">이렇게 하면 모델에서 생성된 출력과 함께 `SentimentText` 속성의 원래 데이터를 더 쉽게 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a3bf-152">This makes it easier to see the original data in the `SentimentText` property along with the output generated by the model.</span></span>

## <a name="register-predictionenginepool-for-use-in-the-application"></a><span data-ttu-id="5a3bf-153">애플리케이션에서 사용하기 위해 PredictionEnginePool 등록</span><span class="sxs-lookup"><span data-stu-id="5a3bf-153">Register PredictionEnginePool for use in the application</span></span>

<span data-ttu-id="5a3bf-154">단일 예측을 수행하려면 [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602)을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a3bf-154">To make a single prediction, you have to create a [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602).</span></span> <span data-ttu-id="5a3bf-155">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602)은 스레드로부터 안전하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5a3bf-155">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) is not thread-safe.</span></span> <span data-ttu-id="5a3bf-156">또한 애플리케이션 내에서 필요한 모든 위치에서 인스턴스를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a3bf-156">Additionally, you have to create an instance of it everywhere it is needed within your application.</span></span> <span data-ttu-id="5a3bf-157">애플리케이션이 커지면 이 프로세스를 관리할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a3bf-157">As your application grows, this process can become unmanageable.</span></span> <span data-ttu-id="5a3bf-158">성능 및 스레드 보안을 개선하려면 종속성 주입과 `PredictionEnginePool` 서비스를 함께 사용합니다. 이 서비스는 애플리케이션 전체에서 사용할 [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) 개체의 [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601)을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5a3bf-158">For improved performance and thread safety, use a combination of dependency injection and the `PredictionEnginePool` service, which creates an [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) of [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) objects for use throughout your application.</span></span>

<span data-ttu-id="5a3bf-159">다음 링크에서는 [ASP.NET Core에서 종속성 주입](/aspnet/core/fundamentals/dependency-injection?view=aspnetcore-2.1)에 대한 자세한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5a3bf-159">The following link provides more information if you want to learn more about [dependency injection in ASP.NET Core](/aspnet/core/fundamentals/dependency-injection?view=aspnetcore-2.1).</span></span>

1. <span data-ttu-id="5a3bf-160">*Startup.cs* 클래스를 열고 다음 using 문을 파일 맨 위에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5a3bf-160">Open the *Startup.cs* class and add the following using statement to the top of the file:</span></span>

    ```csharp
    using Microsoft.AspNetCore.Builder;
    using Microsoft.AspNetCore.Hosting;
    using Microsoft.AspNetCore.Mvc;
    using Microsoft.Extensions.Configuration;
    using Microsoft.Extensions.DependencyInjection;
    using Microsoft.Extensions.ML;
    using SentimentAnalysisWebAPI.DataModels;
    ```

2. <span data-ttu-id="5a3bf-161">*ConfigureServices* 메서드에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5a3bf-161">Add the following code to the *ConfigureServices* method:</span></span>

    ```csharp
    services.AddPredictionEnginePool<SentimentData, SentimentPrediction>()
        .FromFile(modelName: "SentimentAnalysisModel", filePath:"MLModels/sentiment_model.zip", watchForChanges: true);
    ```

<span data-ttu-id="5a3bf-162">개략적으로 이 코드는 애플리케이션을 수동으로 초기화하지 않고도 애플리케이션에서 요청할 때 나중에 사용할 수 있도록 자동으로 개체 및 서비스를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="5a3bf-162">At a high level, this code initializes the objects and services automatically for later use when requested by the application instead of having to manually do it.</span></span>

<span data-ttu-id="5a3bf-163">기계 학습 모델은 정적이지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5a3bf-163">Machine learning models are not static.</span></span> <span data-ttu-id="5a3bf-164">새 학습 데이터를 사용할 수 있게 되면 모델을 다시 학습하고 다시 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="5a3bf-164">As new training data becomes available, the model is retrained and redeployed.</span></span> <span data-ttu-id="5a3bf-165">최신 버전의 모델을 애플리케이션으로 가져오는 한 가지 방법은 전체 애플리케이션을 다시 배포하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5a3bf-165">One way to get the latest version of the model into your application is to redeploy the entire application.</span></span> <span data-ttu-id="5a3bf-166">그러나 이 경우 애플리케이션 가동 중지 시간이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="5a3bf-166">However, this introduces application downtime.</span></span> <span data-ttu-id="5a3bf-167">`PredictionEnginePool` 서비스는 애플리케이션을 가동 중지하지 않으면서 업데이트된 모델을 다시 로드하는 메커니즘을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5a3bf-167">The `PredictionEnginePool` service provides a mechanism to reload an updated model without taking your application down.</span></span>

<span data-ttu-id="5a3bf-168">`watchForChanges` 매개 변수를 `true`로 설정하면 `PredictionEnginePool`은 파일 시스템 변경 알림을 수신 대기하고 파일이 변경될 때 이벤트를 발생시키는 [`FileSystemWatcher`](xref:System.IO.FileSystemWatcher)를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="5a3bf-168">Set the `watchForChanges` parameter to `true`, and the `PredictionEnginePool` starts a [`FileSystemWatcher`](xref:System.IO.FileSystemWatcher) that listens to the file system change notifications and raises events when there is a change to the file.</span></span> <span data-ttu-id="5a3bf-169">그러면 `PredictionEnginePool`에서 모델을 자동으로 다시 로드하도록 지정할 수 있는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a3bf-169">This prompts the `PredictionEnginePool` to automatically reload the model.</span></span>

<span data-ttu-id="5a3bf-170">모델은 `modelName` 매개 변수로 식별되므로 변경 시, 애플리케이션당 두 개 이상의 모델이 다시 로드될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a3bf-170">The model is identified by the `modelName` parameter so that more than one model per application can be reloaded upon change.</span></span>

> [!TIP]
> <span data-ttu-id="5a3bf-171">또는 원격으로 저장된 모델을 사용하는 경우 `FromUri` 메서드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a3bf-171">Alternatively, you can use the `FromUri` method when working with models stored remotely.</span></span> <span data-ttu-id="5a3bf-172">`FromUri`는 파일 변경 이벤트를 감시하지 않고, 원격 위치에서 변경 내용을 폴링합니다.</span><span class="sxs-lookup"><span data-stu-id="5a3bf-172">Rather than watching for file changed events, `FromUri` polls the remote location for changes.</span></span> <span data-ttu-id="5a3bf-173">폴링 간격의 기본값은 5분입니다.</span><span class="sxs-lookup"><span data-stu-id="5a3bf-173">The polling interval defaults to 5 minutes.</span></span> <span data-ttu-id="5a3bf-174">애플리케이션의 요구 사항에 따라 폴링 간격을 늘리거나 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a3bf-174">You can increase or decrease the polling interval based on your application's requirements.</span></span> <span data-ttu-id="5a3bf-175">아래 코드 샘플에서 `PredictionEnginePool`은 1분마다 지정된 URI에 저장된 모델을 폴링합니다.</span><span class="sxs-lookup"><span data-stu-id="5a3bf-175">In the code sample below, the `PredictionEnginePool` polls the model stored at the specified URI every minute.</span></span>
>
>```csharp
>services.AddPredictionEnginePool<SentimentData, SentimentPrediction>()
>   .FromUri(
>       modelName: "SentimentAnalysisModel",
>       uri:"https://github.com/dotnet/samples/raw/master/machine-learning/models/sentimentanalysis/sentiment_model.zip",
>       period: TimeSpan.FromMinutes(1));
>```

## <a name="create-predict-controller"></a><span data-ttu-id="5a3bf-176">예측 컨트롤러 만들기</span><span class="sxs-lookup"><span data-stu-id="5a3bf-176">Create Predict controller</span></span>

<span data-ttu-id="5a3bf-177">들어오는 HTTP 요청을 처리하려면 컨트롤러를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5a3bf-177">To process your incoming HTTP requests, create a controller.</span></span>

1. <span data-ttu-id="5a3bf-178">솔루션 탐색기에서 *Controllers* 디렉터리를 마우스 오른쪽 단추로 클릭하고 **추가 > 컨트롤러**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5a3bf-178">In Solution Explorer, right-click the *Controllers* directory, and then select **Add > Controller**.</span></span>
1. <span data-ttu-id="5a3bf-179">**새 항목 추가** 대화 상자에서 **API 컨트롤러 비어 있음**을 선택하고 **추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5a3bf-179">In the **Add New Item** dialog box, select **API Controller Empty** and select **Add**.</span></span>
1. <span data-ttu-id="5a3bf-180">프롬프트에서 **컨트롤러 이름** 필드를 *PredictController.cs*로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="5a3bf-180">In the prompt change the **Controller Name** field to *PredictController.cs*.</span></span> <span data-ttu-id="5a3bf-181">그런 다음, [추가] 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5a3bf-181">Then, select the Add button.</span></span> <span data-ttu-id="5a3bf-182">*PredictController.cs* 파일이 코드 편집기에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="5a3bf-182">The *PredictController.cs* file opens in the code editor.</span></span> <span data-ttu-id="5a3bf-183">다음 using 문을 *PredictController.cs*의 맨 위에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5a3bf-183">Add the following using statement to the top of *PredictController.cs*:</span></span>

    ```csharp
    using System;
    using Microsoft.AspNetCore.Mvc;
    using Microsoft.Extensions.ML;
    using SentimentAnalysisWebAPI.DataModels;
    ```

    <span data-ttu-id="5a3bf-184">기존 클래스 정의를 제거하고 다음 코드를 *PredictController.cs* 파일에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5a3bf-184">Remove the existing class definition and add the following code to the *PredictController.cs* file:</span></span>

    ```csharp
    public class PredictController : ControllerBase
    {
        private readonly PredictionEnginePool<SentimentData, SentimentPrediction> _predictionEnginePool;

        public PredictController(PredictionEnginePool<SentimentData,SentimentPrediction> predictionEnginePool)
        {
            _predictionEnginePool = predictionEnginePool;
        }

        [HttpPost]
        public ActionResult<string> Post([FromBody] SentimentData input)
        {
            if(!ModelState.IsValid)
            {
                return BadRequest();
            }

            SentimentPrediction prediction = _predictionEnginePool.Predict(modelName: "SentimentAnalysisModel", example: input);

            string sentiment = Convert.ToBoolean(prediction.Prediction) ? "Positive" : "Negative";

            return Ok(sentiment);
        }
    }
    ```

<span data-ttu-id="5a3bf-185">이 코드는 종속성 주입을 통해 가져오는 컨트롤러의 생성자에 `PredictionEnginePool`을 전달하여 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="5a3bf-185">This code assigns the `PredictionEnginePool` by passing it to the controller's constructor which you get via dependency injection.</span></span> <span data-ttu-id="5a3bf-186">그런 다음, `Predict` 컨트롤러의 `Post` 메서드가 `PredictionEnginePool`을 사용하여 `Startup` 클래스에 등록된 `SentimentAnalysisModel`로 예측을 수행하고 성공하면 결과를 사용자에게 다시 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="5a3bf-186">Then, the `Predict` controller's `Post` method uses the `PredictionEnginePool` to make predictions using the `SentimentAnalysisModel` registered in the `Startup` class and returns the results back to the user if successful.</span></span>

## <a name="test-web-api-locally"></a><span data-ttu-id="5a3bf-187">로컬로 Web API 테스트</span><span class="sxs-lookup"><span data-stu-id="5a3bf-187">Test web API locally</span></span>

<span data-ttu-id="5a3bf-188">이제 모든 것이 설정되면 애플리케이션을 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a3bf-188">Once everything is set up, it's time to test the application.</span></span>

1. <span data-ttu-id="5a3bf-189">애플리케이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="5a3bf-189">Run the application.</span></span>
1. <span data-ttu-id="5a3bf-190">PowerShell을 열고 PORT가 애플리케이션이 수신 대기 중인 포트인 경우 다음 코드를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="5a3bf-190">Open PowerShell and enter the following code where PORT is the port your application is listening on.</span></span>

    ```powershell
    Invoke-RestMethod "https://localhost:<PORT>/api/predict" -Method Post -Body (@{SentimentText="This was a very bad steak"} | ConvertTo-Json) -ContentType "application/json"
    ```

    <span data-ttu-id="5a3bf-191">성공하면 출력이 아래 텍스트와 같이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a3bf-191">If successful, the output should look similar to the text below:</span></span>

    ```powershell
    Negative
    ```

<span data-ttu-id="5a3bf-192">지금까지</span><span class="sxs-lookup"><span data-stu-id="5a3bf-192">Congratulations!</span></span> <span data-ttu-id="5a3bf-193">ASP.NET Core Web API를 사용하여 인터넷을 통해 예측을 수행하도록 모델을 제공했습니다.</span><span class="sxs-lookup"><span data-stu-id="5a3bf-193">You have successfully served your model to make predictions over the internet using an ASP.NET Core Web API.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5a3bf-194">다음 단계</span><span class="sxs-lookup"><span data-stu-id="5a3bf-194">Next Steps</span></span>

- [<span data-ttu-id="5a3bf-195">Azure에 배포</span><span class="sxs-lookup"><span data-stu-id="5a3bf-195">Deploy to Azure</span></span>](/aspnet/core/tutorials/publish-to-azure-webapp-using-vs#deploy-the-app-to-azure)
