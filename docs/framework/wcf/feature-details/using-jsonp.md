---
description: JSONP 사용에 대 한 자세한 정보
title: JSONP 사용
ms.date: 03/30/2017
ms.assetid: f386718c-b4ba-4931-a610-40c27a46672a
ms.openlocfilehash: f4d21670cf468328b8579fa8a9cf2c2e06f09337
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99632193"
---
# <a name="using-jsonp"></a><span data-ttu-id="85508-103">JSONP 사용</span><span class="sxs-lookup"><span data-stu-id="85508-103">Using JSONP</span></span>

<span data-ttu-id="85508-104">JSONP(JSON Padding)는 웹 브라우저에서 사이트 간 스크립팅을 지원할 수 있도록 하는 메커니즘입니다.</span><span class="sxs-lookup"><span data-stu-id="85508-104">JSON Padding (JSONP) is a mechanism that enables cross-site scripting support in Web browsers.</span></span> <span data-ttu-id="85508-105">JSONP는 현재 로드된 문서를 가져온 사이트가 아닌 다른 사이트에서 스크립트를 로드하는 웹 브라우저의 기능을 기반으로 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="85508-105">JSONP is designed around the ability of Web browsers to load scripts from a site different from the one the current loaded document was retrieved from.</span></span> <span data-ttu-id="85508-106">이 메커니즘은 다음 예제와 같이 JSON 페이로드를 사용자 정의 콜백 함수 이름으로 채우는 방식으로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="85508-106">The mechanism works by padding the JSON payload with a user-defined callback function name, as shown in the following example.</span></span>

```javascript
callback({"a" = \\"b\\"});
```

<span data-ttu-id="85508-107">위의 예제에서 `{"a" = \\"b\\"}` JSON 페이로드는 `callback` 함수 호출로 래핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="85508-107">In the preceding example the JSON payload, `{"a" = \\"b\\"}`, is wrapped in a function call, `callback`.</span></span> <span data-ttu-id="85508-108">콜백 함수는 현재 웹 페이지에 이미 정의되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85508-108">The callback function must already be defined in the current Web page.</span></span> <span data-ttu-id="85508-109">JSONP 응답의 콘텐츠 형식은 `application/javascript` 입니다.</span><span class="sxs-lookup"><span data-stu-id="85508-109">The content type of a JSONP response is `application/javascript`.</span></span>

<span data-ttu-id="85508-110">JSONP는 자동으로 사용되도록 설정되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="85508-110">JSONP is not automatically enabled.</span></span> <span data-ttu-id="85508-111">JSONP를 사용하도록 설정하려면 다음 예제와 같이 HTTP 표준 엔드포인트(`javascriptCallbackEnabled` 또는 `true`) 중 하나에서 <xref:System.ServiceModel.Description.WebHttpEndpoint> 특성을 <xref:System.ServiceModel.Description.WebScriptEndpoint>로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="85508-111">To enable it, set the `javascriptCallbackEnabled` attribute to `true` on one of the HTTP standard endpoints (<xref:System.ServiceModel.Description.WebHttpEndpoint> or <xref:System.ServiceModel.Description.WebScriptEndpoint>), as shown in the following example.</span></span>

```xml
<system.serviceModel>
  <standardEndpoints>
    <webHttpEndpoint>
      <standardEndpoint name="" javascriptCallbackEnabled="true"/>
    </webHttpEndpoint>
  </standardEndpoints>
</system.serviceModel>
```

<span data-ttu-id="85508-112">콜백 함수 이름은 다음 URL과 같이 callback이라는 쿼리 변수에 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85508-112">The name of the callback function can be specified in a query variable called callback as shown in the following URL.</span></span>

`http://baseaddress/Service/RestService?callback=functionName`

<span data-ttu-id="85508-113">이 서비스는 호출되면 다음과 같은 응답을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="85508-113">When invoked, the service sends a response like the following.</span></span>

```javascript
functionName({"root":"Something"});
```  

<span data-ttu-id="85508-114">또한 다음과 같이 서비스 클래스에 <xref:System.ServiceModel.Web.JavascriptCallbackBehaviorAttribute>를 적용하여 콜백 함수 이름을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85508-114">You can also specify the callback function name by applying the <xref:System.ServiceModel.Web.JavascriptCallbackBehaviorAttribute> to the service class, as shown in the following example.</span></span>

```csharp
[ServiceContract]
[JavascriptCallbackBehavior(ParameterName = "$callback")]
public class Service1
{
    [OperationContract]
    [WebGet(ResponseFormat=WebMessageFormat.Json)]
    public string GetData()
    {
    }
}
```

<span data-ttu-id="85508-115">위에 나온 서비스는 다음을 사용하여 요청됩니다.</span><span class="sxs-lookup"><span data-stu-id="85508-115">For the service shown previously, a request looks like the following.</span></span>

`http://baseaddress/Service/RestService?$callback=anotherFunction`

<span data-ttu-id="85508-116">이 서비스는 호출되면 다음을 사용하여 응답합니다.</span><span class="sxs-lookup"><span data-stu-id="85508-116">When invoked, the service responds with the following.</span></span>

```javascript
anotherFunction ({"root":"Something"});
```

## <a name="http-status-codes"></a><span data-ttu-id="85508-117">HTTP 상태 코드</span><span class="sxs-lookup"><span data-stu-id="85508-117">HTTP Status Codes</span></span>

<span data-ttu-id="85508-118">200 이외의 HTTP 상태 코드가 있는 JSONP 응답에는 다음 예제와 같이 HTTP 상태 코드의 숫자 표현이 있는 두 번째 매개 변수가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="85508-118">JSONP responses with HTTP status codes other than 200 include a second parameter with the numeric representation of the HTTP status code, as shown in the following example.</span></span>

```javascript
anotherFunction ({"root":"Something"}, 201);
```

## <a name="validations"></a><span data-ttu-id="85508-119">유효성 검사</span><span class="sxs-lookup"><span data-stu-id="85508-119">Validations</span></span>

<span data-ttu-id="85508-120">JSONP를 사용하도록 설정한 경우 다음 유효성 검사가 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="85508-120">The following validations are performed when JSONP is enabled:</span></span>

- <span data-ttu-id="85508-121">`javascriptCallback`이 사용되도록 설정되어 있고, 콜백 쿼리 문자열 매개 변수가 요청에 있고, 응답 형식이 JSON으로 설정된 경우 WCF 인프라에서 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="85508-121">The WCF infrastructure throws an exception if `javascriptCallback` is enabled, a callback query-string parameter is present in the request and the response format is set to JSON.</span></span>

- <span data-ttu-id="85508-122">요청에 콜백 쿼리 문자열 매개 변수가 포함되어 있지만 작업이 HTTP GET이 아닌 경우 콜백 매개 변수가 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="85508-122">If the request contains the callback query string parameter but the operation is not an HTTP GET, the callback parameter is ignored.</span></span>

- <span data-ttu-id="85508-123">콜백 이름이 `null`이거나 빈 문자열이면 응답 형식이 JSONP로 지정되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="85508-123">If the callback name is `null` or empty string the response is not formatted as JSONP.</span></span>

## <a name="see-also"></a><span data-ttu-id="85508-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="85508-124">See also</span></span>

- [<span data-ttu-id="85508-125">WCF 웹 HTTP 프로그래밍 모델 개요</span><span class="sxs-lookup"><span data-stu-id="85508-125">WCF Web HTTP Programming Model Overview</span></span>](wcf-web-http-programming-model-overview.md)
