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
ms.openlocfilehash: d8cfae2fb47876d578c51e5f4acdfe0c31e752fe
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460898"
---
# <a name="how-to-configure-visual-studio-to-debug-a-xaml-browser-application-to-call-a-web-service"></a><span data-ttu-id="50698-102">방법: Visual Studio를 구성하여 웹 서비스를 호출하는 XAML 브라우저 애플리케이션 디버깅</span><span class="sxs-lookup"><span data-stu-id="50698-102">How to: Configure Visual Studio to Debug a XAML Browser Application to Call a Web Service</span></span>
<span data-ttu-id="50698-103">Xbap (XAML 브라우저 응용 프로그램)는 인터넷 영역 권한 집합으로 제한 된 부분 신뢰 보안 샌드박스 내에서 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="50698-103">XAML browser applications (XBAPs) run within a partial-trust security sandbox that is restricted to the Internet zone set of permissions.</span></span> <span data-ttu-id="50698-104">이 권한 집합은 웹 서비스 호출을 XBAP 응용 프로그램의 원본 사이트에 있는 웹 서비스로만 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="50698-104">This permission set restricts Web service calls to only Web services that are located at the XBAP application's site of origin.</span></span> <span data-ttu-id="50698-105">그러나 Visual Studio 2005에서 XBAP를 디버그 하는 경우 해당 XBAP는 참조 하는 웹 서비스와 동일한 원본 사이트를 포함 하지 않는 것으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="50698-105">When an XBAP is debugged from Visual Studio 2005, though, it is not considered to have the same site of origin as the Web service it references.</span></span> <span data-ttu-id="50698-106">이렇게 하면 XBAP에서 웹 서비스를 호출 하려고 할 때 보안 예외가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="50698-106">This causes security exceptions to be raised when the XBAP attempts to call the Web service.</span></span> <span data-ttu-id="50698-107">그러나 Visual Studio 2005 XAML 브라우저 응용 프로그램 (WPF) 프로젝트는 디버깅 하는 동안 호출 하는 웹 서비스와 동일한 원본 사이트를 시뮬레이션 하도록 구성 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50698-107">However, a Visual Studio 2005 XAML Browser Application (WPF) project can be configured to simulate having the same site of origin as the Web service it calls while debugging.</span></span> <span data-ttu-id="50698-108">이렇게 하면 XBAP가 보안 예외를 발생 시 키 지 않고 웹 서비스를 안전 하 게 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50698-108">This allows the XBAP to safely call the Web service without causing security exceptions.</span></span>

## <a name="configuring-visual-studio"></a><span data-ttu-id="50698-109">Visual Studio 구성</span><span class="sxs-lookup"><span data-stu-id="50698-109">Configuring Visual Studio</span></span>
 <span data-ttu-id="50698-110">웹 서비스를 호출 하는 XBAP를 디버깅 하기 위해 Visual Studio 2005을 구성 하려면:</span><span class="sxs-lookup"><span data-stu-id="50698-110">To configure Visual Studio 2005 to debug an XBAP that calls a Web service:</span></span>

1. <span data-ttu-id="50698-111">**솔루션 탐색기**에서 프로젝트를 선택한 상태에서 **프로젝트** 메뉴에서 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="50698-111">With a project selected in **Solution Explorer**, on the **Project** menu, click **Properties**.</span></span>

2. <span data-ttu-id="50698-112">**프로젝트 디자이너**에서 **디버그** 탭을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="50698-112">In the **Project Designer**, click the **Debug** tab.</span></span>

3. <span data-ttu-id="50698-113">**시작 작업** 섹션에서 **시작 외부 프로그램** 을 선택 하 고 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="50698-113">In the **Start Action** section, select **Start external program** and enter the following:</span></span>

     `C:\WINDOWS\System32\PresentationHost.exe`

4. <span data-ttu-id="50698-114">**시작 옵션** 섹션에서 **명령줄 인수** 텍스트 상자에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="50698-114">In the **Start Options** section, enter the following into the **Command line arguments** text box:</span></span>

     <span data-ttu-id="50698-115">*파일 이름* `-debug`</span><span class="sxs-lookup"><span data-stu-id="50698-115">`-debug`  *filename*</span></span>

     <span data-ttu-id="50698-116">**-Debug** 매개 변수에 대 한 *파일 이름* 값은 xbap 파일 이름입니다. 예를 들어:</span><span class="sxs-lookup"><span data-stu-id="50698-116">The *filename* value for the **-debug** parameter is the .xbap filename; for example:</span></span>

     `-debug c:\example.xbap`

> [!NOTE]
> <span data-ttu-id="50698-117">Visual Studio 2005 XAML 브라우저 응용 프로그램 (WPF) 프로젝트 템플릿을 사용 하 여 만든 솔루션에 대 한 기본 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="50698-117">This is the default configuration for solutions that are created with the Visual Studio 2005 XAML Browser Application (WPF) project template.</span></span>

1. <span data-ttu-id="50698-118">**솔루션 탐색기**에서 프로젝트를 선택한 상태에서 **프로젝트** 메뉴에서 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="50698-118">With a project selected in **Solution Explorer**, on the **Project** menu, click **Properties**.</span></span>

2. <span data-ttu-id="50698-119">**프로젝트 디자이너**에서 **디버그** 탭을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="50698-119">In the **Project Designer**, click the **Debug** tab.</span></span>

3. <span data-ttu-id="50698-120">**시작 옵션** 섹션의 명령줄 **인수** 텍스트 상자에 다음 명령줄 매개 변수를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="50698-120">In the **Start Options** section, add the following command-line parameter to the **Command line arguments** text box:</span></span>

     <span data-ttu-id="50698-121">`-debugSecurityZoneURL`  *URL*</span><span class="sxs-lookup"><span data-stu-id="50698-121">`-debugSecurityZoneURL`  *URL*</span></span>

     <span data-ttu-id="50698-122">**-DebugSecurityZoneURL** 매개 변수에 대 한 *url* 값은 응용 프로그램의 원본 사이트로 시뮬레이션 하려는 위치의 url입니다.</span><span class="sxs-lookup"><span data-stu-id="50698-122">The *URL* value for the **-debugSecurityZoneURL** parameter is the URL for the location that you want to simulate as being the site of origin of your application.</span></span>

 <span data-ttu-id="50698-123">예를 들어 다음 URL이 포함 된 웹 서비스를 사용 하는 XBAP (XAML 브라우저 응용 프로그램)를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="50698-123">As an example, consider a XAML browser application (XBAP) that uses a Web service with the following URL:</span></span>

 `http://services.msdn.microsoft.com/ContentServices/ContentService.asmx`

 <span data-ttu-id="50698-124">이 웹 서비스의 원본 사이트 URL은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="50698-124">The site of origin URL for this Web service is:</span></span>

 `http://services.msdn.microsoft.com`

 <span data-ttu-id="50698-125">따라서 **debugSecurityZoneURL** 명령줄 매개 변수 및 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="50698-125">Consequently, the complete **-debugSecurityZoneURL** command-line parameter and value is:</span></span>

 `-debugSecurityZoneURL http://services.msdn.microsoft.com`

## <a name="see-also"></a><span data-ttu-id="50698-126">참조</span><span class="sxs-lookup"><span data-stu-id="50698-126">See also</span></span>

- [<span data-ttu-id="50698-127">WPF 호스트(PresentationHost.exe)</span><span class="sxs-lookup"><span data-stu-id="50698-127">WPF Host (PresentationHost.exe)</span></span>](wpf-host-presentationhost-exe.md)
