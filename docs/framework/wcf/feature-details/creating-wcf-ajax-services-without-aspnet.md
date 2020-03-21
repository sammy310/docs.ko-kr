---
title: ASP.NET을 사용하지 않고 WCF AJAX 서비스 만들기
ms.date: 03/30/2017
ms.assetid: ba4a7d1b-e277-4978-9f62-37684e6dc934
ms.openlocfilehash: f4d1d093132c501844aacbaa9cf28ecc3cede442
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185234"
---
# <a name="creating-wcf-ajax-services-without-aspnet"></a>ASP.NET을 사용하지 않고 WCF AJAX 서비스 만들기
Windows 통신 재단(WCF) AJAX 서비스는 ASP.NET AJAX없이 모든 자바스크립트 지원 웹 페이지에서 액세스할 수 있습니다. 이 항목에서는 이러한 WCF 서비스를 만드는 방법에 대해 설명합니다.  
  
 ASP.NET AJAX와 함께 WCF를 사용하는 방법에 대한 지침은 [ASP.NET AJAX에 대한 WCF 서비스 만들기를](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md)참조하십시오.  
  
 WCF AJAX 서비스 만들기에는 세 부분으로 구성됩니다.  
  
- 브라우저에서 액세스할 수 있는 AJAX 엔드포인트 만들기  
  
- AJAX 호환 서비스 계약 만들기  
  
- WCF AJAX 서비스 액세스  
  
## <a name="creating-an-ajax-endpoint"></a>AJAX 엔드포인트 만들기  
 WCF 서비스에서 AJAX 지원을 사용하도록 설정하는 가장 기본적인 <xref:System.ServiceModel.Activation.WebServiceHostFactory> 방법은 다음 예제와 같이 서비스와 연결된 .svc 파일에서 사용하는 것입니다.  
  
```text
<%ServiceHost
    language=c#  
    Debug="true"  
    Service="Microsoft.Ajax.Samples.CityService"  
    Factory=System.ServiceModel.Activation.WebServiceHostFactory  
%>  
```  
  
 또는 구성을 사용하여 AJAX 엔드포인트를 추가할 수도 있습니다. 서비스 엔드포인트에서 <xref:System.ServiceModel.WebHttpBinding>을 사용하고 해당 엔드포인트를 다음 코드 조각에 표시된 것처럼 <xref:System.ServiceModel.Description.WebHttpBehavior>로 구성합니다.  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="AjaxBehavior">  
          <webHttp/>  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
    <services>  
      <service name="Microsoft.Ajax.Samples.CityService">  
        <endpoint
          address="ajaxEndpoint"  
          behaviorConfiguration="AjaxBehavior"  
          binding="webHttpBinding"  
          contract="Microsoft.Ajax.Samples.ICityService" />  
      </service>  
    </services>  
  </system.serviceModel>  
</configuration>  
```  
  
 작업 예제는 [JSON 및 XML이 있는 AJAX 서비스를](../../../../docs/framework/wcf/samples/ajax-service-with-json-and-xml-sample.md)참조하십시오.  
  
## <a name="creating-an-ajax-compatible-service-contract"></a>AJAX 호환 서비스 계약 만들기  
 기본적으로 AJAX 엔드포인트를 통해 노출된 서비스 계약은 데이터를 XML 형식으로 반환합니다. 또한 기본적으로 서비스 작업은 다음 예제에서처럼 HTTP POST 요청을 통해 엔드포인트 주소 다음에 작업 이름이 오는 URL에 액세스할 수 있습니다.  
  
```csharp
[OperationContract]  
string[] GetCities(string firstLetters);  
```  
  
 이 작업은 HTTP POST를 `http://serviceaddress/endpointaddress/GetCities` 사용하여 XML 메시지를 반환하고 반환할 수 있습니다.  
  
 전체 웹 프로그래밍 모델을 사용하여 이러한 기본 측면을 사용자 지정할 수 있습니다. 예를 들어 <xref:System.ServiceModel.Web.WebGetAttribute> 또는 <xref:System.ServiceModel.Web.WebInvokeAttribute> 특성을 사용하여 작업이 응답하는 HTTP 동사를 제어하거나 이러한 각 특성의 `UriTemplate` 속성을 사용하여 사용자 지정 URI를 지정할 수 있습니다. 자세한 내용은 [WCF 웹 HTTP 프로그래밍 모델](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md) 항목을 참조하십시오.  
  
 JSON 데이터 형식은 AJAX 서비스에서 주로 사용됩니다. XML 대신 JSON을 반환하는 작업을 만들려면 <xref:System.ServiceModel.Web.WebGetAttribute.ResponseFormat%2A> (또는 <xref:System.ServiceModel.Web.WebInvokeAttribute.ResponseFormat%2A>) 속성을 <xref:System.ServiceModel.Web.WebMessageFormat.Json>으로 설정합니다. [독립 실행형 JSON 직렬화](../../../../docs/framework/wcf/feature-details/stand-alone-json-serialization.md) 항목에서는 기본 제공 .NET 형식 및 데이터 계약 형식이 JSON에 매핑되는 방법을 보여 주었습니다.  
  
 일반적으로 JSON 요청 및 응답은 하나의 항목으로만 구성됩니다. 앞의 `GetCities` 작업의 경우 요청은 다음 문과 유사하고.  
  
```json
"na"  
```  
  
 해당 요청에 대한 응답은 다음 문과 유사합니다.  
  
```json
["Nairobi", "Naples", "Nashville"]  
```  
  
 작업에서 추가 매개 변수를 가져올 경우 요청 스타일은 단일 JSON 개체에서 두 매개 변수를 래핑하기 위해 래핑되어야 합니다. 이 스타일 JSON 메시지의 예는 다음 예제에 나와 있습니다.  
  
```json  
{"firstLetters": "na", "maxNumber": 2}  
```  
  
 다음 계약이 이 메시지를 받습니다.  
  
```csharp
[WebInvoke(BodyStyle=WebMessageBodyStyle.WrappedRequest, ResponseFormat=WebMessageFormat.Json)]  
[OperationContract]  
string[] GetCities(string firstLetters, int maxNumber);  
```  
  
## <a name="accessing-ajax-services"></a>AJAX 서비스 액세스  
 WCF AJAX 엔드포인트는 항상 JSON 및 XML 요청을 모두 수락합니다.  
  
 "응용 프로그램/json"의 콘텐츠 유형이 있는 HTTP POST 요청은 JSON으로 처리되고 XML(예: "텍스트/xml")을 나타내는 콘텐츠 유형의 요청은 XML로 처리됩니다.  
  
 HTTP GET 요청에는 URL 자체의 모든 요청 매개 변수가 포함되어 있습니다.  
  
 엔드포인트에 대한 HTTP 요청을 만드는 방법을 결정하는 것은 사용자의 몫입니다. 또한 사용자는 요청 본문을 형성하는 JSON 생성에 대한 전체 제어 권한을 가집니다. 자바 스크립트에서 요청을 만드는 예는 [JSON 및 XML이있는 AJAX 서비스를](../../../../docs/framework/wcf/samples/ajax-service-with-json-and-xml-sample.md)참조하십시오.
