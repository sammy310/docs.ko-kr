---
title: Windows Communication Foundation과 함께 사용하도록 Windows Process Activation Service 구성
ms.date: 03/30/2017
ms.assetid: 1d50712e-53cd-4773-b8bc-a1e1aad66b78
ms.openlocfilehash: 06d3a7bd798913b06d342ac09d12e736fc436b3c
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84597503"
---
# <a name="configuring-the-windows-process-activation-service-for-use-with-windows-communication-foundation"></a>Windows Communication Foundation과 함께 사용하도록 Windows Process Activation Service 구성
이 항목에서는 Windows Vista에서 HTTP 네트워크 프로토콜을 통해 통신 하지 않는 WCF (Windows Communication Foundation) 서비스를 호스트 하는 Windows Process Activation Service (WAS 라고도 함)를 설정 하는 데 필요한 단계에 대해 설명 합니다. 다음 단원에서는 이 구성 단계에 대해 간략히 설명합니다.  
  
- 필요한 WCF 활성화 구성 요소를 설치 하거나 설치를 확인 합니다.  
  
- 사용할 네트워크 프로토콜 바인딩으로 WAS 사이트를 만들거나 새 프로토콜 바인딩을 기존 사이트에 추가합니다.  
  
- 서비스를 호스팅할 애플리케이션을 만들고 이 애플리케이션에서 필요한 네트워크 프로토콜을 사용하도록 설정합니다.  
  
- HTTP가 아닌 끝점을 노출 하는 WCF 서비스를 빌드합니다.  
  
## <a name="configuring-a-site-with-non-http-bindings"></a>HTTP가 아닌 바인딩을 사용하여 사이트 구성  
 WAS에 HTTP가 아닌 바인딩을 사용하려면 사이트 바인딩을 WAS 구성에 추가해야 합니다. WAS에 대한 구성 저장소는 %windir%\system32\inetsrv\config 디렉터리에 있는 applicationHost.config 파일입니다. WAS와 IIS 7.0에서 이 구성 저장소를 공유합니다.  
  
 applicationHost.config는 메모장과 같은 표준 텍스트 편집기에서 열 수 있는 XML 텍스트 파일입니다. 그러나 IIS 7.0 명령줄 구성 도구 (appcmd.exe)는 비 HTTP 사이트 바인딩을 추가 하는 데 선호 되는 방법입니다.  
  
 다음 명령은 appcmd.exe(이 명령은 한 줄로 입력됨)를 사용하여 net.tcp 사이트 바인딩을 기본 웹 사이트에 추가합니다.  
  
```console  
appcmd.exe set site "Default Web Site" -+bindings.[protocol='net.tcp',bindingInformation='808:*']  
```  
  
 이 명령은 applicationHost.config 파일에 아래 표시된 줄을 추가하여 새 net.tcp 바인딩을 기본 웹 사이트에 추가합니다.  
  
```xml  
<sites>  
    <site name="Default Web Site" id="1">  
        <bindings>  
            <binding protocol="HTTP" bindingInformation="*:80:" />  
            //The following line is added by the command.  
            <binding protocol="net.tcp" bindingInformation="808:*" />  
        </bindings>  
    </site>  
</sites>  
```  
  
## <a name="enabling-an-application-to-use-non-http-protocols"></a>HTTP가 아닌 프로토콜을 사용하도록 애플리케이션 설정  
 응용 프로그램 수준에서 개별 네트워크 protocolsat를 사용 하거나 사용 하지 않도록 설정할 수 있습니다. 다음 명령은 `Default Web Site`에서 실행되는 애플리케이션에 대한 HTTP 및 net.tcp 프로토콜을 모두 사용하도록 설정하는 방법을 보여 줍니다.  
  
```console  
appcmd.exe set app "Default Web Site/appOne" /enabledProtocols:net.tcp  
```  
  
 \<applicationDefaults>Applicationhost.config에 저장 된 사이트 XML 구성의 요소에서 사용 하도록 설정 된 프로토콜의 목록을 설정할 수도 있습니다.  
  
 applicationHost.config의 다음과 같은 XML 코드는 HTTP 프로토콜 및 HTTP가 아닌 프로토콜에 모두 바인딩되는 사이트를 보여 줍니다. HTTP가 아닌 프로토콜을 지원하는 데 필요한 추가 구성은 주석으로 호출됩니다.  
  
```xml  
<sites>  
    <site name="Default Web Site" id="1">  
      <application path="/">  
        <virtualDirectory path="/" physicalPath="D:\inetpub\wwwroot" />  
      </application>  
      <bindings>  
            <!-- The following two lines are added by the command. -->
            <binding protocol="HTTP" bindingInformation="*:80:" />  
            <binding protocol="net.tcp" bindingInformation="808:*" />  
       </bindings>  
    </site>  
    <siteDefaults>  
        <logFile
        customLogPluginClsid="{FF160663-DE82-11CF-BC0A-00AA006111E0}"  
          directory="D:\inetpub\logs\LogFiles" />  
        <traceFailedRequestsLogging
          directory="D:\inetpub\logs\FailedReqLogFiles" />  
    </siteDefaults>  
    <applicationDefaults
      applicationPool="DefaultAppPool"
      <!-- The following line is inserted by the command. -->
      enabledProtocols="http, net.tcp" />  
    <virtualDirectoryDefaults allowSubDirConfig="true" />  
</sites>  
```  
  
 WAS를 설치 및 구성하지 않은 상태에서 WAS for Non-HTTP Activation을 사용하여 서비스를 활성화하려고 하면 다음 오류가 나타날 수 있습니다.  
  
```output  
[InvalidOperationException: The protocol 'net.tcp' does not have an implementation of HostedTransportConfiguration type registered.]   System.ServiceModel.AsyncResult.End(IAsyncResult result) +15778592   System.ServiceModel.Activation.HostedHttpRequestAsyncResult.End(IAsyncResult result) +15698937   System.ServiceModel.Activation.HostedHttpRequestAsyncResult.ExecuteSynchronous(HttpApplication context, Boolean flowContext) +265   System.ServiceModel.Activation.HttpModule.ProcessRequest(Object sender, EventArgs e) +227   System.Web.SyncEventExecutionStep.System.Web.HttpApplication.IExecutionStep.Execute() +80   System.Web.HttpApplication.ExecuteStep(IExecutionStep step, Boolean& completedSynchronously) +171  
```  
  
 이 오류가 표시되는 경우 WAS for Non-HTTP Activation을 올바르게 설치하고 구성하십시오. 자세한 내용은 [방법: WCF 정품 인증 구성 요소 설치 및 구성](how-to-install-and-configure-wcf-activation-components.md)을 참조 하세요.  
  
## <a name="building-a-wcf-service-that-uses-was-for-non-http-activation"></a>비 HTTP 활성화에 WAS를 사용하는 WCF 서비스 빌드  
 WAS를 설치 및 구성 하는 단계를 수행 하는 경우 ( [방법: WCF 활성화 구성 요소 설치 및 구성](how-to-install-and-configure-wcf-activation-components.md)참조) 활성화를 위해 was를 사용 하도록 서비스를 구성 하는 것은 IIS에서 호스팅되는 서비스를 구성 하는 것과 비슷합니다.  
  
 WAS 활성 WCF 서비스를 빌드하는 방법에 대 한 자세한 지침은 [방법: was에서 WCF 서비스 호스팅](how-to-host-a-wcf-service-in-was.md)을 참조 하세요.  
  
## <a name="see-also"></a>참고 항목

- [Windows Process Activation Service에서의 호스팅](hosting-in-windows-process-activation-service.md)
- [Windows Server App Fabric 호스팅 기능](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))
