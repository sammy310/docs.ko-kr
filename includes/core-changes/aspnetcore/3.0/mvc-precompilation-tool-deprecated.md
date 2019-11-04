---
ms.openlocfilehash: 3f702febc78488b9413ec9303ded211493650f02
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2019
ms.locfileid: "73198511"
---
### <a name="mvc-precompilation-tool-deprecated"></a><span data-ttu-id="f5c41-101">MVC: 미리 컴파일 도구가 사용되지 않음</span><span class="sxs-lookup"><span data-stu-id="f5c41-101">MVC: Precompilation tool deprecated</span></span>

<span data-ttu-id="f5c41-102">ASP.NET Core 1.1에서는 Razor 파일( *.cshtml* 파일)의 게시 시간 컴파일 지원을 추가하기 위해 `Microsoft.AspNetCore.Mvc.Razor.ViewCompilation`(MVC 미리 컴파일 도구) 패키지가 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f5c41-102">In ASP.NET Core 1.1, the `Microsoft.AspNetCore.Mvc.Razor.ViewCompilation` (MVC precompilation tool) package was introduced to add support for publish-time compilation of Razor files (*.cshtml* files).</span></span> <span data-ttu-id="f5c41-103">ASP.NET Core 2.1에서는 [Razor SDK](/aspnet/core/razor-pages/sdk?view=aspnetcore-2.1)가 미리 컴파일 도구의 기능을 확장하기 위해 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f5c41-103">In ASP.NET Core 2.1, the [Razor SDK](/aspnet/core/razor-pages/sdk?view=aspnetcore-2.1) was introduced to expand upon features of the precompilation tool.</span></span> <span data-ttu-id="f5c41-104">Razor SDK는 Razor 파일의 빌드 및 게시 시간 컴파일에 대한 지원을 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="f5c41-104">The Razor SDK added support for build- and publish-time compilation of Razor files.</span></span> <span data-ttu-id="f5c41-105">SDK는 앱 시작 시간을 개선하면서 빌드 시 *.cshtml* 파일의 정확성을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f5c41-105">The SDK verifies the correctness of *.cshtml* files at build time while improving on app startup time.</span></span> <span data-ttu-id="f5c41-106">Razor SDK는 기본적으로 켜져 있으며 사용을 시작하는 데 제스처는 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f5c41-106">The Razor SDK is on by default, and no gesture is required to start using it.</span></span>

<span data-ttu-id="f5c41-107">ASP.NET Core 3.0에서는 ASP.NET Core 1.1-era MVC 미리 컴파일 도구가 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f5c41-107">In ASP.NET Core 3.0, the ASP.NET Core 1.1-era MVC precompilation tool was removed.</span></span> <span data-ttu-id="f5c41-108">이전 패키지 버전은 패치 릴리스에서 중요한 버그 및 보안 픽스를 계속 받습니다.</span><span class="sxs-lookup"><span data-stu-id="f5c41-108">Earlier package versions will continue receiving important bug and security fixes in the patch release.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="f5c41-109">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="f5c41-109">Version introduced</span></span>

<span data-ttu-id="f5c41-110">3.0</span><span class="sxs-lookup"><span data-stu-id="f5c41-110">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="f5c41-111">이전 동작</span><span class="sxs-lookup"><span data-stu-id="f5c41-111">Old behavior</span></span>

<span data-ttu-id="f5c41-112">`Microsoft.AspNetCore.Mvc.Razor.ViewCompilation` 패키지는 MVC Razor 뷰를 미리 컴파일하는 데 사용되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f5c41-112">The `Microsoft.AspNetCore.Mvc.Razor.ViewCompilation` package was used to pre-compile MVC Razor views.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="f5c41-113">새 동작</span><span class="sxs-lookup"><span data-stu-id="f5c41-113">New behavior</span></span>

<span data-ttu-id="f5c41-114">Razor SDK는 기본적으로 이 기능을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="f5c41-114">The Razor SDK natively supports this functionality.</span></span> <span data-ttu-id="f5c41-115">`Microsoft.AspNetCore.Mvc.Razor.ViewCompilation` 패키지가 더 이상 업데이트되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f5c41-115">The `Microsoft.AspNetCore.Mvc.Razor.ViewCompilation` package is no longer updated.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="f5c41-116">변경 이유</span><span class="sxs-lookup"><span data-stu-id="f5c41-116">Reason for change</span></span>

<span data-ttu-id="f5c41-117">Razor SDK는 더 많은 기능을 제공하고 빌드 시 *.cshtml* 파일의 정확성을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f5c41-117">The Razor SDK provides more functionality and verifies the correctness of *.cshtml* files at build time.</span></span> <span data-ttu-id="f5c41-118">또한 SDK는 앱 시작 시간을 개선합니다.</span><span class="sxs-lookup"><span data-stu-id="f5c41-118">The SDK also improves app startup time.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="f5c41-119">권장 작업</span><span class="sxs-lookup"><span data-stu-id="f5c41-119">Recommended action</span></span>

<span data-ttu-id="f5c41-120">ASP.NET Core 2.1 이상 사용자의 경우 [Razor SDK](/aspnet/core/razor-pages/sdk?view=aspnetcore-3.0)에서 미리 컴파일에 대한 기본 지원을 사용하도록 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="f5c41-120">For users of ASP.NET Core 2.1 or later, update to use the native support for precompilation in the [Razor SDK](/aspnet/core/razor-pages/sdk?view=aspnetcore-3.0).</span></span> <span data-ttu-id="f5c41-121">버그 또는 누락된 기능으로 인해 Razor SDK로 마이그레이션할 수 없는 경우 [aspnet/AspNetCore](https://github.com/aspnet/AspNetCore/issues)에서 문제를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f5c41-121">If bugs or missing features prevent migration to the Razor SDK, open an issue at [aspnet/AspNetCore](https://github.com/aspnet/AspNetCore/issues).</span></span>

#### <a name="category"></a><span data-ttu-id="f5c41-122">범주</span><span class="sxs-lookup"><span data-stu-id="f5c41-122">Category</span></span>

<span data-ttu-id="f5c41-123">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="f5c41-123">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="f5c41-124">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="f5c41-124">Affected APIs</span></span>

<span data-ttu-id="f5c41-125">없음</span><span class="sxs-lookup"><span data-stu-id="f5c41-125">None</span></span>

<!-- 

### Affected APIs

Not detectable via API analysis

-->
