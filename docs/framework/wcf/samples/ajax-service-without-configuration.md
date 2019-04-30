---
title: 구성을 사용하지 않고 AJAX 서비스 만들기
ms.date: 03/30/2017
ms.assetid: e6db7acd-5679-45d4-b98a-8449c6873838
ms.openlocfilehash: f5ebc952fcc6c2ca4c7272a90dc1929d4b4a0eae
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62002822"
---
# <a name="ajax-service-without-configuration"></a><span data-ttu-id="c35ec-102">구성을 사용하지 않고 AJAX 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="c35ec-102">AJAX Service Without Configuration</span></span>
<span data-ttu-id="c35ec-103">이 샘플에서는 구성을 사용 하지 않고 기본 ASP.NET Asynchronous JavaScript and XML (AJAX) 서비스 (웹 브라우저 클라이언트에서 JavaScript 코드를 사용 하 여 액세스할 수 있는 서비스)를 만들려면 Windows Communication Foundation (WCF)를 사용 하는 방법을 보여 줍니다. 설정.</span><span class="sxs-lookup"><span data-stu-id="c35ec-103">This sample demonstrates how to use Windows Communication Foundation (WCF) to create a basic ASP.NET Asynchronous JavaScript and XML (AJAX) service (a service that you can access by using JavaScript code from a Web browser client) without using any configuration settings.</span></span> <span data-ttu-id="c35ec-104">이 서비스는 .svc 파일의 특수한 구문을 사용하여 AJAX 엔드포인트를 사용하도록 자동으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c35ec-104">The service uses special syntax in the .svc file to automatically enable an AJAX endpoint.</span></span>  
  
 <span data-ttu-id="c35ec-105">WCF의 AJAX 지원 ASP.NET AJAX를 통해 사용에 최적화 된는 `ScriptManager` 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="c35ec-105">AJAX support in WCF is optimized for use with ASP.NET AJAX through the `ScriptManager` control.</span></span> <span data-ttu-id="c35ec-106">ASP.NET AJAX와 함께 WCF를 사용 하 여 예제를 참조 합니다 [Ajax 샘플](ajax.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c35ec-106">For an example of using WCF with ASP.NET AJAX, see the [Ajax Samples](ajax.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c35ec-107">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c35ec-107">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="c35ec-108">이 샘플은 AJAX Service Using HTTP POST를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="c35ec-108">This sample builds upon the AJAX Service Using HTTP POST.</span></span> <span data-ttu-id="c35ec-109">에 설명 된 대로 합니다 [기본 AJAX 서비스](../../../../docs/framework/wcf/samples/basic-ajax-service.md) 샘플에서는 <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> 서비스를 호스트 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c35ec-109">As described in the [Basic AJAX Service](../../../../docs/framework/wcf/samples/basic-ajax-service.md) sample, <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> is used to host the service.</span></span>  

```svc
<%ServiceHost  
    language=c#  
    Debug="true"  
    Service="Microsoft.Ajax.Samples.CalculatorService  
    Factory="System.ServiceModel.Activation.WebScriptServiceHostFactory"  
%>  
```

 <span data-ttu-id="c35ec-110"><xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>가 자동으로 <xref:System.ServiceModel.Description.WebScriptEndpoint>를 서비스에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c35ec-110"><xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> automatically adds a <xref:System.ServiceModel.Description.WebScriptEndpoint> to the service.</span></span> <span data-ttu-id="c35ec-111">엔드포인트에 대한 구성 변경이 필요하지 않은 경우 서비스에 대한 Web.config 파일에서 `<system.ServiceModel>` 섹션을 완전히 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c35ec-111">If no configuration changes need to be made to the endpoint, the `<system.ServiceModel>` section can be completely removed from the Web.config file for the service.</span></span> <span data-ttu-id="c35ec-112">Web.config 파일에는 ConfigFreeClientPage.aspx에 사용되는 몇 가지 ASP.NET 설정이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c35ec-112">The Web.config file contains some ASP.NET settings, which are used by ConfigFreeClientPage.aspx.</span></span> <span data-ttu-id="c35ec-113">그렇지 않은 경우 전체 Web.config 파일을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c35ec-113">If that were not the case, the entire Web.config file could be removed.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c35ec-114">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c35ec-114">The samples may already be installed on your computer.</span></span> <span data-ttu-id="c35ec-115">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="c35ec-115">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="c35ec-116">이 디렉터리가 없으면로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4 용 Windows WF (Workflow Foundation) 샘플](https://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플.</span><span class="sxs-lookup"><span data-stu-id="c35ec-116">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="c35ec-117">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c35ec-117">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\ConfigFreeAjaxService`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="c35ec-118">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="c35ec-118">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="c35ec-119">설치 지침을 수행 했는지 확인 [Windows Communication Foundation 샘플에 대 한 일회성 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c35ec-119">Ensure that you perform the setup instructions in [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="c35ec-120">에 설명 된 대로 ConfigFreeAjaxService.sln 솔루션을 빌드합니다 [Building Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c35ec-120">Build the solution ConfigFreeAjaxService.sln as described in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="c35ec-121">이동할 `http://localhost/ServiceModelSamples/ConfigFreeClientPage.aspx` (프로젝트 디렉터리 내에서 브라우저 ConfigFreeClientPage.aspx를 열고 수행).</span><span class="sxs-lookup"><span data-stu-id="c35ec-121">Navigate to `http://localhost/ServiceModelSamples/ConfigFreeClientPage.aspx` (do not open ConfigFreeClientPage.aspx in the browser from within the project directory).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c35ec-122">이 샘플을 실행할 때 IIS의 ServiceModelSamples 폴더에 대해 익명 인증 및 Windows 인증을 동시에 사용하도록 설정되지 않았는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="c35ec-122">When running this sample, please ensure that Anonymous Authentication and Windows Authentication are not enabled simultaneously for the ServiceModelSamples folder in IIS.</span></span> <span data-ttu-id="c35ec-123">두 인증이 동시에 사용하도록 설정되어 있는 경우에는 Windows 인증을 비활성화하세요.</span><span class="sxs-lookup"><span data-stu-id="c35ec-123">If that is the case, please disable Windows Authentication.</span></span> <span data-ttu-id="c35ec-124">샘플을 실행한 다음 Windows 인증을 사용하도록 설정하고 "iisreset"를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c35ec-124">Once you have run the sample, enable Windows Authentication and run "iisreset".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c35ec-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="c35ec-125">See also</span></span>

- [<span data-ttu-id="c35ec-126">기본 AJAX 서비스</span><span class="sxs-lookup"><span data-stu-id="c35ec-126">Basic AJAX Service</span></span>](../../../../docs/framework/wcf/samples/basic-ajax-service.md)
