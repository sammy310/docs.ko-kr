---
title: '방법: Visual Studio를 구성하여 웹 서비스를 호출하는 XAML 브라우저 애플리케이션 디버깅'
ms.date: 03/30/2017
helpviewer_keywords:
- debugging XBAPs that call a Web service [WPF]
- debugging security exceptions for XBAPs [WPF]
- security exception for XBAPs [WPF], debugging
- configuring Visual Studio to debug XAML browser applications [WPF]
- configuring Visual Studio to debug XBAPs [WPF]
ms.assetid: fd1db082-a7bb-4c4b-9331-6ad74a0682d0
ms.openlocfilehash: a4fe68ca4c2d4a58ecf561d17111fdf6a68a9118
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59171849"
---
# <a name="how-to-configure-visual-studio-to-debug-a-xaml-browser-application-to-call-a-web-service"></a>방법: Visual Studio를 구성하여 웹 서비스를 호출하는 XAML 브라우저 애플리케이션 디버깅
[!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] 인터넷 영역 권한 집합과 제한 되는 부분 신뢰 보안 샌드박스 내에서 실행 합니다. 이 권한 집합에만 웹에 있는 서비스를 웹 서비스 호출 제한 된 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 응용 프로그램의 원본 사이트입니다. 경우는 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 디버깅은 Visual Studio 2005에서 그러나 간주 되지는 않습니다 동일한 원본 사이트의 웹 서비스 참조 하도록 합니다. 이 원인 보안 예외 때 발생 하는 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 웹 서비스를 호출 하려고 합니다. 그러나 Visual Studio 2005는 [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] 디버깅 하는 동안 호출 웹 서비스와 동일한 원본 사이트를 것을 시뮬레이션 하기 위해 프로젝트를 구성할 수 있습니다. 따라서는 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 안전 하 게 보안 예외가 발생 하지 않고 웹 서비스를 호출 합니다.

## <a name="configuring-visual-studio"></a>Visual Studio 구성
 디버깅 하려면 Visual Studio 2005를 구성 하는 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 웹 서비스를 호출 하는:

1.  **솔루션 탐색기**에서 프로젝트를 선택한 상태에서 **프로젝트** 메뉴에서 **속성**을 클릭합니다.

2.  에 **프로젝트 디자이너**를 클릭 합니다 **디버그** 탭 합니다.

3.  에 **시작 작업** 섹션에서 **시작 외부 프로그램** 하 고 다음을 입력:

     `C:\WINDOWS\System32\PresentationHost.exe`

4.  에 **시작 옵션** 섹션에서 다음을 입력 합니다 **명령줄 인수** 텍스트 상자:

     `-debug`  *filename*

     합니다 *filename* 에 대 한 값을 **-디버그** 매개 변수에.xbap 파일 이름입니다 예를 들면:

     `-debug c:\example.xbap`

> [!NOTE]
>  이 Visual Studio 2005를 사용 하 여 만든 솔루션에 대 한 기본 구성이 [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] 프로젝트 템플릿.

1.  **솔루션 탐색기**에서 프로젝트를 선택한 상태에서 **프로젝트** 메뉴에서 **속성**을 클릭합니다.

2.  에 **프로젝트 디자이너**를 클릭 합니다 **디버그** 탭 합니다.

3.  에 **시작 옵션** 섹션에서 다음 명령줄 매개 변수를 추가 합니다 **명령줄 인수** 텍스트 상자:

     `-debugSecurityZoneURL`  *URL*

     *URL* 에 대 한 값을 **-debugSecurityZoneURL** 매개 변수는는 [!INCLUDE[TLA#tla_url](../../../../includes/tlasharptla-url-md.md)] 응용 프로그램의 원본 사이트에 있는 것으로 시뮬레이션 하려는 위치에 대 한 합니다.

 예를 들어 고려를 [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] 다음을 사용 하 여 웹 서비스를 사용 하는 [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)]:

 `http://services.msdn.microsoft.com/ContentServices/ContentService.asmx`

 원본 사이트의 [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] 이 웹 서비스는:

 `http://services.msdn.microsoft.com`

 따라서 전체 **-debugSecurityZoneURL** 명령줄 매개 변수 및 값은:

 `-debugSecurityZoneURL http://services.msdn.microsoft.com`

## <a name="see-also"></a>참고자료

- [WPF 호스트(PresentationHost.exe)](wpf-host-presentationhost-exe.md)
