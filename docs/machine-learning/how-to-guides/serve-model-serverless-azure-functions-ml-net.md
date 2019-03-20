---
title: Azure Functions에 ML.NET 모델 배포
description: Azure Functions를 사용하여 인터넷을 통해 예측하기 위한 ML.NET 감정 분석 기계 학습 모델 제공
ms.date: 03/08/2019
ms.custom: mvc,how-to
ms.openlocfilehash: db29e37660665b02ab93a07b37418f0c4c20a608
ms.sourcegitcommit: 5d9f4b805787f890ca6e0dc7ea30a43018bc9cbb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2019
ms.locfileid: "57788647"
---
# <a name="how-to-use-mlnet-model-in-azure-functions"></a><span data-ttu-id="9e294-103">방법: Azure Functions에서 ML.NET 모델 사용</span><span class="sxs-lookup"><span data-stu-id="9e294-103">How-To: Use ML.NET Model in Azure Functions</span></span>

<span data-ttu-id="9e294-104">이 방법은 Azure Functions와 같은 서버리스 환경에서 인터넷을 통해 미리 빌드된 ML.NET 기계 학습 모델을 사용하여 개별 예측을 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9e294-104">This how-to shows how individual predictions can be made using a pre-built ML.NET machine learning model through the internet in a serverless environment such as Azure Functions.</span></span>

> [!NOTE]
> <span data-ttu-id="9e294-105">이 항목은 현재 미리 보기로 제공되는 ML.NET을 참조하며, 자료는 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e294-105">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="9e294-106">자세한 내용은 [ML.NET 소개](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9e294-106">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="9e294-107">이 방법과 관련 샘플에서는 현재 **ML.NET 버전 0.10**을 사용하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e294-107">This how-to and related sample are currently using **ML.NET version 0.10**.</span></span> <span data-ttu-id="9e294-108">자세한 내용은 [dotnet/machinelearning GitHub 리포지토리](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes)에서 릴리스 정보를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9e294-108">For more information, see the release notes at the [dotnet/machinelearning github repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9e294-109">전제 조건</span><span class="sxs-lookup"><span data-stu-id="9e294-109">Prerequisites</span></span>

- <span data-ttu-id="9e294-110">“.NET Core 플랫폼 간 개발” 워크로드 및 “Azure 개발”이 설치된 [Visual Studio 2017 15.6 이상](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017).</span><span class="sxs-lookup"><span data-stu-id="9e294-110">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload and "Azure development" installed.</span></span> 
- [<span data-ttu-id="9e294-111">Azure Functions 도구</span><span class="sxs-lookup"><span data-stu-id="9e294-111">Azure Functions Tools</span></span>](/azure/azure-functions/functions-develop-vs#check-your-tools-version)
- <span data-ttu-id="9e294-112">PowerShell</span><span class="sxs-lookup"><span data-stu-id="9e294-112">Powershell</span></span>
- <span data-ttu-id="9e294-113">미리 학습된 모델입니다.</span><span class="sxs-lookup"><span data-stu-id="9e294-113">Pre-trained model.</span></span> 
    - <span data-ttu-id="9e294-114">[ML.NET 감정 분석 자습서](../tutorials/sentiment-analysis.md)를 사용하여 고유한 모델을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="9e294-114">Use the [ML.NET Sentiment Analysis tutorial](../tutorials/sentiment-analysis.md) to build your own model.</span></span>
    - <span data-ttu-id="9e294-115">이 [미리 학습된 감정 분석 기계 학습 모델](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="9e294-115">Download this [pre-trained sentiment analysis machine learning model](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)</span></span>

## <a name="create-azure-functions-project"></a><span data-ttu-id="9e294-116">Azure Functions 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="9e294-116">Create Azure Functions Project</span></span>

1. <span data-ttu-id="9e294-117">Visual Studio 2017을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="9e294-117">Open Visual Studio 2017.</span></span> <span data-ttu-id="9e294-118">메뉴 모음에서 **파일** > **새로 만들기** > **프로젝트**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9e294-118">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="9e294-119">**새 프로젝트** 대화 상자에서 **Visual C#** 노드와 **Cloud** 노드를 차례로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9e294-119">In the **New Project** dialog, select the **Visual C#** node followed by the **Cloud** node.</span></span> <span data-ttu-id="9e294-120">그런 다음, **Azure Functions** 프로젝트 템플릿을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9e294-120">Then select the **Azure Functions** project template.</span></span> <span data-ttu-id="9e294-121">**이름** 텍스트 상자에 “SentimentAnalysisFunctionsApp”을 입력한 다음, **확인** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9e294-121">In the **Name** text box, type "SentimentAnalysisFunctionsApp" and then select the **OK** button.</span></span>
1. <span data-ttu-id="9e294-122">**새 프로젝트** 대화 상자에서 프로젝트 옵션 위의 드롭다운을 열고 **Azure Functions v2(.NET Core)** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9e294-122">In the **New Project** dialog, open the dropdown above the project options and select **Azure Functions v2 (.NET Core)**.</span></span> <span data-ttu-id="9e294-123">그런 다음, **HTTP 트리거** 프로젝트를 선택한 후 **확인** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9e294-123">Then, select the **Http trigger** project and then select the **OK** button.</span></span>
1. <span data-ttu-id="9e294-124">프로젝트에서 *MLModels* 디렉터리를 만들어 모델을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="9e294-124">Create a directory named *MLModels* in your project to save your model:</span></span>

    <span data-ttu-id="9e294-125">**솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가** > **새 폴더**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9e294-125">In **Solution Explorer**, right-click on your project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="9e294-126">“MLModels”를 입력하고 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="9e294-126">Type "MLModels" and hit Enter.</span></span>

1. <span data-ttu-id="9e294-127">**Microsoft.ML NuGet 패키지**를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="9e294-127">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="9e294-128">솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **NuGet 패키지 관리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9e294-128">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="9e294-129">“nuget.org”를 패키지 소스로 선택하고, [찾아보기] 탭을 선택하고, **Microsoft.ML**을 검색하고, 목록에서 해당 패키지를 선택하고, **설치** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9e294-129">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="9e294-130">**변경 내용 미리 보기** 대화 상자에서 **확인** 단추를 선택한 다음, 나열된 패키지의 사용 조건에 동의하는 경우 **라이선스 승인** 대화 상자에서 **동의함** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9e294-130">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

## <a name="add-pre-built-model-to-project"></a><span data-ttu-id="9e294-131">프로젝트에 미리 빌드된 모델 추가</span><span class="sxs-lookup"><span data-stu-id="9e294-131">Add Pre-built Model To Project</span></span>

1. <span data-ttu-id="9e294-132">미리 빌드된 모델을 *MLModels* 폴더에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="9e294-132">Copy your pre-built model to the *MLModels* folder.</span></span>
1. <span data-ttu-id="9e294-133">솔루션 탐색기에서 미리 빌드된 모델 파일을 마우스 오른쪽 단추로 클릭하고 **속성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9e294-133">In Solution Explorer, right-click your pre-built model file and select **Properties**.</span></span> <span data-ttu-id="9e294-134">**고급** 아래에서 **출력 디렉터리에 복사** 값을 **변경된 내용만 복사**로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="9e294-134">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

## <a name="create-function-to-analyze-sentiment"></a><span data-ttu-id="9e294-135">감정을 분석하는 함수 만들기</span><span class="sxs-lookup"><span data-stu-id="9e294-135">Create Function to Analyze Sentiment</span></span>

<span data-ttu-id="9e294-136">감정을 예측하는 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9e294-136">Create a class to predict sentiment.</span></span> <span data-ttu-id="9e294-137">새 클래스를 프로젝트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9e294-137">Add a new class to your project:</span></span>

1. <span data-ttu-id="9e294-138">**솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가** > **새 항목**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9e294-138">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="9e294-139">**새 항목 추가** 대화 상자에서 **Azure 함수**를 선택하고 **이름** 필드를 *AnalyzeSentiment.cs*로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="9e294-139">In the **Add New Item** dialog box, select **Azure Function** and change the **Name** field to *AnalyzeSentiment.cs*.</span></span> <span data-ttu-id="9e294-140">그런 다음, **추가** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9e294-140">Then, select the **Add** button.</span></span>

1. <span data-ttu-id="9e294-141">**새 Azure 함수** 대화 상자에서 **HTTP 트리거**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9e294-141">In the **New Azure Function** dialog box, select **Http Trigger**.</span></span> <span data-ttu-id="9e294-142">그런 다음, **확인** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9e294-142">Then, select the **OK** button.</span></span>

    <span data-ttu-id="9e294-143">*AnalyzeSentiment.cs* 파일이 코드 편집기에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="9e294-143">The *AnalyzeSentiment.cs* file opens in the code editor.</span></span> <span data-ttu-id="9e294-144">다음 `using` 문을 *GitHubIssueData.cs*의 맨 위에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9e294-144">Add the following `using` statement to the top of *GitHubIssueData.cs*:</span></span>

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
using Microsoft.ML;
using Microsoft.ML.Core.Data;
using Microsoft.ML.Data;
using MLNETServerless.DataModels;
```

### <a name="create-data-models"></a><span data-ttu-id="9e294-145">데이터 모델 만들기</span><span class="sxs-lookup"><span data-stu-id="9e294-145">Create Data Models</span></span>

<span data-ttu-id="9e294-146">입력 데이터 및 예측에 대한 일부 클래스를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e294-146">You need to create some classes for your input data and predictions.</span></span> <span data-ttu-id="9e294-147">새 클래스를 프로젝트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9e294-147">Add a new class to your project:</span></span>

1. <span data-ttu-id="9e294-148">프로젝트에서 *DataModels* 디렉터리를 만들어 데이터 모델을 저장합니다. 솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가 > 새 폴더**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9e294-148">Create a directory named *DataModels* in your project to save your data models: In Solution Explorer, right-click on your project and select **Add > New Folder**.</span></span> <span data-ttu-id="9e294-149">“DataModels”를 입력하고 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="9e294-149">Type "DataModels" and hit Enter.</span></span>
2. <span data-ttu-id="9e294-150">솔루션 탐색기에서 *DataModels* 디렉터리를 마우스 오른쪽 단추로 클릭하고 **추가 > 새 항목**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9e294-150">In Solution Explorer, right-click the *DataModels* directory, and then select **Add > New Item**.</span></span>
3. <span data-ttu-id="9e294-151">**새 항목 추가** 대화 상자에서 **클래스**를 선택하고 **이름** 필드를 *SentimentData.cs*로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="9e294-151">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentData.cs*.</span></span> <span data-ttu-id="9e294-152">그런 다음, **추가** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9e294-152">Then, select the **Add** button.</span></span> <span data-ttu-id="9e294-153">*SentimentData.cs* 파일이 코드 편집기에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="9e294-153">The *SentimentData.cs* file opens in the code editor.</span></span> <span data-ttu-id="9e294-154">다음 using 문을 *SentimentData.cs*의 맨 위에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9e294-154">Add the following using statement to the top of *SentimentData.cs*:</span></span>

```csharp
using Microsoft.ML.Data;
```

<span data-ttu-id="9e294-155">기존 클래스 정의를 제거하고 다음 코드를 SentimentData.cs 파일에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9e294-155">Remove the existing class definition and add the following code to the SentimentData.cs file:</span></span>

```csharp
public class SentimentData
{
    [LoadColumn(0)]
    public bool Label { get; set; }
    [LoadColumn(1)]
    public string Text { get; set; }
}
```

4. <span data-ttu-id="9e294-156">솔루션 탐색기에서 *DataModels* 디렉터리를 마우스 오른쪽 단추로 클릭하고 **추가 > 새 항목**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9e294-156">In Solution Explorer, right-click the *DataModels* directory, and then select **Add > New Item**.</span></span>
5. <span data-ttu-id="9e294-157">**새 항목 추가** 대화 상자에서 **클래스**를 선택하고 **이름** 필드를 *SentimentPrediction.cs*로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="9e294-157">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentPrediction.cs*.</span></span> <span data-ttu-id="9e294-158">그런 다음, **추가** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9e294-158">Then, select the **Add** button.</span></span> <span data-ttu-id="9e294-159">*SentimentPrediction.cs* 파일이 코드 편집기에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="9e294-159">The *SentimentPrediction.cs* file opens in the code editor.</span></span> <span data-ttu-id="9e294-160">다음 using 문을 *SentimentPrediction.cs*의 맨 위에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9e294-160">Add the following using statement to the top of *SentimentPrediction.cs*:</span></span>

```csharp
using Microsoft.ML.Data;
```

<span data-ttu-id="9e294-161">기존 클래스 정의를 제거하고 다음 코드를 *SentimentPrediction.cs* 파일에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9e294-161">Remove the existing class definition and add the following code to the *SentimentPrediction.cs* file:</span></span>

```csharp
public class SentimentPrediction
{
    [ColumnName("PredictedLabel")]
    public bool Prediction { get; set; }
}
```

### <a name="add-prediction-logic"></a><span data-ttu-id="9e294-162">예측 논리 추가</span><span class="sxs-lookup"><span data-stu-id="9e294-162">Add Prediction Logic</span></span>

<span data-ttu-id="9e294-163">*AnalyzeSentiment* 클래스에서 *Run* 메서드의 기존 구현을 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="9e294-163">Replace the existing implementation of *Run* method in *AnalyzeSentiment* class with the following code:</span></span>

```csharp
    public static async Task<IActionResult> Run(
        [HttpTrigger(AuthorizationLevel.Function,"post", Route = null)] HttpRequest req,
        ILogger log)
    {
        log.LogInformation("C# HTTP trigger function processed a request.");

        //Create Context
        MLContext mlContext = new MLContext();

        //Load Model
        using (var fs = File.OpenRead("MLModels/sentiment_model.zip"))
        {
            model = mlContext.Model.Load(fs);
        }

        //Parse HTTP Request Body
        string requestBody = await new StreamReader(req.Body).ReadToEndAsync();
        SentimentData data = JsonConvert.DeserializeObject<SentimentData>(requestBody);

        //Create Prediction Engine
        PredictionEngine<SentimentData, SentimentPrediction> predictionEngine = model.CreatePredictionEngine<SentimentData, SentimentPrediction>(mlContext);

        //Make Prediction
        SentimentPrediction prediction = predictionEngine.Predict(data);

        //Convert prediction to string
        string isToxic = Convert.ToBoolean(prediction.Prediction) ? "Toxic" : "Not Toxic";

        //Return Prediction
        return (ActionResult)new OkObjectResult(isToxic);
    }
}
```

## <a name="test-locally"></a><span data-ttu-id="9e294-164">로컬로 테스트</span><span class="sxs-lookup"><span data-stu-id="9e294-164">Test Locally</span></span>

<span data-ttu-id="9e294-165">이제 모든 것이 설정되었으므로 애플리케이션을 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e294-165">Now that everything is set up, it's time to test the application:</span></span>

1. <span data-ttu-id="9e294-166">애플리케이션 실행</span><span class="sxs-lookup"><span data-stu-id="9e294-166">Run the application</span></span>
1. <span data-ttu-id="9e294-167">PowerShell을 열고 PORT가 애플리케이션을 실행 중인 포트인 경우 프롬프트에 코드를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9e294-167">Open PowerShell and enter the code into the prompt where PORT is the port your application is running on.</span></span> <span data-ttu-id="9e294-168">일반적으로 포트는 7071입니다.</span><span class="sxs-lookup"><span data-stu-id="9e294-168">Typically the port is 7071.</span></span> 

```powershell
Invoke-RestMethod "http://localhost:<PORT>/api/AnalyzeSentiment" -Method Post -Body (@{Text="This is a very rude movie"} | ConvertTo-Json) -ContentType "application/json"
```

<span data-ttu-id="9e294-169">성공하면 출력이 아래 텍스트와 같이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e294-169">If successful, the output should look similar to the text below:</span></span>

```powershell
Toxic
```

<span data-ttu-id="9e294-170">지금까지</span><span class="sxs-lookup"><span data-stu-id="9e294-170">Congratulations!</span></span> <span data-ttu-id="9e294-171">Azure 함수를 사용하여 인터넷을 통해 예측을 수행하도록 모델을 제공했습니다.</span><span class="sxs-lookup"><span data-stu-id="9e294-171">You have successfully served your model to make predictions over the internet using an Azure Function.</span></span>

## <a name="next-steps"></a><span data-ttu-id="9e294-172">다음 단계</span><span class="sxs-lookup"><span data-stu-id="9e294-172">Next Steps</span></span>

- [<span data-ttu-id="9e294-173">Azure에 배포</span><span class="sxs-lookup"><span data-stu-id="9e294-173">Deploy to Azure</span></span>](/azure/azure-functions/functions-develop-vs#publish-to-azure)