---
description: '자세한 정보: 방법: Windows Server 앱 패브릭을 사용 하 여 워크플로 서비스 호스팅'
title: '방법: Windows Server App Fabric을 사용하여 워크플로 서비스 호스팅'
ms.date: 03/30/2017
ms.assetid: 83b62cce-5fc2-4c6d-b27c-5742ba3bac73
ms.openlocfilehash: 057e81c50844d1a36e32fe899de3469f024d775b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99793807"
---
# <a name="how-to-host-a-workflow-service-with-windows-server-app-fabric"></a>방법: Windows Server App Fabric을 사용하여 워크플로 서비스 호스팅

AppFabric에서 워크플로 서비스를 호스팅하는 것은 IIS/WAS에서 호스팅하는 것과 유사합니다. 유일한 차이점은 AppFabric에서 워크플로 서비스의 배포, 모니터링 및 관리를 위해 제공하는 도구입니다. 이 항목에서는 [장기 실행 워크플로 서비스 만들기](creating-a-long-running-workflow-service.md)에서 만든 워크플로 서비스를 사용 합니다. 이 항목에서는 워크플로 서비스를 만드는 방법을 안내하며, AppFabric을 사용하여 워크플로 서비스를 호스팅하는 방법을 설명합니다. Windows Server Fabric에 대 한 자세한 내용은 [Windows Server App Fabric 설명서](/previous-versions/appfabric/ff384253(v=azure.10))를 참조 하세요. 아래의 단계를 완료하기 전에 Windows Server AppFabric이 설치되어 있는지 확인합니다.  이렇게 하려면 인터넷 정보 서비스 (inetmgr.exe)을 (를) 엽니다. **연결** 보기에서 서버 이름을 클릭 하 고 사이트를 클릭 한 다음 **기본 웹 사이트** 를 클릭 합니다. 화면 오른쪽에는 **App Fabric** 이라는 섹션이 표시 됩니다. 이 섹션(오른쪽 창의 맨 위에 있음)이 없으면 AppFabric이 설치되지 않은 것입니다. Windows Server Fabric을 설치 하는 방법에 대 한 자세한 내용은 [Windows Server App Fabric 설치](/previous-versions/appfabric/ee790960(v=azure.10))를 참조 하세요.  
  
### <a name="creating-a-simple-workflow-service"></a>간단한 워크플로 서비스 만들기  
  
1. Visual Studio 2012을 열고 [장기 실행 워크플로 서비스 만들기](creating-a-long-running-workflow-service.md) 항목에서 만든 orderprocessing 솔루션을 로드 합니다.  
  
2. **Orderservice** 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 **속성** 을 선택한 다음 **웹** 탭을 선택 합니다.  
  
3. 속성 페이지의 **시작 작업** 섹션에서 **특정 페이지** 를 선택 하 고 편집 상자에 .xamlx를 입력 합니다.  
  
4. 속성 페이지의 **서버** 섹션에서 **로컬 IIS 웹 서버 사용** 을 선택 하 고 다음 URL을 입력 합니다. `http://localhost/OrderService`  
  
5. **가상 디렉터리 만들기** 단추를 클릭 합니다. 새 가상 디렉터리가 만들어지고 프로젝트가 빌드될 때 이 가상 디렉터리에 필요한 파일을 복사하도록 프로젝트가 설정됩니다.  또는 .xamlx, web.config 및 필요한 DLL을 가상 디렉터리에 수동으로 복사할 수 있습니다.  
  
### <a name="configuring-a-workflow-service-hosted-in-windows-server-app-fabric"></a>Windows Server AppFabric에서 호스팅되는 워크플로 서비스 구성  
  
1. 인터넷 정보 서비스 관리자(inetmgr.exe)를 엽니다.  
  
2. **연결** 창에서 orderservice 가상 디렉터리로 이동 합니다.  
  
3. OrderService를 마우스 오른쪽 단추로 클릭 하 고 **WCF 및 WF 서비스 관리**, **구성**...을 차례로 선택 합니다. **응용 프로그램에 대해 WCF 및 WF 구성** 대화 상자가 표시 됩니다.  
  
4. 다음 스크린샷에 표시 된 것 처럼 **일반** 탭을 선택 하 여 응용 프로그램에 대 한 일반 정보를 표시 합니다.  
  
     ![App Fabric 구성 대화 상자의 일반 탭](media/appfabricconfiguration-general.gif "AppFabricConfiguration-General")  
  
5. **모니터링** 탭을 선택 합니다. 다음 스크린샷에 표시 된 것 처럼 다양 한 모니터링 설정이 표시 됩니다.  
  
     ![App Fabric Configuration Monitoring 탭](media/appfabricconfiguration-monitoring.gif "AppFabricConfiguration-Monitoring")  
  
     App Fabric에서 워크플로 서비스 모니터링을 구성 하는 방법에 대 한 자세한 내용은 [App fabric을 사용 하 여 모니터링 구성](/previous-versions/appfabric/ee677384(v=azure.10))을 참조 하세요.  
  
6. **워크플로 지 속성** 탭을 선택 합니다. 이를 통해 다음 스크린샷에 표시 된 것 처럼 응용 프로그램에서 App Fabric의 기본 지 속성 공급자를 사용 하도록 구성할 수 있습니다.  
  
     ![응용 프로그램 패브릭 구성 &#45; 지 속성](media/appfabricconfiguration-persistence.gif "AppFabricConfiguration-Persistence")  
  
     Windows Server Fabric에서 워크플로 지 속성을 구성 하는 방법에 대 한 자세한 내용은 [App fabric에서 워크플로 지 속성 구성](/previous-versions/appfabric/ee677353(v=azure.10))을 참조 하세요.  
  
7. **워크플로 호스트 관리** 탭을 선택 합니다. 이를 통해 다음 스크린샷에 표시 된 것 처럼 유휴 워크플로 서비스 인스턴스를 언로드하고 유지할지 지정할 수 있습니다.  
  
     ![App Fabric 구성 워크플로 호스트 관리](media/appfabricconfiguration-management.gif "AppFabricConfiguration-Management")  
  
     워크플로 호스트 관리 구성에 대 한 자세한 내용은 [App Fabric에서 워크플로 호스트 관리 구성](/previous-versions/appfabric/ff383424(v=azure.10))을 참조 하세요.  
  
8. **자동 시작** 탭을 선택 합니다. 이렇게 하면 다음 스크린샷에 표시 된 것 처럼 응용 프로그램에서 워크플로 서비스에 대 한 자동 시작 설정을 지정할 수 있습니다.  
  
     ![앱 패브릭 자동&#45;시작 구성을 보여 주는 스크린샷](./media/how-to-host-a-workflow-service-with-windows-server-app-fabric/app-fabric-auto-start-configuration.gif)  
  
     자동 시작을 구성 하는 방법에 대 한 자세한 내용은 [App Fabric을 사용 하 여 자동 시작 구성](/previous-versions/appfabric/ee677261(v=azure.10))을 참조 하세요.  
  
9. **제한** 탭을 선택 합니다. 이를 통해 다음 스크린샷에 표시 된 것 처럼 워크플로 서비스에 대 한 제한 설정을 구성할 수 있습니다.  
  
     ![앱 패브릭 제한 구성을 보여 주는 스크린샷](./media/how-to-host-a-workflow-service-with-windows-server-app-fabric/app-fabric-throttling-configuration.gif)  
  
     제한을 구성 하는 방법에 대 한 자세한 내용은 [App Fabric을 사용 하 여 제한 구성](/previous-versions/appfabric/ee677261(v=azure.10))을 참조 하세요.  
  
10. **보안** 탭을 선택 합니다. 이를 통해 다음 스크린샷에 표시 된 대로 응용 프로그램에 대 한 보안 설정을 구성할 수 있습니다.  
  
     ![App Fabric 보안 구성](media/appfabricconfiguration-security.gif "AppFabricConfiguration-Security")  
  
     Windows Server Fabric을 사용 하 여 보안을 구성 하는 방법에 대 한 자세한 내용은 [App fabric으로 보안 구성](/previous-versions/appfabric/ee677278(v=azure.10))을 참조 하세요.  
  
### <a name="using-windows-server-app-fabric"></a>Windows Server AppFabric 사용  
  
1. 솔루션을 빌드하여 필요한 파일을 가상 디렉터리에 복사합니다.  
  
2. OrderClient 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 **디버그**, **새 인스턴스 시작** 을 차례로 선택 하 여 클라이언트 응용 프로그램을 시작 합니다.  
  
3. 클라이언트가 실행 되 고 Visual Studio에 **보안 경고 연결** 대화 상자가 표시 되 면 **연결 안 함** 단추를 클릭 합니다. 이렇게 하면 Visual Studio에서 디버깅을 위해 IIS 프로세스에 연결하지 않습니다.  
  
4. 클라이언트 애플리케이션은 워크플로 서비스를 즉시 호출한 다음 기다립니다. 워크플로 서비스는 유휴 상태가 되고 유지됩니다. 인터넷 정보 서비스(inetmgr.exe)를 시작하고 연결 창에서 OrderService로 이동한 다음 선택하여 이를 확인할 수 있습니다. 그런 다음 오른쪽 창에서 AppFabric 대시보드 아이콘을 클릭합니다. 지속형 WF 인스턴스 아래에는 다음 스크린샷에 표시 된 것 처럼 지속형 워크플로 서비스 인스턴스가 하나씩 표시 됩니다.  
  
     ![앱 패브릭 대시보드를 보여 주는 스크린샷](./media/how-to-host-a-workflow-service-with-windows-server-app-fabric/app-fabric-dashboard.gif)  
  
     **WF 인스턴스 기록은** 워크플로 서비스 활성화 수, 워크플로 서비스 인스턴스 완료 횟수 및 오류가 발생 한 워크플로 인스턴스의 수와 같은 워크플로 서비스에 대 한 정보를 나열 합니다. 활성 또는 유휴 인스턴스 아래에서 링크가 표시 됩니다. 링크를 클릭 하면 다음 스크린샷에 표시 된 것 처럼 유휴 워크플로 인스턴스에 대 한 자세한 정보가 표시 됩니다.  
  
     ![지속형 워크플로 인스턴스 정보를 보여 주는 스크린샷](./media/how-to-host-a-workflow-service-with-windows-server-app-fabric/persisted-workflow-instance-detail.gif)  
  
     Windows Server App Fabric 기능 및 사용 방법에 대 한 자세한 내용은 [Windows Server App Fabric 호스팅 기능](/previous-versions/appfabric/ee677189(v=azure.10)) 을 참조 하세요.  
  
## <a name="see-also"></a>참고 항목

- [장기 실행 워크플로 서비스 만들기](creating-a-long-running-workflow-service.md)
- [Windows Server App Fabric 호스팅 기능](/previous-versions/appfabric/ee677189(v=azure.10))
- [Windows Server App Fabric 설치](/previous-versions/appfabric/ee790960(v=azure.10))
- [Windows Server App Fabric 설명서](/previous-versions/appfabric/ff384253(v=azure.10))
