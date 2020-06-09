---
title: AJAX Service Using HTTP POST
ms.date: 03/30/2017
ms.assetid: 1ac80f20-ac1c-4ed1-9850-7e49569ff44e
ms.openlocfilehash: 143585b40a493983b7265971a17224165de6f36d
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84575890"
---
# <a name="ajax-service-using-http-post"></a><span data-ttu-id="cbea2-102">AJAX Service Using HTTP POST</span><span class="sxs-lookup"><span data-stu-id="cbea2-102">AJAX Service Using HTTP POST</span></span>

<span data-ttu-id="cbea2-103">이 샘플에서는 WCF (Windows Communication Foundation)를 사용 하 여 HTTP POST를 사용 하는 AJAX (ASP.NET 비동기 JavaScript and XML) 서비스를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cbea2-103">This sample demonstrates how to use Windows Communication Foundation (WCF) to create an ASP.NET Asynchronous JavaScript and XML (AJAX) service that uses HTTP POST.</span></span> <span data-ttu-id="cbea2-104">AJAX 서비스는 웹 브라우저 클라이언트에서 기본 JavaScript 코드를 사용하여 액세스할 수 있는 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="cbea2-104">An AJAX service is one that you can access by using basic JavaScript code from a Web browser client.</span></span> <span data-ttu-id="cbea2-105">이 샘플은 [기본 AJAX 서비스](basic-ajax-service.md) 샘플을 기반으로 합니다. 두 샘플 간의 유일한 차이점은 HTTP GET 대신 HTTP POST를 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="cbea2-105">This sample builds on the [Basic AJAX Service](basic-ajax-service.md) sample; the only difference between the two samples is the use of HTTP POST instead of HTTP GET.</span></span>

<span data-ttu-id="cbea2-106">WCF (Windows Communication Foundation)의 AJAX 지원은 컨트롤을 통해 ASP.NET AJAX와 함께 사용 하도록 최적화 되어 `ScriptManager` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbea2-106">AJAX support in Windows Communication Foundation (WCF) is optimized for use with ASP.NET AJAX through the `ScriptManager` control.</span></span> <span data-ttu-id="cbea2-107">ASP.NET AJAX에서 WCF를 사용 하는 예제는 [Ajax 샘플](ajax-service-using-http-post.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cbea2-107">For an example of using WCF with ASP.NET AJAX, see the [Ajax Samples](ajax-service-using-http-post.md).</span></span>

> [!NOTE]
> <span data-ttu-id="cbea2-108">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbea2-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

<span data-ttu-id="cbea2-109">다음 샘플의 서비스는 AJAX 특정 코드가 없는 WCF 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="cbea2-109">The service in the following sample is a WCF service with no AJAX-specific code.</span></span>

<span data-ttu-id="cbea2-110">특성을 <xref:System.ServiceModel.Web.WebInvokeAttribute> 작업에 적용 하거나 <xref:System.ServiceModel.Web.WebGetAttribute> 특성을 적용 하지 않으면 기본 HTTP 동사 ("POST")가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cbea2-110">If the <xref:System.ServiceModel.Web.WebInvokeAttribute> attribute is applied on an operation, or the <xref:System.ServiceModel.Web.WebGetAttribute> attribute is not applied, the default HTTP verb ("POST") is used.</span></span> <span data-ttu-id="cbea2-111">POST 요청이 GET 요청보다 구성하기 어렵지만 해당 요청은 캐시되지 않습니다. 캐싱이 적절하지 않은 모든 작업에 POST 요청을 사용하십시오.</span><span class="sxs-lookup"><span data-stu-id="cbea2-111">POST requests are harder to construct than GET requests, but they are not cached; use POST requests for all operations where caching is not appropriate.</span></span>

```csharp
[ServiceContract(Namespace = "PostAjaxService")]
public interface ICalculator
{
    [WebInvoke]
    double Add(double n1, double n2);
    //Other operations omitted…
}
```

<span data-ttu-id="cbea2-112">기본 AJAX 서비스 샘플에서와 마찬가지로, <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>를 사용하여 서비스에 AJAX 엔드포인트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="cbea2-112">Create an AJAX endpoint on the service by using the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>, just as in the Basic AJAX Service sample.</span></span>

<span data-ttu-id="cbea2-113">GET 요청과 달리 브라우저에서 POST 서비스를 호출할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cbea2-113">Unlike GET requests, you cannot invoke POST services from the browser.</span></span> <span data-ttu-id="cbea2-114">예를 들어로 이동 하면 `http://localhost/ServiceModelSamples/service.svc/Add?n1=100&n2=200` POST 서비스에서는 `n1` `n2` URL이 아니라 JSON 형식의 메시지 본문에서 및 매개 변수를 보내기 때문에 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbea2-114">For example, navigating to `http://localhost/ServiceModelSamples/service.svc/Add?n1=100&n2=200` results in an error, because the POST service expects the `n1` and `n2` parameters to be sent in the message body in the JSON format, and not in the URL.</span></span>

<span data-ttu-id="cbea2-115">클라이언트 웹 페이지 PostAjaxClientPage.aspx에는 사용자가 페이지에 있는 작업 단추 중 하나를 클릭할 때마다 서비스를 호출하는 ASP.NET 코드가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbea2-115">The client Web page PostAjaxClientPage.aspx contains ASP.NET code to invoke the service whenever the user clicks one of the operation buttons on the page.</span></span> <span data-ttu-id="cbea2-116">서비스는 GET 요청을 사용 하 여 [기본 AJAX 서비스](basic-ajax-service.md) 샘플과 동일한 방식으로 응답 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbea2-116">The service responds in the same way as in the [Basic AJAX Service](basic-ajax-service.md) sample, with the GET request.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cbea2-117">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbea2-117">The samples may already be installed on your computer.</span></span> <span data-ttu-id="cbea2-118">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="cbea2-118">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="cbea2-119">이 디렉터리가 없는 경우 [.NET Framework 4에 대 한 Windows Communication Foundation (wcf) 및 Windows Workflow Foundation (WF) 샘플](https://www.microsoft.com/download/details.aspx?id=21459) 로 이동 하 여 모든 WINDOWS COMMUNICATION FOUNDATION (wcf) 및 샘플을 다운로드 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbea2-119">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="cbea2-120">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbea2-120">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\PostAjaxService`

## <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="cbea2-121">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="cbea2-121">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="cbea2-122">[Windows Communication Foundation 샘플에 대 한 설치 지침 일회성 설치 절차](one-time-setup-procedure-for-the-wcf-samples.md)를 수행 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbea2-122">Ensure that you perform the setup instructions [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="cbea2-123">[Windows Communication Foundation 샘플 빌드](building-the-samples.md)에 설명 된 대로 postajaxservice.sln 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="cbea2-123">Build the solution PostAjaxService.sln as described in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

3. <span data-ttu-id="cbea2-124">로 이동 `http://localhost/ServiceModelSamples/PostAjaxClientPage.aspx` 합니다 (프로젝트 디렉터리에서 브라우저에서 postajaxclientpage.aspx를 열지 마세요.).</span><span class="sxs-lookup"><span data-stu-id="cbea2-124">Navigate to `http://localhost/ServiceModelSamples/PostAjaxClientPage.aspx` (do not open PostAjaxClientPage.aspx in the browser from the project directory).</span></span>
