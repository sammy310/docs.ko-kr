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
# <a name="how-to-configure-visual-studio-to-debug-a-xaml-browser-application-to-call-a-web-service"></a><span data-ttu-id="a8a96-102">방법: Visual Studio를 구성하여 웹 서비스를 호출하는 XAML 브라우저 애플리케이션 디버깅</span><span class="sxs-lookup"><span data-stu-id="a8a96-102">How to: Configure Visual Studio to Debug a XAML Browser Application to Call a Web Service</span></span>
[!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] <span data-ttu-id="a8a96-103">인터넷 영역 권한 집합과 제한 되는 부분 신뢰 보안 샌드박스 내에서 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8a96-103">run within a partial-trust security sandbox that is restricted to the Internet zone set of permissions.</span></span> <span data-ttu-id="a8a96-104">이 권한 집합에만 웹에 있는 서비스를 웹 서비스 호출 제한 된 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 응용 프로그램의 원본 사이트입니다.</span><span class="sxs-lookup"><span data-stu-id="a8a96-104">This permission set restricts Web service calls to only Web services that are located at the [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] application's site of origin.</span></span> <span data-ttu-id="a8a96-105">경우는 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 디버깅은 Visual Studio 2005에서 그러나 간주 되지는 않습니다 동일한 원본 사이트의 웹 서비스 참조 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8a96-105">When an [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] is debugged from Visual Studio 2005, though, it is not considered to have the same site of origin as the Web service it references.</span></span> <span data-ttu-id="a8a96-106">이 원인 보안 예외 때 발생 하는 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 웹 서비스를 호출 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8a96-106">This causes security exceptions to be raised when the [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] attempts to call the Web service.</span></span> <span data-ttu-id="a8a96-107">그러나 Visual Studio 2005는 [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] 디버깅 하는 동안 호출 웹 서비스와 동일한 원본 사이트를 것을 시뮬레이션 하기 위해 프로젝트를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8a96-107">However, a Visual Studio 2005 [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] project can be configured to simulate having the same site of origin as the Web service it calls while debugging.</span></span> <span data-ttu-id="a8a96-108">따라서는 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 안전 하 게 보안 예외가 발생 하지 않고 웹 서비스를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8a96-108">This allows the [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] to safely call the Web service without causing security exceptions.</span></span>

## <a name="configuring-visual-studio"></a><span data-ttu-id="a8a96-109">Visual Studio 구성</span><span class="sxs-lookup"><span data-stu-id="a8a96-109">Configuring Visual Studio</span></span>
 <span data-ttu-id="a8a96-110">디버깅 하려면 Visual Studio 2005를 구성 하는 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 웹 서비스를 호출 하는:</span><span class="sxs-lookup"><span data-stu-id="a8a96-110">To configure Visual Studio 2005 to debug an [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] that calls a Web service:</span></span>

1.  <span data-ttu-id="a8a96-111">**솔루션 탐색기**에서 프로젝트를 선택한 상태에서 **프로젝트** 메뉴에서 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a8a96-111">With a project selected in **Solution Explorer**, on the **Project** menu, click **Properties**.</span></span>

2.  <span data-ttu-id="a8a96-112">에 **프로젝트 디자이너**를 클릭 합니다 **디버그** 탭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8a96-112">In the **Project Designer**, click the **Debug** tab.</span></span>

3.  <span data-ttu-id="a8a96-113">에 **시작 작업** 섹션에서 **시작 외부 프로그램** 하 고 다음을 입력:</span><span class="sxs-lookup"><span data-stu-id="a8a96-113">In the **Start Action** section, select **Start external program** and enter the following:</span></span>

     `C:\WINDOWS\System32\PresentationHost.exe`

4.  <span data-ttu-id="a8a96-114">에 **시작 옵션** 섹션에서 다음을 입력 합니다 **명령줄 인수** 텍스트 상자:</span><span class="sxs-lookup"><span data-stu-id="a8a96-114">In the **Start Options** section, enter the following into the **Command line arguments** text box:</span></span>

     `-debug`  *<span data-ttu-id="a8a96-115">filename</span><span class="sxs-lookup"><span data-stu-id="a8a96-115">filename</span></span>*

     <span data-ttu-id="a8a96-116">합니다 *filename* 에 대 한 값을 **-디버그** 매개 변수에.xbap 파일 이름입니다 예를 들면:</span><span class="sxs-lookup"><span data-stu-id="a8a96-116">The *filename* value for the **-debug** parameter is the .xbap filename; for example:</span></span>

     `-debug c:\example.xbap`

> [!NOTE]
>  <span data-ttu-id="a8a96-117">이 Visual Studio 2005를 사용 하 여 만든 솔루션에 대 한 기본 구성이 [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] 프로젝트 템플릿.</span><span class="sxs-lookup"><span data-stu-id="a8a96-117">This is the default configuration for solutions that are created with the Visual Studio 2005 [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] project template.</span></span>

1.  <span data-ttu-id="a8a96-118">**솔루션 탐색기**에서 프로젝트를 선택한 상태에서 **프로젝트** 메뉴에서 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a8a96-118">With a project selected in **Solution Explorer**, on the **Project** menu, click **Properties**.</span></span>

2.  <span data-ttu-id="a8a96-119">에 **프로젝트 디자이너**를 클릭 합니다 **디버그** 탭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8a96-119">In the **Project Designer**, click the **Debug** tab.</span></span>

3.  <span data-ttu-id="a8a96-120">에 **시작 옵션** 섹션에서 다음 명령줄 매개 변수를 추가 합니다 **명령줄 인수** 텍스트 상자:</span><span class="sxs-lookup"><span data-stu-id="a8a96-120">In the **Start Options** section, add the following command-line parameter to the **Command line arguments** text box:</span></span>

     `-debugSecurityZoneURL`  *<span data-ttu-id="a8a96-121">URL</span><span class="sxs-lookup"><span data-stu-id="a8a96-121">URL</span></span>*

     <span data-ttu-id="a8a96-122">*URL* 에 대 한 값을 **-debugSecurityZoneURL** 매개 변수는는 [!INCLUDE[TLA#tla_url](../../../../includes/tlasharptla-url-md.md)] 응용 프로그램의 원본 사이트에 있는 것으로 시뮬레이션 하려는 위치에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8a96-122">The *URL* value for the **-debugSecurityZoneURL** parameter is the [!INCLUDE[TLA#tla_url](../../../../includes/tlasharptla-url-md.md)] for the location that you want to simulate as being the site of origin of your application.</span></span>

 <span data-ttu-id="a8a96-123">예를 들어 고려를 [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] 다음을 사용 하 여 웹 서비스를 사용 하는 [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="a8a96-123">As an example, consider a [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] that uses a Web service with the following [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)]:</span></span>

 `http://services.msdn.microsoft.com/ContentServices/ContentService.asmx`

 <span data-ttu-id="a8a96-124">원본 사이트의 [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] 이 웹 서비스는:</span><span class="sxs-lookup"><span data-stu-id="a8a96-124">The site of origin [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] for this Web service is:</span></span>

 `http://services.msdn.microsoft.com`

 <span data-ttu-id="a8a96-125">따라서 전체 **-debugSecurityZoneURL** 명령줄 매개 변수 및 값은:</span><span class="sxs-lookup"><span data-stu-id="a8a96-125">Consequently, the complete **-debugSecurityZoneURL** command-line parameter and value is:</span></span>

 `-debugSecurityZoneURL http://services.msdn.microsoft.com`

## <a name="see-also"></a><span data-ttu-id="a8a96-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="a8a96-126">See also</span></span>

- [<span data-ttu-id="a8a96-127">WPF 호스트(PresentationHost.exe)</span><span class="sxs-lookup"><span data-stu-id="a8a96-127">WPF Host (PresentationHost.exe)</span></span>](wpf-host-presentationhost-exe.md)
