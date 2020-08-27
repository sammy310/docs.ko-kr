---
ms.openlocfilehash: 115cd6be935ae12a1293f948a0f899c6c3ff0d78
ms.sourcegitcommit: cbb19e56d48cf88375d35d0c27554d4722761e0d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/19/2020
ms.locfileid: "88608466"
---
### <a name="winhttphandler-removed-from-net-runtime"></a><span data-ttu-id="e0f71-101">.NET 런타임에서 WinHttpHandler 제거됨</span><span class="sxs-lookup"><span data-stu-id="e0f71-101">WinHttpHandler removed from .NET runtime</span></span>

<span data-ttu-id="e0f71-102">`WinHttpHandler` 클래스가 *System.Net.Http.dll* 어셈블리에서 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e0f71-102">The `WinHttpHandler` class was removed from the *System.Net.Http.dll* assembly.</span></span> <span data-ttu-id="e0f71-103">이제 OOB(대역 외) [NuGet 패키지](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/)로만 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0f71-103">It's now available only as an out-of-band (OOB) [NuGet package](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="e0f71-104">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="e0f71-104">Version introduced</span></span>

<span data-ttu-id="e0f71-105">5.0</span><span class="sxs-lookup"><span data-stu-id="e0f71-105">5.0</span></span>

#### <a name="change-description"></a><span data-ttu-id="e0f71-106">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="e0f71-106">Change description</span></span>

<span data-ttu-id="e0f71-107">이전 .NET 버전에서는 <xref:System.Net.Http.WinHttpHandler> 클래스를 핵심 .NET 라이브러리의 일부로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0f71-107">In previous .NET versions, the <xref:System.Net.Http.WinHttpHandler> class is available as part of the core .NET libraries.</span></span> <span data-ttu-id="e0f71-108">.NET 5.0부터 <xref:System.Net.Http.WinHttpHandler> 클래스는 별도로 설치되는 [NuGet 패키지](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/)로만 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0f71-108">Starting in .NET 5.0, the <xref:System.Net.Http.WinHttpHandler> class is only available as a separately installed [NuGet package](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/).</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="e0f71-109">권장 조치</span><span class="sxs-lookup"><span data-stu-id="e0f71-109">Recommended action</span></span>

<span data-ttu-id="e0f71-110">[System.Net.Http.WinHttpHandler NuGet 패키지](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/)를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="e0f71-110">Install the [System.Net.Http.WinHttpHandler NuGet package](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/).</span></span> <span data-ttu-id="e0f71-111">또는 WinHTTP 관련 기능이 필요하지 않은 경우 <xref:System.Net.Http.SocketsHttpHandler>를 대신 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e0f71-111">Or, if you don't require WinHTTP-specific features, use <xref:System.Net.Http.SocketsHttpHandler> instead.</span></span>

#### <a name="category"></a><span data-ttu-id="e0f71-112">범주</span><span class="sxs-lookup"><span data-stu-id="e0f71-112">Category</span></span>

<span data-ttu-id="e0f71-113">네트워킹</span><span class="sxs-lookup"><span data-stu-id="e0f71-113">Networking</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="e0f71-114">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="e0f71-114">Affected APIs</span></span>

- <xref:System.Net.Http.WinHttpHandler?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Net.Http.WinHttpHandler`

-->
