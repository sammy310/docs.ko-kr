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
# <a name="how-to-detect-whether-the-wpf-plug-in-for-firefox-is-installed"></a><span data-ttu-id="b8792-102">방법: Firefox용 WPF 플러그 인 설치 여부 확인</span><span class="sxs-lookup"><span data-stu-id="b8792-102">How to: Detect Whether the WPF Plug-In for Firefox Is Installed</span></span>

<span data-ttu-id="b8792-103">Firefox 용 WPF (Windows Presentation Foundation) 플러그 인은 Xbap (XAML 브라우저 응용 프로그램) 및 느슨한 XAML 파일이 Mozilla Firefox 브라우저에서 실행 될 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8792-103">The Windows Presentation Foundation (WPF) plug-in for Firefox enables XAML browser applications (XBAPs) and loose XAML files to run in the Mozilla Firefox browser.</span></span> <span data-ttu-id="b8792-104">이 항목에서는 관리자가 Firefox 용 WPF 플러그 인 설치 여부를 확인 하는 데 사용할 수 있는 HTML 및 JavaScript로 작성 된 스크립트를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8792-104">This topic provides a script written in HTML and JavaScript that administrators can use to determine whether the WPF plug-in for Firefox is installed.</span></span>

> [!NOTE]
> <span data-ttu-id="b8792-105">.NET Framework 설치, 배포 및 검색 하는 방법에 대 한 자세한 내용은 [개발자 용 .NET Framework 설치](../../install/guide-for-developers.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b8792-105">For more information about installing, deploying, and detecting the .NET Framework, see [Install the .NET Framework for developers](../../install/guide-for-developers.md).</span></span>

## <a name="example"></a><span data-ttu-id="b8792-106">예</span><span class="sxs-lookup"><span data-stu-id="b8792-106">Example</span></span>

<span data-ttu-id="b8792-107">.NET Framework 3.5가 설치 되 면 클라이언트 컴퓨터는 Firefox 용 WPF 플러그 인을 사용 하 여 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8792-107">When the .NET Framework 3.5 is installed, the client computer is configured with a WPF plug-in for Firefox.</span></span> <span data-ttu-id="b8792-108">다음 예제 스크립트는 Firefox 용 WPF 플러그 인을 확인 한 다음 적절 한 상태 메시지를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8792-108">The following example script checks for the WPF plug-in for Firefox and then displays an appropriate status message.</span></span>

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

<span data-ttu-id="b8792-109">Firefox 용 WPF 플러그 인에 대 한 확인이 성공 하면 다음 상태 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8792-109">If the check for the WPF plug-in for Firefox is successful, the following status message is displayed:</span></span>

`The WPF plug-in for Firefox is installed.`

<span data-ttu-id="b8792-110">그렇지 않으면 다음 상태 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8792-110">Otherwise, the following status message is displayed:</span></span>

`The WPF plug-in for Firefox is not installed. Please install or reinstall the .NET Framework 3.5.`

## <a name="see-also"></a><span data-ttu-id="b8792-111">참조</span><span class="sxs-lookup"><span data-stu-id="b8792-111">See also</span></span>

- [<span data-ttu-id="b8792-112">.NET Framework 3.0 설치 여부 확인</span><span class="sxs-lookup"><span data-stu-id="b8792-112">Detect Whether the .NET Framework 3.0 Is Installed</span></span>](how-to-detect-whether-the-net-framework-3-0-is-installed.md)
- [<span data-ttu-id="b8792-113">.NET Framework 3.5 설치 여부 확인</span><span class="sxs-lookup"><span data-stu-id="b8792-113">Detect Whether the .NET Framework 3.5 Is Installed</span></span>](how-to-detect-whether-the-net-framework-3-5-is-installed.md)
- [<span data-ttu-id="b8792-114">WPF XAML 브라우저 애플리케이션 개요</span><span class="sxs-lookup"><span data-stu-id="b8792-114">WPF XAML Browser Applications Overview</span></span>](wpf-xaml-browser-applications-overview.md)
