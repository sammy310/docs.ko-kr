---
title: IWpfHostSupport
ms.date: 03/30/2017
helpviewer_keywords:
- IWpfHostSupport interface [WPF]
ms.assetid: cc5a0281-de81-4cc1-87e4-0e46b1a811e9
ms.openlocfilehash: 85309e46403b2f22f9afb760d4c4ae370c39246b
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004096"
---
# <a name="iwpfhostsupport"></a><span data-ttu-id="b2766-102">IWpfHostSupport</span><span class="sxs-lookup"><span data-stu-id="b2766-102">IWpfHostSupport</span></span>
<span data-ttu-id="b2766-103">Presentationhost.exe를 통해 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 콘텐츠를 호스트 하는 응용 프로그램은이 인터페이스를 구현 하 여 호스트와 Presentationhost.exe 간의 통합 지점을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2766-103">Applications that host [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] content via PresentationHost.exe implement this interface to provide a point of integration between the host and PresentationHost.exe.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b2766-104">설명</span><span class="sxs-lookup"><span data-stu-id="b2766-104">Remarks</span></span>  
 <span data-ttu-id="b2766-105">웹 브라우저와 같은 [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] 응용 프로그램은 @no__t 1 및 느슨한 XAML을 포함 하 여 WPF 콘텐츠를 호스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2766-105">[!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] applications such as Web browsers can host WPF content, including [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] and loose XAML.</span></span> <span data-ttu-id="b2766-106">WPF 콘텐츠를 호스트 하기 위해 [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] 응용 프로그램은 [WebBrowser 컨트롤](https://go.microsoft.com/fwlink/?LinkId=97911)의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b2766-106">To host WPF content, [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] applications create an instance of the [WebBrowser control](https://go.microsoft.com/fwlink/?LinkId=97911).</span></span> <span data-ttu-id="b2766-107">호스트 되는 WPF는 호스트에 호스팅된 WPF 콘텐츠를 제공 하는 Presentationhost.exe의 인스턴스를 만들어 [WebBrowser 컨트롤](https://go.microsoft.com/fwlink/?LinkId=97911)에 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2766-107">To be hosted, WPF creates an instance of PresentationHost.exe, which provides the hosted WPF content to the host for display in the [WebBrowser control](https://go.microsoft.com/fwlink/?LinkId=97911).</span></span>  
  
 <span data-ttu-id="b2766-108">@No__t-0에서 통합을 사용 하도록 설정 하면 Presentationhost.exe에서 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2766-108">The integration enabled by `IWpfHostSupport` allows PresentationHost.exe to:</span></span>  
  
- <span data-ttu-id="b2766-109">호스트 응용 프로그램이 관심 있는 원시 입력 장치 (휴먼 인터페이스 장치)를 검색 하 고 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2766-109">Discover and register with the raw input devices (Human Interface Devices) that the host application is interested in.</span></span>  
  
- <span data-ttu-id="b2766-110">등록 된 원시 입력 장치에서 입력 메시지를 수신 하 고 호스트 응용 프로그램에 적절 한 메시지를 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2766-110">Receive input messages from the registered raw input devices and forward appropriate messages to the host application.</span></span>  
  
- <span data-ttu-id="b2766-111">호스트 응용 프로그램에서 사용자 지정 진행률 및 오류 사용자 인터페이스를 쿼리 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2766-111">Query the host application for custom progress and error user interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b2766-112">이 API는 로컬 클라이언트 컴퓨터에서만 사용할 수 있도록 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2766-112">This API is only intended and supported for use on the local client machine</span></span>  
  
## <a name="members"></a><span data-ttu-id="b2766-113">멤버</span><span class="sxs-lookup"><span data-stu-id="b2766-113">Members</span></span>  
  
|<span data-ttu-id="b2766-114">멤버</span><span class="sxs-lookup"><span data-stu-id="b2766-114">Member</span></span>|<span data-ttu-id="b2766-115">Description</span><span class="sxs-lookup"><span data-stu-id="b2766-115">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b2766-116">GetRawInputDevices</span><span class="sxs-lookup"><span data-stu-id="b2766-116">GetRawInputDevices</span></span>](getrawinputdevices.md)|<span data-ttu-id="b2766-117">PresentationHost.exe가 호스트 애플리케이션과 관련된 원시 입력 디바이스(휴먼 인터페이스 디바이스)를 검색할 수 있게 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2766-117">Allows PresentationHost.exe to discover the raw input devices (Human Interface Devices) that the host application is interested in.</span></span>|  
|[<span data-ttu-id="b2766-118">FilterInputMessage</span><span class="sxs-lookup"><span data-stu-id="b2766-118">FilterInputMessage</span></span>](filterinputmessage.md)|<span data-ttu-id="b2766-119">E_NOTIMPL이 반환되지 않는 한 메시지를 받을 때마다 PresentationHost.exe에서 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2766-119">Called by PresentationHost.exe whenever a message is received unless E_NOTIMPL is returned.</span></span>|  
|[<span data-ttu-id="b2766-120">GetCustomUI</span><span class="sxs-lookup"><span data-stu-id="b2766-120">GetCustomUI</span></span>](getcustomui.md)|<span data-ttu-id="b2766-121">기본적으로 Presentationhost.exe는 WPF 콘텐츠가 배포 될 때 표시 되는 고유한 배포 진행률 및 배포 오류 사용자 인터페이스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2766-121">By default, PresentationHost.exe provides its own deployment progress and deployment error user interfaces that are displayed when WPF content is deployed.</span></span>|
