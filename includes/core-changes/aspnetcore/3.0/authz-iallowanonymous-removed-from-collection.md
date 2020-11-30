---
ms.openlocfilehash: 0c88d40e34d2d6458bb463a09d716dea42b711fe
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032469"
---
### <a name="authorization-iallowanonymous-removed-from-authorizationfiltercontextfilters"></a><span data-ttu-id="6a0ba-101">권한 부여: AuthorizationFilterContext.Filters에서 IAllowAnonymous 제거됨</span><span class="sxs-lookup"><span data-stu-id="6a0ba-101">Authorization: IAllowAnonymous removed from AuthorizationFilterContext.Filters</span></span>

<span data-ttu-id="6a0ba-102">ASP.NET Core 3.0을 기준으로 MVC에서 컨트롤러 및 작업 메서드에서 검색된 [[AllowAnonymous]](xref:Microsoft.AspNetCore.Authorization.AllowAnonymousAttribute) 특성에 대해 [AllowAnonymousFilters](xref:Microsoft.AspNetCore.Mvc.Authorization.AllowAnonymousFilter)를 추가하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-102">As of ASP.NET Core 3.0, MVC doesn't add [AllowAnonymousFilters](xref:Microsoft.AspNetCore.Mvc.Authorization.AllowAnonymousFilter) for [[AllowAnonymous]](xref:Microsoft.AspNetCore.Authorization.AllowAnonymousAttribute) attributes that were discovered on controllers and action methods.</span></span> <span data-ttu-id="6a0ba-103">이 변경 사항은 <xref:Microsoft.AspNetCore.Authorization.AuthorizeAttribute>의 파생에 대해 로컬로 처리하지만 <xref:Microsoft.AspNetCore.Mvc.Filters.IAsyncAuthorizationFilter> 및 <xref:Microsoft.AspNetCore.Mvc.Filters.IAuthorizationFilter> 구현에 대해 호환성이 손상됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-103">This change is addressed locally for derivatives of <xref:Microsoft.AspNetCore.Authorization.AuthorizeAttribute>, but it's a breaking change for <xref:Microsoft.AspNetCore.Mvc.Filters.IAsyncAuthorizationFilter> and <xref:Microsoft.AspNetCore.Mvc.Filters.IAuthorizationFilter> implementations.</span></span> <span data-ttu-id="6a0ba-104">[[TypeFilter]](xref:Microsoft.AspNetCore.Mvc.TypeFilterAttribute) 특성에 래핑된 이러한 구현은 구성 및 종속성 주입이 모두 필요한 경우 강력한 형식의 특성 기반 권한 부여를 달성하는 [일반적](https://stackoverflow.com/a/41348219/608220)이고 지원되는 방식입니다.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-104">Such implementations wrapped in a [[TypeFilter]](xref:Microsoft.AspNetCore.Mvc.TypeFilterAttribute) attribute are a [popular](https://stackoverflow.com/a/41348219/608220) and supported way to achieve strongly-typed, attribute-based authorization when both configuration and dependency injection are required.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="6a0ba-105">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="6a0ba-105">Version introduced</span></span>

<span data-ttu-id="6a0ba-106">3.0</span><span class="sxs-lookup"><span data-stu-id="6a0ba-106">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="6a0ba-107">이전 동작</span><span class="sxs-lookup"><span data-stu-id="6a0ba-107">Old behavior</span></span>

<span data-ttu-id="6a0ba-108"><xref:Microsoft.AspNetCore.Authorization.IAllowAnonymous>가 [AuthorizationFilterContext.Filters](xref:Microsoft.AspNetCore.Mvc.Filters.FilterContext.Filters%2A) 컬렉션에 표시되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-108"><xref:Microsoft.AspNetCore.Authorization.IAllowAnonymous> appeared in the [AuthorizationFilterContext.Filters](xref:Microsoft.AspNetCore.Mvc.Filters.FilterContext.Filters%2A) collection.</span></span> <span data-ttu-id="6a0ba-109">인터페이스의 현재 상태에 대한 테스트는 개별 컨트롤러 메서드에서 필터를 재정의하거나 사용하지 않도록 설정하는 유효한 방법이었습니다.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-109">Testing for the interface's presence was a valid approach to override or disable the filter on individual controller methods.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="6a0ba-110">새 동작</span><span class="sxs-lookup"><span data-stu-id="6a0ba-110">New behavior</span></span>

<span data-ttu-id="6a0ba-111">`AuthorizationFilterContext.Filters` 컬렉션에 `IAllowAnonymous`가 더 이상 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-111">`IAllowAnonymous` no longer appears in the `AuthorizationFilterContext.Filters` collection.</span></span> <span data-ttu-id="6a0ba-112">이전 동작에 의존하는 `IAsyncAuthorizationFilter` 구현은 일반적으로 일시적인 HTTP 401 Unauthorized 또는 HTTP 403 Forbidden 응답의 원인이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-112">`IAsyncAuthorizationFilter` implementations that are dependent on the old behavior typically cause intermittent HTTP 401 Unauthorized or HTTP 403 Forbidden responses.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="6a0ba-113">변경 이유</span><span class="sxs-lookup"><span data-stu-id="6a0ba-113">Reason for change</span></span>

<span data-ttu-id="6a0ba-114">새 엔드포인트 라우팅 전략은 ASP.NET Core 3.0에서 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-114">A new endpoint routing strategy was introduced in ASP.NET Core 3.0.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="6a0ba-115">권장 조치</span><span class="sxs-lookup"><span data-stu-id="6a0ba-115">Recommended action</span></span>

<span data-ttu-id="6a0ba-116">`IAllowAnonymous`에 대한 엔드포인트 메타데이터를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-116">Search the endpoint metadata for `IAllowAnonymous`.</span></span> <span data-ttu-id="6a0ba-117">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="6a0ba-117">For example:</span></span>

```csharp
var endpoint = context.HttpContext.GetEndpoint();
if (endpoint?.Metadata?.GetMetadata<IAllowAnonymous>() != null)
{
}
```

<span data-ttu-id="6a0ba-118">이 기법에 대한 예는 [HasAllowAnonymous 메서드](https://github.com/dotnet/aspnetcore/blob/bd65275148abc9b07a3b59797a88d485341152bf/src/Mvc/Mvc.Core/src/Authorization/AuthorizeFilter.cs#L236)에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a0ba-118">An example of this technique is seen in [this HasAllowAnonymous method](https://github.com/dotnet/aspnetcore/blob/bd65275148abc9b07a3b59797a88d485341152bf/src/Mvc/Mvc.Core/src/Authorization/AuthorizeFilter.cs#L236).</span></span>

#### <a name="category"></a><span data-ttu-id="6a0ba-119">범주</span><span class="sxs-lookup"><span data-stu-id="6a0ba-119">Category</span></span>

<span data-ttu-id="6a0ba-120">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="6a0ba-120">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="6a0ba-121">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="6a0ba-121">Affected APIs</span></span>

<span data-ttu-id="6a0ba-122">없음</span><span class="sxs-lookup"><span data-stu-id="6a0ba-122">None</span></span>

<!--

#### Affected APIs

Not detectable via API analysis

-->
