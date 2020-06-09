---
title: 구성을 사용하지 않고 AJAX 서비스 만들기
ms.date: 03/30/2017
ms.assetid: e6db7acd-5679-45d4-b98a-8449c6873838
ms.openlocfilehash: ab3731ab6aeb80e0e46228b8bf702b0fe5c6e6e9
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84575903"
---
# <a name="ajax-service-without-configuration"></a>구성을 사용하지 않고 AJAX 서비스 만들기

이 샘플에서는 WCF (Windows Communication Foundation)를 사용 하 여 구성 설정을 사용 하지 않고 기본 ASP.NET AJAX (비동기 JavaScript and XML) 서비스 (웹 브라우저 클라이언트에서 JavaScript 코드를 사용 하 여 액세스할 수 있는 서비스)를 만드는 방법을 보여 줍니다. 이 서비스는 .svc 파일의 특수한 구문을 사용하여 AJAX 엔드포인트를 사용하도록 자동으로 설정합니다.

WCF의 AJAX 지원은 컨트롤을 통해 ASP.NET AJAX와 함께 사용 하도록 최적화 되어 `ScriptManager` 있습니다. ASP.NET AJAX에서 WCF를 사용 하는 예제는 [Ajax 샘플](ajax.md)을 참조 하세요.

> [!NOTE]
> 이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.

 이 샘플은 AJAX Service Using HTTP POST를 기반으로 합니다. [기본 AJAX 서비스](basic-ajax-service.md) 샘플에 설명 된 대로 <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> 는 서비스를 호스트 하는 데 사용 됩니다.

```text
<%ServiceHost
    language=c#
    Debug="true"
    Service="Microsoft.Ajax.Samples.CalculatorService
    Factory="System.ServiceModel.Activation.WebScriptServiceHostFactory"
%>
```

<xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>가 자동으로 <xref:System.ServiceModel.Description.WebScriptEndpoint>를 서비스에 추가합니다. 엔드포인트에 대한 구성 변경이 필요하지 않은 경우 서비스에 대한 Web.config 파일에서 `<system.ServiceModel>` 섹션을 완전히 제거할 수 있습니다. Web.config 파일에는 ConfigFreeClientPage.aspx에 사용되는 몇 가지 ASP.NET 설정이 포함되어 있습니다. 그렇지 않은 경우 전체 Web.config 파일을 제거할 수 있습니다.

> [!IMPORTANT]
> 컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> 이 디렉터리가 없는 경우 [.NET Framework 4에 대 한 Windows Communication Foundation (wcf) 및 Windows Workflow Foundation (WF) 샘플](https://www.microsoft.com/download/details.aspx?id=21459) 로 이동 하 여 모든 WINDOWS COMMUNICATION FOUNDATION (wcf) 및 샘플을 다운로드 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 합니다. 이 샘플은 다음 디렉터리에 있습니다.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\ConfigFreeAjaxService`

#### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면

1. [Windows Communication Foundation 샘플에 대 한 일회성 설치 절차](one-time-setup-procedure-for-the-wcf-samples.md)의 설치 지침을 수행 했는지 확인 합니다.

2. [Windows Communication Foundation 샘플 빌드](building-the-samples.md)에 설명 된 대로 ConfigFreeAjaxService 솔루션을 빌드합니다.

3. `http://localhost/ServiceModelSamples/ConfigFreeClientPage.aspx`(프로젝트 디렉터리 내에서 브라우저에서 configfreeclientpage.aspx을 열지 마십시오.)로 이동 합니다.

> [!NOTE]
> 이 샘플을 실행할 때 IIS의 ServiceModelSamples 폴더에 대해 익명 인증 및 Windows 인증을 동시에 사용하도록 설정되지 않았는지 확인하세요. 두 인증이 동시에 사용하도록 설정되어 있는 경우에는 Windows 인증을 비활성화하세요. 샘플을 실행한 다음 Windows 인증을 사용하도록 설정하고 "iisreset"를 실행합니다.

## <a name="see-also"></a>참고 항목

- [Basic AJAX Service](basic-ajax-service.md)
