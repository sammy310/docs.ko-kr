---
title: AJAX Service Using Complex Types 샘플
ms.date: 03/30/2017
ms.assetid: 88242b99-4811-4cbe-8201-52ddf48fb174
ms.openlocfilehash: 4227446e8844accd06490d8e7cf933da43d875a6
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84575916"
---
# <a name="ajax-service-using-complex-types-sample"></a><span data-ttu-id="8c32d-102">AJAX Service Using Complex Types 샘플</span><span class="sxs-lookup"><span data-stu-id="8c32d-102">AJAX Service Using Complex Types Sample</span></span>

<span data-ttu-id="8c32d-103">이 샘플에서는 WCF (Windows Communication Foundation)를 사용 하 여 복합 형식의 인스턴스를 만들고이를 서비스와 클라이언트 (JSON) JavaScript Object Notation로 전송 하는 AJAX (ASP.NET 비동기 JavaScript and XML) 서비스를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8c32d-103">This sample demonstrates how to use Windows Communication Foundation (WCF) to create an ASP.NET Asynchronous JavaScript and XML (AJAX) service that creates instances of complex types and sends them between service and client as JavaScript Object Notation (JSON).</span></span> <span data-ttu-id="8c32d-104">웹 브라우저 클라이언트에서 JavaScript 코드를 사용하여 AJAX 서비스에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c32d-104">You can access an AJAX service by using JavaScript code from a Web browser client.</span></span> <span data-ttu-id="8c32d-105">이 샘플은 [기본 AJAX 서비스](basic-ajax-service.md) 샘플을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c32d-105">This sample builds on the [Basic AJAX Service](basic-ajax-service.md) sample.</span></span>

<span data-ttu-id="8c32d-106">WCF의 AJAX 지원은 컨트롤을 통해 ASP.NET AJAX와 함께 사용 하도록 최적화 되어 <xref:System.Web.UI.ScriptManager> 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c32d-106">AJAX support in WCF is optimized for use with ASP.NET AJAX through the <xref:System.Web.UI.ScriptManager> control.</span></span> <span data-ttu-id="8c32d-107">ASP.NET AJAX에서 WCF를 사용 하는 예제는 [Ajax 샘플](ajax.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8c32d-107">For an example of using WCF with ASP.NET AJAX, see the [AJAX Samples](ajax.md).</span></span>

> [!NOTE]
> <span data-ttu-id="8c32d-108">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c32d-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

<span data-ttu-id="8c32d-109">다음 샘플의 서비스는 AJAX 특정 코드가 없는 WCF 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="8c32d-109">The service in the following sample is a WCF service with no AJAX-specific code.</span></span> <span data-ttu-id="8c32d-110"><xref:System.ServiceModel.Web.WebGetAttribute> 특성이 적용되지 않으므로 기본 HTTP 동사("POST")가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c32d-110">Because the <xref:System.ServiceModel.Web.WebGetAttribute> attribute is not applied, the default HTTP verb ("POST") is used.</span></span> <span data-ttu-id="8c32d-111">서비스에는 `DoMath`라는 복합 형식을 반환하는 단일 작업인 `MathResult`가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c32d-111">The service has one operation, `DoMath`, which returns a complex type named `MathResult`.</span></span> <span data-ttu-id="8c32d-112">복합 형식은 마찬가지로 AJAX 특정 코드가 없는 표준 데이터 계약 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="8c32d-112">The complex type is a standard data contract type, which also contains no AJAX-specific code.</span></span>

```csharp
[DataContract]
public class MathResult
{
    [DataMember]
    public double sum;
    [DataMember]
    public double difference;
    [DataMember]
    public double product;
    [DataMember]
    public double quotient;
}
```

<span data-ttu-id="8c32d-113">기본 AJAX 서비스 샘플에서와 마찬가지로, <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>를 사용하여 서비스에 AJAX 엔드포인트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8c32d-113">Create an AJAX endpoint on the service by using the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>, just as in the Basic AJAX Service sample.</span></span>

<span data-ttu-id="8c32d-114">클라이언트 웹 페이지 Complextypeclientpage.aspx에는 사용자가 페이지에서 **계산 수행** 단추를 클릭할 때 서비스를 호출 하는 ASP.NET 및 JavaScript 코드가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c32d-114">The client Web page ComplexTypeClientPage.aspx contains ASP.NET and JavaScript code to invoke the service when the user clicks the **Perform calculation** button on the page.</span></span> <span data-ttu-id="8c32d-115">서비스를 호출 하는 코드는 HTTP post 샘플을 [사용 하는 AJAX 서비스](ajax-service-using-http-post.md) 와 유사 하 게 JSON 본문을 생성 하 고 http post를 사용 하 여 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="8c32d-115">The code to invoke the service constructs a JSON body and sends it using HTTP POST, similar to the [AJAX Service Using HTTP POST](ajax-service-using-http-post.md) sample.</span></span>

<span data-ttu-id="8c32d-116">서비스 호출에 성공한 후 결과 JavaScript 개체에서 개별 데이터 멤버(`sum`, `difference`, `product` 및 `quotient`)에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c32d-116">After the service call succeeds, you can access the individual data members (`sum`, `difference`, `product` and `quotient`) on the resulting JavaScript object.</span></span>

```javascript
function onSuccess(mathResult){
     document.getElementById("sum").value = mathResult.sum;
     document.getElementById("difference").value = mathResult.difference;
     document.getElementById("product").value = mathResult.product;
     document.getElementById("quotient").value = mathResult.quotient;
}
```

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="8c32d-117">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="8c32d-117">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="8c32d-118">[Windows Communication Foundation 샘플에 대 한 일회성 설치 절차](one-time-setup-procedure-for-the-wcf-samples.md)를 수행 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c32d-118">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="8c32d-119">[Windows Communication Foundation 샘플 빌드](building-the-samples.md)에 설명 된 대로 ComplexTypeAjaxService 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="8c32d-119">Build the solution ComplexTypeAjaxService.sln as described in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

3. <span data-ttu-id="8c32d-120">로 이동 `http://localhost/ServiceModelSamples/ComplexTypeClientPage.aspx` 합니다 (프로젝트 디렉터리에서 브라우저에서 complextypeclientpage.aspx를 열지 마세요.).</span><span class="sxs-lookup"><span data-stu-id="8c32d-120">Navigate to `http://localhost/ServiceModelSamples/ComplexTypeClientPage.aspx` (do not open ComplexTypeClientPage.aspx in the browser from the project directory).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8c32d-121">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c32d-121">The samples may already be installed on your computer.</span></span> <span data-ttu-id="8c32d-122">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="8c32d-122">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="8c32d-123">이 디렉터리가 없는 경우 [.NET Framework 4에 대 한 Windows Communication Foundation (wcf) 및 Windows Workflow Foundation (WF) 샘플](https://www.microsoft.com/download/details.aspx?id=21459) 로 이동 하 여 모든 WINDOWS COMMUNICATION FOUNDATION (wcf) 및 샘플을 다운로드 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c32d-123">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="8c32d-124">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c32d-124">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\ComplexTypeAjaxService`

## <a name="see-also"></a><span data-ttu-id="8c32d-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8c32d-125">See also</span></span>

- [<span data-ttu-id="8c32d-126">Basic AJAX Service</span><span class="sxs-lookup"><span data-stu-id="8c32d-126">Basic AJAX Service</span></span>](basic-ajax-service.md)
