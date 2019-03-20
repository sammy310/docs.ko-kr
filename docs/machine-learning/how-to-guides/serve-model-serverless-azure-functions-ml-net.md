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
# <a name="how-to-use-mlnet-model-in-azure-functions"></a>방법: Azure Functions에서 ML.NET 모델 사용

이 방법은 Azure Functions와 같은 서버리스 환경에서 인터넷을 통해 미리 빌드된 ML.NET 기계 학습 모델을 사용하여 개별 예측을 수행하는 방법을 보여 줍니다.

> [!NOTE]
> 이 항목은 현재 미리 보기로 제공되는 ML.NET을 참조하며, 자료는 변경될 수 있습니다. 자세한 내용은 [ML.NET 소개](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet)를 참조하세요.

이 방법과 관련 샘플에서는 현재 **ML.NET 버전 0.10**을 사용하고 있습니다. 자세한 내용은 [dotnet/machinelearning GitHub 리포지토리](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes)에서 릴리스 정보를 참조하세요.

## <a name="prerequisites"></a>전제 조건

- “.NET Core 플랫폼 간 개발” 워크로드 및 “Azure 개발”이 설치된 [Visual Studio 2017 15.6 이상](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017). 
- [Azure Functions 도구](/azure/azure-functions/functions-develop-vs#check-your-tools-version)
- PowerShell
- 미리 학습된 모델입니다. 
    - [ML.NET 감정 분석 자습서](../tutorials/sentiment-analysis.md)를 사용하여 고유한 모델을 빌드합니다.
    - 이 [미리 학습된 감정 분석 기계 학습 모델](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)을 다운로드합니다.

## <a name="create-azure-functions-project"></a>Azure Functions 프로젝트 만들기

1. Visual Studio 2017을 엽니다. 메뉴 모음에서 **파일** > **새로 만들기** > **프로젝트**를 선택합니다. **새 프로젝트** 대화 상자에서 **Visual C#** 노드와 **Cloud** 노드를 차례로 선택합니다. 그런 다음, **Azure Functions** 프로젝트 템플릿을 선택합니다. **이름** 텍스트 상자에 “SentimentAnalysisFunctionsApp”을 입력한 다음, **확인** 단추를 선택합니다.
1. **새 프로젝트** 대화 상자에서 프로젝트 옵션 위의 드롭다운을 열고 **Azure Functions v2(.NET Core)** 를 선택합니다. 그런 다음, **HTTP 트리거** 프로젝트를 선택한 후 **확인** 단추를 선택합니다.
1. 프로젝트에서 *MLModels* 디렉터리를 만들어 모델을 저장합니다.

    **솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가** > **새 폴더**를 선택합니다. “MLModels”를 입력하고 Enter 키를 누릅니다.

1. **Microsoft.ML NuGet 패키지**를 설치합니다.

    솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **NuGet 패키지 관리**를 선택합니다. “nuget.org”를 패키지 소스로 선택하고, [찾아보기] 탭을 선택하고, **Microsoft.ML**을 검색하고, 목록에서 해당 패키지를 선택하고, **설치** 단추를 선택합니다. **변경 내용 미리 보기** 대화 상자에서 **확인** 단추를 선택한 다음, 나열된 패키지의 사용 조건에 동의하는 경우 **라이선스 승인** 대화 상자에서 **동의함** 단추를 선택합니다.

## <a name="add-pre-built-model-to-project"></a>프로젝트에 미리 빌드된 모델 추가

1. 미리 빌드된 모델을 *MLModels* 폴더에 복사합니다.
1. 솔루션 탐색기에서 미리 빌드된 모델 파일을 마우스 오른쪽 단추로 클릭하고 **속성**을 선택합니다. **고급** 아래에서 **출력 디렉터리에 복사** 값을 **변경된 내용만 복사**로 변경합니다.

## <a name="create-function-to-analyze-sentiment"></a>감정을 분석하는 함수 만들기

감정을 예측하는 클래스를 만듭니다. 새 클래스를 프로젝트에 추가합니다.

1. **솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가** > **새 항목**을 선택합니다.

1. **새 항목 추가** 대화 상자에서 **Azure 함수**를 선택하고 **이름** 필드를 *AnalyzeSentiment.cs*로 변경합니다. 그런 다음, **추가** 단추를 선택합니다.

1. **새 Azure 함수** 대화 상자에서 **HTTP 트리거**를 선택합니다. 그런 다음, **확인** 단추를 선택합니다.

    *AnalyzeSentiment.cs* 파일이 코드 편집기에서 열립니다. 다음 `using` 문을 *GitHubIssueData.cs*의 맨 위에 추가합니다.

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

### <a name="create-data-models"></a>데이터 모델 만들기

입력 데이터 및 예측에 대한 일부 클래스를 만들어야 합니다. 새 클래스를 프로젝트에 추가합니다.

1. 프로젝트에서 *DataModels* 디렉터리를 만들어 데이터 모델을 저장합니다. 솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가 > 새 폴더**를 선택합니다. “DataModels”를 입력하고 Enter 키를 누릅니다.
2. 솔루션 탐색기에서 *DataModels* 디렉터리를 마우스 오른쪽 단추로 클릭하고 **추가 > 새 항목**을 선택합니다.
3. **새 항목 추가** 대화 상자에서 **클래스**를 선택하고 **이름** 필드를 *SentimentData.cs*로 변경합니다. 그런 다음, **추가** 단추를 선택합니다. *SentimentData.cs* 파일이 코드 편집기에서 열립니다. 다음 using 문을 *SentimentData.cs*의 맨 위에 추가합니다.

```csharp
using Microsoft.ML.Data;
```

기존 클래스 정의를 제거하고 다음 코드를 SentimentData.cs 파일에 추가합니다.

```csharp
public class SentimentData
{
    [LoadColumn(0)]
    public bool Label { get; set; }
    [LoadColumn(1)]
    public string Text { get; set; }
}
```

4. 솔루션 탐색기에서 *DataModels* 디렉터리를 마우스 오른쪽 단추로 클릭하고 **추가 > 새 항목**을 선택합니다.
5. **새 항목 추가** 대화 상자에서 **클래스**를 선택하고 **이름** 필드를 *SentimentPrediction.cs*로 변경합니다. 그런 다음, **추가** 단추를 선택합니다. *SentimentPrediction.cs* 파일이 코드 편집기에서 열립니다. 다음 using 문을 *SentimentPrediction.cs*의 맨 위에 추가합니다.

```csharp
using Microsoft.ML.Data;
```

기존 클래스 정의를 제거하고 다음 코드를 *SentimentPrediction.cs* 파일에 추가합니다.

```csharp
public class SentimentPrediction
{
    [ColumnName("PredictedLabel")]
    public bool Prediction { get; set; }
}
```

### <a name="add-prediction-logic"></a>예측 논리 추가

*AnalyzeSentiment* 클래스에서 *Run* 메서드의 기존 구현을 다음 코드로 바꿉니다.

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

## <a name="test-locally"></a>로컬로 테스트

이제 모든 것이 설정되었으므로 애플리케이션을 테스트할 수 있습니다.

1. 애플리케이션 실행
1. PowerShell을 열고 PORT가 애플리케이션을 실행 중인 포트인 경우 프롬프트에 코드를 입력합니다. 일반적으로 포트는 7071입니다. 

```powershell
Invoke-RestMethod "http://localhost:<PORT>/api/AnalyzeSentiment" -Method Post -Body (@{Text="This is a very rude movie"} | ConvertTo-Json) -ContentType "application/json"
```

성공하면 출력이 아래 텍스트와 같이 표시됩니다.

```powershell
Toxic
```

지금까지 Azure 함수를 사용하여 인터넷을 통해 예측을 수행하도록 모델을 제공했습니다.

## <a name="next-steps"></a>다음 단계

- [Azure에 배포](/azure/azure-functions/functions-develop-vs#publish-to-azure)