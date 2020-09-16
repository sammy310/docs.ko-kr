---
title: Windows 서비스 애플리케이션에서의 호스팅
ms.date: 03/30/2017
ms.assetid: f4199998-27f3-4dd9-aee4-0a4addfa9f24
ms.openlocfilehash: cb952cfcd670a790033fbec70de00a4db2541237
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90555850"
---
# <a name="hosting-in-a-windows-service-application"></a>Windows 서비스 애플리케이션에서의 호스팅
Windows 서비스(이전의 Windows NT 서비스)에서는 장기 실행되는 실행 파일에 있어야 하는 애플리케이션에 특히 적합한 프로세스 모델을 제공하지만 사용자 인터페이스 폼을 표시하지 않습니다. Windows 서비스 애플리케이션의 프로세스 수명은 Windows 서비스 애플리케이션을 시작, 중지 및 일지 중지할 수 있도록 해 주는 SCM(서비스 제어 관리자)이 관리합니다. 컴퓨터가 시작 될 때 자동으로 시작 되도록 Windows 서비스 프로세스를 구성 하 여 "always on" 응용 프로그램에 적합 한 호스팅 환경을 만들 수 있습니다. Windows 서비스 응용 프로그램에 대 한 자세한 내용은 [Windows 서비스 응용 프로그램](https://go.microsoft.com/fwlink/?LinkId=89450)을 참조 하십시오.  
  
 WCF (장기 실행 Windows Communication Foundation) 서비스를 호스팅하는 응용 프로그램은 Windows 서비스와 많은 특성을 공유 합니다. 특히 WCF 서비스는 사용자와 직접 상호 작용 하지 않는 장기 실행 서버 실행 파일 이므로 어떤 형태의 사용자 인터페이스도 구현 하지 않습니다. 따라서 Windows 서비스 응용 프로그램 내에서 WCF 서비스를 호스트 하는 것은 강력 하 고 오래 실행 되는 WCF 응용 프로그램을 빌드하기 위한 하나의 옵션입니다.  
  
 WCF 개발자는 종종 WCF 응용 프로그램을 Windows 서비스 응용 프로그램 내부에서 호스트할 지, 아니면 IIS (Windows Process Activation Service) 호스팅 환경 인터넷 정보 서비스 내에서 호스트할 지를 결정 해야 합니다. 다음과 같은 경우에는 Windows 서비스 애플리케이션을 사용하는 것을 고려해야 합니다.  
  
- 애플리케이션에서 명시적 활성화가 필요한 경우. 예를 들어, 서버가 들어오는 첫 번째 메시지에 대한 응답으로 동적으로 시작되는 대신 시작될 때 애플리케이션이 자동으로 시작되어야 하는 경우 Windows 서비스를 사용해야 합니다.  
  
- 애플리케이션을 호스트하는 프로세스가 일단 시작되면 계속 실행되어야 하는 경우. Windows 서비스 프로세스는 일단 시작되면 서버 관리자가 서비스 제어 관리자를 사용하여 명시적으로 종료하지 않는 한 계속 실행됩니다. IIS 또는 WAS에서 호스트되는 애플리케이션은 시스템 리소스의 사용을 최적화하기 위해 동적으로 시작되거나 중지될 수 있습니다. 호스팅 프로세스의 수명을 명시적으로 제어할 필요가 있는 애플리케이션은 IIS 또는 WAS 대신 Windows 서비스를 사용해야 합니다.  
  
- WCF 서비스는 Windows Server 2003에서 실행 해야 하며 HTTP 이외의 전송을 사용 해야 합니다. Windows Server 2003에서 IIS 6.0 호스팅 환경은 HTTP 통신 으로만 제한 됩니다. Windows 서비스 응용 프로그램은이 제한이 적용 되지 않으며 net.tcp, net.pipe 및 net.tcp를 비롯 하 여 WCF에서 지 원하는 모든 전송을 사용할 수 있습니다.  
  
### <a name="to-host-wcf-inside-of-a-windows-service-application"></a>Windows 서비스 애플리케이션 대신 WCF를 호스트하려면  
  
1. Windows 서비스 애플리케이션을 만듭니다. <xref:System.ServiceProcess> 네임스페이스에 있는 클래스를 사용하여 관리 코드에서 Windows 서비스 애플리케이션을 작성할 수 있습니다. 이 애플리케이션에는 <xref:System.ServiceProcess.ServiceBase>에서 상속된 하나의 클래스가 있어야 합니다.  
  
2. WCF 서비스의 수명을 Windows 서비스 응용 프로그램의 수명에 연결 합니다. 일반적으로 호스팅 서비스가 시작 될 때 Windows 서비스 응용 프로그램에서 호스트 되는 WCF 서비스를 활성화 하 고, 호스팅 서비스가 중지 될 때 메시지 수신 대기를 중지 하 고, WCF 서비스에 오류가 발생할 때 호스팅 프로세스를 종료 하려고 합니다. 이렇게 하려면 다음을 수행합니다.  
  
    - <xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29>를 재정의하여 <xref:System.ServiceModel.ServiceHost>의 인스턴스를 하나 이상 엽니다. 단일 Windows 서비스 응용 프로그램은 그룹으로 시작 및 중지 되는 여러 WCF 서비스를 호스트할 수 있습니다.  
  
    - <xref:System.ServiceProcess.ServiceBase.OnStop%2A> <xref:System.ServiceModel.Channels.CommunicationObject.Closed> 에서 시작 된 실행 중인 WCF 서비스에 대해를 호출 하도록 재정의 <xref:System.ServiceModel.ServiceHost> <xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29> 합니다.  
  
    - <xref:System.ServiceModel.Channels.CommunicationObject.Faulted>의 <xref:System.ServiceModel.ServiceHost> 이벤트를 구독하고 <xref:System.ServiceProcess.ServiceController> 클래스를 사용하여 오류가 발생한 경우 Windows 서비스 애플리케이션을 종료합니다.  
  
     Wcf 서비스를 호스트 하는 windows 서비스 응용 프로그램은 WCF를 사용 하지 않는 Windows 서비스 응용 프로그램과 동일한 방식으로 배포 및 관리 됩니다.  
  
## <a name="see-also"></a>참조

- <xref:System.ServiceProcess>
- [연습: 구성 요소 디자이너에서 Windows 서비스 애플리케이션 만들기](https://go.microsoft.com/fwlink/?LinkId=94875)
- [방법: 관리형 Windows 서비스에서 WCF 서비스 호스팅](how-to-host-a-wcf-service-in-a-managed-windows-service.md)
- [Windows Service 호스트](../samples/windows-service-host.md)
- [서비스 애플리케이션 프로그래밍 아키텍처](https://go.microsoft.com/fwlink/?LinkId=94876)
- [Windows Server App Fabric 호스팅 기능](/previous-versions/appfabric/ee677189(v=azure.10))
