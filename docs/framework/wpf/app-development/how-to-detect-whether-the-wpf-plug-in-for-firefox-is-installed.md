---
title: '방법: Firefox용 WPF 플러그 인 설치 여부 확인'
ms.date: 03/30/2017
helpviewer_keywords:
- plug-in for Firefox [WPF]
- detecting Firefox installation [WPF]
- checking for the Firefox plug-in [WPF]
- Firefox [WPF], detecting installation
- detecting whether the WPF plug-in for Firefox is installed [WPF]
ms.assetid: 5f839373-e3fb-44f1-88ad-4a0761f02189
ms.openlocfilehash: 5ae2f39883c8edd7be912bfeb8326c14ca38704a
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65592624"
---
# <a name="how-to-detect-whether-the-wpf-plug-in-for-firefox-is-installed"></a><span data-ttu-id="c4188-102">방법: Firefox용 WPF 플러그 인 설치 여부 확인</span><span class="sxs-lookup"><span data-stu-id="c4188-102">How to: Detect Whether the WPF Plug-In for Firefox Is Installed</span></span>

<span data-ttu-id="c4188-103">Windows Presentation Foundation (WPF) Firefox 플러그 인을 사용 하면 [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] 및 느슨한 XAML 파일에서 Mozilla Firefox 브라우저를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4188-103">The Windows Presentation Foundation (WPF) plug-in for Firefox enables [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] and loose XAML files to run in the Mozilla Firefox browser.</span></span> <span data-ttu-id="c4188-104">이 항목에서는 관리자 Firefox 용 WPF 플러그 설치 되어 있는지 확인 하는 데 사용할 수 있는 JavaScript 및 HTML로 작성 된 스크립트를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4188-104">This topic provides a script written in HTML and JavaScript that administrators can use to determine whether the WPF plug-in for Firefox is installed.</span></span>

> [!NOTE]
> <span data-ttu-id="c4188-105">설치 하는 방법에 대 한 자세한 내용은 배포 및.NET Framework 검색 참조 [개발자 용.NET Framework 설치](../../install/guide-for-developers.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c4188-105">For more information about installing, deploying, and detecting the .NET Framework, see [Install the .NET Framework for developers](../../install/guide-for-developers.md).</span></span>

## <a name="example"></a><span data-ttu-id="c4188-106">예제</span><span class="sxs-lookup"><span data-stu-id="c4188-106">Example</span></span>

<span data-ttu-id="c4188-107">경우는 [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)] 가 설치 된 클라이언트 컴퓨터가 구성 된 WPF 플러그 인을 사용 하 여 Firefox에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4188-107">When the [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)] is installed, the client computer is configured with a WPF plug-in for Firefox.</span></span> <span data-ttu-id="c4188-108">다음 예제 스크립트 Firefox 용 WPF 플러그 인에 대해 확인 하 고는 적절 한 상태 메시지를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4188-108">The following example script checks for the WPF plug-in for Firefox and then displays an appropriate status message.</span></span>

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

<span data-ttu-id="c4188-109">Firefox 용 WPF 플러그 인에 대 한 검사를 성공한 경우에 다음과 같은 상태 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4188-109">If the check for the WPF plug-in for Firefox is successful, the following status message is displayed:</span></span>

`The WPF plug-in for Firefox is installed.`

<span data-ttu-id="c4188-110">그렇지 않은 경우 다음과 같은 상태 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4188-110">Otherwise, the following status message is displayed:</span></span>

`The WPF plug-in for Firefox is not installed. Please install or reinstall the .NET Framework 3.5.`

## <a name="see-also"></a><span data-ttu-id="c4188-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="c4188-111">See also</span></span>

- [<span data-ttu-id="c4188-112">.NET Framework 3.0 설치 여부 확인</span><span class="sxs-lookup"><span data-stu-id="c4188-112">Detect Whether the .NET Framework 3.0 Is Installed</span></span>](how-to-detect-whether-the-net-framework-3-0-is-installed.md)
- [<span data-ttu-id="c4188-113">.NET Framework 3.5 설치 여부 확인</span><span class="sxs-lookup"><span data-stu-id="c4188-113">Detect Whether the .NET Framework 3.5 Is Installed</span></span>](how-to-detect-whether-the-net-framework-3-5-is-installed.md)
- [<span data-ttu-id="c4188-114">WPF XAML 브라우저 응용 프로그램 개요</span><span class="sxs-lookup"><span data-stu-id="c4188-114">WPF XAML Browser Applications Overview</span></span>](wpf-xaml-browser-applications-overview.md)
