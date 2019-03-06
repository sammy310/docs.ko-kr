---
title: .NET 응용 프로그램 배포를 지원하기 위한 Firefox 추가 기능
ms.date: 03/30/2017
helpviewer_keywords:
- Firefox add-ons for .NET application deployment
- WPF plug-in for Firefox
- .NET application deployment [WPF], deploying with Firefox add-ons
- .NET Framework Assistant for Firefox
ms.assetid: 2403403b-9b14-48e9-b70d-fa288a3c9081
ms.openlocfilehash: 837ed1cd41869031e8c0b549ffcd26e3285570cd
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57368066"
---
# <a name="firefox-add-ons-to-support-net-application-deployment"></a>.NET 응용 프로그램 배포를 지원하기 위한 Firefox 추가 기능
Windows Presentation Foundation (WPF) Firefox 및 Firefox에 대 한.NET Framework Assistant에 대 한 플러그 인을 사용 하도록 설정 [!INCLUDE[TLA#tla_winfxwebapp#plural](../../../../includes/tlasharptla-winfxwebappsharpplural-md.md)]느슨한, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], 및 Mozilla Firefox 브라우저를 사용 하 여 ClickOnce 응용 프로그램입니다.  
  
## <a name="wpf-plug-in-for-firefox"></a>Firefox 용 WPF 플러그  
 Firefox 용 WPF 플러그 수 있도록 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] 느슨한 및 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일을 탐색 하 고 최상위 수준 또는 Firefox 브라우저에서 HTML IFRAME에서를 실행 합니다. [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 되는 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 웹 서버에 게시 하 고 내에서 시작할 수 있는 응용 프로그램에서 지원 되는 브라우저입니다. 느슨한 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 는 XAML 전용 파일을 탐색 하 고 XML 파일에서와 마찬가지로 지원 되는 브라우저에 표시 수입니다.  
  
 합니다 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Firefox와 함께 설치에 대 한 플러그 인을 [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)]입니다. 7 창에는 [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)]를 포함 하지 않습니다는 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Firefox 플러그 인. 설치할 수 없습니다는 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Windows 7에서 Firefox 플러그 인입니다.  
  
 합니다 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] 포함 되지 않습니다는 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Firefox 플러그 인입니다. 그러나 둘 다를 [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)] 및 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] 는 설치 된 Firefox 용 WPF 플러그와 함께 설치 되는 [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)]합니다. 따라서 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] WPF 호스트 올바른 버전의 프레임 워크 로드 되므로 응용 프로그램은 계속 실행 됩니다. 자세한 내용은 [WPF 호스트 (PresentationHost.exe)](wpf-host-presentationhost-exe.md)합니다.  
  
## <a name="net-framework-assistant-for-firefox"></a>Firefox용 .NET Framework Assistant  
 Firefox 용.NET Framework Assistant Firefox 브라우저에서 실행할 독립 실행형 ClickOnce 응용 프로그램을 수 있습니다. Firefox 용.NET Framework Assistant 함수 동일 하 게 Firefox 브라우저 전후 설치 되어 있는 경우입니다. Firefox 브라우저를 시작할 때 및 [!INCLUDE[net_v35SP1_short](../../../../includes/net-v35sp1-short-md.md)] 가 설치 된 Firefox 찾습니다 및 Firefox에 대 한.NET Framework Assistant를 설치 합니다. 사용자는 다음을 수행 하는 Firefox 용.NET Framework Assistant 구성할 수 있습니다.  
  
-   ClickOnce 응용 프로그램을 실행 하기 전에 확인 합니다.  
  
-   설치 된 모든 버전의.NET Framework 또는 최신 버전에만 보고 합니다.  
  
 Firefox 용.NET Framework Assistant가 포함 된 [!INCLUDE[net_v35SP1_short](../../../../includes/net-v35sp1-short-md.md)]합니다. Firefox 용.NET Framework Assistant를 제거 하는 방법에 대 한 내용은 [Firefox 용.NET Framework Assistant를 제거 하는 방법](https://go.microsoft.com/fwlink/?LinkId=177944)합니다.  
  
## <a name="see-also"></a>참고자료
- [WPF 응용 프로그램 배포](deploying-a-wpf-application-wpf.md)
- [WPF XAML 브라우저 응용 프로그램 개요](wpf-xaml-browser-applications-overview.md)
- [Firefox용 WPF 플러그 인 설치 여부 확인](how-to-detect-whether-the-wpf-plug-in-for-firefox-is-installed.md)
