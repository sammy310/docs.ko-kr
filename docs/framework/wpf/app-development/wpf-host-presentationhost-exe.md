---
title: WPF 호스트(PresentationHost.exe)
ms.date: 03/30/2017
helpviewer_keywords:
- WPF Host application [WPF]
- PresentationHost.exe
ms.assetid: 3215bfa1-722c-4ac8-a7c5-bdd02d30afbd
ms.openlocfilehash: 88e4c6895039c84a57ed215a37a10a4b68851b2d
ms.sourcegitcommit: 10736f243dd2296212e677e207102c463e5f143e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2019
ms.locfileid: "68817918"
---
# <a name="wpf-host-presentationhostexe"></a><span data-ttu-id="b8cba-102">WPF 호스트(PresentationHost.exe)</span><span class="sxs-lookup"><span data-stu-id="b8cba-102">WPF Host (PresentationHost.exe)</span></span>
<span data-ttu-id="b8cba-103">WPF (Windows Presentation Foundation) 호스트 (presentationhost.exe)는 응용 프로그램을 호환 브라우저 ( [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Microsoft Internet Explorer 6 이상 포함)에서 호스팅할 수 있도록 하는 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="b8cba-103">Windows Presentation Foundation (WPF) Host (PresentationHost.exe) is the application that enables [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] applications to be hosted in compatible browsers (including Microsoft Internet Explorer 6 and later).</span></span> <span data-ttu-id="b8cba-104">기본적으로 Windows Presentation Foundation (WPF) 호스트는 브라우저에서 호스트 [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 되는 콘텐츠에 대 한 셸 및 처리기로 등록 됩니다. 여기에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8cba-104">By default, Windows Presentation Foundation (WPF) Host is registered as the shell and [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] handler for browser-hosted [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] content, which includes:</span></span>  
  
- <span data-ttu-id="b8cba-105">느슨하게 압축되지 않은 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일(.xaml).</span><span class="sxs-lookup"><span data-stu-id="b8cba-105">Loose (uncompiled) [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] files (.xaml).</span></span>  
  
- [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)]<span data-ttu-id="b8cba-106">(.xbap).</span><span class="sxs-lookup"><span data-stu-id="b8cba-106">(.xbap).</span></span>  
  
 <span data-ttu-id="b8cba-107">이러한 형식의 파일에 대해서는 WPF (Windows Presentation Foundation) 호스트:</span><span class="sxs-lookup"><span data-stu-id="b8cba-107">For files of these types, Windows Presentation Foundation (WPF) Host:</span></span>  
  
- <span data-ttu-id="b8cba-108">Windows Presentation Foundation (WPF) 콘텐츠를 호스팅하기 위해 등록 된 HTML 처리기를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8cba-108">Launches the registered HTML handler to host the Windows Presentation Foundation (WPF) content.</span></span>  
  
- <span data-ttu-id="b8cba-109">필요한 CLR (공용 언어 런타임) 및 Windows Presentation Foundation (WPF) 어셈블리의 올바른 버전을 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8cba-109">Loads the right versions of the required common language runtime (CLR) and Windows Presentation Foundation (WPF) assemblies.</span></span>  
  
- <span data-ttu-id="b8cba-110">배포 영역에 대해 적절한 권한 수준이 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b8cba-110">Ensures the appropriate permission levels for the zone of deployment are in place.</span></span>  
  
 <span data-ttu-id="b8cba-111">이 항목에서는 PresentationHost.exe에서 사용할 수 있는 명령줄 매개 변수를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b8cba-111">This topic describes the command line parameters that can be used with PresentationHost.exe.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="b8cba-112">용도</span><span class="sxs-lookup"><span data-stu-id="b8cba-112">Usage</span></span>  
 `PresentationHost.exe [parameters] uri|filename`  
  
## <a name="parameters"></a><span data-ttu-id="b8cba-113">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b8cba-113">Parameters</span></span>  
  
|<span data-ttu-id="b8cba-114">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b8cba-114">Parameter</span></span>|<span data-ttu-id="b8cba-115">설명</span><span class="sxs-lookup"><span data-stu-id="b8cba-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b8cba-116">filename</span><span class="sxs-lookup"><span data-stu-id="b8cba-116">filename</span></span>|<span data-ttu-id="b8cba-117">활성화할 파일의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="b8cba-117">The path of the file to be activated.</span></span> <span data-ttu-id="b8cba-118">[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]가 될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8cba-118">Can also be a [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span></span>|  
|<span data-ttu-id="b8cba-119">-debug</span><span class="sxs-lookup"><span data-stu-id="b8cba-119">-debug</span></span>|<span data-ttu-id="b8cba-120">애플리케이션을 활성화할 때 저장소에서 커밋하거나 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b8cba-120">When activating an application, does not commit it to or run it from the store.</span></span> <span data-ttu-id="b8cba-121">이는 로컬 파일이 활성화된 경우에만 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="b8cba-121">This only works when a local file is activated.</span></span>|  
|<span data-ttu-id="b8cba-122">-debugSecurityZoneURL \<url></span><span class="sxs-lookup"><span data-stu-id="b8cba-122">-debugSecurityZoneURL \<url></span></span>|<span data-ttu-id="b8cba-123">지정된 [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)]에서 배포된 것처럼 애플리케이션이 디버깅되어야 함을 PresentationHost.exe에 알리기 위해 [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] 값과 함께 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8cba-123">Used with a [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] value to indicate to PresentationHost.exe that an application should be debugged as if it were deployed from the specified [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)].</span></span> <span data-ttu-id="b8cba-124">이를 통해 배포 영역과 원본 사이트가 모두 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8cba-124">This determines both the deployment zone and the site of origin.</span></span>|  
|<span data-ttu-id="b8cba-125">-embedding</span><span class="sxs-lookup"><span data-stu-id="b8cba-125">-embedding</span></span>|<span data-ttu-id="b8cba-126">OLE에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b8cba-126">Required by OLE.</span></span> <span data-ttu-id="b8cba-127">`-event` 또는 `-debug` 매개 변수가 지정된 경우 `-embedding` 매개 변수가 내부적으로 설정되기 때문에 해당 매개 변수를 지정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b8cba-127">If the `-event` or `-debug` parameter are specified, it is not necessary to specify the `-embedding` parameter, since that parameter is set internally.</span></span>|  
|<span data-ttu-id="b8cba-128">-event \<eventname></span><span class="sxs-lookup"><span data-stu-id="b8cba-128">-event \<eventname></span></span>|<span data-ttu-id="b8cba-129">이 이름으로 이벤트를 연 다음 PresentationHost.exe가 초기화되고 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 콘텐츠를 호스팅할 준비가 되면 이 이벤트에 신호를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="b8cba-129">Open the event with this name and signal it when PresentationHost.exe is initialized and ready to host [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] content.</span></span> <span data-ttu-id="b8cba-130">이벤트가 아직 만들어지지 않은 등의 이유로 인해 이벤트를 여는 데 오류가 발생하면 PresentationHost.exe가 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8cba-130">PresentationHost.exe will terminate if there was an error opening the event, such as if it has not already been created.</span></span>|  
|<span data-ttu-id="b8cba-131">-launchApplication \<url></span><span class="sxs-lookup"><span data-stu-id="b8cba-131">-launchApplication \<url></span></span>|<span data-ttu-id="b8cba-132">지정 된 URL에서 독립 실행형 ClickOnce 응용 프로그램을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8cba-132">Launches a standalone ClickOnce application from the specified URL.</span></span> <span data-ttu-id="b8cba-133">.NET 응용 프로그램과 관련 된 Internet Explorer 및 WinINet 보안 정책이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8cba-133">Internet Explorer and WinINet security policy concerning .NET applications are applied.</span></span>|  
  
## <a name="scenarios"></a><span data-ttu-id="b8cba-134">시나리오</span><span class="sxs-lookup"><span data-stu-id="b8cba-134">Scenarios</span></span>  
  
### <a name="shell-handler"></a><span data-ttu-id="b8cba-135">셸 처리기</span><span class="sxs-lookup"><span data-stu-id="b8cba-135">Shell Handler</span></span>  
 `PresentationHost.exe example.xbap`  
  
### <a name="mime-handler"></a><span data-ttu-id="b8cba-136">MIME 처리기</span><span class="sxs-lookup"><span data-stu-id="b8cba-136">MIME Handler</span></span>  
 `PresentationHost.exe -embedding example.xbap`  
  
### <a name="visual-studio-debugging"></a><span data-ttu-id="b8cba-137">Visual Studio 디버깅</span><span class="sxs-lookup"><span data-stu-id="b8cba-137">Visual Studio Debugging</span></span>  
 `PresentationHost.exe -debug example.xbap`  
  
### <a name="visual-studio-debugging-in-zone"></a><span data-ttu-id="b8cba-138">영역에서 Visual Studio 디버깅</span><span class="sxs-lookup"><span data-stu-id="b8cba-138">Visual Studio Debugging In Zone</span></span>  
 `PresentationHost.exe -debug -debugSecurityZoneURL http://www.example.com c:\folderpath\example.xbap`  
  
## <a name="see-also"></a><span data-ttu-id="b8cba-139">참고자료</span><span class="sxs-lookup"><span data-stu-id="b8cba-139">See also</span></span>

- [<span data-ttu-id="b8cba-140">보안</span><span class="sxs-lookup"><span data-stu-id="b8cba-140">Security</span></span>](../security-wpf.md)
