---
ms.openlocfilehash: e5355387d5cb6d9e6de89f5b85e64bc100b32ae1
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "72522664"
---
### <a name="spas-spaservices-and-nodeservices-no-longer-fall-back-to-console-logger"></a><span data-ttu-id="0aba4-101">SPA: SpaServices 및 NodeServices가 더 이상 콘솔 로거로 대체되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0aba4-101">SPAs: SpaServices and NodeServices no longer fall back to console logger</span></span>

<span data-ttu-id="0aba4-102">로깅을 구성하지 않으면 <xref:Microsoft.AspNetCore.SpaServices?displayProperty=nameWithType> 및 <xref:Microsoft.AspNetCore.NodeServices?displayProperty=nameWithType>에 콘솔 로그가 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0aba4-102"><xref:Microsoft.AspNetCore.SpaServices?displayProperty=nameWithType> and <xref:Microsoft.AspNetCore.NodeServices?displayProperty=nameWithType> won't display console logs unless logging is configured.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="0aba4-103">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="0aba4-103">Version introduced</span></span>

<span data-ttu-id="0aba4-104">3.0</span><span class="sxs-lookup"><span data-stu-id="0aba4-104">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="0aba4-105">이전 동작</span><span class="sxs-lookup"><span data-stu-id="0aba4-105">Old behavior</span></span>

<span data-ttu-id="0aba4-106">로깅이 구성되지 않은 경우 `Microsoft.AspNetCore.SpaServices` 및 `Microsoft.AspNetCore.NodeServices`는 콘솔 로거를 자동으로 만드는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0aba4-106">`Microsoft.AspNetCore.SpaServices` and `Microsoft.AspNetCore.NodeServices` used to automatically create a console logger when logging isn't configured.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="0aba4-107">새 동작</span><span class="sxs-lookup"><span data-stu-id="0aba4-107">New behavior</span></span>

<span data-ttu-id="0aba4-108">로깅을 구성하지 않으면 `Microsoft.AspNetCore.SpaServices` 및 `Microsoft.AspNetCore.NodeServices`에 콘솔 로그가 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0aba4-108">`Microsoft.AspNetCore.SpaServices` and `Microsoft.AspNetCore.NodeServices` won't display console logs unless logging is configured.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="0aba4-109">변경 이유</span><span class="sxs-lookup"><span data-stu-id="0aba4-109">Reason for change</span></span>

<span data-ttu-id="0aba4-110">다른 ASP.NET Core 패키지에서 로깅을 구현하는 방법에 맞춰 조정할 필요가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0aba4-110">There's a need to align with how other ASP.NET Core packages implement logging.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="0aba4-111">권장 작업</span><span class="sxs-lookup"><span data-stu-id="0aba4-111">Recommended action</span></span>

<span data-ttu-id="0aba4-112">이전 동작이 필요한 경우 콘솔 로깅을 구성하려면 `Setup.ConfigureServices` 메서드에 `services.AddLogging(builder => builder.AddConsole())`을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0aba4-112">If the old behavior is required, to configure console logging, add `services.AddLogging(builder => builder.AddConsole())` to your `Setup.ConfigureServices` method.</span></span>

#### <a name="category"></a><span data-ttu-id="0aba4-113">범주</span><span class="sxs-lookup"><span data-stu-id="0aba4-113">Category</span></span>

<span data-ttu-id="0aba4-114">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="0aba4-114">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="0aba4-115">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="0aba4-115">Affected APIs</span></span>

<span data-ttu-id="0aba4-116">없음</span><span class="sxs-lookup"><span data-stu-id="0aba4-116">None</span></span>

<!--

#### Affected APIs

Not detectable via API analysis

-->
