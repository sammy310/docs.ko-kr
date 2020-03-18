---
ms.openlocfilehash: 60ebcd9fc9ca18c33d31b82ba5020426d22a7d5a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "75901781"
---
### <a name="authentication-httpcontextauthentication-property-removed"></a><span data-ttu-id="d973e-101">인증: HttpContext.Authentication 인증 속성이 제거됨</span><span class="sxs-lookup"><span data-stu-id="d973e-101">Authentication: HttpContext.Authentication property removed</span></span>

<span data-ttu-id="d973e-102">`HttpContext`에서 사용되지 않는 `Authentication` 속성이 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d973e-102">The deprecated `Authentication` property on `HttpContext` has been removed.</span></span>

#### <a name="change-description"></a><span data-ttu-id="d973e-103">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="d973e-103">Change description</span></span>

<span data-ttu-id="d973e-104">[dotnet/aspnetcore#6504](https://github.com/dotnet/aspnetcore/pull/6504)의 일부로, `HttpContext`에서 사용되지 않는 `Authentication` 속성이 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d973e-104">As part of [dotnet/aspnetcore#6504](https://github.com/dotnet/aspnetcore/pull/6504), the deprecated `Authentication` property on `HttpContext` has been removed.</span></span> <span data-ttu-id="d973e-105">`Authentication` 속성은 2.0 이후 더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d973e-105">The `Authentication` property has been deprecated since 2.0.</span></span> <span data-ttu-id="d973e-106">사용되지 않는 이 속성을 사용하여 코드를 새 대체 API로 마이그레이션하기 위해 [마이그레이션 가이드](/aspnet/core/migration/1x-to-2x/identity-2x?view=aspnetcore-2.2#use-httpcontext-authentication-extensions)가 게시되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d973e-106">A [migration guide](/aspnet/core/migration/1x-to-2x/identity-2x?view=aspnetcore-2.2#use-httpcontext-authentication-extensions) was published to migrate code using this deprecated property to the new replacement APIs.</span></span> <span data-ttu-id="d973e-107">이전 ASP.NET Core 1.x 인증 스택과 관련된 사용되지 않는 나머지 클래스 / API는 커밋 [dotnet/aspnetcore@d7a7c65](https://github.com/dotnet/aspnetcore/commit/d7a7c65)에서 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d973e-107">The remaining unused classes / APIs related to the old ASP.NET Core 1.x authentication stack were removed in commit [dotnet/aspnetcore@d7a7c65](https://github.com/dotnet/aspnetcore/commit/d7a7c65).</span></span>

<span data-ttu-id="d973e-108">토론은 [dotnet/aspnetcore#6533](https://github.com/dotnet/aspnetcore/issues/6533)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d973e-108">For discussion, see [dotnet/aspnetcore#6533](https://github.com/dotnet/aspnetcore/issues/6533).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="d973e-109">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="d973e-109">Version introduced</span></span>

<span data-ttu-id="d973e-110">3.0</span><span class="sxs-lookup"><span data-stu-id="d973e-110">3.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="d973e-111">변경 이유</span><span class="sxs-lookup"><span data-stu-id="d973e-111">Reason for change</span></span>

<span data-ttu-id="d973e-112">ASP.NET Core 1.0 API는 <xref:Microsoft.AspNetCore.Authentication.AuthenticationHttpContextExtensions?displayProperty=fullName>의 확장 메서드로 대체되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d973e-112">ASP.NET Core 1.0 APIs have been replaced by extension methods in <xref:Microsoft.AspNetCore.Authentication.AuthenticationHttpContextExtensions?displayProperty=fullName>.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="d973e-113">권장 조치</span><span class="sxs-lookup"><span data-stu-id="d973e-113">Recommended action</span></span>

<span data-ttu-id="d973e-114">[마이그레이션 가이드](/aspnet/core/migration/1x-to-2x/identity-2x?view=aspnetcore-2.2#use-httpcontext-authentication-extensions)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d973e-114">See the [migration guide](/aspnet/core/migration/1x-to-2x/identity-2x?view=aspnetcore-2.2#use-httpcontext-authentication-extensions).</span></span>

#### <a name="category"></a><span data-ttu-id="d973e-115">범주</span><span class="sxs-lookup"><span data-stu-id="d973e-115">Category</span></span>

<span data-ttu-id="d973e-116">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="d973e-116">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="d973e-117">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="d973e-117">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.Http.Authentication.AuthenticateInfo?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Authentication.AuthenticationManager?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Authentication.AuthenticationProperties?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Features.Authentication.AuthenticateContext?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Features.Authentication.ChallengeBehavior?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Features.Authentication.ChallengeContext?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Features.Authentication.DescribeSchemesContext?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Features.Authentication.IAuthenticationHandler?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Features.Authentication.IHttpAuthenticationFeature.Handler?displayProperty=fullName>
- <xref:Microsoft.AspNetCore.Http.Features.Authentication.SignInContext?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Features.Authentication.SignOutContext?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.HttpContext.Authentication?displayProperty=fullName>

<!-- 

#### Affected APIs

- `T:Microsoft.AspNetCore.Http.Authentication.AuthenticateInfo`
- `T:Microsoft.AspNetCore.Http.Authentication.AuthenticationManager`
- `T:Microsoft.AspNetCore.Http.Authentication.AuthenticationProperties`
- `T:Microsoft.AspNetCore.Http.Features.Authentication.AuthenticateContext`
- `T:Microsoft.AspNetCore.Http.Features.Authentication.ChallengeBehavior`
- `T:Microsoft.AspNetCore.Http.Features.Authentication.ChallengeContext`
- `T:Microsoft.AspNetCore.Http.Features.Authentication.DescribeSchemesContext`
- `T:Microsoft.AspNetCore.Http.Features.Authentication.IAuthenticationHandler`
- `P:Microsoft.AspNetCore.Http.Features.Authentication.IHttpAuthenticationFeature.Handler`
- `T:Microsoft.AspNetCore.Http.Features.Authentication.SignInContext`
- `T:Microsoft.AspNetCore.Http.Features.Authentication.SignOutContext`
- `P:Microsoft.AspNetCore.Http.HttpContext.Authentication`

-->
