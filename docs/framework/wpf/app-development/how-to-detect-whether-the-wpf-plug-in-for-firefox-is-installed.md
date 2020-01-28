---
title: Firefox 용 WPF 플러그 인 설치 여부를 검색 합니다.
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- plug-in for Firefox [WPF]
- detecting Firefox installation [WPF]
- checking for the Firefox plug-in [WPF]
- Firefox [WPF], detecting installation
- detecting whether the WPF plug-in for Firefox is installed [WPF]
ms.assetid: 5f839373-e3fb-44f1-88ad-4a0761f02189
ms.openlocfilehash: 91680859c1742e5d5443d626c81273a80504f4a8
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740402"
---
# <a name="how-to-detect-whether-the-wpf-plug-in-for-firefox-is-installed"></a>방법: Firefox용 WPF 플러그 인 설치 여부 확인

Firefox 용 WPF (Windows Presentation Foundation) 플러그 인은 Xbap (XAML 브라우저 응용 프로그램) 및 느슨한 XAML 파일이 Mozilla Firefox 브라우저에서 실행 될 수 있도록 합니다. 이 항목에서는 관리자가 Firefox 용 WPF 플러그 인 설치 여부를 확인 하는 데 사용할 수 있는 HTML 및 JavaScript로 작성 된 스크립트를 제공 합니다.

> [!NOTE]
> .NET Framework 설치, 배포 및 검색 하는 방법에 대 한 자세한 내용은 [개발자 용 .NET Framework 설치](../../install/guide-for-developers.md)를 참조 하세요.

## <a name="example"></a>예

.NET Framework 3.5가 설치 되 면 클라이언트 컴퓨터는 Firefox 용 WPF 플러그 인을 사용 하 여 구성 됩니다. 다음 예제 스크립트는 Firefox 용 WPF 플러그 인을 확인 한 다음 적절 한 상태 메시지를 표시 합니다.

```html
<HTML>

  <HEAD>
    <TITLE>Test for the WPF plug-in for Firefox</TITLE>
    <META HTTP-EQUIV="Content-Type" CONTENT="text/html; charset=utf-8" />
    <SCRIPT type="text/javascript">
    <!--
    function OnLoad()
    {

       // Check for the WPF plug-in for Firefox and report
       var msg = "The WPF plug-in for Firefox is ";
       var wpfPlugin = navigator.plugins["Windows Presentation Foundation"];
       if( wpfPlugin != null ) {
          document.writeln(msg + " installed.");
       }
       else {
          document.writeln(msg + " not installed. Please install or reinstall the .NET Framework 3.5.");
       }
    }
    -->
    </SCRIPT>
  </HEAD>

  <BODY onload="OnLoad()" />

</HTML>
```

Firefox 용 WPF 플러그 인에 대 한 확인이 성공 하면 다음 상태 메시지가 표시 됩니다.

`The WPF plug-in for Firefox is installed.`

그렇지 않으면 다음 상태 메시지가 표시 됩니다.

`The WPF plug-in for Firefox is not installed. Please install or reinstall the .NET Framework 3.5.`

## <a name="see-also"></a>참조

- [.NET Framework 3.0 설치 여부 확인](how-to-detect-whether-the-net-framework-3-0-is-installed.md)
- [.NET Framework 3.5 설치 여부 확인](how-to-detect-whether-the-net-framework-3-5-is-installed.md)
- [WPF XAML 브라우저 애플리케이션 개요](wpf-xaml-browser-applications-overview.md)
