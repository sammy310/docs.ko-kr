---
title: ASP.NET Core Web API에서 기계 학습 모델 제공
description: ASP.NET Core Web API를 사용하여 인터넷을 통해 ML.NET 감정 분석 기계 학습 모델 제공
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: 07b751caff8ef0ca9a23bed68ddf88feb7b5ae4f
ms.sourcegitcommit: 69bf8b719d4c289eec7b45336d0b933dd7927841
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57856709"
---
# <a name="how-to-serve-machine-learning-model-through-aspnet-core-web-api"></a>방법: ASP.NET Core Web API를 통해 기계 학습 모델 제공

이 방법은 ASP.NET Core Web API를 사용하여 웹에 미리 빌드된 ML.NET 기계 학습 모델을 제공하는 방법을 보여 줍니다. 이렇게 하면 사용자가 표준 HTTP 메서드를 통해 예측을 위해 API에 액세스할 수 있습니다.

> [!NOTE]
> 이 항목은 현재 미리 보기로 제공되는 ML.NET을 참조하며, 자료는 변경될 수 있습니다. 자세한 내용은 [ML.NET 소개](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet)를 참조하세요.

이 방법과 관련 샘플에서는 현재 **ML.NET 버전 0.10**을 사용하고 있습니다. 자세한 내용은 [dotnet/machinelearning GitHub 리포지토리](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes)에서 릴리스 정보를 참조하세요.

## <a name="prerequisites"></a>전제 조건

- “.NET Core 플랫폼 간 개발” 워크로드가 설치된 [Visual Studio 2017 15.6 이상](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017).
- PowerShell.
- 미리 학습된 모델입니다.
    - [ML.NET 감정 분석 자습서](../tutorials/sentiment-analysis.md)를 사용하여 고유한 모델을 빌드합니다.
    - 이 [미리 학습된 감정 분석 기계 학습 모델](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)을 다운로드합니다.

## <a name="create-aspnet-core-web-api-project"></a>ASP.NET Core Web API 프로젝트 만들기

1. Visual Studio 2017을 엽니다. 메뉴 모음에서 **파일 > 새로 만들기 > 프로젝트**를 선택합니다. [새 프로젝트] 대화 상자에서 **Visual C#** 노드와 **Web** 노드를 차례로 선택합니다. 그런 다음, **ASP.NET Core 웹 애플리케이션** 프로젝트 템플릿을 선택합니다. **이름** 텍스트 상자에 “SentimentAnalysisWebAPI”를 입력한 다음, **확인** 단추를 선택합니다.
1. 다른 유형의 ASP.NET Core 프로젝트를 표시하는 창에서 **API**를 선택하고 **확인** 단추를 선택합니다.
1. 프로젝트에서 *MLModels* 디렉터리를 만들어 미리 빌드된 기계 학습 모델 파일을 저장합니다.

    솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 [추가] > [새 폴더]를 선택합니다. “MLModels”를 입력하고 Enter 키를 누릅니다.

1. **Microsoft.ML NuGet 패키지**를 설치합니다.

    솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **NuGet 패키지 관리**를 선택합니다. “nuget.org”를 패키지 소스로 선택하고, [찾아보기] 탭을 선택하고, **Microsoft.ML**을 검색하고, 목록에서 해당 패키지를 선택하고, [설치] 단추를 선택합니다. **변경 내용 미리 보기** 대화 상자에서 **확인** 단추를 선택한 다음, 나열된 패키지의 사용 조건에 동의하는 경우 [라이선스 승인] 대화 상자에서 **동의함** 단추를 선택합니다.

### <a name="add-model-to-aspnet-core-web-api-project"></a>ASP.NET Core Web API 프로젝트에 모델 추가

1. 미리 빌드된 모델을 *MLModels* 디렉터리에 복사합니다.
1. 솔루션 탐색기에서 모델 zip 파일을 마우스 오른쪽 단추로 클릭하고 [속성]을 선택합니다. [고급] 아래에서 [출력 디렉터리에 복사] 값을 [변경된 내용만 복사]로 변경합니다.

## <a name="build-data-models"></a>데이터 모델 빌드

입력 데이터 및 예측에 대한 일부 클래스를 만들어야 합니다. 새 클래스를 프로젝트에 추가합니다.

1. 프로젝트에서 *DataModels* 디렉터리를 만들어 데이터 모델을 저장합니다.

    솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 [추가] > [새 폴더]를 선택합니다. “DataModels”를 입력하고 **Enter** 키를 누릅니다.

2. 솔루션 탐색기에서 *DataModels* 디렉터리를 마우스 오른쪽 단추로 클릭하고 [추가] > [새 항목]을 선택합니다.
3. **새 항목 추가** 대화 상자에서 **클래스**를 선택하고 **이름** 필드를 *SentimentData.cs*로 변경합니다. 그런 다음, **추가** 단추를 선택합니다. *SentimentData.cs* 파일이 코드 편집기에서 열립니다. 다음 using 문을 *SentimentData.cs*의 맨 위에 추가합니다.

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Threading.Tasks;
using Microsoft.ML.Data;
```

기존 클래스 정의를 제거하고 다음 코드를 **SentimentData.cs** 파일에 추가합니다.

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
5. **새 항목 추가** 대화 상자에서 **클래스**를 선택하고 **이름** 필드를 *SentimentPrediction.cs*로 변경합니다. 그런 다음, [추가] 단추를 선택합니다. *SentimentPrediction.cs* 파일이 코드 편집기에서 열립니다. 다음 using 문을 *SentimentPrediction.cs*의 맨 위에 추가합니다.

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Threading.Tasks;
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

## <a name="create-prediction-service"></a>예측 서비스 만들기

전체 애플리케이션에서 예측 논리를 구성하고 다시 사용하려면 예측 서비스를 만듭니다.

1. 프로젝트에서 *Services* 디렉터리를 만들어 애플리케이션에서 사용할 서비스를 저장합니다.

    솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가 > 새 폴더**를 선택합니다. “Services”를 입력하고 **Enter** 키를 누릅니다.

1. 솔루션 탐색기에서 *Services* 디렉터리를 마우스 오른쪽 단추로 클릭하고 **추가 > 새 항목**을 선택합니다.
1. **새 항목 추가** 대화 상자에서 **클래스**를 선택하고 **이름** 필드를 *PredictionService.cs*로 변경합니다. 그런 다음, **추가** 단추를 선택합니다. *PredictionService.cs* 파일이 코드 편집기에서 열립니다. 다음 using 문을 *PredictionService.cs*의 맨 위에 추가합니다.

```csharp
using System;
using System.IO;
using System.Collections.Generic;
using System.Linq;
using System.Threading.Tasks;
using Microsoft.ML;
using Microsoft.ML.Core.Data;
using SentimentAnalysisWebAPI.DataModels;
```

기존 클래스 정의를 제거하고 다음 코드를 *PredictionService.cs* 파일에 추가합니다.

```csharp
public class PredictionService
{
    private readonly PredictionEngine<SentimentData, SentimentPrediction> _predictionEngine;
    public PredictionService(PredictionEngine<SentimentData,SentimentPrediction> predictionEngine)
    {
        _predictionEngine = predictionEngine;
    }

    public string Predict(SentimentData input)
    {
        // Make a prediction
        SentimentPrediction prediction = _predictionEngine.Predict(input);

        //If prediction is true then it is toxic. If it is false, the it is not.
        string isToxic = Convert.ToBoolean(prediction.Prediction) ? "Toxic" : "Not Toxic";

        return isToxic;

    }
}
```

## <a name="register-predictions-service-for-use-in-application"></a>애플리케이션에서 사용할 예측 서비스 등록

애플리케이션에서 예측 서비스를 사용하려면 필요할 때마다 서비스를 만들어야 합니다. 이 경우 가장 좋은 방법은 ASP.NET Core 종속성 주입을 고려하는 것입니다.

[종속성 주입](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection?view=aspnetcore-2.1)에 대한 자세한 내용은 다음 링크를 참조하세요.

1. *Startup.cs* 클래스를 열고 다음 using 문을 파일 맨 위에 추가합니다.

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
using SentimentAnalysisWebAPI.Services;
```

1. *ConfigureServices* 메서드에 다음 코드 줄을 추가합니다.

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddMvc().SetCompatibilityVersion(CompatibilityVersion.Version_2_1);

    services.AddSingleton<MLContext>();
    services.AddSingleton<PredictionEngine<SentimentData, SentimentPrediction>>((ctx) =>
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
    services.AddSingleton<PredictionService>();
}
```

개략적으로 이 코드는 애플리케이션을 수동으로 초기화하지 않고도 애플리케이션에서 요청할 때 자동으로 개체 및 서비스를 초기화합니다.

## <a name="create-predict-controller"></a>예측 컨트롤러 만들기

들어오는 HTTP 요청을 처리하려면 컨트롤러를 만들어야 합니다.

1. 솔루션 탐색기에서 *Controllers* 디렉터리를 마우스 오른쪽 단추로 클릭하고 **추가 > 컨트롤러**를 선택합니다.
1. **새 항목 추가** 대화 상자에서 **API 컨트롤러 비어 있음**을 선택하고 **추가**를 선택합니다.
1. 프롬프트에서 **컨트롤러 이름** 필드를 *PredictController.cs*로 변경합니다. 그런 다음, [추가] 단추를 선택합니다. *PredictController.cs* 파일이 코드 편집기에서 열립니다. 다음 using 문을 *PredictController.cs*의 맨 위에 추가합니다.

```csharp
using Microsoft.AspNetCore.Mvc;
using SentimentAnalysisWebAPI.DataModels;
using SentimentAnalysisWebAPI.Services;
```

기존 클래스 정의를 제거하고 다음 코드를 *PredictController.cs* 파일에 추가합니다.

```csharp
public class PredictController : ControllerBase
{

    private readonly PredictionService _predictionService;

    public PredictController(PredictionService predictionService)
    {
        _predictionService = predictionService; //Define prediction service
    }

    [HttpPost]
    public ActionResult<string> Post([FromBody]SentimentData input)
    {
        if(!ModelState.IsValid)
        {
            return BadRequest();
        }
        return Ok(_predictionService.Predict(input));
    }

}
```

이렇게 하면 예측 서비스가 종속성 주입을 통해 가져오는 컨트롤러의 생성자에 전달되어 할당됩니다. 그런 다음, 이 컨트롤러의 POST 메서드에서 예측 서비스는 예측을 생성하고 성공한 경우 결과를 사용자에게 다시 반환하는 데 사용됩니다.

## <a name="test-web-api-locally"></a>로컬로 Web API 테스트

이제 모든 것이 설정되면 애플리케이션을 테스트할 수 있습니다.

1. 애플리케이션을 실행합니다.
1. PowerShell을 열고 PORT가 애플리케이션이 수신 대기 중인 포트인 경우 다음 코드를 입력합니다.

```powershell
Invoke-RestMethod "https://localhost:<PORT>/api/predict" -Method Post -Body (@{Text="This is a very rude movie"} | ConvertTo-Json) -ContentType "application/json"
```

성공하면 출력이 아래 텍스트와 같이 표시됩니다.

```powershell
Toxic
```

지금까지 ASP.NET Core API를 사용하여 인터넷을 통해 예측을 수행하도록 모델을 제공했습니다.

## <a name="next-steps"></a>다음 단계

- [Azure에 배포](/aspnet/core/tutorials/publish-to-azure-webapp-using-vs?view=aspnetcore-2.1#deploy-the-app-to-azure)