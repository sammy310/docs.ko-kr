---
title: ASP.NET MVC와 ASP.NET Core 간의 인증 및 권한 부여 비교
description: ASP.NET MVC와 ASP.NET Core 간의 인증 및 권한 부여의 차이에 대 한 요약입니다.
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: c8f3314186b7408e40d3a79cbc922a29eb75c5d2
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401819"
---
# <a name="compare-authentication-and-authorization-between-aspnet-mvc-and-aspnet-core"></a><span data-ttu-id="061e0-103">ASP.NET MVC와 ASP.NET Core 간의 인증 및 권한 부여 비교</span><span class="sxs-lookup"><span data-stu-id="061e0-103">Compare authentication and authorization between ASP.NET MVC and ASP.NET Core</span></span>

<span data-ttu-id="061e0-104">ASP.NET MVC 5에서 인증은 *App_Start* 폴더의 *Startup.Auth.cs* 에서 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="061e0-104">In ASP.NET MVC 5, authentication is configured in *Startup.Auth.cs* in the *App_Start* folder.</span></span> <span data-ttu-id="061e0-105">ASP.NET Core MVC에서이 구성은에서 발생 `Startup.cs` 합니다.</span><span class="sxs-lookup"><span data-stu-id="061e0-105">In ASP.NET Core MVC, this configuration occurs in `Startup.cs`.</span></span> <span data-ttu-id="061e0-106">에서 요청 파이프라인에 추가 된 미들웨어를 사용 하 여 인증 및 권한 부여를 수행 합니다 `ConfigureServices` .</span><span class="sxs-lookup"><span data-stu-id="061e0-106">Authentication and authorization are performed using middleware added to the request pipeline in `ConfigureServices`:</span></span>

```csharp
// inside Startup.ConfigureServices

app.UseRouting();

app.UseAuthentication();
app.UseAuthorization();

app.UseEndpoints(endpoints =>
{
    endpoints.MapControllerRoute(
        name: "default",
        pattern: "{controller=Home}/{action=Index}/{id?}");
    endpoints.MapRazorPages();
});
```

<span data-ttu-id="061e0-107">미들웨어 파이프라인에서 적절 한 순서로 auth 미들웨어를 추가 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="061e0-107">It's important to add the auth middleware in the appropriate order in the middleware pipeline.</span></span> <span data-ttu-id="061e0-108">미들웨어에 게이를 수행 하는 요청만 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="061e0-108">Only requests that make it to the middleware will be impacted by it.</span></span> <span data-ttu-id="061e0-109">예를 들어,에 대 한 호출이 `UseStaticFiles()` 여기에 표시 된 코드 위에 배치 된 경우 인증 및 권한 부여로 보호 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="061e0-109">For instance, if a call to `UseStaticFiles()` was placed above the code shown here, it wouldn't be protected by authentication and authorization.</span></span>

<span data-ttu-id="061e0-110">ASP.NET MVC 및 Web API에서 앱은 종종 속성을 사용 하 여 현재 사용자를 참조 `ClaimsPrincipal.Current` 합니다.</span><span class="sxs-lookup"><span data-stu-id="061e0-110">In ASP.NET MVC and Web API, apps often refer to the current user using the `ClaimsPrincipal.Current` property.</span></span> <span data-ttu-id="061e0-111">이 속성은 ASP.NET Core 설정 되지 않으며,이 속성에 의존 하는 앱의 모든 동작은 현재에 [](/aspnet/core/migration/claimsprincipal-current) 대 `User` 한 속성을 사용 하거나 현재에 대 `ControllerBase` 한 액세스를 가져오고 `HttpContext` 해당 속성을 참조 `User` 하 여 ClaimsPrincipal에서 마이그레이션해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="061e0-111">This property isn't set in ASP.NET Core, and any behavior in your app that depends on it will need to [migrate from ClaimsPrincipal.Current](/aspnet/core/migration/claimsprincipal-current) by using the `User` property on `ControllerBase` or getting access to the current `HttpContext` and referencing its `User` property.</span></span> <span data-ttu-id="061e0-112">이러한 방법 중 하나를 선택 하지 않으면 서비스는 사용자를 인수로 요청할 수 있습니다 .이 경우 응용 프로그램의 다른 위치에서 해당 사용자를 제공 해야 합니다. 그렇지 않으면를 `IHttpContextAccessor` 요청 하 여를 가져오는 데 사용할 수 있습니다 `HttpContext` .</span><span class="sxs-lookup"><span data-stu-id="061e0-112">If neither of these solutions is an option, services can request the User as an argument, in which case it must be supplied from elsewhere in the app, or the `IHttpContextAccessor` can be requested and used to get the `HttpContext`.</span></span>

## <a name="authorization"></a><span data-ttu-id="061e0-113">권한 부여</span><span class="sxs-lookup"><span data-stu-id="061e0-113">Authorization</span></span>

<span data-ttu-id="061e0-114">권한 부여는 지정 된 사용자가 앱 내에서 수행할 수 있는 작업을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="061e0-114">Authorization defines what a given user can do within the app.</span></span> <span data-ttu-id="061e0-115">인증과는 별개로 사용자를 식별 하는 것과 관련 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="061e0-115">It's separate from authentication, which is concerned merely with identifying who the user is.</span></span> <span data-ttu-id="061e0-116">ASP.NET Core는 간단한 선언적 역할과 권한 부여를 위한 풍부한 정책 기반 모델을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="061e0-116">ASP.NET Core provides a simple, declarative role and a rich, policy-based model for authorization.</span></span> <span data-ttu-id="061e0-117">리소스가 권한 부여를 요구 하도록 지정 하는 것은 `[Authorize]` 작업 또는 컨트롤러에 특성을 추가 하는 것 만큼 간단 합니다.</span><span class="sxs-lookup"><span data-stu-id="061e0-117">Specifying that a resource requires authorization is often as simple as adding the `[Authorize]` attribute to the action or controller.</span></span> <span data-ttu-id="061e0-118">MVC 뷰에서 Razor Pages으로 마이그레이션하는 경우 [시작 시 Razor Pages를 구성할 때 권한 부여 규칙을 지정](/aspnet/core/security/authorization/razor-pages-authorization)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="061e0-118">If you're migrating to Razor Pages from MVC views, you should [specify conventions for authorization when you configure Razor Pages in Startup](/aspnet/core/security/authorization/razor-pages-authorization).</span></span>

<span data-ttu-id="061e0-119">ASP.NET Core 권한 부여는 인증 된 사용자를 허용 하는 동시에 익명 사용자를 금지 하는 것 처럼 간단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="061e0-119">Authorization in ASP.NET Core may be as simple as prohibiting anonymous users while allowing authenticated users.</span></span> <span data-ttu-id="061e0-120">또는 역할 기반, 클레임 기반 또는 정책 기반 권한 부여 방법을 지원 하도록 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="061e0-120">Or it can scale up to support role-based, claims-based, or policy-based authorization approaches.</span></span> <span data-ttu-id="061e0-121">이러한 접근 방식에 대 한 자세한 내용은 [ASP.NET Core의 권한 부여](/aspnet/core/security/authorization/introduction)에 대 한 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="061e0-121">For more information on these approaches, see the documentation on [authorization in ASP.NET Core](/aspnet/core/security/authorization/introduction).</span></span> <span data-ttu-id="061e0-122">그 중 하나가 현재 권한 부여 방법과 밀접 하 게 일치 하는 것을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="061e0-122">You'll likely find that one of them is closely aligned with your current authorization approach.</span></span>

## <a name="references"></a><span data-ttu-id="061e0-123">참조</span><span class="sxs-lookup"><span data-stu-id="061e0-123">References</span></span>

- [<span data-ttu-id="061e0-124">ASP.NET MVC를 사용 하 여 보안, 인증 및 권한 부여</span><span class="sxs-lookup"><span data-stu-id="061e0-124">Security, Authentication, and Authorization with ASP.NET MVC</span></span>](/aspnet/mvc/overview/security/)
- [<span data-ttu-id="061e0-125">ASP.NET Core 인증 및 Id 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="061e0-125">Migrate Authentication and Identity to ASP.NET Core</span></span>](/aspnet/mvc/overview/security/)
- [<span data-ttu-id="061e0-126">ClaimsPrincipal에서 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="061e0-126">Migrate from ClaimsPrincipal.Current</span></span>](/aspnet/core/migration/claimsprincipal-current)
- [<span data-ttu-id="061e0-127">ASP.NET Core 권한 부여 소개</span><span class="sxs-lookup"><span data-stu-id="061e0-127">Introduction to Authorization in ASP.NET Core</span></span>](/aspnet/core/security/authorization/introduction)

>[!div class="step-by-step"]
><span data-ttu-id="061e0-128">[이전](webapi-differences.md)
>[다음](identity-differences.md)</span><span class="sxs-lookup"><span data-stu-id="061e0-128">[Previous](webapi-differences.md)
[Next](identity-differences.md)</span></span>
