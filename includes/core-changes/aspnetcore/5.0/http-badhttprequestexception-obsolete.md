---
ms.openlocfilehash: c4e7864262a11aafa4b7f1f4bdf632fbf084c560
ms.sourcegitcommit: 1cb64b53eb1f253e6a3f53ca9510ef0be1fd06fe
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/29/2020
ms.locfileid: "82507094"
---
### <a name="http-kestrel-and-iis-badhttprequestexception-types-marked-obsolete-and-replaced"></a><span data-ttu-id="bed33-101">HTTP: Kestrel 및 IIS BadHttpRequestException 형식이 사용되지 않는 것으로 표시되고 대체됨</span><span class="sxs-lookup"><span data-stu-id="bed33-101">HTTP: Kestrel and IIS BadHttpRequestException types marked obsolete and replaced</span></span>

<span data-ttu-id="bed33-102">`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` 및 `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException`은 사용되지 않는 것으로 표시되며 `Microsoft.AspNetCore.Http.BadHttpRequestException`에서 파생되도록 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bed33-102">`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` and `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` have been marked obsolete and changed to derive from `Microsoft.AspNetCore.Http.BadHttpRequestException`.</span></span> <span data-ttu-id="bed33-103">Kestrel 및 IIS 서버는 이전 버전과의 호환성을 위해 이전 예외 형식을 계속 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="bed33-103">The Kestrel and IIS servers still throw their old exception types for backwards compatibility.</span></span> <span data-ttu-id="bed33-104">사용 되지 않는 형식은 이후 릴리스에서 제거될 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="bed33-104">The obsolete types will be removed in a future release.</span></span>

<span data-ttu-id="bed33-105">자세한 내용은 [dotnet/aspnetcore#20614](https://github.com/dotnet/aspnetcore/issues/20614)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bed33-105">For discussion, see [dotnet/aspnetcore#20614](https://github.com/dotnet/aspnetcore/issues/20614).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="bed33-106">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="bed33-106">Version introduced</span></span>

<span data-ttu-id="bed33-107">5.0 미리 보기 4</span><span class="sxs-lookup"><span data-stu-id="bed33-107">5.0 Preview 4</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="bed33-108">이전 동작</span><span class="sxs-lookup"><span data-stu-id="bed33-108">Old behavior</span></span>

<span data-ttu-id="bed33-109">`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` 및 `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException`이 <xref:System.IO.IOException?displayProperty=nameWithType>에서 파생되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bed33-109">`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` and `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` derived from <xref:System.IO.IOException?displayProperty=nameWithType>.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="bed33-110">새 동작</span><span class="sxs-lookup"><span data-stu-id="bed33-110">New behavior</span></span>

<span data-ttu-id="bed33-111">`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` 및 `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException`는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bed33-111">`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` and `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` are obsolete.</span></span> <span data-ttu-id="bed33-112">또한 형식은 `System.IO.IOException`에서 파생되는 `Microsoft.AspNetCore.Http.BadHttpRequestException`에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="bed33-112">The types also derive from `Microsoft.AspNetCore.Http.BadHttpRequestException`, which derives from `System.IO.IOException`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="bed33-113">변경 이유</span><span class="sxs-lookup"><span data-stu-id="bed33-113">Reason for change</span></span>

<span data-ttu-id="bed33-114">변경 내용:</span><span class="sxs-lookup"><span data-stu-id="bed33-114">The change was made to:</span></span>

* <span data-ttu-id="bed33-115">중복된 형식을 통합합니다.</span><span class="sxs-lookup"><span data-stu-id="bed33-115">Consolidate duplicate types.</span></span>
* <span data-ttu-id="bed33-116">여러 서버 구현에서 동작을 통합합니다.</span><span class="sxs-lookup"><span data-stu-id="bed33-116">Unify behavior across server implementations.</span></span>

<span data-ttu-id="bed33-117">이제 앱은 Kestrel 또는 IIS를 사용할 때 기본 예외 `Microsoft.AspNetCore.Http.BadHttpRequestException`을 catch할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bed33-117">An app can now catch the base exception `Microsoft.AspNetCore.Http.BadHttpRequestException` when using either Kestrel or IIS.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="bed33-118">권장 조치</span><span class="sxs-lookup"><span data-stu-id="bed33-118">Recommended action</span></span>

<span data-ttu-id="bed33-119">`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` 및 `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` 사용을 `Microsoft.AspNetCore.Http.BadHttpRequestException`으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="bed33-119">Replace usages of `Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` and `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` with `Microsoft.AspNetCore.Http.BadHttpRequestException`.</span></span>

#### <a name="category"></a><span data-ttu-id="bed33-120">범주</span><span class="sxs-lookup"><span data-stu-id="bed33-120">Category</span></span>

<span data-ttu-id="bed33-121">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="bed33-121">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="bed33-122">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="bed33-122">Affected APIs</span></span>

- [<span data-ttu-id="bed33-123">Microsoft.AspNetCore.Server.IIS.BadHttpRequestException</span><span class="sxs-lookup"><span data-stu-id="bed33-123">Microsoft.AspNetCore.Server.IIS.BadHttpRequestException</span></span>](/dotnet/api/microsoft.aspnetcore.server.iis.badhttprequestexception?view=aspnetcore-3.1)
- [<span data-ttu-id="bed33-124">Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException</span><span class="sxs-lookup"><span data-stu-id="bed33-124">Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException</span></span>](/dotnet/api/microsoft.aspnetcore.server.kestrel.badhttprequestexception?view=aspnetcore-1.1)

<!--

#### Affected APIs

- `T:Microsoft.AspNetCore.Server.IIS.BadHttpRequestException`
- `T:Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException`

-->
