---
title: SystemWebRouting Integration 샘플
ms.date: 03/30/2017
ms.assetid: f1c94802-95c4-49e4-b1e2-ee9dd126ff93
ms.openlocfilehash: 2f12d80085e3ac27dac8ce80b6bb09f69337bfd8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79143956"
---
# <a name="systemwebrouting-integration-sample"></a>SystemWebRouting Integration 샘플
이 샘플에서는 호스팅 계층과 <xref:System.Web.Routing> 네임스페이스에 있는 클래스의 통합을 보여 줍니다. <xref:System.Web.Routing> 네임스페이스의 클래스를 사용하면 애플리케이션에서 실제 리소스에 직접적으로 해당하지 않는 URL을 사용할 수 있습니다. 웹 라우팅을 사용하면 개발자가 HTTP에 대한 가상 주소를 만든 다음 실제 WCF 서비스에 다시 매핑할 수 있습니다. 이렇게 하면 실제 파일 또는 리소스 없이 WCF 서비스를 호스트해야 하거나 .html 또는 .aspx와 같은 파일 확장명이 포함되지 않은 URL을 사용하여 서비스에 액세스해야 하는 경우에 유용합니다. 이 샘플에서는 <xref:System.Web.Routing.RouteTable> 클래스를 사용하여 global.asax에 정의된 실행 중인 서비스에 매핑되는 가상 URI를 만드는 방법을 보여 줍니다.

> [!NOTE]
> <xref:System.Web.Routing> 네임스페이스의 클래스는 HTTP를 통해 호스트되는 서비스에 대해서만 작동합니다.  
  
이 예제에서는 WCF를 사용하여 피드와 `movies` 피드라는 `channels` 두 개의 RSS 피드를 만듭니다. 서비스를 활성화하는 URL에는 확장이 포함되지 않으며 클래스에서 `Application_Start` 파생된 `Global` 클래스의 메서드에 <xref:System.Web.HttpApplication> 등록됩니다.  
  
> [!NOTE]
> 이 샘플은 IIS 6.0이 확장 없는 URL을 지원하는 다른 방법을 사용하므로 IIS(인터넷 정보 서비스) 7.0 이상에서만 작동합니다.  

#### <a name="to-download-this-sample"></a>이 샘플을 다운로드하려면
  
이 샘플은 컴퓨터에 이미 설치되어 있을 수 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  

`<InstallDrive>:\WF_WCF_Samples`  

 이 디렉터리가 없는 경우 [.NET Framework 4에 대한 WCF(Windows 통신 재단) 및 WF(Windows 워크플로우 재단) 샘플로](https://www.microsoft.com/download/details.aspx?id=21459) 이동하여 모든 WCF(Windows 통신 재단) 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 다운로드합니다. 이 샘플은 다음 디렉터리에 있습니다.  

`<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WebRoutingIntegration`  
  
#### <a name="to-use-this-sample"></a>이 샘플을 사용하려면  
  
1. 비주얼 스튜디오를 사용하여 웹 라우팅통합.sln 파일을 엽니다.  
  
2. F5 키를 눌러 솔루션을 실행하고 웹 개발 서버를 시작합니다.  
  
     샘플의 디렉터리 목록이 나타납니다. 파일 확장명이 .svc인 파일은 없습니다.  
  
3. 주소 표시줄에서 `movies` URL을 추가하여 읽고 `http://localhost:[port]/movies` ENTER를 누릅니다.  
  
     movies 피드가 브라우저에 나타납니다.  
  
4. 주소 표시줄에서 `channels` URL에 추가하여 읽고 `http://localhost:[port]/channels` ENTER를 누릅니다.  
  
     channels 피드가 브라우저에 나타납니다.  
  
5. Alt+F4를 눌러 웹 브라우저를 닫습니다.  
  
     개발 서버가 종료되지 않은 경우 알림 영역 아이콘을 마우스 오른쪽 단추로 클릭하고 **중지를 선택합니다.**  
  
#### <a name="to-use-this-sample-when-hosted-in-iis"></a>IIS에서 호스트될 때 이 샘플을 사용하려면  
  
1. 비주얼 스튜디오를 사용하여 웹 라우팅통합.sln 파일을 엽니다.  
  
2. Ctrl+Shift+B를 눌러 프로젝트를 빌드합니다.  
  
3. IIS(인터넷 정보 서비스) 관리자에서 웹 애플리케이션을 만듭니다.  
  
    1. IIS 관리자에서 기본 **웹 사이트를** 마우스 오른쪽 단추로 클릭하고 **응용 프로그램 추가를**선택합니다.  
  
    2. **별칭에**대해 을 `WebRoutingIntegration`입력합니다.  
  
    3. 물리적 **경로의**경우 프로젝트 내의 서비스 폴더를 선택합니다.  
  
    4. **확인**을 누릅니다.  
  
4. 웹 응용 프로그램을 마우스 오른쪽 단추로 클릭하고 응용 프로그램 **관리를** 선택한 다음 **을 찾아서 응용**프로그램을 시작합니다.  
  
5. 주소 표시줄에서 `movies` URL에 추가하여 읽고 `http://localhost:[port]/movies` ENTER를 누릅니다.  
  
     movies 피드가 브라우저에 나타납니다.  
  
6. 주소 표시줄에서 `channels` URL에 추가하여 읽고 `http://localhost:[port]/channels` ENTER를 누릅니다.  
  
     channels 피드가 브라우저에 나타납니다.  
  
7. Alt+F4를 눌러 웹 브라우저를 닫습니다.  
  
 이 샘플에서는 HTTP를 통해 호스트되는 서비스의 요청을 라우트하기 위해 <xref:System.Web.Routing> 네임스페이스의 클래스를 사용하여 호스팅 계층을 작성할 수 있음을 보여 줍니다.  
  
> [!NOTE]
> 버전 2로 설정된 경우 기본 응용 프로그램 풀 버전을 .NET Framework 4로 업데이트해야 합니다.  
  
## <a name="see-also"></a>참고 항목

- [AppFabric 호스팅 및 지속성 샘플](https://docs.microsoft.com/previous-versions/appfabric/ff383418(v=azure.10))
