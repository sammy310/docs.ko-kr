---
ms.openlocfilehash: 6679e38aefa7d61ce430dc5375ff3b35c641ea27
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394174"
---
### <a name="identity-signinasync-throws-exception-for-unauthenticated-identity"></a><span data-ttu-id="e793d-101">ID: SignInAsync는 인증되지 않은 ID에 대해 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="e793d-101">Identity: SignInAsync throws exception for unauthenticated identity</span></span>

<span data-ttu-id="e793d-102">기본적으로 `SignInAsync`는 `IsAuthenticated`가 `false`인 보안 주체/ID에 대해 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="e793d-102">By default, `SignInAsync` throws an exception for principals / identities in which `IsAuthenticated` is `false`.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="e793d-103">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="e793d-103">Version introduced</span></span>

<span data-ttu-id="e793d-104">3.0</span><span class="sxs-lookup"><span data-stu-id="e793d-104">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="e793d-105">이전 동작</span><span class="sxs-lookup"><span data-stu-id="e793d-105">Old behavior</span></span>

<span data-ttu-id="e793d-106">`SignInAsync`는 `IsAuthenticated`가 `false`인 ID를 포함하여 모든 보안 주체/ID를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="e793d-106">`SignInAsync` accepts any principals / identities, including identities in which `IsAuthenticated` is `false`.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="e793d-107">새 동작</span><span class="sxs-lookup"><span data-stu-id="e793d-107">New behavior</span></span>

<span data-ttu-id="e793d-108">기본적으로 `SignInAsync`는 `IsAuthenticated`가 `false`인 보안 주체/ID에 대해 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="e793d-108">By default, `SignInAsync` throws an exception for principals / identities in which `IsAuthenticated` is `false`.</span></span> <span data-ttu-id="e793d-109">이 동작을 표시하지 않는 새로운 플래그가 있지만 기본 동작이 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e793d-109">There's a new flag to suppress this behavior, but the default behavior has changed.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="e793d-110">변경 이유</span><span class="sxs-lookup"><span data-stu-id="e793d-110">Reason for change</span></span>

<span data-ttu-id="e793d-111">기본적으로 이러한 보안 주체는 `[Authorize]` / `RequireAuthenticatedUser()`에 의해 거부되었기 때문에 이전 동작은 문제가 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="e793d-111">The old behavior was problematic because, by default, these principals were rejected by `[Authorize]` / `RequireAuthenticatedUser()`.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="e793d-112">권장 작업</span><span class="sxs-lookup"><span data-stu-id="e793d-112">Recommended action</span></span>

<span data-ttu-id="e793d-113">ASP.NET Core 3.0 Preview 6에서는 기본적으로 `true`인 `AuthenticationOptions`에 `RequireAuthenticatedSignIn` 플래그가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e793d-113">In ASP.NET Core 3.0 Preview 6, there's a `RequireAuthenticatedSignIn` flag on `AuthenticationOptions` that is `true` by default.</span></span> <span data-ttu-id="e793d-114">이전 동작을 복원하려면 이 플래그를 `false`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e793d-114">Set this flag to `false` to restore the old behavior.</span></span>

#### <a name="category"></a><span data-ttu-id="e793d-115">범주</span><span class="sxs-lookup"><span data-stu-id="e793d-115">Category</span></span>

<span data-ttu-id="e793d-116">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e793d-116">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="e793d-117">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="e793d-117">Affected APIs</span></span>

<span data-ttu-id="e793d-118">없음</span><span class="sxs-lookup"><span data-stu-id="e793d-118">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
