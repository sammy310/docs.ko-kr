---
title: '방법: 구성을 사용하지 않고 ASP.NET AJAX 엔드포인트 추가'
ms.date: 03/30/2017
ms.assetid: b05c1742-8d0a-4673-9d71-725b18a3008e
ms.openlocfilehash: 9aab53d6457aa7848fd4acea6317a30da352cc98
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84579633"
---
# <a name="how-to-add-an-aspnet-ajax-endpoint-without-using-configuration"></a><span data-ttu-id="92876-102">방법: 구성을 사용하지 않고 ASP.NET AJAX 엔드포인트 추가</span><span class="sxs-lookup"><span data-stu-id="92876-102">How to: Add an ASP.NET AJAX Endpoint Without Using Configuration</span></span>
<span data-ttu-id="92876-103">WCF (Windows Communication Foundation)를 사용 하면 클라이언트 웹 사이트의 JavaScript에서 호출할 수 있는 ASP.NET AJAX 사용 끝점을 노출 하는 서비스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92876-103">Windows Communication Foundation (WCF) allows you to create a service that exposes an ASP.NET AJAX-enabled endpoint that can be called from JavaScript on a client Web site.</span></span> <span data-ttu-id="92876-104">이와 같은 엔드포인트를 만들려면 다른 모든 WCF 엔드포인트에서처럼 구성 파일을 사용하거나 구성 요소가 필요하지 않은 메서드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92876-104">To create such an endpoint, you can either use a configuration file, as with all other WCF endpoints, or use a method that does not require any configuration elements.</span></span> <span data-ttu-id="92876-105">이 항목에서는 두 번째 접근 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="92876-105">This topic demonstrates the second approach.</span></span>  
  
 <span data-ttu-id="92876-106">구성 없이 ASP.NET AJAX 엔드포인트를 사용하여 서비스를 만들려면 서비스는 IIS(인터넷 정보 서비스)에 의해 호스팅되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="92876-106">To create services with ASP.NET AJAX endpoints without configuration, the services must be hosted by Internet Information Services (IIS).</span></span> <span data-ttu-id="92876-107">이 접근 방식을 사용 하 여 ASP.NET AJAX 끝점을 활성화 하려면 <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> .svc 파일의 [ \@ ServiceHost](../../configure-apps/file-schema/wcf-directive/servicehost.md) 지시문에서를 팩터리 매개 변수로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="92876-107">To activate an ASP.NET AJAX endpoint using this approach, specify the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> as the Factory parameter in the [\@ServiceHost](../../configure-apps/file-schema/wcf-directive/servicehost.md) directive in the .svc file.</span></span> <span data-ttu-id="92876-108">이 사용자 지정 팩터리는 클라이언트 웹 사이트의 JavaScript에서 호출할 수 있도록 ASP.NET AJAX 엔드포인트를 자동으로 구성하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="92876-108">This custom factory is the component that automatically configures an ASP.NET AJAX endpoint so that it can be called from JavaScript on a client Web site.</span></span>  
  
 <span data-ttu-id="92876-109">작업 예제는 [구성 없이 AJAX 서비스](../samples/ajax-service-without-configuration.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="92876-109">For a working example, see the [AJAX Service Without Configuration](../samples/ajax-service-without-configuration.md).</span></span>  
  
 <span data-ttu-id="92876-110">구성 요소를 사용 하 여 ASP.NET AJAX 끝점을 구성 하는 방법에 대 한 개요는 [방법: 구성을 사용 하 여 ASP.NET Ajax 끝점 추가](how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="92876-110">For an outline of how to configure an ASP.NET AJAX endpoint using configuration elements, see [How to: Use Configuration to Add an ASP.NET AJAX Endpoint](how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md).</span></span>  
  
### <a name="to-create-a-basic-wcf-service"></a><span data-ttu-id="92876-111">기본 WCF 서비스를 만들려면</span><span class="sxs-lookup"><span data-stu-id="92876-111">To create a basic WCF service</span></span>  
  
1. <span data-ttu-id="92876-112">특성으로 표시 된 인터페이스를 사용 하 여 기본 WCF 서비스 계약을 정의 <xref:System.ServiceModel.ServiceContractAttribute> 합니다.</span><span class="sxs-lookup"><span data-stu-id="92876-112">Define a basic WCF service contract with an interface marked with the <xref:System.ServiceModel.ServiceContractAttribute> attribute.</span></span> <span data-ttu-id="92876-113">각 작업을 <xref:System.ServiceModel.OperationContractAttribute>로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="92876-113">Mark each operation with the <xref:System.ServiceModel.OperationContractAttribute>.</span></span> <span data-ttu-id="92876-114"><xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A> 속성을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="92876-114">Be sure to set the <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A> property.</span></span>  
  
    ```csharp  
    [ServiceContract(Namespace = "MyService")]]  
    public interface ICalculator  
    {  
        [OperationContract]  
        // This operation returns the sum of d1 and d2.  
        double Add(double n1, double n2);  
  
        //Other operations omitted…  
  
    }  
    ```  
  
2. <span data-ttu-id="92876-115">`ICalculator`를 사용하여 `CalculatorService` 서비스 계약을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="92876-115">Implement the `ICalculator` service contract with a `CalculatorService`.</span></span>  
  
    ```csharp  
    public class CalculatorService : ICalculator  
    {  
        public double Add(double n1, double n2)  
        {  
            return n1 + n2;  
        }  
  
    //Other operations omitted…  
    ```  
  
3. <span data-ttu-id="92876-116">네임스페이스 블록에 `ICalculator` 및 `CalculatorService` 구현을 래핑하여 이러한 구현에 대한 네임스페이스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="92876-116">Define a namespace for the `ICalculator` and `CalculatorService` implementations by wrapping them in a namespace block.</span></span>  
  
    ```csharp  
    Namespace Microsoft.Ajax.Samples  
    {  
        //Include the code for ICalculator and Caculator here.  
    }  
    ```  
  
### <a name="to-host-the-service-in-internet-information-services-without-configuration"></a><span data-ttu-id="92876-117">구성 없이 인터넷 정보 서비스에서 서비스를 호스팅하려면</span><span class="sxs-lookup"><span data-stu-id="92876-117">To host the service in Internet Information Services without configuration</span></span>  
  
1. <span data-ttu-id="92876-118">애플리케이션에서 .svc 확장명이 있는 service라는 새 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="92876-118">Create a new file named service with a .svc extension in the application.</span></span> <span data-ttu-id="92876-119">서비스에 대 한 적절 한 [ \@ ServiceHost](../../configure-apps/file-schema/wcf-directive/servicehost.md) 지시문 정보를 추가 하 여이 파일을 편집 합니다.</span><span class="sxs-lookup"><span data-stu-id="92876-119">Edit this file by adding the appropriate [\@ServiceHost](../../configure-apps/file-schema/wcf-directive/servicehost.md) directive information for the service.</span></span> <span data-ttu-id="92876-120"><xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>ASP.NET AJAX 끝점을 자동으로 구성 하기 위해 [ \@ ServiceHost](../../configure-apps/file-schema/wcf-directive/servicehost.md) 지시문에서를 사용 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="92876-120">Specify that the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> is to be used in the [\@ServiceHost](../../configure-apps/file-schema/wcf-directive/servicehost.md) directive to automatically configure an ASP.NET AJAX endpoint.</span></span>  
  
    ```text
    <%@ServiceHost
        language=c#
        Debug="true"
        Service="Microsoft.Ajax.Samples.CalculatorService"  
        Factory=System.ServiceModel.Activation.WebScriptServiceHostFactory  
    %>  
    ```  
  
2. <span data-ttu-id="92876-121">서비스를 빌드하고 클라이언트에서 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="92876-121">Build the service and call it from the client.</span></span> <span data-ttu-id="92876-122">호출하면 IIS(인터넷 정보 서비스)가 해당 서비스를 활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="92876-122">Internet Information Services (IIS) activates the service when called.</span></span> <span data-ttu-id="92876-123">IIS에서 호스트 하는 방법에 대 한 자세한 내용은 [방법: iis에서 WCF 서비스](how-to-host-a-wcf-service-in-iis.md)호스팅을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="92876-123">For more information about hosting in IIS, see [How to: Host a WCF Service in IIS](how-to-host-a-wcf-service-in-iis.md).</span></span>  
  
### <a name="to-call-the-service"></a><span data-ttu-id="92876-124">서비스를 호출하려면</span><span class="sxs-lookup"><span data-stu-id="92876-124">To call the service</span></span>  
  
1. <span data-ttu-id="92876-125">끝점은 .svc 파일을 기준으로 하는 빈 주소에 구성 되어 있으므로 서비스를 사용할 수 있으며, 서비스에 대 한 요청을 전송 하 여 호출할 수 있습니다. \<operation> 예를 들어 작업에 대해 서비스 .svc/Add를 사용할 수 있습니다. `Add`</span><span class="sxs-lookup"><span data-stu-id="92876-125">The endpoint is configured at an empty address relative to the .svc file, so the service is now available and can be invoked by sending requests to service.svc/\<operation> - for example, service.svc/Add for the `Add` operation.</span></span> <span data-ttu-id="92876-126">서비스 URL을 ASP.NET AJAX Script Manager 컨트롤의 스크립트 컬렉션에 입력하여 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92876-126">You can use it by entering the service URL into the Scripts collection of the ASP.NET AJAX Script Manager control.</span></span> <span data-ttu-id="92876-127">예제는 [구성 없이 AJAX 서비스](../samples/ajax-service-without-configuration.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="92876-127">For an example, see the [AJAX Service Without Configuration](../samples/ajax-service-without-configuration.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="92876-128">예제</span><span class="sxs-lookup"><span data-stu-id="92876-128">Example</span></span>  
  
 <span data-ttu-id="92876-129">자동으로 구성된 엔드포인트는 기본 URL을 기준으로 비어 있는 주소에 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="92876-129">The automatically-configured endpoint is created at an empty address relative to the base URL.</span></span> <span data-ttu-id="92876-130">또한 구성 파일을 추가하여 이 접근 방법으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92876-130">A configuration file can also be added and used with this approach.</span></span> <span data-ttu-id="92876-131">구성 파일에 엔드포인트 정의가 포함된 경우 이러한 엔드포인트는 자동으로 구성된 엔드포인트에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="92876-131">If the configuration file contains endpoint definitions, these endpoints are added to the automatically-configured endpoint.</span></span>  
  
 <span data-ttu-id="92876-132">예를 들어, service.svc는 <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>를 사용하고 서비스 디렉터리에는 "soap" 상대 주소에서 <xref:System.ServiceModel.BasicHttpBinding>을 사용하여 동일한 서비스에 대해 엔드포인트를 정의하는 Web.config 파일이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92876-132">For example, service.svc uses the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> and the service directory contains a Web.config file that defines an endpoint for the same service using the <xref:System.ServiceModel.BasicHttpBinding> at the "soap" relative address.</span></span> <span data-ttu-id="92876-133">이 경우 서비스는 두 개의 엔드포인트를 포함합니다. 한 엔드포인트는 ASP.NET AJAX 요청에 응답하는 service.svc에 위치하고 다른 엔드포인트는 SOAP 요청에 응답하는 service.svc/soap에 위치합니다.</span><span class="sxs-lookup"><span data-stu-id="92876-133">In this case, the service contains two endpoints: one at service.svc (which responds to ASP.NET AJAX requests) and another at service.svc/soap (which responds to SOAP requests).</span></span>  
  
 <span data-ttu-id="92876-134">구성 파일이 비어 있는 상대 주소에 엔드포인트를 정의하고 <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>가 사용되는 경우 예외가 throw되어 서비스를 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="92876-134">If the configuration file defines an endpoint at an empty relative address and the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> is used, an exception is thrown and the service fails to start.</span></span>  
  
 <span data-ttu-id="92876-135">구성을 사용하여 자동으로 구성된 엔드포인트에서 설정을 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="92876-135">You cannot use configuration to modify settings on the automatically-configured endpoint.</span></span> <span data-ttu-id="92876-136">판독기 할당량과 같은 설정을 수정해야 하는 경우 .svc 파일에서 <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>를 제거하고 엔드포인트에 대한 구성 항목을 만들어 구성을 사용하지 않는 접근 방법을 사용하지 말아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="92876-136">If any setting (such as a reader quota) must be modified, you must not use the configuration-free approach by removing the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> from the .svc file and creating a configuration entry for the endpoint.</span></span>  
  
 <span data-ttu-id="92876-137">서비스를 사용하려면 ASP.NET 호환 모드가 필요합니다. 예를 들어, <xref:System.Web.HttpContext> 클래스 또는 ASP.NET 인증 메커니즘을 사용하는 경우 이 모드를 사용하도록 설정하려면 구성 파일이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="92876-137">If your service requires ASP.NET Compatibility Mode - for example, if it uses the <xref:System.Web.HttpContext> class or ASP.NET authorization mechanisms - a configuration file is still required to turn on this mode.</span></span> <span data-ttu-id="92876-138">필요한 구성 요소는 [\<serviceHostingEnvironment>](../../configure-apps/file-schema/wcf/servicehostingenvironment.md) 다음과 같이 추가 해야 하는 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="92876-138">The configuration element required is the [\<serviceHostingEnvironment>](../../configure-apps/file-schema/wcf/servicehostingenvironment.md) element, which must be added as follows.</span></span>  
  
 `<system.serviceModel>`  
  
 `<serviceHostingEnvironment aspNetCompatibilityEnabled="true" /> </system.serviceModel>`  
  
 <span data-ttu-id="92876-139">자세한 내용은 [WCF 서비스 및 ASP.NET](wcf-services-and-aspnet.md) 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="92876-139">For more information, see the [WCF Services and ASP.NET](wcf-services-and-aspnet.md) topic.</span></span>  
  
 <span data-ttu-id="92876-140"><xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> 클래스가 <xref:System.ServiceModel.Activation.ServiceHostFactory>의 파생 클래스인 경우</span><span class="sxs-lookup"><span data-stu-id="92876-140">The <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> class is a derived class of <xref:System.ServiceModel.Activation.ServiceHostFactory>.</span></span> <span data-ttu-id="92876-141">서비스 호스트 팩터리 메커니즘에 대 한 자세한 설명은 [ServiceHostFactory을 사용 하 여 호스팅 확장](../extending/extending-hosting-using-servicehostfactory.md) 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="92876-141">For a detailed explanation of the service host factory mechanism, see the [Extending Hosting Using ServiceHostFactory](../extending/extending-hosting-using-servicehostfactory.md) topic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92876-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="92876-142">See also</span></span>

- [<span data-ttu-id="92876-143">ASP.NET AJAX용 WCF 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="92876-143">Creating WCF Services for ASP.NET AJAX</span></span>](creating-wcf-services-for-aspnet-ajax.md)
- [<span data-ttu-id="92876-144">방법: AJAX 사용 ASP.NET 웹 서비스를 WCF로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="92876-144">How to: Migrate AJAX-Enabled ASP.NET Web Services to WCF</span></span>](how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)
