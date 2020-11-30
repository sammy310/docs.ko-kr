---
ms.openlocfilehash: 15ba678431b97e7c961c119d83546569bdf9bad2
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032529"
---
### <a name="http-some-cookie-samesite-defaults-changed-to-none"></a><span data-ttu-id="e394d-101">HTTP: 일부 쿠키 SameSite 기본값이 없음으로 변경됨</span><span class="sxs-lookup"><span data-stu-id="e394d-101">HTTP: Some cookie SameSite defaults changed to None</span></span>

<span data-ttu-id="e394d-102">`SameSite`은(는) 일부 CSRF(교차 사이트 요청 위조) 공격을 완화하는 데 도움이 되는 쿠키의 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="e394d-102">`SameSite` is an option for cookies that can help mitigate some Cross-Site Request Forgery (CSRF) attacks.</span></span> <span data-ttu-id="e394d-103">처음에 이 옵션을 도입했을 때 다양한 ASP.NET Core API에서 일관되지 않은 기본값이 사용되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e394d-103">When this option was initially introduced, inconsistent defaults were used across various ASP.NET Core APIs.</span></span> <span data-ttu-id="e394d-104">이와 같은 불일치로 혼란스러운 결과가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="e394d-104">The inconsistency has led to confusing results.</span></span> <span data-ttu-id="e394d-105">ASP.NET Core 3.0부터, 이 기본값은 효율적으로 정렬되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e394d-105">As of ASP.NET Core 3.0, these defaults are better aligned.</span></span> <span data-ttu-id="e394d-106">구성 요소별로 이 기능을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e394d-106">You must opt in to this feature on a per-component basis.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="e394d-107">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="e394d-107">Version introduced</span></span>

<span data-ttu-id="e394d-108">3.0</span><span class="sxs-lookup"><span data-stu-id="e394d-108">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="e394d-109">이전 동작</span><span class="sxs-lookup"><span data-stu-id="e394d-109">Old behavior</span></span>

<span data-ttu-id="e394d-110">유사한 ASP.NET Core API에서 다른 기본 <xref:Microsoft.AspNetCore.Http.SameSiteMode> 값을 사용했습니다.</span><span class="sxs-lookup"><span data-stu-id="e394d-110">Similar ASP.NET Core APIs used different default <xref:Microsoft.AspNetCore.Http.SameSiteMode> values.</span></span> <span data-ttu-id="e394d-111">불일치에 대한 예는 기본값인 `SameSiteMode.None` 및 `SameSiteMode.Lax`(으)로 각각 설정된 `HttpResponse.Cookies.Append(String, String)` 및 `HttpResponse.Cookies.Append(String, String, CookieOptions)`에서 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e394d-111">An example of the inconsistency is seen in `HttpResponse.Cookies.Append(String, String)` and `HttpResponse.Cookies.Append(String, String, CookieOptions)`, which defaulted to `SameSiteMode.None` and `SameSiteMode.Lax`, respectively.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="e394d-112">새 동작</span><span class="sxs-lookup"><span data-stu-id="e394d-112">New behavior</span></span>

<span data-ttu-id="e394d-113">영향을 받는 모든 API의 기본값은 `SameSiteMode.None`입니다.</span><span class="sxs-lookup"><span data-stu-id="e394d-113">All the affected APIs default to `SameSiteMode.None`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="e394d-114">변경 이유</span><span class="sxs-lookup"><span data-stu-id="e394d-114">Reason for change</span></span>

<span data-ttu-id="e394d-115">`SameSite`을(를) 옵트인 기능으로 설정하도록 기본값이 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e394d-115">The default value was changed to make `SameSite` an opt-in feature.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="e394d-116">권장 조치</span><span class="sxs-lookup"><span data-stu-id="e394d-116">Recommended action</span></span>

<span data-ttu-id="e394d-117">쿠키를 내보내는 각 구성 요소는 `SameSite`이(가) 시나리오에 적합한지 여부를 결정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e394d-117">Each component that emits cookies needs to decide if `SameSite` is appropriate for its scenarios.</span></span> <span data-ttu-id="e394d-118">영향을 받는 API의 사용을 검토하고 필요에 따라 `SameSite`을(를) 다시 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="e394d-118">Review your usage of the affected APIs and reconfigure `SameSite` as needed.</span></span>

#### <a name="category"></a><span data-ttu-id="e394d-119">범주</span><span class="sxs-lookup"><span data-stu-id="e394d-119">Category</span></span>

<span data-ttu-id="e394d-120">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e394d-120">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="e394d-121">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="e394d-121">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.Http.IResponseCookies.Append(System.String,System.String,Microsoft.AspNetCore.Http.CookieOptions)?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Builder.CookiePolicyOptions.MinimumSameSitePolicy%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:Microsoft.AspNetCore.Http.IResponseCookies.Append(System.String,System.String,Microsoft.AspNetCore.Http.CookieOptions)`
- `Overload:Microsoft.AspNetCore.Builder.CookiePolicyOptions.MinimumSameSitePolicy`

-->
