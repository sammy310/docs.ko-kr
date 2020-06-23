---
title: '방법: SSL을 사용하여 IIS에서 호스팅되는 WCF 서비스 구성'
description: Iis에 등록 된 인증서가 필요한 HTTP 전송 보안을 사용 하도록 IIS에서 호스팅되는 WCF 서비스를 설정 하는 방법에 대해 알아봅니다.
ms.date: 03/30/2017
ms.assetid: df2fe31f-a4bb-4024-92ca-b74ba055e038
ms.openlocfilehash: 8dc4692863d93e407a122c0ba93ae38323b8b213
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85245260"
---
# <a name="how-to-configure-an-iis-hosted-wcf-service-with-ssl"></a>방법: SSL을 사용하여 IIS에서 호스팅되는 WCF 서비스 구성
이 항목에서는 HTTP 전송 보안을 사용하도록 IIS에서 호스트되는 WCF 서비스를 설정하는 방법에 대해 설명합니다. HTTP 전송 보안에는 IIS에 등록할 SSL 인증서가 필요합니다. SSL 인증서가 없는 경우에는 IIS를 사용하여 테스트 인증서를 생성할 수 있습니다. 그런 다음 SSL 바인딩을 웹 사이트에 추가하고 웹 사이트의 인증 속성을 구성해야 합니다. 마지막으로, HTTPS를 사용하도록 WCF 서비스를 구성해야 합니다.  
  
### <a name="creating-a-self-signed-certificate"></a>자체 서명된 인증서 만들기  
  
1. 인터넷 정보 서비스 관리자(inetmgr.exe)를 열고 왼쪽 트리 뷰에서 컴퓨터 이름을 선택합니다. 화면 오른쪽에서 서버 인증서를 선택합니다.  
  
     ![IIS Manager 홈 화면](media/mg-inetmgrhome.jpg "mg_INetMgrHome")  
  
2. 서버 인증서 창에서 **자체 서명 된 인증서 만들기** ...를 클릭 합니다. 링크를 클릭합니다.  
  
     ![IIS를 사용 하 여 자체&#45;서명 된 인증서 만들기](media/mg-createselfsignedcert.jpg "mg_CreateSelfSignedCert")  
  
3. 자체 서명 된 인증서의 이름을 입력 하 고 **확인**을 클릭 합니다.  
  
     ![자체&#45;서명 된 인증서 만들기 대화 상자](media/mg-mycert.jpg "mg_MyCert")  
  
     이제 새로 만든 자체 서명 된 인증서 정보가 **서버 인증서** 창에 표시 됩니다.  
  
     ![서버 인증서 창](media/mg-servercertificatewindow.jpg "mg_ServerCertificateWindow")  
  
     생성된 인증서는 신뢰할 수 있는 루트 인증 기관 저장소에 설치됩니다.  
  
### <a name="add-ssl-binding"></a>SSL 바인딩 추가  
  
1. 인터넷 정보 서비스 관리자에서 **사이트** 폴더를 확장 한 다음 화면 왼쪽의 트리 뷰에서 **기본 웹 사이트** 폴더를 확장 합니다.  
  
2. **바인딩** ...을 클릭 합니다. 창 오른쪽 위에 있는 **동작** 섹션의 링크입니다.  
  
     ![SSL 바인딩 추가](media/mg-addsslbinding.jpg "mg_AddSSLBinding")  
  
3. 사이트 바인딩 창에서 **추가** 단추를 클릭 합니다.  
  
     ![사이트 바인딩 대화 상자](media/mg-sitebindingsdialog.jpg "mg_SiteBindingsDialog")  
  
4. **사이트 바인딩 추가** 대화 상자에서 유형에 대해 https를 선택 하 고 방금 만든 자체 서명 된 인증서의 이름을 선택 합니다.  
  
     ![사이트 바인딩 예제](media/mg-mycertbinding.jpg "mg_MyCertBinding")  
  
### <a name="configure-virtual-directory-for-ssl"></a>SSL용 가상 디렉터리 구성  
  
1. 인터넷 정보 서비스 관리자에서 WCF 보안 서비스를 포함하는 가상 디렉터리를 선택합니다.  
  
2. 창의 가운데 창에서 IIS 섹션의 **SSL 설정** 을 선택 합니다.  
  
     ![가상 디렉터리에 대한 SSL 설정](media/mg-sslsettingsforvdir.jpg "mg_SSLSettingsForVDir")  
  
3. SSL 설정 창에서 **Ssl 필요** 확인란을 선택 하 고 화면 오른쪽의 **작업** 섹션에서 **적용** 링크를 클릭 합니다.  
  
     ![가상 디렉터리 SSL 설정](media/mg-vdirsslsettings.JPG "mg_VDirSSLSettings")  
  
### <a name="configure-wcf-service-for-http-transport-security"></a>HTTP 전송 보안을 위한 WCF 서비스 구성  
  
1. WCF 서비스의 web.config에서 다음 XML에 표시된 것처럼 전송 보안을 사용하도록 HTTP 바인딩을 구성합니다.  
  
    ```xml  
    <bindings>  
          <basicHttpBinding>  
            <binding name="secureHttpBinding">  
              <security mode="Transport">  
                <transport clientCredentialType="None"/>  
              </security>  
            </binding>  
          </basicHttpBinding>  
    </bindings>  
    ```  
  
2. 다음 XML에 표시된 것처럼 서비스 및 서비스 엔드포인트를 지정합니다.  
  
    ```xml  
    <services>  
          <service name="MySecureWCFService.Service1">  
            <endpoint address=""  
                      binding="basicHttpBinding"  
                      bindingConfiguration="secureHttpBinding"  
                      contract="MySecureWCFService.IService1"/>  
  
            <endpoint address="mex"  
                      binding="mexHttpsBinding"  
                      contract="IMetadataExchange" />  
          </service>  
    </services>  
    ```  
  
## <a name="example"></a>예제  
 다음은 HTTP 전송 보안을 사용하는 WCF 서비스에 대한 web.config 파일의 전체 예제입니다.  
  
```xml  
<?xml version="1.0"?>  
<configuration>  
  
  <system.web>  
    <compilation debug="true" targetFramework="4.0" />  
  </system.web>  
  <system.serviceModel>  
    <services>  
      <service name="MySecureWCFService.Service1">  
        <endpoint address=""  
                  binding="basicHttpBinding"  
                  bindingConfiguration="secureHttpBinding"  
                  contract="MySecureWCFService.IService1"/>  
  
        <endpoint address="mex"  
                  binding="mexHttpsBinding"  
                  contract="IMetadataExchange" />  
      </service>  
    </services>  
    <bindings>  
      <basicHttpBinding>  
        <binding name="secureHttpBinding">  
          <security mode="Transport">  
            <transport clientCredentialType="None"/>  
          </security>  
        </binding>  
      </basicHttpBinding>  
    </bindings>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <!-- To avoid disclosing metadata information, set the value below to false and remove the metadata endpoint above before deployment -->  
          <serviceMetadata httpsGetEnabled="true"/>  
          <!-- To receive exception details in faults for debugging purposes, set the value below to true.  Set to false before deployment to avoid disclosing exception information -->  
          <serviceDebug includeExceptionDetailInFaults="false"/>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <serviceHostingEnvironment multipleSiteBindingsEnabled="true" />  
  </system.serviceModel>  
  <system.webServer>  
    <modules runAllManagedModulesForAllRequests="true"/>  
  </system.webServer>  
  
</configuration>  
```  
  
## <a name="see-also"></a>참고 항목

- [인터넷 정보 서비스에서의 호스팅](hosting-in-internet-information-services.md)
- [인터넷 정보 서비스 호스팅 지침](../samples/internet-information-service-hosting-instructions.md)
- [인터넷 정보 서비스 호스팅을 위한 최선의 방법](internet-information-services-hosting-best-practices.md)
- [인라인 코드를 사용한 IIS 호스팅](../samples/iis-hosting-using-inline-code.md)
