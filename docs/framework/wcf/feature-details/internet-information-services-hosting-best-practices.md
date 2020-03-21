---
title: 인터넷 정보 서비스 호스팅을 위한 최선의 방법
ms.date: 03/30/2017
ms.assetid: 0834768e-9665-46bf-86eb-d4b09ab91af5
ms.openlocfilehash: 3be9d4c81f891ad898099ba9041a09b16388b7e4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184713"
---
# <a name="internet-information-services-hosting-best-practices"></a>인터넷 정보 서비스 호스팅을 위한 최선의 방법
이 항목에서는 WCF(Windows 통신 재단) 서비스를 호스팅하기 위한 몇 가지 모범 사례를 간략하게 설명합니다.  
  
## <a name="implementing-wcf-services-as-dlls"></a>WCF 서비스를 DLL로 구현  
 웹 응용 프로그램의 \bin 디렉터리에 배포되는 DLL로 WCF 서비스를 구현하면 IIS(인터넷 정보 서비스)가 배포되지 않은 테스트 환경에서 웹 응용 프로그램 모델 외부에서 서비스를 다시 사용할 수 있습니다.  
  
## <a name="service-hosts-in-iis-hosted-applications"></a>IIS에서 호스팅되는 애플리케이션의 서비스 호스트  
 IIS 호스팅 환경에서 기본적으로 지원되지 않는 네트워크 전송에서 수신대기하는 새 서비스 호스트를 만들기 위해 명령적 자체 호스트 API를 사용하지 마십시오(예: TCP 통신이 IIS 6.0에서 기본적으로 지원되지 않으므로 TCP 서비스를 호스트하는 IIS 6.0). 이는 권장되는 방법이 아닙니다. 명령적으로 만들어진 서비스 호스트는 IIS 호스팅 환경 내에서 알 수 없습니다. 중요한 점은 호스팅 애플리케이션 풀이 유휴 상태인지 여부를 결정할 때 명령적으로 만든 서비스에서 수행된 처리가 IIS에 의해 정의되지 않는다는 것입니다. 결과적으로 명령적으로 그러한 서비스 호스트를 만든 애플리케이션에 적극적으로 IIS 호스트 프로세스를 삭제하는 IIS 호스팅 환경이 포함됩니다.  
  
## <a name="uris-and-iis-hosted-endpoints"></a>URI 및 IIS에서 호스팅되는 엔드포인트  
 IIS에서 호스팅되는 서비스의 엔드포인트는 절대 주소가 아닌 상대 URI(Uniform Resource Identifier)를 사용하여 구성되어야 합니다. 이렇게 하면 엔드포인트 주소가 호스팅 애플리케이션에 속하는 URI 주소 집합 내에 있게 되고 예상한 대로 메시지 기반 활성화가 수행됩니다.  
  
## <a name="state-management-and-process-recycling"></a>상태 관리 및 프로세스 재활용  
 IIS 호스팅 환경은 메모리에 로컬 상태를 유지 관리하지 않는 서비스에 맞게 최적화됩니다. IIS는 여러 외부 및 내부 이벤트에 대한 응답으로 호스트 프로세스를 재활용하여 메모리에만 저장된 일시적 상태가 손실됩니다. IIS에서 호스팅된 서비스는 해당 상태를 프로세스 외부(예: 데이터베이스)에 저장하거나 애플리케이션 재활용 이벤트가 발생하는 경우 쉽게 다시 만들 수 있는 메모리 내 캐시에 저장해야 합니다.  
  
> [!NOTE]
> WCF가 메시지 계층 안정성 및 보안에 사용하는 프로토콜은 휘발성 메모리 내 상태를 사용합니다. WCF 신뢰할 수 있는 세션 및 보안 세션 응용 프로그램 재활용으로 인해 예기치 않게 종료될 수 있습니다. 이러한 프로토콜을 사용하는 IIS 호스팅 응용 프로그램은 응용 프로그램 계층 상태(예: 응용 프로그램 계층 구문 또는 사용자 지정 상관 관계 헤더)의 상관 관계를 위해 WCF에서 제공한 세션 키 이외의 응용 프로그램에 의존하거나 사용하지 않도록 설정해야 합니다. IIS는 호스팅된 응용 프로그램에 대한 재활용을 처리합니다.  
  
## <a name="optimizing-performance-in-middle-tier-scenarios"></a>중간 계층 시나리오에서 성능 최적화  
 *중간 계층 시나리오에서*최적의 성능을 위해 들어오는 메시지에 대한 응답으로 다른 서비스를 호출하는 서비스로 WCF 서비스 클라이언트를 원격 서비스에 한 번 인스턴스화하고 여러 들어오는 요청에서 다시 사용합니다. WCF 서비스 클라이언트를 인스턴스화하는 것은 기존 클라이언트 인스턴스에서 서비스를 호출하는 데 비해 비용이 많이 드는 작업이며 중간 계층 시나리오는 요청 간에 원격 클라이언트를 캐싱하여 고유한 성능 향상을 생성합니다. WCF 서비스 클라이언트는 스레드에서 안전하므로 여러 스레드에서 클라이언트에 대한 액세스를 동기화할 필요가 없습니다.  
  
 중간 계층 시나리오는 또한 `svcutil /a` 옵션에서 생성된 비동기 API를 사용하여 성능을 향상시킵니다. 이 `/a` 옵션을 사용하면 [ServiceModel 메타데이터 유틸리티 도구(Svcutil.exe)가](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) 각 서비스 작업에 대한 메서드를 생성하여 `BeginXXX/EndXXX` 백그라운드 스레드에서 원격 서비스에 대한 장기 실행 호출을 수행할 수 있습니다.  
  
## <a name="wcf-in-multi-homed-or-multi-named-scenarios"></a>멀티홈 또는 여러 개의 이름이 지정된 시나리오의 WCF  
 컴퓨터 집합이 일반적인 외부 `http://www.contoso.com`이름(예:)을 공유하지만 서로 다른 호스트 이름으로 개별적으로 주소가 지정되는 IIS 웹 팜 `http://www.contoso.com` 내에서 WCF 서비스를 배포할 수 있습니다(예: 명명된 `http://machine1.internal.contoso.com` 두 개의 서로 다른 컴퓨터로 `http://machine2.internal.contoso.com`트래픽을 직접 지정할 수 있음). 이 배포 시나리오는 WCF에서 완전히 지원되지만 서비스의 메타데이터(웹 서비스 설명 언어)에 올바른(외부) 호스트 이름을 표시하려면 WCF 서비스를 호스팅하는 IIS 웹 사이트의 특별한 구성이 필요합니다.  
  
 WCF가 생성하는 서비스 메타데이터에 올바른 호스트 이름이 표시되도록 하려면 WCF 서비스를 호스팅하는 IIS 웹 사이트의 기본 ID를 구성하여 명시적 호스트 이름을 사용합니다. 예를 들어 `www.contoso.com` 팜 내에 있는 컴퓨터는 HTTP의 경우 *:80:www.contoso.com의 IIS \*사이트 바인딩을 사용하고 HTTPS의 경우 :443:www.contoso.com을 사용해야 합니다.  
  
 IIS MMC(Microsoft Management Console) 스냅인을 사용하여 IIS 웹 사이트 바인딩을 구성할 수 있습니다.  
  
## <a name="application-pools-running-in-different-user-contexts-overwrite-assemblies-from-other-accounts-in-the-temporary-folder"></a>다른 사용자 컨텍스트에서 실행되는 애플리케이션 풀이 임시 폴더에 있는 다른 계정의 어셈블리를 덮어씀  
 다른 사용자 컨텍스트에서 실행되는 응용 프로그램 풀이 임시 ASP.NET 파일 폴더의 다른 계정의 어셈블리를 덮어쓸 수 없도록 하려면 다른 응용 프로그램에 대해 다른 ID 및 임시 폴더를 사용합니다. 예를 들어 두 개의 가상 애플리케이션/Application1 및 / Application2가 있을 경우 ID가 다른 두 개의 애플리케이션 풀 A와 B를 만들 수 있습니다. 애플리케이션 풀 A는 사용자 ID(user1)에서 실행되는 동시에 애플리케이션 풀 B는 다른 사용자 ID(user2)에서 실행되며 A를 사용하도록 /Application1을 구성하고 B를 사용하도록 /Application2를 구성할 수 있습니다.  
  
 Web.config에서> 사용하여 \< system.web/compilation/@tempFolder 임시 폴더를 구성할 수 있습니다. /Application1의 경우 "c:\tempForUser1"일 수 있으며 응용 프로그램2의 경우 "c:\tempForUser2"일 수 있습니다. 이러한 폴더에 대해 해당하는 쓰기 권한을 두 ID에 부여합니다.  
  
 그러면 user2는 c:\tempForUser1에 있는 /application2에 대한 코드 생성 폴더를 변경할 수 없습니다.  
  
## <a name="enabling-asynchronous-processing"></a>비동기 처리 사용  
 기본적으로 IIS 6.0 및 이전 에서 호스팅되는 WCF 서비스로 전송된 메시지는 동기 식으로 처리됩니다. ASP.NET 자체 스레드(ASP.NET 작업자 스레드)에서 WCF를 호출하고 WCF는 다른 스레드를 사용하여 요청을 처리합니다. WCF는 처리를 완료할 때까지 ASP.NET 작업자 스레드를 보관합니다. 따라서 요청이 동기 방식으로 처리됩니다. 요청을 비동기적으로 처리하면 요청을 처리하는 동안 ASP.NET 스레드를 보유하지 않는 요청을 처리하는 데 필요한 스레드 수가 줄어들기 때문에 확장성이 향상됩니다. IIS 6.0을 실행하는 컴퓨터에는 서버를 DOS(서비스 *거부)* 공격에 개방하는 들어오는 요청을 제한할 수 없으므로 비동기 동작을 사용하지 않는 것이 좋습니다. IIS 7.0부터는 동시 요청 스로틀(`[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ASP.NET\2.0.50727.0]"MaxConcurrentRequestsPerCpu`)이 도입되었습니다. 이 새 스로틀을 사용하면 비동기 처리를 사용해도 안전합니다.  IIS 7.0에서는 기본적으로 비동기 처리기 및 모듈이 등록되어 있습니다. 이러한 비동기 처리기 및 모듈이 해제되어 있는 경우 애플리케이션의 Web.config 파일에서 비동기 처리 요청을 사용하도록 수동으로 설정할 수 있습니다. 사용하는 설정은 `aspNetCompatibilityEnabled` 설정에 따라 달라집니다. `aspNetCompatibilityEnabled`를 `false`로 설정한 경우에는 다음 구성 코드 조각에 나와 있는 것처럼 `System.ServiceModel.Activation.ServiceHttpModule`을 구성하십시오.  
  
```xml  
<system.serviceModel>  
    <serviceHostingEnvironment aspNetCompatibilityEnabled="false" />
  </system.serviceModel>  
  <system.webServer>  
    <modules>  
      <remove name="ServiceModel"/>  
      <add name="ServiceModel"
           preCondition="integratedMode,runtimeVersionv2.0"
           type="System.ServiceModel.Activation.ServiceHttpModule, System.ServiceModel,Version=3.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"/>  
    </modules>  
    </system.webServer>  
```  
  
 `aspNetCompatibilityEnabled`를 `true`로 설정한 경우에는 다음 구성 코드 조각에 나와 있는 것처럼 `System.ServiceModel.Activation.ServiceHttpHandlerFactory`를 구성하십시오.  
  
```xml  
<system.serviceModel>  
    <serviceHostingEnvironment aspNetCompatibilityEnabled="true" />
  </system.serviceModel>  
  <system.webServer>  
    <handlers>  
          <clear/>  
          <add name="TestAsyncHttpHandler"
               path="*.svc"
               verb="*"
               type="System.ServiceModel.Activation.ServiceHttpHandlerFactory, System.ServiceModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"
               />  
    </handlers>
  </system.webServer>  
```  
  
## <a name="see-also"></a>참고 항목

- [서비스 호스팅 샘플](../samples/hosting.md)
- [Windows Server App Fabric 호스팅 기능](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))
