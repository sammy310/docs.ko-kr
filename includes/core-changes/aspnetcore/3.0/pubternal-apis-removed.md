---
ms.openlocfilehash: 224cd3c7897c64ef05baba7d3d31dbe5ac0dd610
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606180"
---
### <a name="pubternal-apis-removed"></a><span data-ttu-id="bcc20-101">"Pubternal" API가 제거됨</span><span class="sxs-lookup"><span data-stu-id="bcc20-101">"Pubternal" APIs removed</span></span>

<span data-ttu-id="bcc20-102">ASP.NET Core의 공용 API 노출 영역을 보다 효율적으로 유지 관리하기 위해 `*.Internal` 네임스페이스(:::no-loc text="\"pubternal\""::: API라고 함)에 있는 대부분의 형식이 진정한 내부용이 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bcc20-102">To better maintain the public API surface of ASP.NET Core, most of the types in `*.Internal` namespaces (referred to as :::no-loc text="\"pubternal\""::: APIs) have become truly internal.</span></span> <span data-ttu-id="bcc20-103">이러한 네임스페이스의 멤버는 공용 API로 지원되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="bcc20-103">Members in these namespaces were never meant to be supported as public-facing APIs.</span></span> <span data-ttu-id="bcc20-104">이러한 API는 마이너 릴리스에서 중단 가능성이 있었고 실제로 자주 중단되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bcc20-104">The APIs could break in minor releases and often did.</span></span> <span data-ttu-id="bcc20-105">ASP.NET Core 3.0으로 업데이트할 때 이러한 API에 종속된 코드가 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="bcc20-105">Code that depends on these APIs breaks when updating to ASP.NET Core 3.0.</span></span>

<span data-ttu-id="bcc20-106">자세한 내용은 [dotnet/aspnetcore#4932](https://github.com/dotnet/aspnetcore/issues/4932) 및 [dotnet/aspnetcore#11312](https://github.com/dotnet/aspnetcore/issues/11312)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bcc20-106">For more information, see [dotnet/aspnetcore#4932](https://github.com/dotnet/aspnetcore/issues/4932) and [dotnet/aspnetcore#11312](https://github.com/dotnet/aspnetcore/issues/11312).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="bcc20-107">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="bcc20-107">Version introduced</span></span>

<span data-ttu-id="bcc20-108">3.0</span><span class="sxs-lookup"><span data-stu-id="bcc20-108">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="bcc20-109">이전 동작</span><span class="sxs-lookup"><span data-stu-id="bcc20-109">Old behavior</span></span>

<span data-ttu-id="bcc20-110">영향을 받는 API가 `public` 액세스 한정자로 표시되고 `*.Internal` 네임스페이스에 존재합니다.</span><span class="sxs-lookup"><span data-stu-id="bcc20-110">The affected APIs are marked with the `public` access modifier and exist in `*.Internal` namespaces.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="bcc20-111">새 동작</span><span class="sxs-lookup"><span data-stu-id="bcc20-111">New behavior</span></span>

<span data-ttu-id="bcc20-112">영향을 받는 API가 [internal](../../../../docs/csharp/language-reference/keywords/internal.md) 액세스 한정자로 표시되며, 해당 어셈블리 외부의 코드에서 이 API를 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bcc20-112">The affected APIs are marked with the [internal](../../../../docs/csharp/language-reference/keywords/internal.md) access modifier and can no longer be used by code outside that assembly.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="bcc20-113">변경 이유</span><span class="sxs-lookup"><span data-stu-id="bcc20-113">Reason for change</span></span>

<span data-ttu-id="bcc20-114">이러한 :::no-loc text="\"pubternal\""::: API에 대한 지침은 다음과 같은 특성이 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="bcc20-114">The guidance for these :::no-loc text="\"pubternal\""::: APIs was that they:</span></span>

* <span data-ttu-id="bcc20-115">예고 없이 변경될 수 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="bcc20-115">Could change without notice.</span></span>
* <span data-ttu-id="bcc20-116">호환성이 손상되는 변경을 방지하기 위해 .NET 정책에 적용되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="bcc20-116">Weren't subject to .NET policies to prevent breaking changes.</span></span>

<span data-ttu-id="bcc20-117">API를 `public`으로 유지하여(`*.Internal` 네임스페이스에서도) 고객이 혼동할 수 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="bcc20-117">Leaving the APIs `public` (even in the `*.Internal` namespaces) was confusing to customers.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="bcc20-118">권장 조치</span><span class="sxs-lookup"><span data-stu-id="bcc20-118">Recommended action</span></span>

<span data-ttu-id="bcc20-119">이러한 :::no-loc text="\"pubternal\""::: API 사용을 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="bcc20-119">Stop using these :::no-loc text="\"pubternal\""::: APIs.</span></span> <span data-ttu-id="bcc20-120">대체 API에 대한 질문이 있는 경우 [dotnet/aspnetcore](https://github.com/dotnet/aspnetcore/issues) 리포지토리에서 문제를 여세요.</span><span class="sxs-lookup"><span data-stu-id="bcc20-120">If you have questions about alternate APIs, open an issue in the [dotnet/aspnetcore](https://github.com/dotnet/aspnetcore/issues) repository.</span></span>

<span data-ttu-id="bcc20-121">예를 들어 ASP.NET Core 2.2 프로젝트에서 다음 HTTP 요청 버퍼링 코드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bcc20-121">For example, consider the following HTTP request buffering code in an ASP.NET Core 2.2 project.</span></span> <span data-ttu-id="bcc20-122">`EnableRewind` 확장 메서드는 `Microsoft.AspNetCore.Http.Internal` 네임스페이스에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bcc20-122">The `EnableRewind` extension method exists in the `Microsoft.AspNetCore.Http.Internal` namespace.</span></span>

```csharp
HttpContext.Request.EnableRewind();
```

<span data-ttu-id="bcc20-123">ASP.NET Core 3.0 프로젝트에서 `EnableRewind` 호출을 `EnableBuffering` 확장 메서드에 대한 호출로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="bcc20-123">In an ASP.NET Core 3.0 project, replace the `EnableRewind` call with a call to the `EnableBuffering` extension method.</span></span> <span data-ttu-id="bcc20-124">요청 버퍼링 기능은 이전과 동일하게 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="bcc20-124">The request buffering feature works as it did in the past.</span></span> <span data-ttu-id="bcc20-125">`EnableBuffering`은 이제 `internal` API를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="bcc20-125">`EnableBuffering` calls the now `internal` API.</span></span>

```csharp
HttpContext.Request.EnableBuffering();
```

#### <a name="category"></a><span data-ttu-id="bcc20-126">범주</span><span class="sxs-lookup"><span data-stu-id="bcc20-126">Category</span></span>

<span data-ttu-id="bcc20-127">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="bcc20-127">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="bcc20-128">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="bcc20-128">Affected APIs</span></span>

<span data-ttu-id="bcc20-129">네임 스페이스 이름에 `Internal` 세그먼트가 있는 `Microsoft.AspNetCore.*` 및 `Microsoft.Extensions.*` 네임스페이스의 모든 API.</span><span class="sxs-lookup"><span data-stu-id="bcc20-129">All APIs in the `Microsoft.AspNetCore.*` and `Microsoft.Extensions.*` namespaces that have an `Internal` segment in the namespace name.</span></span> <span data-ttu-id="bcc20-130">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="bcc20-130">For example:</span></span>

- `Microsoft.AspNetCore.Authentication.Internal`
- `Microsoft.AspNetCore.Builder.Internal`
- `Microsoft.AspNetCore.DataProtection.Cng.Internal`
- `Microsoft.AspNetCore.DataProtection.Internal`
- `Microsoft.AspNetCore.Hosting.Internal`
- `Microsoft.AspNetCore.Http.Internal`
- `Microsoft.AspNetCore.Mvc.Core.Infrastructure`
- `Microsoft.AspNetCore.Mvc.Core.Internal`
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
- `Microsoft.AspNetCore.Rewrite.Internal`
- `Microsoft.AspNetCore.Routing.Internal`
- `Microsoft.AspNetCore.Server.Kestrel.Core.Adapter.Internal`
- `Microsoft.AspNetCore.Server.Kestrel.Core.Internal.Http`
- `Microsoft.AspNetCore.Server.Kestrel.Core.Internal.Infrastructure`
- `Microsoft.AspNetCore.Server.Kestrel.Https.Internal`

<!--

#### Affected APIs

- `N:Microsoft.AspNetCore.Authentication.Internal`
- `N:Microsoft.AspNetCore.Builder.Internal`
- `N:Microsoft.AspNetCore.DataProtection.Cng.Internal`
- `N:Microsoft.AspNetCore.DataProtection.Internal`
- `N:Microsoft.AspNetCore.Hosting.Internal`
- `N:Microsoft.AspNetCore.Http.Internal`
- `N:Microsoft.AspNetCore.Mvc.Core.Infrastructure`
- `N:Microsoft.AspNetCore.Mvc.Core.Internal`
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
- `N:Microsoft.AspNetCore.Rewrite.Internal`
- `N:Microsoft.AspNetCore.Routing.Internal`
- `N:Microsoft.AspNetCore.Server.Kestrel.Core.Adapter.Internal`
- `N:Microsoft.AspNetCore.Server.Kestrel.Core.Internal.Http`
- `N:Microsoft.AspNetCore.Server.Kestrel.Core.Internal.Infrastructure`
- `N:Microsoft.AspNetCore.Server.Kestrel.Https.Internal`

-->
