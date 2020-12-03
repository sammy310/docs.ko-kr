---
title: '호환성이 손상되는 변경: HTTP: Kestrel 및 IIS BadHttpRequestException 형식이 사용되지 않는 것으로 표시되고 대체됨'
description: 'ASP.NET Core 5.0의 호환성이 손상되는 변경에 대해 알아보기. HTTP: Kestrel 및 IIS BadHttpRequestException 형식이 사용되지 않는 것으로 표시되고 대체됨'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: c51b1dd9d708c04bc1bbcfb65ea2e9daea5330b4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759724"
---
# <a name="http-kestrel-and-iis-badhttprequestexception-types-marked-obsolete-and-replaced"></a><span data-ttu-id="2f10d-103">HTTP: Kestrel 및 IIS BadHttpRequestException 형식이 사용되지 않는 것으로 표시되고 대체됨</span><span class="sxs-lookup"><span data-stu-id="2f10d-103">HTTP: Kestrel and IIS BadHttpRequestException types marked obsolete and replaced</span></span>

<span data-ttu-id="2f10d-104">`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` 및 `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException`은 사용되지 않는 것으로 표시되며 `Microsoft.AspNetCore.Http.BadHttpRequestException`에서 파생되도록 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2f10d-104">`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` and `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` have been marked obsolete and changed to derive from `Microsoft.AspNetCore.Http.BadHttpRequestException`.</span></span> <span data-ttu-id="2f10d-105">Kestrel 및 IIS 서버는 이전 버전과의 호환성을 위해 이전 예외 형식을 계속 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="2f10d-105">The Kestrel and IIS servers still throw their old exception types for backwards compatibility.</span></span> <span data-ttu-id="2f10d-106">사용 되지 않는 형식은 이후 릴리스에서 제거될 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="2f10d-106">The obsolete types will be removed in a future release.</span></span>

<span data-ttu-id="2f10d-107">자세한 내용은 [dotnet/aspnetcore#20614](https://github.com/dotnet/aspnetcore/issues/20614)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2f10d-107">For discussion, see [dotnet/aspnetcore#20614](https://github.com/dotnet/aspnetcore/issues/20614).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="2f10d-108">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="2f10d-108">Version introduced</span></span>

<span data-ttu-id="2f10d-109">5.0 미리 보기 4</span><span class="sxs-lookup"><span data-stu-id="2f10d-109">5.0 Preview 4</span></span>

## <a name="old-behavior"></a><span data-ttu-id="2f10d-110">이전 동작</span><span class="sxs-lookup"><span data-stu-id="2f10d-110">Old behavior</span></span>

<span data-ttu-id="2f10d-111">`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` 및 `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException`이 <xref:System.IO.IOException?displayProperty=nameWithType>에서 파생되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2f10d-111">`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` and `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` derived from <xref:System.IO.IOException?displayProperty=nameWithType>.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="2f10d-112">새 동작</span><span class="sxs-lookup"><span data-stu-id="2f10d-112">New behavior</span></span>

<span data-ttu-id="2f10d-113">`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` 및 `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException`는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2f10d-113">`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` and `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` are obsolete.</span></span> <span data-ttu-id="2f10d-114">또한 형식은 `System.IO.IOException`에서 파생되는 `Microsoft.AspNetCore.Http.BadHttpRequestException`에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f10d-114">The types also derive from `Microsoft.AspNetCore.Http.BadHttpRequestException`, which derives from `System.IO.IOException`.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="2f10d-115">변경 이유</span><span class="sxs-lookup"><span data-stu-id="2f10d-115">Reason for change</span></span>

<span data-ttu-id="2f10d-116">변경 내용:</span><span class="sxs-lookup"><span data-stu-id="2f10d-116">The change was made to:</span></span>

* <span data-ttu-id="2f10d-117">중복된 형식을 통합합니다.</span><span class="sxs-lookup"><span data-stu-id="2f10d-117">Consolidate duplicate types.</span></span>
* <span data-ttu-id="2f10d-118">여러 서버 구현에서 동작을 통합합니다.</span><span class="sxs-lookup"><span data-stu-id="2f10d-118">Unify behavior across server implementations.</span></span>

<span data-ttu-id="2f10d-119">이제 앱은 Kestrel 또는 IIS를 사용할 때 기본 예외 `Microsoft.AspNetCore.Http.BadHttpRequestException`을 catch할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f10d-119">An app can now catch the base exception `Microsoft.AspNetCore.Http.BadHttpRequestException` when using either Kestrel or IIS.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="2f10d-120">권장 조치</span><span class="sxs-lookup"><span data-stu-id="2f10d-120">Recommended action</span></span>

<span data-ttu-id="2f10d-121">`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` 및 `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` 사용을 `Microsoft.AspNetCore.Http.BadHttpRequestException`으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="2f10d-121">Replace usages of `Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` and `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` with `Microsoft.AspNetCore.Http.BadHttpRequestException`.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="2f10d-122">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="2f10d-122">Affected APIs</span></span>

- [<span data-ttu-id="2f10d-123">Microsoft.AspNetCore.Server.IIS.BadHttpRequestException</span><span class="sxs-lookup"><span data-stu-id="2f10d-123">Microsoft.AspNetCore.Server.IIS.BadHttpRequestException</span></span>](/dotnet/api/microsoft.aspnetcore.server.iis.badhttprequestexception?view=aspnetcore-3.1)
- [<span data-ttu-id="2f10d-124">Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException</span><span class="sxs-lookup"><span data-stu-id="2f10d-124">Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException</span></span>](/dotnet/api/microsoft.aspnetcore.server.kestrel.badhttprequestexception?view=aspnetcore-1.1)

<!--

### Category

ASP.NET Core

### Affected APIs

- `T:Microsoft.AspNetCore.Server.IIS.BadHttpRequestException`
- `T:Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException`

-->
