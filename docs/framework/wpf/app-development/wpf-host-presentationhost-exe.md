---
title: WPF 호스트(PresentationHost.exe)
ms.date: 03/30/2017
helpviewer_keywords:
- WPF Host application [WPF]
- PresentationHost.exe
ms.assetid: 3215bfa1-722c-4ac8-a7c5-bdd02d30afbd
ms.openlocfilehash: 981e518a55f179c2fbf44534783c80fb230e4ecf
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/01/2019
ms.locfileid: "73421121"
---
# <a name="wpf-host-presentationhostexe"></a><span data-ttu-id="68cbb-102">WPF 호스트(PresentationHost.exe)</span><span class="sxs-lookup"><span data-stu-id="68cbb-102">WPF Host (PresentationHost.exe)</span></span>
<span data-ttu-id="68cbb-103">Windows Presentation Foundation (WPF) 호스트 (Presentationhost.exe)는 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 응용 프로그램을 호환 브라우저 (Microsoft Internet Explorer 6 이상 포함)에서 호스팅할 수 있도록 하는 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="68cbb-103">Windows Presentation Foundation (WPF) Host (PresentationHost.exe) is the application that enables [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] applications to be hosted in compatible browsers (including Microsoft Internet Explorer 6 and later).</span></span> <span data-ttu-id="68cbb-104">기본적으로 Windows Presentation Foundation (WPF) 호스트는 브라우저에서 호스트 되는 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 콘텐츠에 대 한 셸 및 MIME 처리기로 등록 됩니다 .이 처리기에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="68cbb-104">By default, Windows Presentation Foundation (WPF) Host is registered as the shell and MIME handler for browser-hosted [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] content, which includes:</span></span>  
  
- <span data-ttu-id="68cbb-105">느슨하게 압축되지 않은 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일(.xaml).</span><span class="sxs-lookup"><span data-stu-id="68cbb-105">Loose (uncompiled) [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] files (.xaml).</span></span>  
  
- <span data-ttu-id="68cbb-106">XBAP (XAML 브라우저 응용 프로그램) (xbap).</span><span class="sxs-lookup"><span data-stu-id="68cbb-106">XAML browser application (XBAP) (.xbap).</span></span>  
  
 <span data-ttu-id="68cbb-107">이러한 형식의 파일에 대해서는 WPF (Windows Presentation Foundation) 호스트:</span><span class="sxs-lookup"><span data-stu-id="68cbb-107">For files of these types, Windows Presentation Foundation (WPF) Host:</span></span>  
  
- <span data-ttu-id="68cbb-108">Windows Presentation Foundation (WPF) 콘텐츠를 호스팅하기 위해 등록 된 HTML 처리기를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="68cbb-108">Launches the registered HTML handler to host the Windows Presentation Foundation (WPF) content.</span></span>  
  
- <span data-ttu-id="68cbb-109">필요한 CLR (공용 언어 런타임) 및 Windows Presentation Foundation (WPF) 어셈블리의 올바른 버전을 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="68cbb-109">Loads the right versions of the required common language runtime (CLR) and Windows Presentation Foundation (WPF) assemblies.</span></span>  
  
- <span data-ttu-id="68cbb-110">배포 영역에 대해 적절한 권한 수준이 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="68cbb-110">Ensures the appropriate permission levels for the zone of deployment are in place.</span></span>  
  
 <span data-ttu-id="68cbb-111">이 항목에서는 PresentationHost.exe에서 사용할 수 있는 명령줄 매개 변수를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="68cbb-111">This topic describes the command line parameters that can be used with PresentationHost.exe.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="68cbb-112">사용 현황</span><span class="sxs-lookup"><span data-stu-id="68cbb-112">Usage</span></span>  
 `PresentationHost.exe [parameters] uri|filename`  
  
## <a name="parameters"></a><span data-ttu-id="68cbb-113">매개 변수</span><span class="sxs-lookup"><span data-stu-id="68cbb-113">Parameters</span></span>  
  
|<span data-ttu-id="68cbb-114">매개 변수</span><span class="sxs-lookup"><span data-stu-id="68cbb-114">Parameter</span></span>|<span data-ttu-id="68cbb-115">설명</span><span class="sxs-lookup"><span data-stu-id="68cbb-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="68cbb-116">filename</span><span class="sxs-lookup"><span data-stu-id="68cbb-116">filename</span></span>|<span data-ttu-id="68cbb-117">활성화할 파일의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="68cbb-117">The path of the file to be activated.</span></span> <span data-ttu-id="68cbb-118">URI 일 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68cbb-118">Can also be a URI.</span></span>|  
|<span data-ttu-id="68cbb-119">-debug</span><span class="sxs-lookup"><span data-stu-id="68cbb-119">-debug</span></span>|<span data-ttu-id="68cbb-120">애플리케이션을 활성화할 때 저장소에서 커밋하거나 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="68cbb-120">When activating an application, does not commit it to or run it from the store.</span></span> <span data-ttu-id="68cbb-121">이는 로컬 파일이 활성화된 경우에만 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="68cbb-121">This only works when a local file is activated.</span></span>|  
|<span data-ttu-id="68cbb-122">-debugSecurityZoneURL \<url></span><span class="sxs-lookup"><span data-stu-id="68cbb-122">-debugSecurityZoneURL \<url></span></span>|<span data-ttu-id="68cbb-123">URL 값과 함께 사용 하 여 지정 된 URL에서 응용 프로그램을 배포 하는 것 처럼 응용 프로그램을 Presentationhost.exe에 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="68cbb-123">Used with a URL value to indicate to PresentationHost.exe that an application should be debugged as if it were deployed from the specified URL.</span></span> <span data-ttu-id="68cbb-124">이를 통해 배포 영역과 원본 사이트가 모두 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="68cbb-124">This determines both the deployment zone and the site of origin.</span></span>|  
|<span data-ttu-id="68cbb-125">-embedding</span><span class="sxs-lookup"><span data-stu-id="68cbb-125">-embedding</span></span>|<span data-ttu-id="68cbb-126">OLE에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="68cbb-126">Required by OLE.</span></span> <span data-ttu-id="68cbb-127">`-event` 또는 `-debug` 매개 변수가 지정된 경우 `-embedding` 매개 변수가 내부적으로 설정되기 때문에 해당 매개 변수를 지정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="68cbb-127">If the `-event` or `-debug` parameter are specified, it is not necessary to specify the `-embedding` parameter, since that parameter is set internally.</span></span>|  
|<span data-ttu-id="68cbb-128">-event \<eventname></span><span class="sxs-lookup"><span data-stu-id="68cbb-128">-event \<eventname></span></span>|<span data-ttu-id="68cbb-129">이 이름으로 이벤트를 연 다음 PresentationHost.exe가 초기화되고 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 콘텐츠를 호스팅할 준비가 되면 이 이벤트에 신호를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="68cbb-129">Open the event with this name and signal it when PresentationHost.exe is initialized and ready to host [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] content.</span></span> <span data-ttu-id="68cbb-130">이벤트가 아직 만들어지지 않은 등의 이유로 인해 이벤트를 여는 데 오류가 발생하면 PresentationHost.exe가 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="68cbb-130">PresentationHost.exe will terminate if there was an error opening the event, such as if it has not already been created.</span></span>|  
|<span data-ttu-id="68cbb-131">-launchApplication \<url></span><span class="sxs-lookup"><span data-stu-id="68cbb-131">-launchApplication \<url></span></span>|<span data-ttu-id="68cbb-132">지정 된 URL에서 독립 실행형 ClickOnce 응용 프로그램을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="68cbb-132">Launches a standalone ClickOnce application from the specified URL.</span></span> <span data-ttu-id="68cbb-133">.NET 응용 프로그램과 관련 된 Internet Explorer 및 WinINet 보안 정책이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="68cbb-133">Internet Explorer and WinINet security policy concerning .NET applications are applied.</span></span>|  
  
## <a name="scenarios"></a><span data-ttu-id="68cbb-134">시나리오</span><span class="sxs-lookup"><span data-stu-id="68cbb-134">Scenarios</span></span>  
  
### <a name="shell-handler"></a><span data-ttu-id="68cbb-135">셸 처리기</span><span class="sxs-lookup"><span data-stu-id="68cbb-135">Shell Handler</span></span>  
 `PresentationHost.exe example.xbap`  
  
### <a name="mime-handler"></a><span data-ttu-id="68cbb-136">MIME 처리기</span><span class="sxs-lookup"><span data-stu-id="68cbb-136">MIME Handler</span></span>  
 `PresentationHost.exe -embedding example.xbap`  
  
### <a name="visual-studio-debugging"></a><span data-ttu-id="68cbb-137">Visual Studio 디버깅</span><span class="sxs-lookup"><span data-stu-id="68cbb-137">Visual Studio Debugging</span></span>  
 `PresentationHost.exe -debug example.xbap`  
  
### <a name="visual-studio-debugging-in-zone"></a><span data-ttu-id="68cbb-138">영역에서 Visual Studio 디버깅</span><span class="sxs-lookup"><span data-stu-id="68cbb-138">Visual Studio Debugging In Zone</span></span>  
 `PresentationHost.exe -debug -debugSecurityZoneURL http://www.example.com c:\folderpath\example.xbap`  
  
## <a name="see-also"></a><span data-ttu-id="68cbb-139">참조</span><span class="sxs-lookup"><span data-stu-id="68cbb-139">See also</span></span>

- [<span data-ttu-id="68cbb-140">Security</span><span class="sxs-lookup"><span data-stu-id="68cbb-140">Security</span></span>](../security-wpf.md)
