---
title: Azure Functions - 서버리스 앱
description: Azure Functions는 여러 언어(C#, JavaScript, Java) 및 플랫폼에서 서버리스 기능을 제공하여 이벤트 기반 즉시 크기 조정 코드를 제공합니다.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 04/06/2020
ms.openlocfilehash: 08e1aaecdee753dc25cca0d6356caaafae1ad510
ms.sourcegitcommit: f99115e12a5eb75638abe45072e023a3ce3351ac
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2020
ms.locfileid: "94557118"
---
# <a name="azure-functions"></a>Azure Functions

Azure Functions는 서버리스 컴퓨팅 환경을 제공합니다. 함수는 *트리거*(예: HTTP 엔드포인트 또는 타이머에 대한 액세스)에 의해 호출되며, 코드 블록 또는 비즈니스 논리를 실행합니다. 또한 함수는 저장소 및 큐와 같은 리소스에 연결하는 특수 *바인딩* 을 지원합니다.

![Azure Functions 로고](./media/azure-functions-logo.png)

현재 런타임 버전 3.0은 플랫폼 간 .NET Core 3.1 애플리케이션을 지원합니다. C# 이외에 JavaScript, F#, Java 같은 언어를 추가로 사용할 수 있습니다. 포털에서 만든 함수는 풍부한 스크립팅 구문을 제공합니다. 독립 실행형 프로젝트로 만들어진 함수는 전체 플랫폼 지원 및 기능을 사용하여 배포할 수 있습니다.

자세한 내용은 [Azure Functions 팩](/azure/azure-functions)을 참조하세요.

## <a name="programming-language-support"></a>프로그래밍 언어 지원

다음 언어는 모두 GA(일반 공급)로 지원됩니다.

|언어      |지원되는 런타임|
|--------------|------------------|
|**C#**        |.NET Core 3.1     |
|**JavaScript**|Node 10 및 12      |
|**F#**        |.NET Core 3.1     |
|**Java**      |Java 8            |
|**Python**    |Python 3.6, 3.7 및 3.8|
|**TypeScript**|Node 10 및 12(JavaScript를 통해)|
|**PowerShell**|PowerShell Core 6|

자세한 내용은 [지원되는 언어](/azure/azure-functions/supported-languages)를 참조하세요.

## <a name="app-service-plans"></a>App Service 계획

함수는 *App Service 계획* 으로 지원됩니다. 계획은 함수 앱에서 사용하는 리소스를 정의합니다. 지역에 계획을 할당하고, 사용되는 가상 머신의 크기 및 수를 결정하고, 가격 책정 계층을 선택할 수 있습니다. 진정한 서버리스 접근 방식을 위해 함수 앱에서 **사용** 계획을 사용할 수 있습니다. 사용 계획은 부하에 따라 자동으로 백 엔드 크기를 조정합니다.

함수 앱에 대한 또 하나의 호스팅 옵션은 [프리미엄 플랜](/azure/azure-functions/functions-premium-plan)입니다. 이 플랜은 콜드 부팅을 방지하고 VNet 연결과 같은 고급 기능을 지원하며 프리미엄 하드웨어에서 실행되는 "always on" 인스턴스를 제공합니다.

자세한 내용은 [App Service 계획](/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview)을 참조하세요.

## <a name="create-your-first-function"></a>첫 번째 기능 만들기

세 가지 일반적인 방법으로 함수 앱을 만들 수 있습니다.

- 포털에서 함수를 스크립팅합니다.
- Azure CLI를 사용하여 필요한 리소스를 만듭니다.
- 즐겨 사용하는 IDE를 사용하여 함수를 로컬에서 빌드하고 Azure에 게시합니다.

포털에서 스크립팅된 함수를 만드는 방법에 대한 자세한 내용은 [Azure Portal에서 첫 번째 함수 만들기](/azure/azure-functions/functions-create-first-azure-function)를 참조하세요.

Azure CLI에서 빌드하려면 [Azure CLI를 사용하여 첫 번째 함수 만들기](/azure/azure-functions/functions-create-first-azure-function-azure-cli)를 참조하세요.

Visual Studio에서 함수를 만들려면 [Visual Studio를 사용하여 첫 번째 함수 만들기](/azure/azure-functions/functions-create-your-first-function-visual-studio)를 참조하세요.

## <a name="understand-triggers-and-bindings"></a>트리거 및 바인딩 이해

함수는 *트리거* 에 의해 호출되며 정확히 하나의 함수를 포함할 수 있습니다. 함수를 호출하는 이외에 일부 트리거는 바인딩으로 사용됩니다. 트리거와 함께 여러 바인딩을 정의할 수도 있습니다. *바인딩* 은 데이터를 코드에 연결하는 선언적 방법을 제공합니다. 이들은 전달되거나(입력) 데이터를 수신할 수 있습니다(출력). 트리거 및 바인딩을 사용하면 함수를 쉽게 사용할 수 있습니다. 바인딩은 수동으로 데이터베이스 또는 파일 시스템 연결을 만드는 오버헤드를 제거합니다. 바인딩에 필요한 모든 정보는 스크립트의 경우 *functions.json* 파일에 포함되거나 코드에서 특성으로 선언됩니다.

몇 가지 일반적인 트리거는 다음과 같습니다.

- Blob Storage: 파일 또는 폴더가 업로드되거나 저장소에서 변경될 때 함수를 호출합니다.
- HTTP: REST API처럼 함수를 호출합니다.
- 큐: 큐에 항목이 있을 때 함수를 호출합니다.
- 타이머: 정기적으로 함수를 호출합니다.

바인딩의 예는 다음과 같습니다.

- CosmosDB: 간편하게 데이터베이스에 연결하여 파일을 로드하거나 저장합니다.
- Table Storage: 함수 앱에서 키/값 저장소로 작업합니다.
- Queue Storage: 간편하게 큐에서 항목을 검색하거나 새 항목을 큐에 넣습니다.

다음 에제 *functions.json* 파일에서는 트리거 및 바인딩을 하나씩 정의합니다.

```json
{
  "bindings": [
    {
      "name": "myBlob",
      "type": "blobTrigger",
      "direction": "in",
      "path": "images/{name}",
      "connection": "AzureWebJobsStorage"
    },
    {
      "name": "$return",
      "type": "queue",
      "direction": "out",
      "queueName": "images",
      "connection": "AzureWebJobsStorage"
    }
  ],
  "disabled": false
}
```

이 예제에서 함수는 `images` 컨테이너의 Blob 스토리지에 대한 변경에 의해 트리거됩니다. 파일 정보가 전달되기 때문에 트리거가 바인딩의 역할도 합니다. `images`라는 큐에 정보를 넣는 다른 바인딩이 있습니다.

다음은 함수에 대한 C# 스크립트입니다.

```csharp
public static string Run(Stream myBlob, string name, TraceWriter log)
{
    log.Info($"C# Blob trigger function Processed blob\n Name:{name} \n Size: {myBlob.Length} Bytes");
    return name;
}
```

예제는 수정되었거나 Blob 스토리지에 업로드된 파일의 이름을 사용하고 나중에 처리할 수 있도록 큐에 배치하는 간단한 함수입니다.

트리거 및 바인딩의 전체 목록은 [Azure Functions 트리거 및 바인딩 개념](/azure/azure-functions/functions-triggers-bindings)을 참조하세요.

>[!div class="step-by-step"]
>[이전](azure-serverless-platform.md)
>[다음](application-insights.md)
