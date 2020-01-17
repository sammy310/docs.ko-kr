---
ms.openlocfilehash: 5741e8cdd51e00d5459c4c1032a56682429aab17
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901724"
---
### <a name="mvc-pubternal-types-changed-to-internal"></a><span data-ttu-id="69e11-101">MVC: "Pubternal" 유형이 내부로 변경됨</span><span class="sxs-lookup"><span data-stu-id="69e11-101">MVC: "Pubternal" types changed to internal</span></span>

<span data-ttu-id="69e11-102">ASP.NET Core 3.0에서는 MVC의 모든 "pubternal" 형식이 지원되는 네임스페이스에서 `public` 또는 필요에 따라 `internal`로 업데이트되었습니다.</span><span class="sxs-lookup"><span data-stu-id="69e11-102">In ASP.NET Core 3.0, all "pubternal" types in MVC were updated to either be `public` in a supported namespace or `internal` as appropriate.</span></span>

#### <a name="change-description"></a><span data-ttu-id="69e11-103">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="69e11-103">Change description</span></span>

<span data-ttu-id="69e11-104">ASP.NET Core에서 "pubternal" 형식은 `public`으로 선언되었지만 `.Internal` 접미사가 지정된 네임스페이스에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69e11-104">In ASP.NET Core, "pubternal" types are declared as `public` but reside in a `.Internal`-suffixed namespace.</span></span> <span data-ttu-id="69e11-105">이러한 형식은 `public`이지만 지원 정책이 없으며 호환성이 손상되는 변경이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="69e11-105">While these types are `public`, they have no support policy and are subject to breaking changes.</span></span> <span data-ttu-id="69e11-106">아쉽게도 이러한 형식의 우발적 사용이 일반적으로 발생하므로 이러한 프로젝트에 대한 호환성이 손상되는 변경이 발생하고 프레임워크를 유지 관리하는 기능이 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="69e11-106">Unfortunately, accidental use of these types has been common, resulting in breaking changes to these projects and limiting the ability to maintain the framework.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="69e11-107">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="69e11-107">Version introduced</span></span>

<span data-ttu-id="69e11-108">3.0</span><span class="sxs-lookup"><span data-stu-id="69e11-108">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="69e11-109">이전 동작</span><span class="sxs-lookup"><span data-stu-id="69e11-109">Old behavior</span></span>

<span data-ttu-id="69e11-110">MVC의 일부 형식은 `public`이지만 `.Internal` 네임스페이스에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69e11-110">Some types in MVC were `public` but in a `.Internal` namespace.</span></span> <span data-ttu-id="69e11-111">이러한 형식에는 지원 정책이 없었으며 호환성이 손상되는 변경이 적용되었습니다.</span><span class="sxs-lookup"><span data-stu-id="69e11-111">These types had no support policy and were subject to breaking changes.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="69e11-112">새 동작</span><span class="sxs-lookup"><span data-stu-id="69e11-112">New behavior</span></span>

<span data-ttu-id="69e11-113">이러한 모든 형식은 지원되는 네임스페이스에서 `public`으로 업데이트되거나 `internal`로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="69e11-113">All such types are updated either to be `public` in a supported namespace or marked as `internal`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="69e11-114">변경 이유</span><span class="sxs-lookup"><span data-stu-id="69e11-114">Reason for change</span></span>

<span data-ttu-id="69e11-115">"pubternal" 형식의 우발적 사용이 일반적으로 발생하므로 이러한 프로젝트에 대한 호환성이 손상되는 변경이 발생하고 프레임워크를 유지 관리하는 기능이 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="69e11-115">Accidental use of the "pubternal" types has been common, resulting in breaking changes to these projects and limiting the ability to maintain the framework.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="69e11-116">권장 조치</span><span class="sxs-lookup"><span data-stu-id="69e11-116">Recommended action</span></span>

<span data-ttu-id="69e11-117">실제로 `public`이 되고 지원되는 새 네임스페이스로 이동한 형식을 사용하는 경우 새 네임스페이스와 일치하도록 참조를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="69e11-117">If you're using types that have become truly `public` and have been moved into a new, supported namespace, update your references to match the new namespaces.</span></span>

<span data-ttu-id="69e11-118">`internal`로 표시된 형식을 사용하는 경우에는 다른 방법을 찾아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="69e11-118">If you're using types that have become marked as `internal`, you'll need to find an alternative.</span></span> <span data-ttu-id="69e11-119">이전에 "pubternal" 형식은 공용으로 지원되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="69e11-119">The previously "pubternal" types were never supported for public use.</span></span> <span data-ttu-id="69e11-120">이러한 네임스페이스의 앱에 중요한 특정 형식이 있는 경우 [dotnet/aspnetcore](https://github.com/dotnet/aspnetcore/issues)에서 문제를 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="69e11-120">If there are specific types in these namespaces that are critical to your apps, file an issue at [dotnet/aspnetcore](https://github.com/dotnet/aspnetcore/issues).</span></span> <span data-ttu-id="69e11-121">요청된 형식 `public`을 만드는 것을 고려할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69e11-121">Considerations may be made for making the requested types `public`.</span></span>

#### <a name="category"></a><span data-ttu-id="69e11-122">범주</span><span class="sxs-lookup"><span data-stu-id="69e11-122">Category</span></span>

<span data-ttu-id="69e11-123">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="69e11-123">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="69e11-124">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="69e11-124">Affected APIs</span></span>

<span data-ttu-id="69e11-125">이 변경 내용에는 다음 네임스페이스의 형식이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="69e11-125">This change includes types in the following namespaces:</span></span>

- `Microsoft.AspNetCore.Mvc.Cors.Internal`
- `Microsoft.AspNetCore.Mvc.DataAnnotations.Internal`
- `Microsoft.AspNetCore.Mvc.Formatters.Internal`
- `Microsoft.AspNetCore.Mvc.Formatters.Json.Internal`
- `Microsoft.AspNetCore.Mvc.Formatters.Xml.Internal`
- `Microsoft.AspNetCore.Mvc.Internal`
- `Microsoft.AspNetCore.Mvc.ModelBinding.Internal`
- `Microsoft.AspNetCore.Mvc.Razor.Internal`
- `Microsoft.AspNetCore.Mvc.RazorPages.Internal`
- `Microsoft.AspNetCore.Mvc.TagHelpers.Internal`
- `Microsoft.AspNetCore.Mvc.ViewFeatures.Internal`

<!--

#### Affected APIs

- `N:Microsoft.AspNetCore.Mvc.Cors.Internal`
- `N:Microsoft.AspNetCore.Mvc.DataAnnotations.Internal`
- `N:Microsoft.AspNetCore.Mvc.Formatters.Internal`
- `N:Microsoft.AspNetCore.Mvc.Formatters.Json.Internal`
- `N:Microsoft.AspNetCore.Mvc.Formatters.Xml.Internal`
- `N:Microsoft.AspNetCore.Mvc.Internal`
- `N:Microsoft.AspNetCore.Mvc.ModelBinding.Internal`
- `N:Microsoft.AspNetCore.Mvc.Razor.Internal`
- `N:Microsoft.AspNetCore.Mvc.RazorPages.Internal`
- `N:Microsoft.AspNetCore.Mvc.TagHelpers.Internal`
- `N:Microsoft.AspNetCore.Mvc.ViewFeatures.Internal`

-->
