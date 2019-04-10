---
title: '방법: 구성을 사용하여 ASP.NET AJAX 엔드포인트 추가'
ms.date: 03/30/2017
ms.assetid: 7cd0099e-dc3a-47e4-a38c-6e10f997f6ea
ms.openlocfilehash: 26a7b0d3fef67cf9dae0913e22e3cd7ec443c111
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59202978"
---
# <a name="how-to-use-configuration-to-add-an-aspnet-ajax-endpoint"></a><span data-ttu-id="d36dc-102">방법: 구성을 사용하여 ASP.NET AJAX 엔드포인트 추가</span><span class="sxs-lookup"><span data-stu-id="d36dc-102">How to: Use Configuration to Add an ASP.NET AJAX Endpoint</span></span>
<span data-ttu-id="d36dc-103">Windows Communication Foundation (WCF)를 사용 하면 클라이언트 웹 사이트의 JavaScript에서 호출할 수 있는 사용 가능한 ASP.NET AJAX 사용 끝점을 활용 하는 서비스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d36dc-103">Windows Communication Foundation (WCF) allows you to create a service that makes an ASP.NET AJAX-enabled endpoint available that can be called from JavaScript on a client Web site.</span></span> <span data-ttu-id="d36dc-104">이러한 끝점을 만들려면 다른 모든 Windows Communication Foundation (WCF) 끝점에서와 마찬가지로 구성 파일을 사용 하거나 구성 요소가 필요 하지 않은 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d36dc-104">To create such an endpoint, you can either use a configuration file, as with all other Windows Communication Foundation (WCF) endpoints, or use a method that does not require any configuration elements.</span></span> <span data-ttu-id="d36dc-105">이 항목에서는 구성 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d36dc-105">This topic demonstrates the configuration approach.</span></span>  
  
 <span data-ttu-id="d36dc-106">끝점을 사용 하 여 구성의 서비스 끝점이 ASP.NET AJAX 사용 되도록 하는 절차의 일부 구성 합니다 <xref:System.ServiceModel.WebHttpBinding> 추가 하는 [ \<enableWebScript >](../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) 끝점 동작.</span><span class="sxs-lookup"><span data-stu-id="d36dc-106">The part of the procedure that enables the service endpoint to become ASP.NET AJAX-enabled consists of configuring the endpoint to use the <xref:System.ServiceModel.WebHttpBinding> and to add the [\<enableWebScript>](../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) endpoint behavior.</span></span> <span data-ttu-id="d36dc-107">끝점을 구성한 후 구현 및 서비스를 호스트 하는 단계는 WCF 서비스에서 사용 되는 것과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="d36dc-107">After configuring the endpoint, the steps to implement and host the service are similar to those used by any WCF service.</span></span> <span data-ttu-id="d36dc-108">작업 예제를 참조 합니다 [AJAX Service Using HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d36dc-108">For a working example, see the [AJAX Service Using HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md).</span></span>  
  
 <span data-ttu-id="d36dc-109">구성을 사용 하지 않고 ASP.NET AJAX 끝점을 구성 하는 방법에 대 한 자세한 내용은 참조 하세요. [방법: 구성을 사용 하지 않고 ASP.NET AJAX 끝점 추가](../../../../docs/framework/wcf/feature-details/how-to-add-an-aspnet-ajax-endpoint-without-using-configuration.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d36dc-109">For more information about how to configure an ASP.NET AJAX endpoint without using configuration, see [How to: Add an ASP.NET AJAX Endpoint Without Using Configuration](../../../../docs/framework/wcf/feature-details/how-to-add-an-aspnet-ajax-endpoint-without-using-configuration.md).</span></span>  
  
### <a name="to-create-a-basic-wcf-service"></a><span data-ttu-id="d36dc-110">기본 WCF 서비스를 만들려면</span><span class="sxs-lookup"><span data-stu-id="d36dc-110">To create a basic WCF service</span></span>  
  
1.  <span data-ttu-id="d36dc-111">기본 WCF 서비스 계약을 사용 하 여 표시 된 인터페이스를 사용 하 여 정의 된 <xref:System.ServiceModel.ServiceContractAttribute> 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="d36dc-111">Define a basic WCF service contract with an interface marked with the <xref:System.ServiceModel.ServiceContractAttribute> attribute.</span></span> <span data-ttu-id="d36dc-112">각 작업을 <xref:System.ServiceModel.OperationContractAttribute>로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d36dc-112">Mark each operation with the <xref:System.ServiceModel.OperationContractAttribute>.</span></span> <span data-ttu-id="d36dc-113"><xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A> 속성을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d36dc-113">Be sure to set the <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A> property.</span></span>  
  
    ```  
    [ServiceContract(Namespace = "MyService")]  
    public interface ICalculator  
    {  
        [OperationContract]  
         // This operation returns the sum of d1 and d2.  
        double Add(double n1, double n2);  
  
        //Other operations omitted…  
  
    }  
    ```  
  
2.  <span data-ttu-id="d36dc-114">`ICalculator`를 사용하여 `CalculatorService` 서비스 계약을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="d36dc-114">Implement the `ICalculator` service contract with a `CalculatorService`.</span></span>  
  
    ```  
    public class CalculatorService : ICalculator  
    {  
        public double Add(double n1, double n2)  
        {  
            return n1 + n2;  
        }  
  
    //Other operations omitted…  
    ```  
  
3.  <span data-ttu-id="d36dc-115">네임스페이스 블록에 `ICalculator` 및 `CalculatorService` 구현을 래핑하여 이러한 구현에 대한 네임스페이스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d36dc-115">Define a namespace for the `ICalculator` and `CalculatorService` implementations by wrapping them in a namespace block.</span></span>  
  
    ```  
    Namespace Microsoft.Ajax.Samples  
    {  
        //Include the code for ICalculator and Caculator here.  
    }  
    ```  
  
### <a name="to-create-an-aspnet-ajax-endpoint-for-the-service"></a><span data-ttu-id="d36dc-116">서비스에 대한 ASP.NET AJAX 엔드포인트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="d36dc-116">To create an ASP.NET AJAX endpoint for the service</span></span>  
  
1.  <span data-ttu-id="d36dc-117">동작 구성을 만들고 지정 된 [ \<enableWebScript >](../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) 서비스의 ASP.NET AJAX 사용 끝점에 대 한 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="d36dc-117">Create a behavior configuration and specify the [\<enableWebScript>](../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) behavior for ASP.NET AJAX-enabled endpoints of the service.</span></span>  
  
    ```xml  
    <system.serviceModel>  
        <behaviors>  
            <endpointBehaviors>  
                <behavior name="AspNetAjaxBehavior">  
                    <enableWebScript />  
                </behavior>  
            </endpointBehaviors>  
        </behaviors>  
    </system.serviceModel>  
    ```  
  
2.  <span data-ttu-id="d36dc-118">이전 단계에서 정의한 <xref:System.ServiceModel.WebHttpBinding> 및 ASP.NET AJAX 동작을 사용하는 서비스에 대한 엔드포인트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d36dc-118">Create an endpoint for the service that uses the <xref:System.ServiceModel.WebHttpBinding> and the ASP.NET AJAX behavior defined in the previous step.</span></span>  
  
    ```xml  
    <system.serviceModel>  
        <services>  
            <service name="Microsoft.Ajax.Samples.CalculatorService">  
                <endpoint address=""  
                    behaviorConfiguration="AspNetAjaxBehavior"   
                    binding="webHttpBinding"  
                    contract="Microsoft.Ajax.Samples.ICalculator" />  
            </service>  
        </services>  
    </system.serviceModel>   
    ```  
  
### <a name="to-host-the-service-in-iis"></a><span data-ttu-id="d36dc-119">IIS에서 서비스를 호스팅하려면</span><span class="sxs-lookup"><span data-stu-id="d36dc-119">To host the service in IIS</span></span>  
  
1.  <span data-ttu-id="d36dc-120">IIS에서 서비스를 호스팅하려면 응용 프로그램에서 .svc 확장명을 가진 새 파일 서비스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d36dc-120">To host the service in IIS, create a new file named service with a .svc extension in the application.</span></span> <span data-ttu-id="d36dc-121">적절 한 추가 하 여이 파일을 편집 [ \@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) 서비스에 대 한 지시문 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="d36dc-121">Edit this file by adding the appropriate [\@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) directive information for the service.</span></span> <span data-ttu-id="d36dc-122">예를 들어 `CalculatorService` 샘플에 대한 서비스 파일의 내용에는 다음 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d36dc-122">For example, the content in the service file for the `CalculatorService` sample contains the following information.</span></span>  
  
    ```  
    <%@ServiceHost   
    language=c#   
    Debug="true"   
    Service="Microsoft.Ajax.Samples.CalculatorService"  
    %>  
    ```  
  
2.  <span data-ttu-id="d36dc-123">IIS에서 호스트 하는 방법에 대 한 자세한 내용은 참조 하세요. [방법: IIS에서 WCF 서비스 호스팅](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d36dc-123">For more information about hosting in IIS, see [How to: Host a WCF Service in IIS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md).</span></span>  
  
### <a name="to-call-the-service"></a><span data-ttu-id="d36dc-124">서비스를 호출하려면</span><span class="sxs-lookup"><span data-stu-id="d36dc-124">To call the service</span></span>  
  
1.  <span data-ttu-id="d36dc-125">끝점은.svc 파일을 기준으로 빈 주소에 구성를 이제 사용할 수 있으며 service.svc/에 요청을 전송 하 여 호출할 수 있도록\<작업 >-예를 들어에 대 한 경우 service.svc/add `Add` 작업.</span><span class="sxs-lookup"><span data-stu-id="d36dc-125">The endpoint is configured at an empty address relative to the .svc file, so the service is now available and can be invoked by sending requests to service.svc/\<operation> - for example, service.svc/Add for the `Add` operation.</span></span> <span data-ttu-id="d36dc-126">엔드포인트 URL을 ASP.NET AJAX Script Manager 컨트롤의 스크립트 컬렉션에 입력하여 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d36dc-126">You can use it by entering the endpoint URL into the Scripts collection of the ASP.NET AJAX Script Manager control.</span></span> <span data-ttu-id="d36dc-127">예를 들어 참조 된 [AJAX Service Using HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d36dc-127">For an example, see the [AJAX Service Using HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d36dc-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="d36dc-128">See also</span></span>

- [<span data-ttu-id="d36dc-129">ASP.NET AJAX용 WCF 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="d36dc-129">Creating WCF Services for ASP.NET AJAX</span></span>](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md)
- [<span data-ttu-id="d36dc-130">방법: AJAX 사용 ASP.NET 웹 서비스를 WCF로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="d36dc-130">How to: Migrate AJAX-Enabled ASP.NET Web Services to WCF</span></span>](../../../../docs/framework/wcf/feature-details/how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)
