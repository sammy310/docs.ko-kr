---
title: 인터넷 정보 서비스에서 호스트하는 WCF 서비스 배포
ms.date: 03/30/2017
ms.assetid: 04ebd329-3fbd-44c3-b3ab-1de3517e27d7
ms.openlocfilehash: a41615ab096f3aa4f1ee94defd775248d0df4d2e
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/12/2019
ms.locfileid: "67025738"
---
# <a name="deploying-an-internet-information-services-hosted-wcf-service"></a>인터넷 정보 서비스에서 호스트하는 WCF 서비스 배포

인터넷 정보 서비스 (IIS)에서 호스트 되는 Windows Communication Foundation (WCF) 서비스를 개발 및 배포에 다음 작업으로 이루어집니다.

- IIS, ASP.NET, WCF 및 WCF 활성화 구성 요소가 올바르게 설치 되어 등록을 확인 합니다.

- 새 IIS 응용 프로그램을 만들거나 기존 ASP.NET 응용 프로그램을 다시 사용 합니다.

- WCF 서비스의.svc 파일을 만듭니다.

- IIS 애플리케이션에 서비스 구현을 배포합니다.

- WCF 서비스를 구성 합니다.

IIS에서 호스팅되는 WCF 서비스를 만드는 자세한 연습을 참조 하세요. [방법: IIS에서 WCF 서비스 호스팅](how-to-host-a-wcf-service-in-iis.md)합니다.

## <a name="ensure-that-iis-aspnet-and-wcf-are-correctly-installed-and-registered"></a>IIS, ASP.NET 및 WCF가 제대로 설치되고 등록되었는지 확인

IIS에서 호스팅되는 WCF 서비스가 제대로 작동 하려면 WCF, IIS 및 ASP.NET을 설치 해야 합니다. (.NET Framework의 일부로) WCF, ASP.NET 및 IIS를 설치 하는 절차는 운영 체제에 따라 달라 집니다. WCF 및.NET Framework를 설치 하는 방법에 대 한 자세한 내용은 참조 하세요. [개발자 용.NET Framework 설치](../../install/guide-for-developers.md)합니다. Windows 10에서 IIS를 설치 하려면 열고 **프로그램 및 기능** 에서 **제어판** 선택한 후 **설정 하는 Windows 기능 사용 /** 합니다. **Windows 기능**를 선택 **인터넷 정보 서비스** 를 선택한 후 **확인**합니다.

![강조 표시 하는 IIS 사용 하 여 Windows 기능](media/windows-features-iis.png)

다른 운영 체제에서 IIS를 설치 하기 위한 지침을 찾을 수 있습니다 [Windows Vista 및 Windows 7에 IIS를 설치](/iis/install/installing-iis-7/installing-iis-on-windows-vista-and-windows-7) 하 고 [Windows Server 2012 R2에서 IIS 8.5 설치](/iis/install/installing-iis-85/installing-iis-85-on-windows-server-2012-r2)합니다.

.NET Framework에 대 한 설치 프로세스를 자동으로 등록 WCF IIS를 사용 하 여 IIS가 컴퓨터에 이미 있는 경우. .NET Framework 후 IIS가 설치 하는 경우 IIS 및 ASP.NET을 사용 하 여 WCF 등록 추가 단계가 필요 합니다. 이러한 작업을 수행하려면 운영 체제에 따라 다음과 같이 하십시오.

- Windows 7 및 Windows Server 2003: 사용 된 [ServiceModel 등록 도구 (ServiceModelReg.exe)](../../../../docs/framework/wcf/servicemodelreg-exe.md) IIS를 사용 하 여 WCF 등록 하는 도구입니다. 이 도구를 사용 하려면 입력 **ServiceModelReg.exe /i /x** 에 [Visual Studio 용 개발자 명령 프롬프트](../../tools/developer-command-prompt-for-vs.md)합니다.

- Windows 7: 마지막으로 ASP.NET이.NET Framework 버전 4 이상을 사용 하도록 구성 되어 있는지 확인 해야 합니다. ASPNET_Regiis 도구를 실행 하 여이 작업을 수행 합니다 `–i` 옵션입니다. 자세한 내용은 [ASP.NET IIS Registration Tool](https://go.microsoft.com/fwlink/?LinkId=201186)합니다.

## <a name="create-a-new-iis-application-or-reuse-an-existing-aspnet-application"></a>새 IIS 애플리케이션을 만들거나 기존 ASP.NET 애플리케이션을 다시 사용

IIS에서 호스팅되는 WCF 서비스는 IIS 응용 프로그램을 내부에 있어야 합니다. 단독으로 WCF 서비스를 호스트할 새 IIS 응용 프로그램을 만들 수 있습니다. 또는 이미 ASP.NET 2.0 콘텐츠 (예:.aspx 페이지 및 ASP.NET 웹 서비스 [ASMX])를 호스트 하는 기존 응용 프로그램에는 WCF 서비스를 배포할 수 있습니다. 이러한 옵션에 대 한 자세한 내용은 참조는 "호스팅 WCF-Side-by-side ASP.NET 사용 하 여" 및 "ASP.NET 호환 모드에서 WCF 서비스 호스팅" 섹션 [WCF 서비스 및 ASP.NET](wcf-services-and-aspnet.md)합니다.

[!INCLUDE[iis601](../../../../includes/iis601-md.md)] 이상 버전은 격리된 개체 지향 프로그래밍 응용 프로그램을 정기적으로 다시 시작합니다. 기본값은 1740분입니다. 지원되는 최대값은 71,582분입니다. 다시 시작은 사용할 수 없습니다. 이 속성에 대 한 자세한 내용은 참조는 [PeriodicRestartTime](https://go.microsoft.com/fwlink/?LinkId=109968)합니다.

## <a name="create-an-svc-file-for-the-wcf-service"></a>WCF 서비스에 대한 .svc 파일 만들기

IIS에서 호스팅되는 WCF 서비스는 IIS 응용 프로그램 내에서 특수 한 콘텐츠 파일 (.svc 파일)으로 표시 됩니다. 이 모델은 ASMX 페이지가 IIS 애플리케이션 내에서 .asmx 파일로 표시되는 방식과 비슷합니다. WCF-특정 처리 지시문을 포함 하는.svc 파일 ([\@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md)) WCF 호스팅 인프라 들어오는 메시지에 대 한 응답에서 호스 티 드 서비스를 활성화할 수 있도록 합니다. .svc 파일의 가장 일반적인 구문은 다음 문에서 볼 수 있습니다.

```
<% @ServiceHost Service="MyNamespace.MyServiceImplementationTypeName" %>
```

이루어져 합니다 [ \@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) 지시문과 단일 특성 `Service`합니다. `Service` 특성 값은 서비스 구현의 CLR(공용 언어 런타임) 형식 이름입니다. 이 지시문을 사용하는 것은 기본적으로 다음 코드를 사용하여 서비스 호스트를 만드는 것과 같습니다.

```csharp
new ServiceHost( typeof( MyNamespace.MyServiceImplementationTypeName ) );
```

서비스의 기본 주소 목록을 만드는 것과 같은 추가 호스팅 구성 작업을 수행할 수도 있습니다. 사용자 지정 <xref:System.ServiceModel.Activation.ServiceHostFactory> 를 사용하여 사용자 지정 호스팅 솔루션에 사용할 지시문을 확장할 수도 있습니다. WCF 서비스를 호스팅하는 IIS 응용 프로그램 만들기 및 수명을 관리 하는 것에 대 한 책임을 지지 않습니다 <xref:System.ServiceModel.ServiceHost> 인스턴스. 관리 되는 WCF 호스팅 인프라에 필요한 만듭니다 <xref:System.ServiceModel.ServiceHost> .svc 파일에 대 한 첫 번째 요청을 받으면 인스턴스를 동적으로 합니다. 이 인스턴스는 코드에서 명시적으로 닫거나 애플리케이션이 재활용될 때까지 해제되지 않습니다.

.Svc 파일에 대 한 구문에 대 한 자세한 내용은 참조 하세요. [ \@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md)합니다.

## <a name="deploy-the-service-implementation-to-the-iis-application"></a>IIS 애플리케이션에 서비스 구현 배포

IIS에서 호스팅되는 WCF 서비스는 ASP.NET 2.0으로 동일한 동적 컴파일 모델을 사용 합니다. ASP.NET의 경우와 마찬가지로 다음과 같이 다양 한 위치에서 여러 가지 방법으로 IIS에서 호스팅되는 WCF 서비스에 대 한 구현 코드를 배포할 수 있습니다.

- GAC(전역 어셈블리 캐시) 또는 애플리케이션의 \bin 디렉터리에 있는 미리 컴파일된 .dll 파일로 배포합니다. 미리 컴파일된 이진 파일은 클래스 라이브러리의 새 버전이 배포될 때까지 업데이트되지 않습니다.

- 컴파일되지 않은 원본 파일이 있는 응용 프로그램의 \App_Code 디렉터리에 배포 합니다. 애플리케이션의 첫 번째 요청을 처리할 때 이 디렉터리에 있는 소스 파일이 동적으로 필요합니다. \App_Code 디렉터리의 파일을 변경하면 다음 요청을 받았을 때 전체 애플리케이션이 재활용되고 다시 컴파일됩니다.

- 컴파일되지 않은 코드는.svc 파일에 직접 배치 합니다. 구현 코드 후 서비스의.svc 파일에서 인라인으로 찾을된 수도 있습니다는 \@ServiceHost 지시문입니다. 인라인 코드를 변경하면 다음 요청을 받았을 때 애플리케이션이 재활용되고 다시 컴파일됩니다.

ASP.NET 2.0 컴파일 모델에 대 한 자세한 내용은 참조 하세요. [ASP.NET 컴파일 개요](https://go.microsoft.com/fwlink/?LinkId=94773)합니다.

## <a name="configure-the-wcf-service"></a>WCF 서비스 구성

IIS에서 호스팅되는 WCF 서비스 응용 프로그램 Web.config 파일에서 해당 구성을 저장합니다. IIS 외부에서 호스팅된 WCF 서비스와 동일한 구성 요소 및 구문을 사용 하는 IIS에서 호스팅되는 서비스입니다. 그러나 다음 제약 조건은 IIS 호스팅 환경에만 적용됩니다.

- IIS에서 호스팅되는 서비스의 기본 주소

- IIS 외부에서 WCF 서비스 호스팅의 기본 집합을 전달 하 여 호스트 하는 서비스의 기본 주소를 제어할 수 있습니다 하는 응용 프로그램 Uri 주소 합니다 <xref:System.ServiceModel.ServiceHost> 생성자 또는 제공 하 여는 [ \<호스트 >](../../../../docs/framework/configure-apps/file-schema/wcf/host.md) 요소에는 서비스의 구성입니다. IIS에서 호스팅되는 서비스에는 해당 기본 주소를 제어하는 기능이 없습니다. IIS에서 호스팅되는 서비스의 기본 주소는 해당 .svc 파일의 주소입니다.

### <a name="endpoint-addresses-for-iis-hosted-services"></a>IIS에서 호스팅되는 서비스의 엔드포인트 주소

IIS에서 호스팅되는 경우 엔드포인트 주소는 서비스를 나타내는 .svc 파일의 주소에 항상 상대적인 것으로 간주됩니다. 예를 들어 WCF 서비스의 기본 주소는 `http://localhost/Application1/MyService.svc` 다음과 같은 끝점 구성을 사용 합니다.

```xml
<endpoint address="anotherEndpoint" .../>
```

끝점에 연결할 수 있는 제공 `http://localhost/Application1/MyService.svc/anotherEndpoint`합니다.

상대 주소에서 연결할 수 있는 끝점을 제공 하는 대로 빈 문자열을 사용 하는 끝점 구성 요소 마찬가지로 `http://localhost/Application1/MyService.svc`, 기본 주소는 합니다.

```xml
<endpoint address="" ... />
```

IIS에서 호스팅되는 서비스 엔드포인트에는 항상 상대 엔드포인트 주소를 사용해야 합니다. 정규화 된 끝점 주소를 제공 (예를 들어 `http://localhost/MyService.svc`) IIS-응용 프로그램에 끝점을 노출 하는 서비스를 호스트 하는 끝점 주소를 가리키지 않을 경우 서비스의 배포에서 오류가 발생할 수 있습니다. 호스팅된 서비스에 상대 엔드포인트 주소를 사용하면 이러한 잠재적 충돌을 예방할 수 있습니다.

### <a name="available-transports"></a>사용 가능한 전송

IIS 5.1에서 호스팅되는 WCF 서비스 및 [!INCLUDE[iis601](../../../../includes/iis601-md.md)] HTTP 기반 통신을 사용 하 여 제한 됩니다. 이러한 IIS 플랫폼에서 HTTP가 아닌 바인딩을 사용하도록 호스팅된 서비스를 구성하면 서비스 활성화 중에 오류가 발생합니다. 기존 MSMQ 애플리케이션과의 호환성을 위해 [!INCLUDE[iisver](../../../../includes/iisver-md.md)]에서 지원되는 전송에는 HTTP, Net.TCP, Net.Pipe, Net.MSMQ 및 msmq.formatname이 있습니다.

### <a name="http-transport-security"></a>HTTP 전송 보안

IIS에서 호스팅되는 WCF 서비스 HTTP 사용 가능 서비스를 포함 하는 IIS 가상 디렉터리를 지 원하는 해당 전송 보안 (예를 들어, HTTPS 및 HTTP와 같은 인증 스키마 기본, 다이제스트 및 Windows 통합 인증) 설정. 호스팅된 엔드포인트의 바인딩에서 HTTP 전송 보안 설정은 엔드포인트의 바인딩을 포함하는 IIS 가상 디렉터리의 전송 보안 설정과 일치해야 합니다.

예를 들어, HTTP 다이제스트 인증을 사용 하도록 WCF 끝점을 HTTP 다이제스트 인증을 허용 하도록 구성 된 IIS 가상 디렉터리에 있어야 합니다. IIS 설정 및 WCF 끝점 설정 조합이 일치 하지 않으면된 서비스 활성화 하는 동안 오류가 발생 합니다.

## <a name="see-also"></a>참고자료

- [인터넷 정보 서비스에서 호스팅](hosting-in-internet-information-services.md)
- [인터넷 정보 서비스 호스팅을 위한 최선의 방법](internet-information-services-hosting-best-practices.md)
- [Windows Server App Fabric 호스팅 기능](https://go.microsoft.com/fwlink/?LinkId=201276)
