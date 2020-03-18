---
ms.openlocfilehash: 959f3959c28c7d0159be7a213986345e2865b9a2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "72394204"
---
### <a name="shared-framework-removed-microsoftaspnetcoreall"></a><span data-ttu-id="590b1-101">공유 프레임워크: 제거된 Microsoft.AspNetCore.All</span><span class="sxs-lookup"><span data-stu-id="590b1-101">Shared framework: Removed Microsoft.AspNetCore.All</span></span>

<span data-ttu-id="590b1-102">ASP.NET Core 3.0부터 `Microsoft.AspNetCore.All` 메타패키지 및 일치하는 `Microsoft.AspNetCore.All` 공유 프레임워크가 더 이상 생성되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="590b1-102">Starting in ASP.NET Core 3.0, the `Microsoft.AspNetCore.All` metapackage and the matching `Microsoft.AspNetCore.All` shared framework are no longer produced.</span></span> <span data-ttu-id="590b1-103">이 패키지는 ASP.NET Core 2.2에서 사용할 수 있으며 ASP.NET Core 2.1에서 서비스 업데이트를 계속 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="590b1-103">This package is available in ASP.NET Core 2.2 and will continue to receive servicing updates in ASP.NET Core 2.1.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="590b1-104">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="590b1-104">Version introduced</span></span>

<span data-ttu-id="590b1-105">3.0</span><span class="sxs-lookup"><span data-stu-id="590b1-105">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="590b1-106">이전 동작</span><span class="sxs-lookup"><span data-stu-id="590b1-106">Old behavior</span></span>

<span data-ttu-id="590b1-107">앱은 `Microsoft.AspNetCore.All` 메타패키지를 사용하여 .NET Core에서 `Microsoft.AspNetCore.All` 공유 프레임워크를 대상으로 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="590b1-107">Apps could use the `Microsoft.AspNetCore.All` metapackage to target the `Microsoft.AspNetCore.All` shared framework on .NET Core.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="590b1-108">새 동작</span><span class="sxs-lookup"><span data-stu-id="590b1-108">New behavior</span></span>

<span data-ttu-id="590b1-109">.NET Core 3.0에는 `Microsoft.AspNetCore.All` 공유 프레임워크가 포함되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="590b1-109">.NET Core 3.0 doesn't include a `Microsoft.AspNetCore.All` shared framework.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="590b1-110">변경 이유</span><span class="sxs-lookup"><span data-stu-id="590b1-110">Reason for change</span></span>

<span data-ttu-id="590b1-111">`Microsoft.AspNetCore.All` 메타패키지에는 많은 수의 외부 종속성이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="590b1-111">The `Microsoft.AspNetCore.All` metapackage included a large number of external dependencies.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="590b1-112">권장 조치</span><span class="sxs-lookup"><span data-stu-id="590b1-112">Recommended action</span></span>

<span data-ttu-id="590b1-113">`Microsoft.AspNetCore.App` 프레임워크를 사용하도록 프로젝트를 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="590b1-113">Migrate your project to use the `Microsoft.AspNetCore.App` framework.</span></span> <span data-ttu-id="590b1-114">이전에 `Microsoft.AspNetCore.All`에서 사용할 수 있었던 구성 요소는 NuGet에서 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="590b1-114">Components that were previously available in `Microsoft.AspNetCore.All` are still available on NuGet.</span></span> <span data-ttu-id="590b1-115">이러한 구성 요소는 이제 공유 프레임워크에 포함되지 않고 앱과 함께 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="590b1-115">Those components are now deployed with your app instead of being included in the shared framework.</span></span>

#### <a name="category"></a><span data-ttu-id="590b1-116">범주</span><span class="sxs-lookup"><span data-stu-id="590b1-116">Category</span></span>

<span data-ttu-id="590b1-117">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="590b1-117">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="590b1-118">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="590b1-118">Affected APIs</span></span>

<span data-ttu-id="590b1-119">없음</span><span class="sxs-lookup"><span data-stu-id="590b1-119">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
