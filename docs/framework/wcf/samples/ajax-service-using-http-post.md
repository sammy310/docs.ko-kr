---
title: AJAX Service Using HTTP POST
ms.date: 03/30/2017
ms.assetid: 1ac80f20-ac1c-4ed1-9850-7e49569ff44e
ms.openlocfilehash: 560739c576965d597010a6885b53c7905aaeb8e7
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74716190"
---
# <a name="ajax-service-using-http-post"></a>AJAX Service Using HTTP POST

이 샘플에서는 WCF (Windows Communication Foundation)를 사용 하 여 HTTP POST를 사용 하는 AJAX (ASP.NET 비동기 JavaScript and XML) 서비스를 만드는 방법을 보여 줍니다. AJAX 서비스는 웹 브라우저 클라이언트에서 기본 JavaScript 코드를 사용하여 액세스할 수 있는 서비스입니다. 이 샘플은 [기본 AJAX 서비스](../../../../docs/framework/wcf/samples/basic-ajax-service.md) 샘플을 기반으로 합니다. 두 샘플 간의 유일한 차이점은 HTTP GET 대신 HTTP POST를 사용 하는 것입니다.

WCF (Windows Communication Foundation)의 AJAX 지원은 `ScriptManager` 컨트롤을 통해 ASP.NET AJAX와 함께 사용 하도록 최적화 되어 있습니다. ASP.NET AJAX에서 WCF를 사용 하는 예제는 [Ajax 샘플](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md)을 참조 하세요.

> [!NOTE]
> 이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.

다음 샘플의 서비스는 AJAX 특정 코드가 없는 WCF 서비스입니다.

작업에 <xref:System.ServiceModel.Web.WebInvokeAttribute> 특성이 적용 되거나 <xref:System.ServiceModel.Web.WebGetAttribute> 특성이 적용 되지 않으면 기본 HTTP 동사 ("POST")가 사용 됩니다. POST 요청이 GET 요청보다 구성하기 어렵지만 해당 요청은 캐시되지 않습니다. 캐싱이 적절하지 않은 모든 작업에 POST 요청을 사용하십시오.

```csharp
[ServiceContract(Namespace = "PostAjaxService")]
public interface ICalculator
{
    [WebInvoke]
    double Add(double n1, double n2);
    //Other operations omitted…
}
```

기본 AJAX 서비스 샘플에서와 마찬가지로, <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>를 사용하여 서비스에 AJAX 엔드포인트를 만듭니다.

GET 요청과 달리 브라우저에서 POST 서비스를 호출할 수는 없습니다. 예를 들어 `http://localhost/ServiceModelSamples/service.svc/Add?n1=100&n2=200`로 이동 하면 오류가 발생 합니다. POST 서비스는 `n1` 및 `n2` 매개 변수를 URL이 아니라 JSON 형식의 메시지 본문으로 보내야 하기 때문입니다.

클라이언트 웹 페이지 PostAjaxClientPage.aspx에는 사용자가 페이지에 있는 작업 단추 중 하나를 클릭할 때마다 서비스를 호출하는 ASP.NET 코드가 포함되어 있습니다. 서비스는 GET 요청을 사용 하 여 [기본 AJAX 서비스](../../../../docs/framework/wcf/samples/basic-ajax-service.md) 샘플과 동일한 방식으로 응답 합니다.

> [!IMPORTANT]
> 컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> 이 디렉터리가 없으면 [.NET Framework 4에 대 한 Windows Communication Foundation (wcf) 및 Windows Workflow Foundation (WF) 샘플](https://www.microsoft.com/download/details.aspx?id=21459) 로 이동 하 여 모든 WINDOWS COMMUNICATION FOUNDATION (wcf) 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 다운로드 합니다. 이 샘플은 다음 디렉터리에 있습니다.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\PostAjaxService`

## <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면

1. [Windows Communication Foundation 샘플에 대 한 설치 지침 일회성 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)를 수행 했는지 확인 합니다.

2. [Windows Communication Foundation 샘플 빌드](../../../../docs/framework/wcf/samples/building-the-samples.md)에 설명 된 대로 postajaxservice.sln 솔루션을 빌드합니다.

3. `http://localhost/ServiceModelSamples/PostAjaxClientPage.aspx`로 이동 합니다 (프로젝트 디렉터리에서 브라우저에서 Postajaxclientpage.aspx를 열지 마세요.).
