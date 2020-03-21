---
title: '방법: ASP.NET AJAX 엔드포인트에 대해 HTTP POST 및 HTTP GET 요청 중에서 선택'
ms.date: 03/30/2017
ms.assetid: b47de82a-4c92-4af6-bceb-a5cb8bb8ede9
ms.openlocfilehash: 0f7a221d1fd14b4a978683f008858e35cbd2df19
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184750"
---
# <a name="how-to-choose-between-http-post-and-http-get-requests-for-aspnet-ajax-endpoints"></a>방법: ASP.NET AJAX 엔드포인트에 대해 HTTP POST 및 HTTP GET 요청 중에서 선택

WCF(Windows 통신 재단)를 사용하면 클라이언트 웹 사이트의 JavaScript에서 호출할 수 있는 ASP.NET AJAX 지원 끝점을 노출하는 서비스를 만들 수 있습니다. 이러한 서비스를 빌드하기 위한 기본 절차는 [구성 을 사용하여 aJAX 끝점을 ASP.NET 추가하는 방법](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md) 및 [구성을 사용하지 않고 ASP.NET AJAX 끝점을 추가하는 방법에 대해 설명합니다.](../../../../docs/framework/wcf/feature-details/how-to-add-an-aspnet-ajax-endpoint-without-using-configuration.md)  
  
 ASP.NET AJAX는 HTTP POST 및 HTTP GET 동사를 사용하며 기본값이 HTTP POST인 작업을 지원합니다. 파생 작업이 없으며 거의 또는 절대 변경되지 않는 데이터를 반환하는 작업을 만드는 경우 대신 HTTP GET을 사용합니다. GET 작업 결과를 캐시할 수 있습니다. 즉, 동일한 작업에 대해 여러 번 호출하더라도 서비스에 대해 하나의 요청만 수행될 수 있습니다. 캐싱은 WCF에서 수행되지 않지만 모든 수준(사용자의 브라우저, 프록시 서버 및 기타 수준)에서 수행될 수 있습니다. 캐싱은 서비스 성능을 높이려는 경우 유리하지만 데이터가 자주 변경되거나 작업이 일부 작업을 수행하는 경우 허용되지 않을 수 있습니다.  
  
 예를 들어, 사용자의 음악 라이브러리를 관리하기 위해 서비스를 디자인하는 경우 앨범 제목에 기초하여 아티스트를 조회하는 작업에서는 GET을 사용함으로써 이점을 얻을 수 있지만, 앨범을 사용자의 개인 컬렉션에 추가하는 작업에서는 POST를 사용해야 합니다.  
  
 캐시 수명을 제어하려면 <xref:System.ServiceModel.Web.OutgoingWebResponseContext> 형식을 사용합니다. 예를 들어, 시간별로 업데이트되는 일기 예보를 반환하는 서비스를 디자인하는 경우 GET을 사용할 수 있지만 캐시 기간을 1시간 이하로 제한하여 서비스 사용자가 오래된 데이터에 액세스하지 않도록 합니다.  
  
 Script Manager 컨트롤이 사용하는 ASP.NET AJAX 페이지에서 서비스를 사용하는 경우 작업에서 GET을 사용하든지 POST를 사용하든지 차이가 없습니다. 스크립트 관리자 메커니즘은 올바른 요청 형식이 발급되었는지 확인합니다.  
  
 HTTP GET 작업은 복합 데이터 계약 형식을 비롯한 POST 작업에서 지원하는 입력 매개 변수를 사용합니다. 그러나 대부분의 경우 캐싱 효율성이 떨어지기 때문에 너무 많은 매개 변수 또는 GET 작업에 있어서 너무 복잡한 매개 변수는 사용하지 않는 것이 좋습니다.  
  
 이 항목에서는 <xref:System.ServiceModel.Web.WebGetAttribute> 또는 <xref:System.ServiceModel.Web.WebInvokeAttribute> 특성을 서비스 계약의 관련 작업에 추가하여 GET과 POST 중에 하나를 선택하는 방법을 보여 줍니다. 서비스를 실행하는 데 필요한 다른 단계(서비스를 구현, 구성 및 호스팅하는 단계)는 WCF의 ASP.NET AJAX 서비스에서 사용하는 것과 유사합니다.  
  
 <xref:System.ServiceModel.Web.WebGetAttribute>로 표시된 작업은 항상 GET 요청을 사용합니다. <xref:System.ServiceModel.Web.WebInvokeAttribute>로 표시된 작업 또는 두 개의 특성으로 표시되지 않은 작업은 POST 요청을 사용합니다. <xref:System.ServiceModel.Web.WebInvokeAttribute>를 사용하면 <xref:System.ServiceModel.Web.WebInvokeAttribute.Method%2A> 속성을 통해 GET과 POST 이외의 다른 HTTP 동사(예: PUT 및 DELETE)를 사용할 수 있습니다. 그러나 이러한 동사는 ASP.NET AJAX에서 지원되지 않습니다. Script Manager 컨트롤을 사용하여 ASP.NET 페이지에서 서비스를 사용하려면 <xref:System.ServiceModel.Web.WebInvokeAttribute.Method%2A> 속성을 사용하지 마세요.  
  
 GET으로 전환하는 작업 예제는 [기본 AJAX 서비스](../../../../docs/framework/wcf/samples/basic-ajax-service.md) 샘플을 참조하십시오.  
  
 POST를 사용하는 샘플은 HTTP POST 샘플을 [사용하는 AJAX 서비스를](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md) 참조하십시오.  
  
## <a name="to-create-a-wcf-service-that-responds-to-http-get-or-http-post-requests"></a>HTTP GET 또는 HTTP POST 요청에 대해 응답하는 WCF 서비스를 만들려면
  
1. 특성이 표시된 인터페이스로 기본 WCF <xref:System.ServiceModel.ServiceContractAttribute> 서비스 계약을 정의합니다. 각 작업을 <xref:System.ServiceModel.OperationContractAttribute>로 표시합니다. <xref:System.ServiceModel.Web.WebGetAttribute> 특성을 추가하여 작업이 HTTP GET 요청에 응답하도록 규정합니다. 또한 <xref:System.ServiceModel.Web.WebInvokeAttribute> 특성을 추가하여 명시적으로 HTTP POST를 지정할 수 있습니다. 특성을 지정하지 않으면 기본적으로 HTTP POST로 설정됩니다.
  
    ```csharp
    [ServiceContract]  
    public interface IMusicService  
    {  
        //This operation uses a GET method.  
        [OperationContract]  
        [WebGet]  
        string LookUpArtist(string album);  
  
        //This operation will use a POST method.  
        [OperationContract]  
        [WebInvoke]  
        void AddAlbum(string user, string album);  
  
        //This operation will use POST method by default  
        //since nothing else is explicitly specified.  
        [OperationContract]  
        string[] GetAlbums(string user);  
  
        //Other operations omitted…  
  
    }  
    ```  
  
2. `IMusicService`를 사용하여 `MusicService` 서비스 계약을 구현합니다.
  
    ```csharp
    public class MusicService : IMusicService  
    {  
        public void AddAlbum(string user, string album)  
        {  
            //Add implementation here.  
        }  
  
         //Other operations omitted…  
    }  
    ```  
  
3. 애플리케이션에서 .svc 확장명이 있는 service라는 새 파일을 만듭니다. 서비스에 대한 적절한 [ \@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) 지시문 정보를 추가하여 이 파일을 편집합니다. ServiceHost <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> 지시문에 사용할 수 있도록 지정하여 ASP.NET AJAX 끝점을 자동으로 구성합니다. [ \@](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md)  
  
    ```
    <%@ServiceHost
        language=c#
        Debug="true"
        Service="Microsoft.Ajax.Samples.MusicService"  
        Factory=System.ServiceModel.Activation.WebScriptServiceHostFactory  
    %>  
    ```  
  
## <a name="to-call-the-service"></a>서비스를 호출하려면  
  
1. 브라우저를 사용하여 클라이언트 코드 없이 서비스의 GET 작업을 테스트할 수 있습니다. 예를 들어 `http://example.com/service.svc` 주소에서 서비스가 구성된 경우 브라우저 주소 `http://example.com/service.svc/LookUpArtist?album=SomeAlbum` 표시줄에 입력하면 서비스가 호출되고 응답이 다운로드되거나 표시됩니다.
  
2. ASP.NET AJAX Script Manager 컨트롤의 스크립트 컬렉션에 서비스 URL을 입력하여 다른 ASP.NET AJAX 서비스와 동일한 방법으로 GET 작업을 통해 서비스를 사용할 수 있습니다. 예를 들어 기본 [AJAX 서비스를](../../../../docs/framework/wcf/samples/basic-ajax-service.md)참조하십시오.
  
## <a name="see-also"></a>참고 항목

- [ASP.NET AJAX용 WCF 서비스 만들기](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md)
- [방법: AJAX 사용 ASP.NET 웹 서비스를 WCF로 마이그레이션](../../../../docs/framework/wcf/feature-details/how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)
