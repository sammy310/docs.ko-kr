---
title: 앱 배포
ms.date: 03/30/2017
helpviewer_keywords:
- WPF applications [WPF], deployment
- deployment [WPF], applications
ms.assetid: 12cadca0-b32c-4064-9a56-e6a306dcc76d
ms.openlocfilehash: 54d14503a0f65bb50f2dfb14d40af3b47d51589c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186320"
---
# <a name="deploy-a-wpf-application"></a>WPF 응용 프로그램 배포

WPF(Windows 프레젠테이션 기반) 응용 프로그램을 빌드한 후에는 배포해야 합니다. Windows 및 .NET 프레임워크에는 여러 배포 기술이 포함되어 있습니다. WPF 응용 프로그램을 배포하는 데 사용되는 배포 기술은 응용 프로그램 유형에 따라 다릅니다. 이 항목에서는 각 배포 기술에 대한 간략한 개요와 각 WPF 응용 프로그램 유형의 배포 요구 사항과 함께 사용되는 방법을 제공합니다.

<a name="Deployment_Technologies"></a>
## <a name="deployment-technologies"></a>배포 기술  
 Windows 및 .NET 프레임워크에는 다음과 같은 몇 가지 배포 기술이 포함되어 있습니다.  
  
- XCopy 배포.  
  
- Windows 설치 관리자 배포.  
  
- ClickOnce 배포.  
  
<a name="XCopy_Deployment"></a>
### <a name="xcopy-deployment"></a>XCopy 배포  
 XCopy 배포는 XCopy 명령줄 프로그램을 사용하여 한 위치에서 다른 위치로 파일을 복사하는 방법을 나타냅니다. XCopy 배포는 다음과 같은 경우에 적합합니다.  
  
- 애플리케이션이 독립적이며, 실행하기 위해 클라이언트를 업데이트할 필요가 없습니다.  
  
- 응용 프로그램 파일은 빌드 위치(로컬 디스크, UNC 파일 공유 등)에서 게시 위치(웹 사이트, UNC 파일 공유 등)로 이동해야 합니다.  
  
- 애플리케이션에 셸 통합(시작 메뉴 바로 가기, 데스크톱 아이콘 등)이 필요하지 않습니다.  
  
 XCopy는 간단한 배포 시나리오에 적합하지만 좀더 복잡한 배포 기능이 필요한 경우 제한됩니다. 특히 XCopy를 사용하면 강력한 방식으로 배포를 관리하기 위한 스크립트를 작성, 실행 및 유지 관리하는 오버헤드가 자주 발생합니다. 또한 XCopy는 버전 관리, 제거 또는 롤백을 지원하지 않습니다.  
  
<a name="Windows_Installer"></a>
### <a name="windows-installer"></a>Windows Installer  
 Windows Installer를 사용하면 응용 프로그램을 클라이언트에 쉽게 배포하고 실행할 수 있는 독립형 실행 기록으로 패키징할 수 있습니다. 또한 Windows 설치 관리자는 Windows와 함께 설치되며 바탕 화면, 시작 메뉴 및 프로그램 제어판과 통합할 수 있습니다.  
  
 Windows Installer는 응용 프로그램의 설치 및 제거를 단순화하지만 설치된 응용 프로그램이 버전 관리 관점에서 최신 상태로 유지되도록 하는 기능을 제공하지는 않습니다.  
  
 Windows 설치 관리자에 대한 자세한 내용은 [Windows 설치](/visualstudio/deployment/deploying-applications-services-and-components#create-an-installer-package-windows-desktop)관리자 배포 를 참조하십시오.
  
<a name="ClickOnce_Deployment"></a>
### <a name="clickonce-deployment"></a>ClickOnce 배포  
 ClickOnce를 사용하면 웹이 아닌 응용 프로그램에 대한 웹 스타일 응용 프로그램 배포가 가능합니다. 애플리케이션이 웹 또는 파일 서버에서 게시되고 배포됩니다. ClickOnce 는 Windows Installer 설치 응용 프로그램이 수행하는 모든 클라이언트 기능을 지원하지 는 않지만 다음을 포함하는 하위 집합을 지원합니다.  
  
- 시작 메뉴 및 프로그램 제어판과의 통합.  
  
- 버전 관리, 롤백 및 제거.  
  
- 항상 배포 위치에서 애플리케이션을 시작하는 온라인 설치 모드.  
  
- 새 버전이 릴리스되는 경우 자동 업데이트.  
  
- 파일 확장명 등록.  
  
 ClickOnce에 대한 자세한 내용은 [ClickOnce 보안 및 배포를](/visualstudio/deployment/clickonce-security-and-deployment)참조하십시오.  
  
<a name="Deploying_WPF_Applications"></a>
## <a name="deploying-wpf-applications"></a>WPF 애플리케이션 배포  
 WPF 응용 프로그램의 배포 옵션은 응용 프로그램의 유형에 따라 다릅니다. 배포 관점에서 WPF에는 세 가지 중요한 응용 프로그램 유형이 있습니다.  
  
- 독립 실행형 애플리케이션.  
  
- 마크업 전용 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 애플리케이션.  
  
- XAML 브라우저 응용 프로그램(XBAPs).  
  
<a name="Deploying_Standalone_Applications"></a>
### <a name="deploying-standalone-applications"></a>독립 실행형 애플리케이션 배포  
 독립 실행형 응용 프로그램은 ClickOnce 또는 Windows 설치 관리자를 사용하여 배포됩니다. 두 방법 모두 독립 실행형 애플리케이션을 실행하려면 완전 신뢰가 필요합니다. Windows Installer를 사용하여 배포되는 독립 실행형 응용 프로그램에는 완전 신뢰가 자동으로 부여됩니다. ClickOnce를 사용하여 배포되는 독립 실행형 응용 프로그램에는 자동으로 완전 신뢰가 부여되지 않습니다. 대신 ClickOnce 독립 실행형 응용 프로그램을 설치 하기 전에 사용자가 수락 해야 하는 보안 경고 대화 상자를 표시 합니다. 동의하면 독립 실행형 애플리케이션이 설치되고 완전 신뢰가 부여됩니다. 동의하지 않으면 독립 실행형 애플리케이션이 설치되지 않습니다.  
  
<a name="Deploying_Markup_Only_XAML_Applications"></a>
### <a name="deploying-markup-only-xaml-applications"></a>마크업 전용 XAML 애플리케이션 배포  
 마크업 전용 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 페이지는 일반적으로 HTML 페이지와 같은 웹 서버에 게시되며 Internet Explorer를 사용하여 볼 수 있습니다. 마크업 전용 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 페이지는 인터넷 영역 권한 설정에 정의된 제한 사항이 있는 부분 신뢰 보안 샌드박스 내에서 실행됩니다. 이렇게 하면 HTML 기반 웹 응용 프로그램에 해당하는 보안 샌드박스가 제공됩니다.  
  
 WPF 응용 프로그램의 보안에 대한 자세한 내용은 [보안](../security-wpf.md)을 참조하십시오.  
  
 XCopy 또는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Windows 설치 관리자를 사용하여 마크업 전용 페이지를 로컬 파일 시스템에 설치할 수 있습니다. 이러한 페이지는 인터넷 탐색기 또는 Windows 탐색기를 사용하여 볼 수 있습니다.  
  
 XAML에 대한 자세한 내용은 [XAML 개요(WPF)](../../../desktop-wpf/fundamentals/xaml.md)를 참조하세요.  
  
<a name="Deploying_XAML_Browser_Applications"></a>
### <a name="deploying-xaml-browser-applications"></a>XAML 브라우저 애플리케이션 배포  
 XBAPs는 다음 세 파일을 배포해야 하는 컴파일된 응용 프로그램입니다.  
  
- *ApplicationName*.exe: 실행 가능한 어셈블리 애플리케이션 파일입니다.  
  
- *ApplicationName*.xbap: 배포 매니페스트입니다.  
  
- *ApplicationName*.exe.manifest: 애플리케이션 매니페스트입니다.  
  
> [!NOTE]
> 배포 및 애플리케이션 매니페스트에 대한 자세한 내용은 [WPF 애플리케이션 만들기](building-a-wpf-application-wpf.md)를 참조하세요.  
  
 이러한 파일은 XBAP가 빌드될 때 생성됩니다. 자세한 내용은 [방법: 새 WPF 브라우저 애플리케이션 프로젝트 만들기](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb628663(v=vs.100))를 참조하세요. 태그 전용 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 페이지와 마찬가지로 XBAP는 일반적으로 웹 서버에 게시되고 Internet Explorer를 사용하여 볼 수 있습니다.  
  
 XBAPs는 배포 기술을 사용하여 클라이언트에 배포할 수 있습니다. 그러나 ClickOnce는 다음과 같은 기능을 제공하기 때문에 권장됩니다.  
  
1. 새 버전이 게시될 때 자동 업데이트.  
  
2. 완전 신뢰로 실행되는 XBAP에 대한 권한 상승 권한입니다.  
  
 기본적으로 ClickOnce는 .deploy 확장명을 사용하여 애플리케이션 파일을 게시합니다. 그러면 문제가 될 수 있지만 사용하지 않도록 설정할 수 있습니다. 자세한 내용은 [ClickOnce 배포 시 서버 및 클라이언트 구성 문제](/visualstudio/deployment/server-and-client-configuration-issues-in-clickonce-deployments)를 참조하세요.  
  
 XAML 브라우저 응용 프로그램(XBAPs) 배포에 대한 자세한 내용은 [WPF XAML 브라우저 응용 프로그램 개요를](wpf-xaml-browser-applications-overview.md)참조하십시오.  
  
<a name="Installing__NET_Framework_3_0"></a>
## <a name="installing-the-net-framework"></a>.NET Framework 설치  
 WPF 응용 프로그램을 실행하려면 클라이언트에 Microsoft .NET 프레임워크를 설치해야 합니다. Internet Explorer는 WPF 브라우저 에서 호스팅되는 응용 프로그램을 볼 때 클라이언트가 .NET Framework에 설치되어 있는지 여부를 자동으로 감지합니다. .NET 프레임워크가 설치되어 있지 않으면 Internet Explorer에서 사용자에게 설치하라는 메시지를 표시합니다.  
  
 .NET Framework가 설치되어 있는지 여부를 감지하기 위해 Internet Explorer에는 다음과 같은 확장자가 있는 콘텐츠 파일에 대해 대체 다목적 인터넷 메일 확장(MIME) 처리기로 등록된 부트래퍼 응용 프로그램이 포함되어 있습니다. 및 .application을 참조하십시오. 이러한 파일 형식을 탐색하고 .NET Framework가 클라이언트에 설치되지 않은 경우 bootstrapper 응용 프로그램은 설치 권한을 요청합니다. 사용 권한이 제공되지 않으면 .NET Framework나 응용 프로그램이 설치되지 않습니다.  
  
 권한이 부여되면 Internet Explorer는 Microsoft 백그라운드 지능형 전송 서비스(BITS)를 사용하여 .NET 프레임워크를 다운로드하고 설치합니다. .NET Framework를 성공적으로 설치한 후 원래 요청한 파일이 새 브라우저 창에서 열립니다.  
  
 자세한 내용은 [.NET Framework 및 애플리케이션 배포](../../deployment/index.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목

- [WPF 애플리케이션 빌드](building-a-wpf-application-wpf.md)
- [보안](../security-wpf.md)
