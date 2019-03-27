---
title: ASP.NET Core Web API에서 기계 학습 모델 제공
description: ASP.NET Core Web API를 사용하여 인터넷을 통해 ML.NET 감정 분석 기계 학습 모델 제공
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: 0cc13ec22b3a8805ec4aa17bf10560b2564ccd63
ms.sourcegitcommit: 77854e8704b9689b73103d691db34d71c2bf1dad
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2019
ms.locfileid: "58307917"
---
# <a name="how-to-serve-machine-learning-model-through-aspnet-core-web-api"></a><span data-ttu-id="5c38d-103">방법: ASP.NET Core Web API를 통해 기계 학습 모델 제공</span><span class="sxs-lookup"><span data-stu-id="5c38d-103">How-To: Serve Machine Learning Model Through ASP.NET Core Web API</span></span>

<span data-ttu-id="5c38d-104">이 방법은 ASP.NET Core Web API를 사용하여 웹에 미리 빌드된 ML.NET 기계 학습 모델을 제공하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5c38d-104">This how-to shows how to serve a pre-built ML.NET machine learning model to the web using an ASP.NET Core Web API.</span></span> <span data-ttu-id="5c38d-105">이렇게 하면 사용자가 표준 HTTP 메서드를 통해 예측을 위해 API에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c38d-105">By doing so it allows for users to access the API for prediction purposes via standard HTTP methods.</span></span>

> [!NOTE]
> <span data-ttu-id="5c38d-106">이 항목은 현재 미리 보기로 제공되는 ML.NET을 참조하며, 자료는 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c38d-106">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="5c38d-107">자세한 내용은 [ML.NET 소개](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5c38d-107">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="5c38d-108">이 방법과 관련 샘플에서는 현재 **ML.NET 버전 0.10**을 사용하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c38d-108">This how-to and related sample are currently using **ML.NET version 0.10**.</span></span> <span data-ttu-id="5c38d-109">자세한 내용은 [dotnet/machinelearning GitHub 리포지토리](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes)에서 릴리스 정보를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5c38d-109">For more information, see the release notes at the [dotnet/machinelearning github repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5c38d-110">전제 조건</span><span class="sxs-lookup"><span data-stu-id="5c38d-110">Prerequisites</span></span>

- <span data-ttu-id="5c38d-111">“.NET Core 플랫폼 간 개발” 워크로드가 설치된 [Visual Studio 2017 15.6 이상](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017).</span><span class="sxs-lookup"><span data-stu-id="5c38d-111">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>
- <span data-ttu-id="5c38d-112">PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5c38d-112">Powershell.</span></span>
- <span data-ttu-id="5c38d-113">미리 학습된 모델입니다.</span><span class="sxs-lookup"><span data-stu-id="5c38d-113">Pre-trained model.</span></span>
    - <span data-ttu-id="5c38d-114">[ML.NET 감정 분석 자습서](../tutorials/sentiment-analysis.md)를 사용하여 고유한 모델을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="5c38d-114">Use the [ML.NET Sentiment Analysis tutorial](../tutorials/sentiment-analysis.md) to build your own model.</span></span>
    - <span data-ttu-id="5c38d-115">이 [미리 학습된 감정 분석 기계 학습 모델](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="5c38d-115">Download this [pre-trained sentiment analysis machine learning model](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)</span></span>

## <a name="create-aspnet-core-web-api-project"></a><span data-ttu-id="5c38d-116">ASP.NET Core Web API 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="5c38d-116">Create ASP.NET Core Web API Project</span></span>

1. <span data-ttu-id="5c38d-117">Visual Studio 2017을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5c38d-117">Open Visual Studio 2017.</span></span> <span data-ttu-id="5c38d-118">메뉴 모음에서 **파일 > 새로 만들기 > 프로젝트**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5c38d-118">Select **File > New > Project** from the menu bar.</span></span> <span data-ttu-id="5c38d-119">[새 프로젝트] 대화 상자에서 **Visual C#** 노드와 **Web** 노드를 차례로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5c38d-119">In the New Project dialog, select the **Visual C#** node followed by the **Web** node.</span></span> <span data-ttu-id="5c38d-120">그런 다음, **ASP.NET Core 웹 애플리케이션** 프로젝트 템플릿을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5c38d-120">Then select the **ASP.NET Core Web Application** project template.</span></span> <span data-ttu-id="5c38d-121">**이름** 텍스트 상자에 “SentimentAnalysisWebAPI”를 입력한 다음, **확인** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5c38d-121">In the **Name** text box, type "SentimentAnalysisWebAPI" and then select the **OK** button.</span></span>
1. <span data-ttu-id="5c38d-122">다른 유형의 ASP.NET Core 프로젝트를 표시하는 창에서 **API**를 선택하고 **확인** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5c38d-122">In the window that displays the different types of ASP.NET Core Projects, select **API** and the select the **OK** button.</span></span>
1. <span data-ttu-id="5c38d-123">프로젝트에서 *MLModels* 디렉터리를 만들어 미리 빌드된 기계 학습 모델 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="5c38d-123">Create a directory named *MLModels* in your project to save your pre-built machine learning model files:</span></span>

    <span data-ttu-id="5c38d-124">솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 [추가] > [새 폴더]를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5c38d-124">In Solution Explorer, right-click on your project and select Add > New Folder.</span></span> <span data-ttu-id="5c38d-125">“MLModels”를 입력하고 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="5c38d-125">Type "MLModels" and hit Enter.</span></span>

1. <span data-ttu-id="5c38d-126">**Microsoft.ML NuGet 패키지**를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="5c38d-126">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="5c38d-127">솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **NuGet 패키지 관리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5c38d-127">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="5c38d-128">“nuget.org”를 패키지 소스로 선택하고, [찾아보기] 탭을 선택하고, **Microsoft.ML**을 검색하고, 목록에서 해당 패키지를 선택하고, [설치] 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5c38d-128">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the Install button.</span></span> <span data-ttu-id="5c38d-129">**변경 내용 미리 보기** 대화 상자에서 **확인** 단추를 선택한 다음, 나열된 패키지의 사용 조건에 동의하는 경우 [라이선스 승인] 대화 상자에서 **동의함** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5c38d-129">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the License Acceptance dialog if you agree with the license terms for the packages listed.</span></span>

### <a name="add-model-to-aspnet-core-web-api-project"></a><span data-ttu-id="5c38d-130">ASP.NET Core Web API 프로젝트에 모델 추가</span><span class="sxs-lookup"><span data-stu-id="5c38d-130">Add Model to ASP.NET Core Web API Project</span></span>

1. <span data-ttu-id="5c38d-131">미리 빌드된 모델을 *MLModels* 디렉터리에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="5c38d-131">Copy your pre-built model to the *MLModels* directory</span></span>
1. <span data-ttu-id="5c38d-132">솔루션 탐색기에서 모델 zip 파일을 마우스 오른쪽 단추로 클릭하고 [속성]을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5c38d-132">In Solution Explorer, right-click the model zip file and select Properties.</span></span> <span data-ttu-id="5c38d-133">[고급] 아래에서 [출력 디렉터리에 복사] 값을 [변경된 내용만 복사]로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="5c38d-133">Under Advanced, change the value of Copy to Output Directory to Copy if newer.</span></span>

## <a name="build-data-models"></a><span data-ttu-id="5c38d-134">데이터 모델 빌드</span><span class="sxs-lookup"><span data-stu-id="5c38d-134">Build Data Models</span></span>

<span data-ttu-id="5c38d-135">입력 데이터 및 예측에 대한 일부 클래스를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c38d-135">You need to create some classes for your input data and predictions.</span></span> <span data-ttu-id="5c38d-136">새 클래스를 프로젝트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5c38d-136">Add a new class to your project:</span></span>

1. <span data-ttu-id="5c38d-137">프로젝트에서 *DataModels* 디렉터리를 만들어 데이터 모델을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="5c38d-137">Create a directory named *DataModels* in your project to save your data models:</span></span>

    <span data-ttu-id="5c38d-138">솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 [추가] > [새 폴더]를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5c38d-138">In Solution Explorer, right-click on your project and select Add > New Folder.</span></span> <span data-ttu-id="5c38d-139">“DataModels”를 입력하고 **Enter** 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="5c38d-139">Type "DataModels" and hit **Enter**.</span></span>

2. <span data-ttu-id="5c38d-140">솔루션 탐색기에서 *DataModels* 디렉터리를 마우스 오른쪽 단추로 클릭하고 [추가] > [새 항목]을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5c38d-140">In Solution Explorer, right-click the *DataModels* directory, and then select Add > New Item.</span></span>
3. <span data-ttu-id="5c38d-141">**새 항목 추가** 대화 상자에서 **클래스**를 선택하고 **이름** 필드를 *SentimentData.cs*로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="5c38d-141">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentData.cs*.</span></span> <span data-ttu-id="5c38d-142">그런 다음, **추가** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5c38d-142">Then, select the **Add** button.</span></span> <span data-ttu-id="5c38d-143">*SentimentData.cs* 파일이 코드 편집기에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="5c38d-143">The *SentimentData.cs* file opens in the code editor.</span></span> <span data-ttu-id="5c38d-144">다음 using 문을 *SentimentData.cs*의 맨 위에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5c38d-144">Add the following using statement to the top of *SentimentData.cs*:</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Threading.Tasks;
using Microsoft.ML.Data;
```

<span data-ttu-id="5c38d-145">기존 클래스 정의를 제거하고 다음 코드를 **SentimentData.cs** 파일에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5c38d-145">Remove the existing class definition and add the following code to the **SentimentData.cs** file:</span></span>

```csharp
public class SentimentData
{
    [LoadColumn(0)]
    public bool Label { get; set; }
    [LoadColumn(1)]
    public string Text { get; set; }   
}
```

4. <span data-ttu-id="5c38d-146">솔루션 탐색기에서 *DataModels* 디렉터리를 마우스 오른쪽 단추로 클릭하고 **추가 > 새 항목**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5c38d-146">In Solution Explorer, right-click the *DataModels* directory, and then select **Add > New Item**.</span></span>
5. <span data-ttu-id="5c38d-147">**새 항목 추가** 대화 상자에서 **클래스**를 선택하고 **이름** 필드를 *SentimentPrediction.cs*로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="5c38d-147">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentPrediction.cs*.</span></span> <span data-ttu-id="5c38d-148">그런 다음, [추가] 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5c38d-148">Then, select the Add button.</span></span> <span data-ttu-id="5c38d-149">*SentimentPrediction.cs* 파일이 코드 편집기에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="5c38d-149">The *SentimentPrediction.cs* file opens in the code editor.</span></span> <span data-ttu-id="5c38d-150">다음 using 문을 *SentimentPrediction.cs*의 맨 위에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5c38d-150">Add the following using statement to the top of *SentimentPrediction.cs*:</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Threading.Tasks;
using Microsoft.ML.Data;
```

<span data-ttu-id="5c38d-151">기존 클래스 정의를 제거하고 다음 코드를 *SentimentPrediction.cs* 파일에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5c38d-151">Remove the existing class definition and add the following code to the *SentimentPrediction.cs* file:</span></span>

```csharp
public class SentimentPrediction
{
    [ColumnName("PredictedLabel")]
    public bool Prediction { get; set; }
}
```

## <a name="register-predictionengine-for-use-in-application"></a><span data-ttu-id="5c38d-152">애플리케이션에서 사용할 PredictionEngine 등록</span><span class="sxs-lookup"><span data-stu-id="5c38d-152">Register PredictionEngine for Use in Application</span></span>

<span data-ttu-id="5c38d-153">단일 예측을 수행하기 위해 `PredictionEngine`을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c38d-153">To make a single prediction, you can use `PredictionEngine`.</span></span> <span data-ttu-id="5c38d-154">애플리케이션에서 `PredictionEngine`을 사용하려면 필요할 때마다 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c38d-154">In order to use `PredictionEngine` in your application you will have to create it every time it is needed.</span></span> <span data-ttu-id="5c38d-155">이 경우 가장 좋은 방법은 ASP.NET Core 종속성 주입을 고려하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5c38d-155">In that case, a best practice to consider is ASP.NET Core dependency injection.</span></span>

<span data-ttu-id="5c38d-156">[종속성 주입](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection?view=aspnetcore-2.1)에 대한 자세한 내용은 다음 링크를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5c38d-156">The following link provides more information if you want to learn about [dependency injection](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection?view=aspnetcore-2.1).</span></span>

1. <span data-ttu-id="5c38d-157">*Startup.cs* 클래스를 열고 다음 using 문을 파일 맨 위에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5c38d-157">Open the *Startup.cs* class and add the following using statement to the top of the file:</span></span>

```csharp
using System.IO;
using Microsoft.AspNetCore.Builder;
using Microsoft.AspNetCore.Hosting;
using Microsoft.AspNetCore.Mvc;
using Microsoft.Extensions.Configuration;
using Microsoft.Extensions.DependencyInjection;
using Microsoft.ML;
using Microsoft.ML.Core.Data;
using SentimentAnalysisWebAPI.DataModels;
```

2. <span data-ttu-id="5c38d-158">*ConfigureServices* 메서드에 다음 코드 줄을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5c38d-158">Add the following lines of code to the *ConfigureServices* method:</span></span>

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddMvc().SetCompatibilityVersion(CompatibilityVersion.Version_2_1);

    services.AddScoped<MLContext>();
    services.AddScoped<PredictionEngine<SentimentData, SentimentPrediction>>((ctx) =>
    {
        MLContext mlContext = ctx.GetRequiredService<MLContext>();
        string modelFilePathName = "MLModels/sentiment_model.zip";

        //Load model from file
        ITransformer model;
        using (var stream = File.OpenRead(modelFilePathName))
        {
            model = mlContext.Model.Load(stream);
        }

        // Return prediction engine
        return model.CreatePredictionEngine<SentimentData, SentimentPrediction>(mlContext);
    });
}
```

> [!WARNING]
> <span data-ttu-id="5c38d-159">`PredictionEngine`는 스레드로부터 안전하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5c38d-159">`PredictionEngine` is not thread-safe.</span></span> <span data-ttu-id="5c38d-160">개체 생성 비용을 제한할 수 있는 방법은 서비스 수명 *Scoped*를 지정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5c38d-160">A way that you can limit the cost of creating the object is by making its service lifetime *Scoped*.</span></span> <span data-ttu-id="5c38d-161">*Scoped* 개체는 요청 내에서는 동일하지만 요청 간에는 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="5c38d-161">*Scoped* objects are the same within a request but different across requests.</span></span> <span data-ttu-id="5c38d-162">[수명 서비스](/aspnet/core/fundamentals/dependency-injection?view=aspnetcore-2.1#service-lifetimes)에 대해 자세히 알아보려면 다음 링크를 방문하세요.</span><span class="sxs-lookup"><span data-stu-id="5c38d-162">Visit the following link to learn more about [service lifetimes](/aspnet/core/fundamentals/dependency-injection?view=aspnetcore-2.1#service-lifetimes).</span></span>

<span data-ttu-id="5c38d-163">개략적으로 이 코드는 애플리케이션을 수동으로 초기화하지 않고도 애플리케이션에서 요청할 때 자동으로 개체 및 서비스를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="5c38d-163">At a high level, this code initializes the objects and services automatically when requested by the application instead of having to manually do it.</span></span>

## <a name="create-predict-controller"></a><span data-ttu-id="5c38d-164">예측 컨트롤러 만들기</span><span class="sxs-lookup"><span data-stu-id="5c38d-164">Create Predict Controller</span></span>

<span data-ttu-id="5c38d-165">들어오는 HTTP 요청을 처리하려면 컨트롤러를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c38d-165">To process your incoming HTTP requests, you need to create a controller.</span></span>

1. <span data-ttu-id="5c38d-166">솔루션 탐색기에서 *Controllers* 디렉터리를 마우스 오른쪽 단추로 클릭하고 **추가 > 컨트롤러**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5c38d-166">In Solution Explorer, right-click the *Controllers* directory, and then select **Add > Controller**.</span></span>
1. <span data-ttu-id="5c38d-167">**새 항목 추가** 대화 상자에서 **API 컨트롤러 비어 있음**을 선택하고 **추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5c38d-167">In the **Add New Item** dialog box, select **API Controller Empty** and select **Add**.</span></span>
1. <span data-ttu-id="5c38d-168">프롬프트에서 **컨트롤러 이름** 필드를 *PredictController.cs*로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="5c38d-168">In the prompt change the **Controller Name** field to *PredictController.cs*.</span></span> <span data-ttu-id="5c38d-169">그런 다음, [추가] 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5c38d-169">Then, select the Add button.</span></span> <span data-ttu-id="5c38d-170">*PredictController.cs* 파일이 코드 편집기에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="5c38d-170">The *PredictController.cs* file opens in the code editor.</span></span> <span data-ttu-id="5c38d-171">다음 using 문을 *PredictController.cs*의 맨 위에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5c38d-171">Add the following using statement to the top of *PredictController.cs*:</span></span>

```csharp
using System;
using Microsoft.AspNetCore.Mvc;
using SentimentAnalysisWebAPI.DataModels;
using Microsoft.ML;
```

<span data-ttu-id="5c38d-172">기존 클래스 정의를 제거하고 다음 코드를 *PredictController.cs* 파일에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5c38d-172">Remove the existing class definition and add the following code to the *PredictController.cs* file:</span></span>

```csharp
public class PredictController : ControllerBase
{
    
    private readonly PredictionEngine<SentimentData,SentimentPrediction> _predictionEngine;

    public PredictController(PredictionEngine<SentimentData, SentimentPrediction> predictionEngine)
    {
        _predictionEngine = predictionEngine; //Define prediction engine
    }

    [HttpPost]
    public ActionResult<string> Post([FromBody]SentimentData input)
    {
        if(!ModelState.IsValid)
        {
            return BadRequest();
        }

        // Make a prediction
        SentimentPrediction prediction = _predictionEngine.Predict(input);

        //If prediction is true then it is toxic. If it is false, the it is not.
        string isToxic = Convert.ToBoolean(prediction.Prediction) ? "Toxic" : "Not Toxic";

        return Ok(isToxic);
    }
    
}
```

<span data-ttu-id="5c38d-173">이렇게 하면 `PredictionEngine`이 종속성 주입을 통해 가져오는 컨트롤러의 생성자에 전달되어 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c38d-173">This is assigning the `PredictionEngine` by passing it to the controller's constructor which you get via dependency injection.</span></span> <span data-ttu-id="5c38d-174">그런 다음, 이 컨트롤러의 POST 메서드에서 `PredictionEngine`은 예측을 생성하고 성공한 경우 결과를 사용자에게 다시 반환하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c38d-174">Then, in the POST method of this controller the `PredictionEngine` is being used to make predictions and return the results back to the user if successful.</span></span>

## <a name="test-web-api-locally"></a><span data-ttu-id="5c38d-175">로컬로 Web API 테스트</span><span class="sxs-lookup"><span data-stu-id="5c38d-175">Test Web API Locally</span></span>

<span data-ttu-id="5c38d-176">이제 모든 것이 설정되면 애플리케이션을 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c38d-176">Once everything is set up, it's time to test the application.</span></span>

1. <span data-ttu-id="5c38d-177">애플리케이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="5c38d-177">Run the application.</span></span>
1. <span data-ttu-id="5c38d-178">PowerShell을 열고 PORT가 애플리케이션이 수신 대기 중인 포트인 경우 다음 코드를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="5c38d-178">Open Powershell and enter the following code where PORT is the port your application is listening on.</span></span>

```powershell
Invoke-RestMethod "https://localhost:<PORT>/api/predict" -Method Post -Body (@{Text="This is a very rude movie"} | ConvertTo-Json) -ContentType "application/json"
```

<span data-ttu-id="5c38d-179">성공하면 출력이 아래 텍스트와 같이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c38d-179">If successful, the output should look similar to the text below:</span></span>

```powershell
Toxic
```

<span data-ttu-id="5c38d-180">지금까지</span><span class="sxs-lookup"><span data-stu-id="5c38d-180">Congratulations!</span></span> <span data-ttu-id="5c38d-181">ASP.NET Core API를 사용하여 인터넷을 통해 예측을 수행하도록 모델을 제공했습니다.</span><span class="sxs-lookup"><span data-stu-id="5c38d-181">You have successfully served your model to make predictions over the internet using an ASP.NET Core API.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5c38d-182">다음 단계</span><span class="sxs-lookup"><span data-stu-id="5c38d-182">Next Steps</span></span>

- [<span data-ttu-id="5c38d-183">Azure에 배포</span><span class="sxs-lookup"><span data-stu-id="5c38d-183">Deploy to Azure</span></span>](/aspnet/core/tutorials/publish-to-azure-webapp-using-vs?view=aspnetcore-2.1#deploy-the-app-to-azure)