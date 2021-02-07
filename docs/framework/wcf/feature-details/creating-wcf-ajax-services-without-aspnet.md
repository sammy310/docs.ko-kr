---
description: '자세히 알아보기: ASP.NET 없이 WCF AJAX 서비스 만들기'
title: ASP.NET을 사용하지 않고 WCF AJAX 서비스 만들기
ms.date: 03/30/2017
ms.assetid: ba4a7d1b-e277-4978-9f62-37684e6dc934
ms.openlocfilehash: 98171a67b3dd2f267edf2281396bb0da1858b0b2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99705150"
---
# <a name="creating-wcf-ajax-services-without-aspnet"></a><span data-ttu-id="fb975-103">ASP.NET을 사용하지 않고 WCF AJAX 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="fb975-103">Creating WCF AJAX Services without ASP.NET</span></span>

<span data-ttu-id="fb975-104">ASP.NET AJAX를 요구 하지 않고 모든 JavaScript 사용 웹 페이지에서 WCF (Windows Communication Foundation) AJAX 서비스에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb975-104">Windows Communication Foundation (WCF) AJAX services can be accessed from any JavaScript-enabled Web page, without requiring ASP.NET AJAX.</span></span> <span data-ttu-id="fb975-105">이 항목에서는 이러한 WCF 서비스를 만드는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb975-105">This topic describes how to create such a WCF service.</span></span>  
  
 <span data-ttu-id="fb975-106">ASP.NET AJAX에서 WCF를 사용 하는 방법에 대 한 지침은 [ASP.NET ajax 용 Wcf 서비스 만들기](creating-wcf-services-for-aspnet-ajax.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fb975-106">For instructions on using WCF with ASP.NET AJAX, see [Creating WCF Services for ASP.NET AJAX](creating-wcf-services-for-aspnet-ajax.md).</span></span>  
  
 <span data-ttu-id="fb975-107">WCF AJAX 서비스를 만드는 세 가지 부분이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb975-107">There are three parts to a creating a WCF AJAX service:</span></span>  
  
- <span data-ttu-id="fb975-108">브라우저에서 액세스할 수 있는 AJAX 엔드포인트 만들기</span><span class="sxs-lookup"><span data-stu-id="fb975-108">Creating an AJAX endpoint that can be accessed from the browser.</span></span>  
  
- <span data-ttu-id="fb975-109">AJAX 호환 서비스 계약 만들기</span><span class="sxs-lookup"><span data-stu-id="fb975-109">Creating an AJAX-compatible service contract.</span></span>  
  
- <span data-ttu-id="fb975-110">WCF AJAX 서비스 액세스</span><span class="sxs-lookup"><span data-stu-id="fb975-110">Accessing WCF AJAX services.</span></span>  
  
## <a name="creating-an-ajax-endpoint"></a><span data-ttu-id="fb975-111">AJAX 엔드포인트 만들기</span><span class="sxs-lookup"><span data-stu-id="fb975-111">Creating an AJAX Endpoint</span></span>  

 <span data-ttu-id="fb975-112">WCF 서비스에서 AJAX 지원을 사용 하도록 설정 하는 가장 기본적인 방법은 <xref:System.ServiceModel.Activation.WebServiceHostFactory> 다음 예제와 같이 서비스와 연결 된 .svc 파일에서를 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="fb975-112">The most basic way to enable AJAX support in a WCF service is to use the <xref:System.ServiceModel.Activation.WebServiceHostFactory> in the .svc file associated with the service, as in the following example.</span></span>  
  
```text
<%ServiceHost
    language=c#  
    Debug="true"  
    Service="Microsoft.Ajax.Samples.CityService"  
    Factory=System.ServiceModel.Activation.WebServiceHostFactory  
%>  
```  
  
 <span data-ttu-id="fb975-113">또는 구성을 사용하여 AJAX 엔드포인트를 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb975-113">Alternatively, you can also use configuration to add an AJAX endpoint.</span></span> <span data-ttu-id="fb975-114">서비스 엔드포인트에서 <xref:System.ServiceModel.WebHttpBinding>을 사용하고 해당 엔드포인트를 다음 코드 조각에 표시된 것처럼 <xref:System.ServiceModel.Description.WebHttpBehavior>로 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="fb975-114">Use the <xref:System.ServiceModel.WebHttpBinding> on the service endpoint and configure that endpoint with the <xref:System.ServiceModel.Description.WebHttpBehavior> as shown in the following code snippet.</span></span>  
  
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
  
 <span data-ttu-id="fb975-115">작업 예제는 [JSON 및 XML을 사용 하는 AJAX 서비스](../samples/ajax-service-with-json-and-xml-sample.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fb975-115">For a working example, see the [AJAX Service with JSON and XML](../samples/ajax-service-with-json-and-xml-sample.md).</span></span>  
  
## <a name="creating-an-ajax-compatible-service-contract"></a><span data-ttu-id="fb975-116">AJAX 호환 서비스 계약 만들기</span><span class="sxs-lookup"><span data-stu-id="fb975-116">Creating an AJAX-Compatible Service Contract</span></span>  

 <span data-ttu-id="fb975-117">기본적으로 AJAX 엔드포인트를 통해 노출된 서비스 계약은 데이터를 XML 형식으로 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="fb975-117">By default, service contracts exposed over an AJAX endpoint return data in the XML format.</span></span> <span data-ttu-id="fb975-118">또한 기본적으로 서비스 작업은 다음 예제에서처럼 HTTP POST 요청을 통해 엔드포인트 주소 다음에 작업 이름이 오는 URL에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb975-118">Also, by default service operations are accessible through HTTP POST requests to URLs that include the endpoint address followed by the operation name, as shown in the following example.</span></span>  
  
```csharp
[OperationContract]  
string[] GetCities(string firstLetters);  
```  
  
 <span data-ttu-id="fb975-119">이 작업은에 대 한 HTTP POST를 사용 하 여 액세스할 수 `http://serviceaddress/endpointaddress/GetCities` 있으며 XML 메시지를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb975-119">This operation is accessible using an HTTP POST to `http://serviceaddress/endpointaddress/GetCities` and return an XML message.</span></span>  
  
 <span data-ttu-id="fb975-120">전체 웹 프로그래밍 모델을 사용하여 이러한 기본 측면을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb975-120">You can use the full Web Programming Model to customize these basic aspects.</span></span> <span data-ttu-id="fb975-121">예를 들어 <xref:System.ServiceModel.Web.WebGetAttribute> 또는 <xref:System.ServiceModel.Web.WebInvokeAttribute> 특성을 사용하여 작업이 응답하는 HTTP 동사를 제어하거나 이러한 각 특성의 `UriTemplate` 속성을 사용하여 사용자 지정 URI를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb975-121">For example, you can use the <xref:System.ServiceModel.Web.WebGetAttribute> or <xref:System.ServiceModel.Web.WebInvokeAttribute> attributes to control the HTTP verb to which the operation responds or use the `UriTemplate` property of these respective attributes to specify custom URIs.</span></span> <span data-ttu-id="fb975-122">자세한 내용은 [WCF 웹 HTTP 프로그래밍 모델](wcf-web-http-programming-model.md) 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fb975-122">For more information, see the [WCF Web HTTP Programming Model](wcf-web-http-programming-model.md) topic.</span></span>  
  
 <span data-ttu-id="fb975-123">JSON 데이터 형식은 AJAX 서비스에서 주로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb975-123">The JSON data format is often used in AJAX services.</span></span> <span data-ttu-id="fb975-124">XML 대신 JSON을 반환하는 작업을 만들려면 <xref:System.ServiceModel.Web.WebGetAttribute.ResponseFormat%2A> (또는 <xref:System.ServiceModel.Web.WebInvokeAttribute.ResponseFormat%2A>) 속성을 <xref:System.ServiceModel.Web.WebMessageFormat.Json>으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="fb975-124">To create an operation that returns JSON instead of XML, set the <xref:System.ServiceModel.Web.WebGetAttribute.ResponseFormat%2A> (or the <xref:System.ServiceModel.Web.WebInvokeAttribute.ResponseFormat%2A>) property to <xref:System.ServiceModel.Web.WebMessageFormat.Json>.</span></span> <span data-ttu-id="fb975-125">[독립 실행형 Json Serialization](stand-alone-json-serialization.md) 항목에서는 기본 제공 .net 형식 및 데이터 계약 형식이 JSON에 매핑되는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fb975-125">The [Stand-Alone JSON Serialization](stand-alone-json-serialization.md) topic shows how built-in .NET types and data contract types map to JSON.</span></span>  
  
 <span data-ttu-id="fb975-126">일반적으로 JSON 요청 및 응답은 하나의 항목으로만 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb975-126">Normally, JSON requests and responses consist of just one item.</span></span> <span data-ttu-id="fb975-127">앞의 `GetCities` 작업의 경우 요청은 다음 문과 유사하고.</span><span class="sxs-lookup"><span data-stu-id="fb975-127">For the preceding `GetCities` operation, the request resembles the following statement.</span></span>  
  
```json
"na"  
```  
  
 <span data-ttu-id="fb975-128">해당 요청에 대한 응답은 다음 문과 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="fb975-128">The response to that request resembles the following statement.</span></span>  
  
```json
["Nairobi", "Naples", "Nashville"]  
```  
  
 <span data-ttu-id="fb975-129">작업에서 추가 매개 변수를 가져올 경우 요청 스타일은 단일 JSON 개체에서 두 매개 변수를 래핑하기 위해 래핑되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb975-129">If the operation takes an extra parameter, the request style must be wrapped to wrap both parameters in a single JSON object.</span></span> <span data-ttu-id="fb975-130">이 스타일 JSON 메시지의 예는 다음 예제에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb975-130">An example of this style JSON message is in the following example.</span></span>  
  
```json  
{"firstLetters": "na", "maxNumber": 2}  
```  
  
 <span data-ttu-id="fb975-131">다음 계약이 이 메시지를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="fb975-131">The following contract accepts this message.</span></span>  
  
```csharp
[WebInvoke(BodyStyle=WebMessageBodyStyle.WrappedRequest, ResponseFormat=WebMessageFormat.Json)]  
[OperationContract]  
string[] GetCities(string firstLetters, int maxNumber);  
```  
  
## <a name="accessing-ajax-services"></a><span data-ttu-id="fb975-132">AJAX 서비스 액세스</span><span class="sxs-lookup"><span data-stu-id="fb975-132">Accessing AJAX Services</span></span>  

 <span data-ttu-id="fb975-133">WCF AJAX 끝점은 항상 JSON 및 XML 요청을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb975-133">WCF AJAX endpoints always accept both JSON and XML requests.</span></span>  
  
 <span data-ttu-id="fb975-134">콘텐츠 형식이 "application/json" 인 HTTP POST 요청은 JSON으로 처리 되 고 XML을 나타내는 content-type 형식 (예: "text/XML")이 XML로 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb975-134">HTTP POST requests with a content-type of "application/json" are treated as JSON, and those with content-type that indicate XML (for example, "text/xml") are treated as XML.</span></span>  
  
 <span data-ttu-id="fb975-135">HTTP GET 요청에는 URL 자체의 모든 요청 매개 변수가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb975-135">HTTP GET requests contain all the request parameters in the URL itself.</span></span>  
  
 <span data-ttu-id="fb975-136">엔드포인트에 대한 HTTP 요청을 만드는 방법을 결정하는 것은 사용자의 몫입니다.</span><span class="sxs-lookup"><span data-stu-id="fb975-136">It is up to the user to decide how to create the HTTP request to the endpoint.</span></span> <span data-ttu-id="fb975-137">또한 사용자는 요청 본문을 형성하는 JSON 생성에 대한 전체 제어 권한을 가집니다.</span><span class="sxs-lookup"><span data-stu-id="fb975-137">Also, the user has full control over constructing the JSON that forms the body of the request.</span></span> <span data-ttu-id="fb975-138">JavaScript에서 요청을 만드는 방법에 대 한 예제는 [JSON 및 XML을 사용 하는 AJAX 서비스](../samples/ajax-service-with-json-and-xml-sample.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fb975-138">For an example of creating a request from JavaScript, see the [AJAX Service with JSON and XML](../samples/ajax-service-with-json-and-xml-sample.md).</span></span>
