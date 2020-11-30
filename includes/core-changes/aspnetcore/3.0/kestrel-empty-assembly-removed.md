---
ms.openlocfilehash: 1c9c899d77dd69e185281d98bfec18ce73d80815
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032589"
---
### <a name="kestrel-empty-https-assembly-removed"></a><span data-ttu-id="888c2-101">Kestrel: 빈 HTTPS 어셈블리가 제거됨</span><span class="sxs-lookup"><span data-stu-id="888c2-101">Kestrel: Empty HTTPS assembly removed</span></span>

<span data-ttu-id="888c2-102"><xref:Microsoft.AspNetCore.Server.Kestrel.Https?displayProperty=fullName> 어셈블리가 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="888c2-102">The assembly <xref:Microsoft.AspNetCore.Server.Kestrel.Https?displayProperty=fullName> has been removed.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="888c2-103">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="888c2-103">Version introduced</span></span>

<span data-ttu-id="888c2-104">3.0</span><span class="sxs-lookup"><span data-stu-id="888c2-104">3.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="888c2-105">변경 이유</span><span class="sxs-lookup"><span data-stu-id="888c2-105">Reason for change</span></span>

<span data-ttu-id="888c2-106">ASP.NET Core 2.1에서 `Microsoft.AspNetCore.Server.Kestrel.Https`의 내용이 <xref:Microsoft.AspNetCore.Server.Kestrel.Core?displayProperty=fullName>으로 이동했습니다.</span><span class="sxs-lookup"><span data-stu-id="888c2-106">In ASP.NET Core 2.1, the contents of `Microsoft.AspNetCore.Server.Kestrel.Https` were moved to <xref:Microsoft.AspNetCore.Server.Kestrel.Core?displayProperty=fullName>.</span></span> <span data-ttu-id="888c2-107">이 변경은 `[TypeForwardedTo]` 특성을 사용하여 중단되지 않는 방식으로 수행되었습니다.</span><span class="sxs-lookup"><span data-stu-id="888c2-107">This change was done in a non-breaking way using `[TypeForwardedTo]` attributes.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="888c2-108">권장 조치</span><span class="sxs-lookup"><span data-stu-id="888c2-108">Recommended action</span></span>

- <span data-ttu-id="888c2-109">`Microsoft.AspNetCore.Server.Kestrel.Https` 2.0를 참조하는 라이브러리는 모든 ASP.NET Core 종속성을 2.1 이상으로 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="888c2-109">Libraries referencing `Microsoft.AspNetCore.Server.Kestrel.Https` 2.0 should update all ASP.NET Core dependencies to 2.1 or later.</span></span> <span data-ttu-id="888c2-110">그렇지 않으면 ASP.NET Core 3.0 앱에 로드될 때 중단될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="888c2-110">Otherwise, they may break when loaded into an ASP.NET Core 3.0 app.</span></span>
- <span data-ttu-id="888c2-111">ASP.NET Core 2.1 이상을 대상으로 하는 앱 및 라이브러리는 `Microsoft.AspNetCore.Server.Kestrel.Https` NuGet 패키지에 대한 직접 참조를 모두 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="888c2-111">Apps and libraries targeting ASP.NET Core 2.1 and later should remove any direct references to the `Microsoft.AspNetCore.Server.Kestrel.Https` NuGet package.</span></span>

#### <a name="category"></a><span data-ttu-id="888c2-112">범주</span><span class="sxs-lookup"><span data-stu-id="888c2-112">Category</span></span>

<span data-ttu-id="888c2-113">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="888c2-113">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="888c2-114">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="888c2-114">Affected APIs</span></span>

<span data-ttu-id="888c2-115">없음</span><span class="sxs-lookup"><span data-stu-id="888c2-115">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
