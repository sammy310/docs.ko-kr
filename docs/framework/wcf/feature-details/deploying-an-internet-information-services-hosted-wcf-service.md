---
title: 인터넷 정보 서비스에서 호스트하는 WCF 서비스 배포
ms.date: 03/30/2017
ms.assetid: 04ebd329-3fbd-44c3-b3ab-1de3517e27d7
ms.openlocfilehash: 67f6877546951bd92b235218f10f6ccc7011ef5c
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463863"
---
# <a name="deploying-an-internet-information-services-hosted-wcf-service"></a>인터넷 정보 서비스에서 호스트하는 WCF 서비스 배포

IIS(인터넷 정보 서비스)에서 호스팅되는 WCF(Windows 통신 재단) 서비스를 개발하고 배포하는 작업은 다음과 같은 작업으로 구성됩니다.

- IIS, ASP.NET, WCF 및 WCF 정품 인증 구성 요소가 올바르게 설치되고 등록되었는지 확인합니다.

- 새 IIS 응용 프로그램을 만들거나 기존 ASP.NET 응용 프로그램을 다시 사용합니다.

- WCF 서비스에 대한 .svc 파일을 만듭니다.

- IIS 애플리케이션에 서비스 구현을 배포합니다.

- WCF 서비스를 구성합니다.

IIS에서 호스팅하는 WCF 서비스를 만드는 방법에 대한 자세한 내용은 [IIS에서 WCF 서비스 호스트 방법을](how-to-host-a-wcf-service-in-iis.md)참조하십시오.

## <a name="ensure-that-iis-aspnet-and-wcf-are-correctly-installed-and-registered"></a>IIS, ASP.NET 및 WCF가 제대로 설치되고 등록되었는지 확인

IIS가 호스팅하는 WCF 서비스가 올바르게 작동하려면 WCF, IIS 및 ASP.NET 설치해야 합니다. .NET 프레임워크의 일부로 WCF를 설치하는 절차는 운영 체제에 따라 ASP.NET. WCF 및 .NET 프레임워크 설치에 대한 자세한 내용은 [개발자를 위한 .NET 프레임워크 설치를](../../install/guide-for-developers.md)참조하십시오. Windows 10에 IIS를 설치하려면 **제어판에서** **프로그램 및 기능을** 연 다음 Windows 기능 **켜기 또는 끄기를**선택합니다. **Windows 기능에서** **인터넷 정보 서비스를** 선택한 다음 **확인을**선택합니다.

![IIS가 강조 표시된 Windows 기능](./media/windows-features-iis.png)

다른 운영 체제에 IIS를 설치하는 방법에 대한 지침은 [윈도우 비스타와 윈도우 7에 IIS를 설치하고](/iis/install/installing-iis-7/installing-iis-on-windows-vista-and-windows-7) [윈도우 서버 2012 R2에 IIS 8.5를 설치에서](/iis/install/installing-iis-85/installing-iis-85-on-windows-server-2012-r2)찾을 수 있습니다 .

.NET Framework의 설치 프로세스는 IIS가 이미 컴퓨터에 있는 경우 IIS에 WCF를 자동으로 등록합니다. .NET 프레임워크 이후에 IIS를 설치하는 경우 IIS 및 ASP.NET WCF를 등록하려면 추가 단계가 필요합니다. 이러한 작업을 수행하려면 운영 체제에 따라 다음과 같이 하십시오.

- Windows 7 및 Windows 서버 2003: [서비스모델 등록 도구(ServiceModelReg.exe)](../../../../docs/framework/wcf/servicemodelreg-exe.md) 도구를 사용하여 IIS에 WCF를 등록합니다. 이 도구를 사용하려면 [Visual Studio에 대한 개발자 명령 프롬프트에서](../../tools/developer-command-prompt-for-vs.md) **ServiceModelReg.exe /i/x를** 입력합니다.

- Windows 7: 마지막으로 ASP.NET .NET Framework 버전 4 이상을 사용하도록 구성되어 있는지 확인해야 합니다. 옵션으로 ASPNET_Regiis 도구를 실행하여 이 `–i` 작업을 수행합니다. 자세한 내용은 [iIS 등록 도구를 ASP.NET.](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/k6h9cz8h(v=vs.90))

## <a name="create-a-new-iis-application-or-reuse-an-existing-aspnet-application"></a>새 IIS 애플리케이션을 만들거나 기존 ASP.NET 애플리케이션을 다시 사용

IIS가 호스팅하는 WCF 서비스는 IIS 응용 프로그램 내에 있어야 합니다. WCF 서비스를 독점적으로 호스트하는 새 IIS 응용 프로그램을 만들 수 있습니다. 또는 WCF 서비스를 이미 호스팅하는 기존 응용 프로그램에 배포할 수 ASP.NET 2.0 콘텐츠(예: .aspx 페이지 및 ASP.NET 웹 서비스 [ASMX]). 이러한 옵션에 대한 자세한 내용은 [WCF 서비스 및 ASP.NET](wcf-services-and-aspnet.md)"ASP.NET WCF 를 나란히 호스팅" 및 "ASP.NET 호환성 모드에서 WCF 서비스 호스팅" 섹션을 참조하십시오.

IIS 6.0 이상 버전은 격리된 개체 지향 프로그래밍 응용 프로그램을 주기적으로 다시 시작합니다. 기본값은 1740분입니다. 지원되는 최대값은 71,582분입니다. 다시 시작은 사용할 수 없습니다. 이 속성에 대한 자세한 내용은 [주기재 다시 시작 시간을](https://docs.microsoft.com/previous-versions/iis/6.0-sdk/ms525914(v=vs.90))참조하십시오.

## <a name="create-an-svc-file-for-the-wcf-service"></a>WCF 서비스에 대한 .svc 파일 만들기

IIS에서 호스팅되는 WCF 서비스는 IIS 응용 프로그램 내에서 특수 콘텐츠 파일(.svc 파일)으로 표시됩니다. 이 모델은 ASMX 페이지가 IIS 애플리케이션 내에서 .asmx 파일로 표시되는 방식과 비슷합니다. .svc 파일에는 WCF 호스팅 인프라가 들어오는 메시지에 대한 응답으로 호스팅된 서비스를 활성화할 수 있는 WCF 관련 처리[\@지시문(ServiceHost)이](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md)포함되어 있습니다. .svc 파일의 가장 일반적인 구문은 다음 문에서 볼 수 있습니다.

`<% @ServiceHost Service="MyNamespace.MyServiceImplementationTypeName" %>`

ServiceHost 지시문과 단일 특성으로 `Service`구성됩니다. [ \@](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) `Service` 특성 값은 서비스 구현의 CLR(공용 언어 런타임) 형식 이름입니다. 이 지시문을 사용하는 것은 기본적으로 다음 코드를 사용하여 서비스 호스트를 만드는 것과 같습니다.

```csharp
new ServiceHost( typeof( MyNamespace.MyServiceImplementationTypeName ) );
```

서비스의 기본 주소 목록을 만드는 것과 같은 추가 호스팅 구성 작업을 수행할 수도 있습니다. 사용자 지정 <xref:System.ServiceModel.Activation.ServiceHostFactory> 를 사용하여 사용자 지정 호스팅 솔루션에 사용할 지시문을 확장할 수도 있습니다. WCF 서비스를 호스팅하는 IIS 응용 프로그램은 인스턴스 생성 <xref:System.ServiceModel.ServiceHost> 및 수명을 관리할 책임이 없습니다. 관리되는 WCF 호스팅 인프라는 .svc 파일에 대한 첫 번째 요청이 수신될 때 필요한 <xref:System.ServiceModel.ServiceHost> 인스턴스를 동적으로 만듭니다. 이 인스턴스는 코드에서 명시적으로 닫거나 애플리케이션이 재활용될 때까지 해제되지 않습니다.

.svc 파일의 구문에 대한 자세한 내용은 [ \@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md)를 참조하십시오.

## <a name="deploy-the-service-implementation-to-the-iis-application"></a>IIS 애플리케이션에 서비스 구현 배포

IIS에서 호스팅되는 WCF 서비스는 ASP.NET 2.0과 동일한 동적 컴파일 모델을 사용합니다. ASP.NET 마찬가지로 다음과 같이 여러 가지 방법으로 IIS 호스팅 WCF 서비스에 대한 구현 코드를 배포할 수 있습니다.

- GAC(전역 어셈블리 캐시) 또는 애플리케이션의 \bin 디렉터리에 있는 미리 컴파일된 .dll 파일로 배포합니다. 미리 컴파일된 이진 파일은 클래스 라이브러리의 새 버전이 배포될 때까지 업데이트되지 않습니다.

- 응용 프로그램의 \App_Code 디렉터리에있는 컴파일되지 않은 소스 파일로. 애플리케이션의 첫 번째 요청을 처리할 때 이 디렉터리에 있는 소스 파일이 동적으로 필요합니다. \App_Code 디렉터리의 파일을 변경하면 다음 요청을 받았을 때 전체 애플리케이션이 재활용되고 다시 컴파일됩니다.

- .svc 파일에 직접 배치된 컴파일되지 않은 코드입니다. \@ServiceHost 지시문 다음으로 구현 코드를 서비스의 .svc 파일에 인라인으로 배치할 수도 있습니다. 인라인 코드를 변경하면 다음 요청을 받았을 때 애플리케이션이 재활용되고 다시 컴파일됩니다.

ASP.NET 2.0 컴파일 모델에 대한 자세한 내용은 [ASP.NET 컴파일 개요를](https://docs.microsoft.com/previous-versions/aspnet/ms178466(v=vs.100))참조하십시오.

## <a name="configure-the-wcf-service"></a>WCF 서비스 구성

IIS에서 호스팅하는 WCF 서비스는 해당 구성을 응용 프로그램 Web.config 파일에 저장합니다. IIS 호스팅 서비스는 IIS 외부에서 호스팅되는 WCF 서비스와 동일한 구성 요소 및 구문을 사용합니다. 그러나 다음 제약 조건은 IIS 호스팅 환경에만 적용됩니다.

- IIS에서 호스팅되는 서비스의 기본 주소

- IIS 외부에서 WCF 서비스를 호스팅하는 응용 프로그램은 기본 주소 URI 집합을 <xref:System.ServiceModel.ServiceHost> 생성자에게 전달하거나 서비스 구성에서 [ \<호스트>](../../../../docs/framework/configure-apps/file-schema/wcf/host.md) 요소를 제공하여 호스트하는 서비스의 기본 주소를 제어할 수 있습니다. IIS에서 호스팅되는 서비스에는 해당 기본 주소를 제어하는 기능이 없습니다. IIS에서 호스팅되는 서비스의 기본 주소는 해당 .svc 파일의 주소입니다.

### <a name="endpoint-addresses-for-iis-hosted-services"></a>IIS에서 호스팅되는 서비스의 엔드포인트 주소

IIS에서 호스팅되는 경우 엔드포인트 주소는 서비스를 나타내는 .svc 파일의 주소에 항상 상대적인 것으로 간주됩니다. 예를 들어 WCF 서비스의 기본 주소가 `http://localhost/Application1/MyService.svc` 다음과 같은 끝점 구성을 가진 경우:

```xml
<endpoint address="anotherEndpoint" />
```

이렇게 하면 에서 `http://localhost/Application1/MyService.svc/anotherEndpoint`도달할 수 있는 끝점을 제공합니다.

마찬가지로 빈 문자열을 상대 주소로 사용하는 끝점 구성 요소는 기본 `http://localhost/Application1/MyService.svc`주소인 에서 연결할 수 있는 끝점을 제공합니다.

```xml
<endpoint address="" />
```

IIS에서 호스팅되는 서비스 엔드포인트에는 항상 상대 엔드포인트 주소를 사용해야 합니다. 정규화된 엔드포인트 `http://localhost/MyService.svc`주소(예:)를 제공하면 끝점 주소가 엔드포인트를 노출하는 서비스를 호스팅하는 IIS 응용 프로그램을 가리키지 않는 경우 서비스 배포에 오류가 발생할 수 있습니다. 호스팅된 서비스에 상대 엔드포인트 주소를 사용하면 이러한 잠재적 충돌을 예방할 수 있습니다.

### <a name="available-transports"></a>사용 가능한 전송

IIS 5.1 및 IIS 6.0에서 호스팅되는 WCF 서비스는 HTTP 기반 통신을 사용할 수 있습니다. 이러한 IIS 플랫폼에서 HTTP가 아닌 바인딩을 사용하도록 호스팅된 서비스를 구성하면 서비스 활성화 중에 오류가 발생합니다. IIS 7.0의 경우 지원되는 전송에는 HTTP, Net.TCP, Net.Pipe, Net.MSMQ 및 기존 MSMQ 응용 프로그램과의 이전 버전과의 호환성을 위한 msmq.formatname이 포함됩니다.

### <a name="http-transport-security"></a>HTTP 전송 보안

IIS가 호스팅하는 WCF 서비스는 서비스를 포함하는 IIS 가상 디렉터리가 이러한 설정을 지원하는 한 HTTP 전송 보안(예: 기본, 다이제스트 및 Windows 통합 인증과 같은 HTTPS 및 HTTP 인증 체계)을 사용할 수 있습니다. 호스팅된 엔드포인트의 바인딩에서 HTTP 전송 보안 설정은 엔드포인트의 바인딩을 포함하는 IIS 가상 디렉터리의 전송 보안 설정과 일치해야 합니다.

예를 들어 HTTP 다이제스트 인증을 사용하도록 구성된 WCF 끝점은 HTTP 다이제스트 인증을 허용하도록 구성된 IIS 가상 디렉터리에도 있어야 합니다. IIS 설정과 WCF 끝점 설정의 타의 추종을 불허하는 조합은 서비스 활성화 중에 오류가 발생합니다.

## <a name="see-also"></a>참조

- [인터넷 정보 서비스에서의 호스팅](hosting-in-internet-information-services.md)
- [인터넷 정보 서비스 호스팅을 위한 최선의 방법](internet-information-services-hosting-best-practices.md)
- [Windows Server App Fabric 호스팅 기능](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))
