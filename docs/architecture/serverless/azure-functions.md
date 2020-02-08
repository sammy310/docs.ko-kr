---
title: Azure Functions - 서버리스 앱
description: Azure Functions는 여러 언어(C#, JavaScript, Java) 및 플랫폼에서 서버리스 기능을 제공하여 이벤트 기반 즉시 크기 조정 코드를 제공합니다.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 8764e6a33f3fdd53e60fa767d0fb584a9c07de7e
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/01/2020
ms.locfileid: "76920973"
---
# <a name="azure-functions"></a>Azure Functions

Azure 함수는 서버리스 컴퓨팅 환경을 제공합니다. 함수는 *트리거*(예: HTTP 엔드포인트 또는 타이머에 대한 액세스)에 의해 호출되며, 코드 블록 또는 비즈니스 논리를 실행합니다. 또한 함수는 저장소 및 큐와 같은 리소스에 연결하는 특수 *바인딩*을 지원합니다.

![Azure Functions 로고](./media/azure-functions-logo.png)

Azure Functions 프레임워크에는 두 가지 버전이 있습니다. 레거시 버전은 전체 .NET Framework를 지원하고 새 런타임은 플랫폼 간 .NET Core 애플리케이션을 지원합니다. C# 이외에 JavaScript, F#, Java 같은 언어를 추가로 사용할 수 있습니다. 포털에서 만든 함수는 풍부한 스크립팅 구문을 제공합니다. 독립 실행형 프로젝트로 만들어진 함수는 전체 플랫폼 지원 및 기능을 사용하여 배포할 수 있습니다.

자세한 내용은 [Azure Functions 팩](https://docs.microsoft.com/azure/azure-functions)을 참조하세요.

## <a name="functions-v1-vs-v2"></a>Functions v1 및 v2

Azure Functions 런타임에는 두 가지 버전이 있습니다. 1.x 및 2.x. 버전 1.x는 GA(일반 공급)입니다. 포털 또는 Windows 컴퓨터에서 .NET 개발을 지원하고 .NET Framework를 사용합니다. 1.x는 C#, JavaScript 및 F#를 지원하며 Python, PHP, TypeScript, Batch, Bash 및 PowerShell에 대한 실험적 지원을 제공합니다.

[버전 2.x도 이제 일반 공급으로 제공됩니다](https://azure.microsoft.com/blog/introducing-azure-functions-2-0/). .NET Core를 활용하고 Windows, macOS 및 Linux 컴퓨터에서 플랫폼 간 개발을 지원합니다. 2.x는 Java에 대한 최고 수준의 지원을 추가했지만 실험적 언어는 아직 직접 지원하지 않습니다. 버전 2.x는 플랫폼에 대한 타사 확장, 독립적인 바인딩 버전 관리, 보다 간소화된 실행 환경을 가능하게 하는 새로운 바인딩 확장성 모델을 사용합니다.

> **1.x는 [바인딩 리디렉션 지원](https://github.com/Azure/azure-functions-host/issues/992)에서 알려진 문제가 있습니다.** 이 문제는 .NET 개발과 관련된 것입니다. 런타임에 포함된 라이브러리와 다른 버전의 라이브러리에 대한 종속성이 있는 프로젝트가 영향을 받습니다. 함수 팀은 이 문제를 해결하기 위해 최선을 다하고 있습니다. 팀은 일반 공급으로 전환하기 전에 2.x의 바인딩 리디렉션을 처리할 예정입니다. 다음은 팀에서 공식적으로 제안한 수정 및 해결 방법입니다. [Azure Functions의 어셈블리 분해능](https://github.com/Azure/azure-functions-host/wiki/Assembly-Resolution-in-Azure-Functions).

자세한 내용은 [1. x 및 2.x 비교](https://docs.microsoft.com/azure/azure-functions/functions-versions)를 참조하세요.

## <a name="programming-language-support"></a>프로그래밍 언어 지원

GA(일반 공급), 미리 보기 또는 실험적으로 지원되는 언어는 다음과 같습니다.

|언어      |1.x         |2.x      |
|--------------|------------|---------|
|**C#**        |GA          |미리 보기  |
|**JavaScript**|GA          |미리 보기  |
|**F#**        |GA          |         |
|**Java**      |            |미리 보기  |
|**Python**    |실험적|         |
|**PHP**       |실험적|         |
|**TypeScript**|실험적|         |
|**Batch**     |실험적|         |
|**Bash**      |실험적|         |
|**PowerShell**|실험적|         |

자세한 내용은 [지원되는 언어](https://docs.microsoft.com/azure/azure-functions/supported-languages)를 참조하세요.

## <a name="app-service-plans"></a>App Service 계획

함수는 *App Service 계획*으로 지원됩니다. 계획은 함수 앱에서 사용하는 리소스를 정의합니다. 지역에 계획을 할당하고, 사용되는 가상 머신의 크기 및 수를 결정하고, 가격 책정 계층을 선택할 수 있습니다. 진정한 서버리스 접근 방식을 위해 함수 앱에서 **사용** 계획을 사용할 수 있습니다. 사용 계획은 부하에 따라 자동으로 백 엔드 크기를 조정합니다.

자세한 내용은 [App Service 계획](https://docs.microsoft.com/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview)을 참조하세요.

## <a name="create-your-first-function"></a>첫 번째 기능 만들기

세 가지 일반적인 방법으로 함수 앱을 만들 수 있습니다.

- 포털에서 함수를 스크립팅합니다.
- Azure CLI를 사용하여 필요한 리소스를 만듭니다.
- 즐겨 사용하는 IDE를 사용하여 함수를 로컬에서 빌드하고 Azure에 게시합니다.

포털에서 스크립팅된 함수를 만드는 방법에 대한 자세한 내용은 [Azure Portal에서 첫 번째 함수 만들기](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function)를 참조하세요.

Azure CLI에서 빌드하려면 [Azure CLI를 사용하여 첫 번째 함수 만들기](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function-azure-cli)를 참조하세요.

Visual Studio에서 함수를 만들려면 [Visual Studio를 사용하여 첫 번째 함수 만들기](https://docs.microsoft.com/azure/azure-functions/functions-create-your-first-function-visual-studio)를 참조하세요.

## <a name="understand-triggers-and-bindings"></a>트리거 및 바인딩 이해

함수는 *트리거*에 의해 호출되며 정확히 하나의 함수를 포함할 수 있습니다. 함수를 호출하는 이외에 일부 트리거는 바인딩으로 사용됩니다. 트리거와 함께 여러 바인딩을 정의할 수도 있습니다. *바인딩*은 데이터를 코드에 연결하는 선언적 방법을 제공합니다. 이들은 전달되거나(입력) 데이터를 수신할 수 있습니다(출력). 트리거 및 바인딩을 사용하면 함수를 쉽게 사용할 수 있습니다. 바인딩은 수동으로 데이터베이스 또는 파일 시스템 연결을 만드는 오버헤드를 제거합니다. 바인딩에 필요한 모든 정보는 스크립트의 경우 *functions.json* 파일에 포함되거나 코드에서 특성으로 선언됩니다.

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

트리거 및 바인딩의 전체 목록은 [Azure Functions 트리거 및 바인딩 개념](https://docs.microsoft.com/azure/azure-functions/functions-triggers-bindings)을 참조하세요.

## <a name="proxies"></a>Proxy

프록시는 애플리케이션에 리디렉션 기능을 제공합니다. 프록시는 엔드포인트를 노출하고 해당 엔드포인트를 다른 리소스에 매핑합니다. 프록시를 사용하여 다음을 수행할 수 있습니다.

- 들어오는 요청을 다른 엔드포인트로 다시 라우팅합니다.
- 들어오는 요청을 수정한 후 전달합니다.
- 응답을 수정하거나 제공합니다.

프록시는 다음과 같은 시나리오에 사용됩니다.

- URL을 단순화, 단축 또는 변경
- 여러 백 엔드 서비스에 일관된 API 접두사를 제공
- 개발 중인 엔드포인트에 대한 응답을 모의
- 잘 알려진 엔드포인트에 정적 응답을 제공
- 백 엔드를 이동하거나 마이그레이션하는 동안 API 엔드포인트를 일관되게 유지

프록시는 JSON 정의로 저장됩니다. 예를 들면 다음과 같습니다.

```json
{
  "$schema": "http://json.schemastore.org/proxies",
  "proxies": {
    "Domain Redirect": {
      "matchCondition": {
        "route": "/{shortUrl}"
      },
      "backendUri": "http://%WEBSITE_HOSTNAME%/api/UrlRedirect/{shortUrl}"
    },
    "Root": {
      "matchCondition": {
        "route": "/"
      },
      "responseOverrides": {
        "response.statusCode": "301",
        "response.statusReason": "Moved Permanently",
        "response.headers.location": "https://docs.microsoft.com/"
      }
    }
  }
}
```

`Domain Redirect` 프록시는 약식 경로를 사용하여 더 긴 함수 리소스에 매핑합니다. 변환은 다음과 같습니다.

`https://--shorturl--/123` -> `https://--longurl--.azurewebsites.net/api/UrlRedirect/123`

`Root` 프록시는 루트 URL(`https://--shorturl--/`)로 전송된 모든 항목을 가져와서 설명서 사이트로 리디렉션합니다.

프록시를 사용하는 예제는 다음 동영상에 나와 있습니다. [Azure: Bring your app to the cloud with serverless Azure Functions](https://channel9.msdn.com/events/Connect/2017/E102). 실시간으로 로컬 SQL Server에서 실행되는 ASP.NET Core 애플리케이션이 Azure Cloud로 마이그레이션됩니다. 프록시는 함수를 사용하기 위해 기존Web API 프로젝트를 리팩터링하는 데 도움이 됩니다.

프록시에 대 한 자세한 내용은 [Azure Functions 프록시 사용](https://docs.microsoft.com/azure/azure-functions/functions-proxies)을 참조하세요.

>[!div class="step-by-step"]
>[이전](azure-serverless-platform.md)
>[다음](application-insights.md)
