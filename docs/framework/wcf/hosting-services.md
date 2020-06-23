---
title: 서비스 호스팅
description: WCF 서비스에 대 한 호스팅 옵션에 대해 알아봅니다. 서비스는이를 만들고 해당 컨텍스트 및 수명을 제어 하는 런타임 환경에서 호스팅해야 합니다.
ms.date: 03/30/2017
helpviewer_keywords:
- hosting services [WCF]
ms.assetid: 192be927-6be2-4fda-98f0-e513c4881acc
ms.openlocfilehash: 86ce392bb76b22e2b6a65fa1d005ed8e9589af15
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85246387"
---
# <a name="hosting-services"></a>호스팅 서비스

활성화할 서비스는 서비스를 만들고 컨텍스트와 수명을 제어하는 런타임 환경에 호스팅해야 합니다. WCF (Windows Communication Foundation) 서비스는 관리 코드를 지 원하는 모든 Windows 프로세스에서 실행 되도록 설계 되었습니다.

WCF는 서비스 지향 응용 프로그램을 빌드하기 위한 통합 프로그래밍 모델을 제공 합니다. 이 프로그래밍 모델은 일관적이며 서비스가 배포되는 런타임 환경에 독립적입니다. 즉, 서비스 코드는 사실상 서비스 호스팅 옵션에 관계없이 거의 동일합니다.

서비스 호스팅 옵션은 콘솔 애플리케이션 내에서 실행하는 경우부터 서버 환경에 이르기까지 다양합니다. 서버 환경의 예를 들면 IIS(인터넷 정보 서비스) 또는 WAS(Windows Process Activation Service)에서 관리하는 작업자 프로세스 내에서 실행되는 Windows 서비스가 있습니다. 개발자는 서비스의 배포 요구 사항을 만족하는 호스팅 환경을 선택합니다. 이러한 요구 사항은 애플리케이션이 배포되는 플랫폼, 메시지를 보내고 받는 데 필요한 전송, 충분한 가용성을 보장하는 데 필요한 프로세스 재활용 유형 및 기타 프로세스 관리 유형, 기타 관리 또는 안정성 요구 사항에 따라 달라집니다. 다음 단원에서는 호스팅 옵션에 대한 정보 및 지침을 제공합니다.

## <a name="hosting-options"></a>호스팅 옵션

### <a name="self-host-in-a-managed-application"></a>관리 되는 응용 프로그램의 자체 호스트
 WCF 서비스는 모든 관리 되는 응용 프로그램에서 호스팅될 수 있습니다. 이 경우 배포하는 데 있어 최소한의 인프라를 필요하므로 가장 유연한 옵션입니다. 관리되는 애플리케이션 코드 내에 서비스 코드를 포함시킨 다음 서비스를 사용할 수 있도록 <xref:System.ServiceModel.ServiceHost> 의 인스턴스를 만들고 엽니다. 자세한 내용은 [방법: 관리 되는 응용 프로그램에서 WCF 서비스 호스팅](how-to-host-a-wcf-service-in-a-managed-application.md)을 참조 하세요.

 이 옵션을 사용 하면 콘솔 응용 프로그램 내에서 실행 되는 WCF 서비스와 Windows Presentation Foundation (WPF) 또는 Windows Forms (WinForms)를 기반으로 하는 클라이언트 응용 프로그램 등의 두 가지 일반적인 시나리오를 사용할 수 있습니다. 콘솔 응용 프로그램 내에서 WCF 서비스를 호스트 하는 작업은 일반적으로 응용 프로그램의 개발 단계에서 유용 합니다. 이 경우 쉽게 디버깅을 수행할 수 있으며, 애플리케이션 내에서 발생하는 상황을 확인하기 위한 추적 정보를 손쉽게 얻을 수 있으며, 새 위치에 서비스를 복사하여 이동하기 용이합니다. 이 호스팅 옵션을 사용 하면 WPF 및 WinForms 응용 프로그램과 같은 리치 클라이언트 응용 프로그램에서 외부 대상과 통신할 수 있습니다. 예를 들어, 사용자 인터페이스에 WPF를 사용 하 고 다른 클라이언트가이 서비스에 연결 하 여 정보를 공유할 수 있도록 하는 WCF 서비스를 호스트 하는 피어 투 피어 공동 작업 클라이언트가 있습니다.

### <a name="managed-windows-services"></a>관리되는 Windows 서비스

이 호스팅 옵션은 WCF 서비스를 관리 되는 Windows 서비스 (이전의 NT 서비스)로 호스트 하는 응용 프로그램 도메인 (AppDomain)을 등록 하 여 서비스의 프로세스 수명이 Windows 서비스의 SCM (서비스 제어 관리자)에 의해 제어 되도록 합니다. 자체 호스팅 옵션과 같이 이러한 유형의 호스팅 환경에서는 일부 호스팅 코드를 애플리케이션의 일부로 작성해야 합니다. 서비스는 WCF 서비스 계약 인터페이스 뿐만 아니라 클래스에서 상속 되도록 하 여 Windows 서비스와 WCF 서비스로 구현 됩니다 <xref:System.ServiceProcess.ServiceBase> . 그러면 <xref:System.ServiceModel.ServiceHost> 가 만들어지고, 재정의된 <xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29> 메서드 내에서 열리고 재정의된 <xref:System.ServiceProcess.ServiceBase.OnStop> 메서드 내에서 닫힙니다. Installutil.exe 도구를 사용하여 프로그램을 Windows 서비스로 설치하려면 <xref:System.Configuration.Install.Installer> 에서 상속되는 설치 관리자 클래스를 구현해야 합니다. 자세한 내용은 [방법: 관리 되는 Windows 서비스에서 WCF 서비스 호스팅](./feature-details/how-to-host-a-wcf-service-in-a-managed-windows-service.md)을 참조 하세요. 관리 되는 Windows 서비스 호스팅 옵션을 통해 사용 하도록 설정 된 시나리오는 메시지가 활성화 되지 않은 보안 환경의 IIS 외부에서 호스팅되는 장기 실행 WCF 서비스의 시나리오입니다. 서비스 수명은 대신 운영 체제에 의해 제어됩니다. 모든 버전의 Windows에서 이 호스팅 옵션을 사용할 수 있습니다.

### <a name="internet-information-services-iis"></a>IIS(인터넷 정보 서비스)

IIS 호스팅 옵션은 ASP.NET와 통합 되며 이러한 기술이 제공 하는 프로세스 재활용, 유휴 상태 종료, 프로세스 상태 모니터링 및 메시지 기반 활성화 기능을 사용 합니다. Windows XP 및 Windows Server 2003 운영 체제에서이 솔루션은 항상 사용 가능 하 고 확장성이 뛰어난 웹 서비스 응용 프로그램을 호스팅하기 위한 기본 솔루션입니다. IIS는 또한 고객이 엔터프라이즈 수준의 서버 제품에서 기대하는 통합된 관리 효율성을 제공합니다. 이 호스팅 옵션을 사용하려면 IIS를 적절히 구성해야 하지만 호스팅 코드를 애플리케이션의 일부로 작성하지 않아도 됩니다. WCF 서비스에 대 한 IIS 호스팅을 구성 하는 방법에 대 한 자세한 내용은 [방법: iis에서 Wcf 서비스](./feature-details/how-to-host-a-wcf-service-in-iis.md)호스팅을 참조 하세요.

 IIS에서 호스팅되는 서비스는 HTTP 전송만 사용할 수 있습니다. IIS 5.1의 구현에는 Windows XP에 몇 가지 제한 사항이 도입 되었습니다. Windows XP에서 IIS 5.1에 의해 WCF 서비스에 제공 되는 메시지 기반 활성화는 동일한 컴퓨터에서 자체 호스팅되는 다른 WCF 서비스에서 포트 80을 사용 하 여 통신 하는 것을 차단 합니다. WCF 서비스는 Windows Server 2003에서 IIS 6.0에 의해 호스팅되는 경우 다른 응용 프로그램과 동일한 AppDomain/응용 프로그램 풀/작업자 프로세스에서 실행할 수 있습니다. 그러나 WCF 및 IIS 6.0 모두 커널 모드 HTTP 스택 (HTTP.sys)을 사용 하기 때문에 iis 6.0는 IIS 5.1와는 달리 포트 80을 동일한 컴퓨터에서 실행 되는 다른 자체 호스팅 WCF 서비스와 공유할 수 있습니다.

### <a name="windows-process-activation-service-was"></a>WAS(Windows Process Activation Service)

WAS (windows Process Activation Service)는 windows Vista 에서도 제공 되는 Windows Server 2008에 대 한 새로운 프로세스 활성화 메커니즘입니다. 친숙 한 IIS 6.0 프로세스 모델 (응용 프로그램 풀 및 메시지 기반 프로세스 활성화)과 호스팅 기능 (예: 오류 급증 시 보호, 상태 모니터링 및 재활용)은 유지 되지만, 활성화 아키텍처에서 HTTP에 대 한 종속성이 제거 됩니다. IIS 7.0는 WAS를 사용 하 여 HTTP를 통한 메시지 기반 활성화를 수행 합니다. 또한 wcf에서 지 원하는 다른 프로토콜 (예: TCP, MSMQ 및 명명 된 파이프)을 통해 메시지 기반 활성화를 제공 하기 위해 추가 WCF 구성 요소가 WAS에 연결 됩니다. 이렇게 하면 통신 프로토콜을 사용하는 애플리케이션에서 프로세스 재활용, 오류로부터 신속한 보호 및 일반적인 구성 시스템과 같은 HTTP 기반 애플리케이션에서만 사용할 수 있었던 IIS 기능을 사용할 수 있습니다.

 이 호스팅 옵션을 사용하려면 IIS를 적절히 구성해야 하지만 호스팅 코드를 애플리케이션의 일부로 작성하지 않아도 됩니다. WAS 호스팅을 구성 하는 방법에 대 한 자세한 내용은 [방법: was에서 WCF 서비스](./feature-details/how-to-host-a-wcf-service-in-was.md)호스팅을 참조 하세요.

## <a name="choose-a-hosting-environment"></a>호스팅 환경 선택
 다음 표에서는 각 호스팅 옵션과 관련된 몇 가지 주요 이점 및 시나리오를 요약하여 설명합니다.

|호스팅 환경|일반적인 시나리오|주요 이점 및 제한|
|-------------------------|----------------------|----------------------------------|
|관리되는 애플리케이션("자체 호스팅")|-개발 중에 사용 되는 콘솔 응용 프로그램입니다.<br />-서비스에 액세스 하는 다양 한 WinForm 및 WPF 클라이언트 응용 프로그램입니다.|플.<br />-쉽게 배포할 수 있습니다.<br />-서비스에 대 한 엔터프라이즈 솔루션이 아닙니다.|
|Windows 서비스(이전의 NT 서비스)|-IIS 외부에서 호스팅되는 장기 실행 WCF 서비스입니다.|-메시지가 활성화 되지 않고 운영 체제에서 제어 하는 서비스 프로세스 수명입니다.<br />-모든 버전의 Windows에서 지원 됩니다.<br />-보안 환경|
|IIS 5.1, IIS 6.0|-HTTP 프로토콜을 사용 하 여 인터넷에서 ASP.NET 콘텐츠를 사용 하 여 WCF 서비스를 나란히 실행 합니다.|-프로세스 재활용<br />-유휴 상태 종료.<br />-상태 모니터링을 처리 합니다.<br />-메시지 기반 활성화.<br />-HTTP 전용|
|WAS(Windows Process Activation Service)|-다양 한 전송 프로토콜을 사용 하 여 인터넷에 IIS를 설치 하지 않고 WCF 서비스를 실행 합니다.|-IIS는 필요 하지 않습니다.<br />-프로세스 재활용<br />-유휴 상태 종료.<br />-상태 모니터링을 처리 합니다.<br />-메시지 기반 활성화.<br />-HTTP, TCP, 명명 된 파이프 및 MSMQ와 함께 작동 합니다.|
|IIS 7.0|-ASP.NET 콘텐츠를 사용 하 여 WCF 서비스를 실행 합니다.<br />-다양 한 전송 프로토콜을 사용 하 여 인터넷에서 WCF 서비스를 실행 합니다.|-이점이 있습니다.<br />-ASP.NET 및 IIS 콘텐츠와 통합 됩니다.|

 애플리케이션이 배포되는 Windows 버전, 메시지를 보내는 데 필요한 전송, 애플리케이션에서 필요로 하는 프로세스와 애플리케이션 도메인 재활용 유형에 따라 선택하는 호스팅 환경이 달라집니다. 다음 표에서는 이러한 요구 사항과 관련된 데이터를 요약하여 설명합니다.

|호스팅 환경|사용 가능한 플랫폼|지원되는 전송|프로세스 및 AppDomain 재활용|
|-------------------------|---------------------------|--------------------------|-------------------------------------|
|관리되는 애플리케이션("자체 호스팅")|Windows XP, Windows Server 2003, Windows Vista,<br /><br /> Windows Server 2008|HTTP,<br /><br /> net.tcp,<br /><br /> net.pipe,<br /><br /> net.msmq|No|
|Windows 서비스(이전의 NT 서비스)|Windows XP, Windows Server 2003, Windows Vista,<br /><br /> Windows Server 2008|HTTP,<br /><br /> net.tcp,<br /><br /> net.pipe,<br /><br /> net.msmq|No|
|IIS 5.1|Windows XP|HTTP|Yes|
|IIS 6.0|Windows Server 2003|HTTP|Yes|
|WAS(Windows Process Activation Service)|Windows Vista, Windows Server 2008|HTTP,<br /><br /> net.tcp,<br /><br /> net.pipe,<br /><br /> net.msmq|Yes|

 신뢰할 수 없는 호스트에서 서비스나 확장을 실행하면 보안이 손상된다는 점에 주의해야 합니다. 또한 가장을 사용 하 여를 열 때 <xref:System.ServiceModel.ServiceHost> 응용 프로그램에서 사용자의를 캐싱하여 사용자가 로그 오프 되지 않았는지 확인 해야 합니다 <xref:System.Security.Principal.WindowsIdentity> .

## <a name="see-also"></a>참고 항목

- [기본 프로그래밍 수명 주기](basic-programming-lifecycle.md)
- [서비스 계약 구현](implementing-service-contracts.md)
- [방법: IIS에서 WCF 서비스 호스팅](./feature-details/how-to-host-a-wcf-service-in-iis.md)
- [방법: WAS에서 WCF 서비스 호스팅](./feature-details/how-to-host-a-wcf-service-in-was.md)
- [방법: 관리형 Windows 서비스에서 WCF 서비스 호스팅](./feature-details/how-to-host-a-wcf-service-in-a-managed-windows-service.md)
- [방법: 관리형 애플리케이션에서 WCF 서비스 호스트](how-to-host-a-wcf-service-in-a-managed-application.md)
