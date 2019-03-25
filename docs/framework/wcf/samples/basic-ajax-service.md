---
title: Basic AJAX Service
ms.date: 03/30/2017
ms.assetid: d66d0c91-0109-45a0-a901-f3e4667c2465
ms.openlocfilehash: 2f488ea1784e41c0c8e4bb815397ab81de95e53b
ms.sourcegitcommit: 0069cb3de8eed4e92b2195d29e5769a76111acdd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/16/2019
ms.locfileid: "56332437"
---
# <a name="basic-ajax-service"></a><span data-ttu-id="09b7b-102">Basic AJAX Service</span><span class="sxs-lookup"><span data-stu-id="09b7b-102">Basic AJAX Service</span></span>
<span data-ttu-id="09b7b-103">이 샘플에는 Windows Communication Foundation (WCF)를 사용 하 여 기본 ASP.NET Asynchronous JavaScript and XML (AJAX) 서비스 (웹 브라우저 클라이언트에서 JavaScript 코드를 사용 하 여 액세스할 수 있는 서비스)를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="09b7b-103">This sample demonstrates how to use Windows Communication Foundation (WCF) to create a basic ASP.NET Asynchronous JavaScript and XML (AJAX) service (a service that you can access using JavaScript code from a Web browser client).</span></span> <span data-ttu-id="09b7b-104">이 서비스에서는 HTTP GET 요청에 응답하고 JSON(JavaScript Object Notation) 데이터 형식을 응답에 사용하도록 <xref:System.ServiceModel.Web.WebGetAttribute> 특성이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="09b7b-104">The service uses the <xref:System.ServiceModel.Web.WebGetAttribute> attribute to ensure that the service responds to HTTP GET requests and is configured to use the JavaScript Object Notation (JSON) data format for responses.</span></span>  
  
 <span data-ttu-id="09b7b-105">WCF의 AJAX 지원 ASP.NET AJAX를 통해 사용에 최적화 된는 `ScriptManager` 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="09b7b-105">AJAX support in WCF is optimized for use with ASP.NET AJAX through the `ScriptManager` control.</span></span> <span data-ttu-id="09b7b-106">ASP.NET AJAX와 함께 WCF를 사용 하 여 예제를 참조 합니다 [AJAX 샘플](ajax.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="09b7b-106">For an example of using WCF with ASP.NET AJAX, see the [AJAX Samples](ajax.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="09b7b-107">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09b7b-107">The set-up procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="09b7b-108">다음 코드에서는 서비스가 HTTP GET 요청에 응답하도록 <xref:System.ServiceModel.Web.WebGetAttribute> 특성이 `Add` 작업에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="09b7b-108">In the following code, the <xref:System.ServiceModel.Web.WebGetAttribute> attribute is applied to the `Add` operation to ensure that the service responds to HTTP GET requests.</span></span> <span data-ttu-id="09b7b-109">이 코드에서는 간편하게 GET을 사용합니다. HTTP GET 요청은 모든 웹 브라우저에서 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09b7b-109">The code uses GET for simplicity (you can construct an HTTP GET request from any Web browser).</span></span> <span data-ttu-id="09b7b-110">또한 GET을 사용하여 캐싱을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09b7b-110">You can also use GET to enable caching.</span></span> <span data-ttu-id="09b7b-111">`WebGetAttribute` 특성이 없을 경우 HTTP POST가 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="09b7b-111">HTTP POST is the default in the absence of the `WebGetAttribute` attribute.</span></span>  

```csharp
[ServiceContract(Namespace = "SimpleAjaxService")]
public interface ICalculator
{
    [WebGet]
    double Add(double n1, double n2);
    //Other operations omitted…
}
```

 <span data-ttu-id="09b7b-112">샘플 .svc 파일은 <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> 표준 끝점을 서비스에 추가하는 <xref:System.ServiceModel.Description.WebScriptEndpoint>를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="09b7b-112">The sample .svc file uses <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>, which adds a <xref:System.ServiceModel.Description.WebScriptEndpoint> standard endpoint to the service.</span></span> <span data-ttu-id="09b7b-113">엔드포인트는 .svc 파일을 기준으로 빈 주소에서 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="09b7b-113">The endpoint is configured at an empty address relative to the .svc file.</span></span> <span data-ttu-id="09b7b-114">즉, 서비스 주소가 `http://localhost/ServiceModelSamples/service.svc`, 작업 이름이 아닌 추가 접미사를 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="09b7b-114">This means that the address of the service is `http://localhost/ServiceModelSamples/service.svc`, with no additional suffixes other than the operation name.</span></span>  

```svc
<%@ServiceHost language="C#" Debug="true" Service="Microsoft.Samples.SimpleAjaxService.CalculatorService" Factory="System.ServiceModel.Activation.WebScriptServiceHostFactory" %>
```

 <span data-ttu-id="09b7b-115"><xref:System.ServiceModel.Description.WebScriptEndpoint>는 ASP.NET AJAX 클라이언트 페이지에서 서비스에 액세스할 수 있도록 하기 위해 미리 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="09b7b-115">The <xref:System.ServiceModel.Description.WebScriptEndpoint> is pre-configured to make the service accessible from an ASP.NET AJAX client page.</span></span> <span data-ttu-id="09b7b-116">Web.config의 다음 섹션은 끝점에 대한 추가 구성 변경 작업을 수행하는 데 사용할 수 있으며</span><span class="sxs-lookup"><span data-stu-id="09b7b-116">The following section in Web.config can be used to make additional configuration changes to the endpoint.</span></span> <span data-ttu-id="09b7b-117">추가 변경이 필요하지 않은 경우 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09b7b-117">It can be removed if no extra changes are required.</span></span>  
  
```xml  
<system.serviceModel>  
  <standardEndpoints>  
    <webScriptEndpoint>  
      <!-- Use this element to configure the endpoint -->  
      <standardEndpoint name=""  />  
    </webScriptEndpoint>  
  </standardEndpoints>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="09b7b-118"><xref:System.ServiceModel.Description.WebScriptEndpoint>는 서비스의 기본 데이터 형식을 XML 대신 JSON으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="09b7b-118">The <xref:System.ServiceModel.Description.WebScriptEndpoint> sets the default data format for the service to JSON instead of XML.</span></span> <span data-ttu-id="09b7b-119">서비스를 호출 하려면 `http://localhost/ServiceModelSamples/service.svc/Add?n1=100&n2=200` 후 설치를 완료 하 고이 항목의 뒷부분에 나와 있는 단계를 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="09b7b-119">To invoke the service, navigate to `http://localhost/ServiceModelSamples/service.svc/Add?n1=100&n2=200` after completing the set up and build steps shown later in this topic.</span></span> <span data-ttu-id="09b7b-120">이 테스트 기능은 HTTP GET 요청을 사용해 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="09b7b-120">This testing functionality is enabled by the use of a HTTP GET request.</span></span>  
  
 <span data-ttu-id="09b7b-121">클라이언트 웹 페이지 SimpleAjaxClientPage.aspx에는 사용자가 페이지에 있는 작업 단추 중 하나를 클릭할 때마다 서비스를 호출하는 ASP.NET 코드가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09b7b-121">The client Web page SimpleAjaxClientPage.aspx contains ASP.NET code to invoke the service whenever the user clicks one of the operation buttons on the page.</span></span> <span data-ttu-id="09b7b-122">`ScriptManager` 컨트롤은 서비스에 대한 프록시를 JavaScript를 통해 액세스할 수 있게 만드는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="09b7b-122">The `ScriptManager` control is used to make a proxy to the service accessible through JavaScript.</span></span>  

```aspx-csharp
<asp:ScriptManager ID="ScriptManager" runat="server">  
    <Services>  
        <asp:ServiceReference Path="service.svc" />  
    </Services>  
</asp:ScriptManager>  
```

 <span data-ttu-id="09b7b-123">다음 JavaScript 코드를 사용하여 로컬 프록시가 인스턴스화되고 작업이 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="09b7b-123">The local proxy is instantiated and operations are invoked using the following JavaScript code.</span></span>  

```javascript
// Code for extracting arguments n1 and n2 omitted…  
// Instantiate a service proxy  
var proxy = new SimpleAjaxService.ICalculator();  
// Code for selecting operation omitted…  
proxy.Add(parseFloat(n1), parseFloat(n2), onSuccess, onFail, null);  
```

 <span data-ttu-id="09b7b-124">서비스 호출에 성공할 경우 `onSuccess` 처리기가 호출되고 작업 결과가 텍스트 상자에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="09b7b-124">If the service call succeeds, the code invokes the `onSuccess` handler and the result of the operation is displayed in a text box.</span></span>  

```javascript
function onSuccess(mathResult){  
     document.getElementById("result").value = mathResult;  
}
```

> [!IMPORTANT]
>  <span data-ttu-id="09b7b-125">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09b7b-125">The samples may already be installed on your machine.</span></span> <span data-ttu-id="09b7b-126">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="09b7b-126">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="09b7b-127">이 디렉터리가 없으면로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4 용 Windows WF (Workflow Foundation) 샘플](https://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플.</span><span class="sxs-lookup"><span data-stu-id="09b7b-127">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="09b7b-128">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09b7b-128">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\SimpleAjaxService`  
  
## <a name="see-also"></a><span data-ttu-id="09b7b-129">참고자료</span><span class="sxs-lookup"><span data-stu-id="09b7b-129">See also</span></span>
