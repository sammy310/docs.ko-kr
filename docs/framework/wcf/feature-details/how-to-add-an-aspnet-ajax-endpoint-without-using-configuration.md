---
title: '방법: 구성을 사용하지 않고 ASP.NET AJAX 엔드포인트 추가'
ms.date: 03/30/2017
ms.assetid: b05c1742-8d0a-4673-9d71-725b18a3008e
ms.openlocfilehash: 9935e2a7738796fff9a037b09237a6acbf7bf988
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185132"
---
# <a name="how-to-add-an-aspnet-ajax-endpoint-without-using-configuration"></a>방법: 구성을 사용하지 않고 ASP.NET AJAX 엔드포인트 추가
WCF(Windows 통신 재단)를 사용하면 클라이언트 웹 사이트의 JavaScript에서 호출할 수 있는 ASP.NET AJAX 지원 끝점을 노출하는 서비스를 만들 수 있습니다. 이와 같은 엔드포인트를 만들려면 다른 모든 WCF 엔드포인트에서처럼 구성 파일을 사용하거나 구성 요소가 필요하지 않은 메서드를 사용할 수 있습니다. 이 항목에서는 두 번째 접근 방법을 보여 줍니다.  
  
 구성 없이 ASP.NET AJAX 엔드포인트를 사용하여 서비스를 만들려면 서비스는 IIS(인터넷 정보 서비스)에 의해 호스팅되어야 합니다. 이 방법을 사용하여 aJAX ASP.NET 활성화하려면 <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> .svc 파일의 [ \@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) 지시문에서 팩터리 매개 변수로 지정합니다. 이 사용자 지정 팩터리는 클라이언트 웹 사이트의 JavaScript에서 호출할 수 있도록 ASP.NET AJAX 엔드포인트를 자동으로 구성하는 구성 요소입니다.  
  
 작업 예제는 [구성이 없는 AJAX 서비스를](../../../../docs/framework/wcf/samples/ajax-service-without-configuration.md)참조하십시오.  
  
 구성 요소를 사용하여 ASP.NET AJAX 끝점을 구성하는 방법에 대한 개요는 [구성 을 사용하여 aJAX 끝점을 ASP.NET 추가하는 방법 참조.](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md)  
  
### <a name="to-create-a-basic-wcf-service"></a>기본 WCF 서비스를 만들려면  
  
1. 특성이 표시된 인터페이스로 기본 WCF <xref:System.ServiceModel.ServiceContractAttribute> 서비스 계약을 정의합니다. 각 작업을 <xref:System.ServiceModel.OperationContractAttribute>로 표시합니다. <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A> 속성을 설정해야 합니다.  
  
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
  
2. `ICalculator`를 사용하여 `CalculatorService` 서비스 계약을 구현합니다.  
  
    ```csharp  
    public class CalculatorService : ICalculator  
    {  
        public double Add(double n1, double n2)  
        {  
            return n1 + n2;  
        }  
  
    //Other operations omitted…  
    ```  
  
3. 네임스페이스 블록에 `ICalculator` 및 `CalculatorService` 구현을 래핑하여 이러한 구현에 대한 네임스페이스를 정의합니다.  
  
    ```csharp  
    Namespace Microsoft.Ajax.Samples  
    {  
        //Include the code for ICalculator and Caculator here.  
    }  
    ```  
  
### <a name="to-host-the-service-in-internet-information-services-without-configuration"></a>구성 없이 인터넷 정보 서비스에서 서비스를 호스팅하려면  
  
1. 애플리케이션에서 .svc 확장명이 있는 service라는 새 파일을 만듭니다. 서비스에 대한 적절한 [ \@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) 지시문 정보를 추가하여 이 파일을 편집합니다. ServiceHost <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> 지시문에 사용할 수 있도록 지정하여 ASP.NET AJAX 끝점을 자동으로 구성합니다. [ \@](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md)  
  
    ```text
    <%@ServiceHost
        language=c#
        Debug="true"
        Service="Microsoft.Ajax.Samples.CalculatorService"  
        Factory=System.ServiceModel.Activation.WebScriptServiceHostFactory  
    %>  
    ```  
  
2. 서비스를 빌드하고 클라이언트에서 호출합니다. 호출하면 IIS(인터넷 정보 서비스)가 해당 서비스를 활성화합니다. IIS에서의 호스팅에 대한 자세한 내용은 [IIS에서 WCF 서비스를 호스팅하는 방법을](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md)참조하십시오.  
  
### <a name="to-call-the-service"></a>서비스를 호출하려면  
  
1. 끝점은 .svc 파일을 기준으로 빈 주소로 구성되므로 서비스를 사용할 수 있으며 service.svc/작업\<> 요청을 전송하여 호출할 수 있습니다(예: service.svc/Add for `Add` 작업에 대한 경우). 서비스 URL을 ASP.NET AJAX Script Manager 컨트롤의 스크립트 컬렉션에 입력하여 사용할 수 있습니다. 예를 들어 [구성이 없는 AJAX 서비스를](../../../../docs/framework/wcf/samples/ajax-service-without-configuration.md)참조하십시오.  
  
## <a name="example"></a>예제  
  
 자동으로 구성된 엔드포인트는 기본 URL을 기준으로 비어 있는 주소에 생성됩니다. 또한 구성 파일을 추가하여 이 접근 방법으로 사용할 수 있습니다. 구성 파일에 엔드포인트 정의가 포함된 경우 이러한 엔드포인트는 자동으로 구성된 엔드포인트에 추가됩니다.  
  
 예를 들어, service.svc는 <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>를 사용하고 서비스 디렉터리에는 "soap" 상대 주소에서 <xref:System.ServiceModel.BasicHttpBinding>을 사용하여 동일한 서비스에 대해 엔드포인트를 정의하는 Web.config 파일이 포함되어 있습니다. 이 경우 서비스는 두 개의 엔드포인트를 포함합니다. 한 엔드포인트는 ASP.NET AJAX 요청에 응답하는 service.svc에 위치하고 다른 엔드포인트는 SOAP 요청에 응답하는 service.svc/soap에 위치합니다.  
  
 구성 파일이 비어 있는 상대 주소에 엔드포인트를 정의하고 <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>가 사용되는 경우 예외가 throw되어 서비스를 시작할 수 없습니다.  
  
 구성을 사용하여 자동으로 구성된 엔드포인트에서 설정을 수정할 수 없습니다. 판독기 할당량과 같은 설정을 수정해야 하는 경우 .svc 파일에서 <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>를 제거하고 엔드포인트에 대한 구성 항목을 만들어 구성을 사용하지 않는 접근 방법을 사용하지 말아야 합니다.  
  
 서비스를 사용하려면 ASP.NET 호환 모드가 필요합니다. 예를 들어, <xref:System.Web.HttpContext> 클래스 또는 ASP.NET 인증 메커니즘을 사용하는 경우 이 모드를 사용하도록 설정하려면 구성 파일이 필요합니다. 필요한 구성 요소는 [ \<다음과](../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) 같이 추가해야 하는 서비스호스팅환경>요소입니다.  
  
 `<system.serviceModel>`  
  
 `<serviceHostingEnvironment aspNetCompatibilityEnabled="true" /> </system.serviceModel>`  
  
 자세한 내용은 [WCF 서비스 및 ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md) 항목을 참조하십시오.  
  
 <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> 클래스가 <xref:System.ServiceModel.Activation.ServiceHostFactory>의 파생 클래스인 경우 서비스 호스트 팩터리 메커니즘에 대한 자세한 설명은 [ServiceHostFactory를 사용하여 호스팅 확장](../../../../docs/framework/wcf/extending/extending-hosting-using-servicehostfactory.md) 항목을 참조하십시오.  
  
## <a name="see-also"></a>참고 항목

- [ASP.NET AJAX용 WCF 서비스 만들기](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md)
- [방법: AJAX 사용 ASP.NET 웹 서비스를 WCF로 마이그레이션](../../../../docs/framework/wcf/feature-details/how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)
