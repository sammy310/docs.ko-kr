---
title: '호환성이 손상되는 변경: IIS: UrlRewrite 미들웨어 쿼리 문자열이 유지됨'
description: 'ASP.NET Core 5.0의 호환성이 손상되는 변경에 대해 알아보기. IIS: UrlRewrite 미들웨어 쿼리 문자열이 유지됨'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: e4d1ecba62f9e43e7377aba1138968f15f8895d5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759600"
---
# <a name="iis-urlrewrite-middleware-query-strings-are-preserved"></a><span data-ttu-id="83b6b-103">IIS: UrlRewrite 미들웨어 쿼리 문자열이 유지됨</span><span class="sxs-lookup"><span data-stu-id="83b6b-103">IIS: UrlRewrite middleware query strings are preserved</span></span>

<span data-ttu-id="83b6b-104">IIS UrlRewrite 미들웨어 결함으로 인해 쿼리 문자열이 다시 쓰기 규칙에서 유지되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="83b6b-104">An IIS UrlRewrite middleware defect prevented the query string from being preserved in rewrite rules.</span></span> <span data-ttu-id="83b6b-105">IIS UrlRewrite 모듈 동작과 일관성을 유지하기 위해 해당 결함이 수정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="83b6b-105">That defect has been fixed to maintain consistency with the IIS UrlRewrite Module's behavior.</span></span>

<span data-ttu-id="83b6b-106">자세한 내용은 이슈 [dotnet/aspnetcore#22972](https://github.com/dotnet/aspnetcore/issues/22972)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="83b6b-106">For discussion, see issue [dotnet/aspnetcore#22972](https://github.com/dotnet/aspnetcore/issues/22972).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="83b6b-107">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="83b6b-107">Version introduced</span></span>

<span data-ttu-id="83b6b-108">ASP.NET Core 5.0 미리 보기 7</span><span class="sxs-lookup"><span data-stu-id="83b6b-108">ASP.NET Core 5.0 Preview 7</span></span>

## <a name="old-behavior"></a><span data-ttu-id="83b6b-109">이전 동작</span><span class="sxs-lookup"><span data-stu-id="83b6b-109">Old behavior</span></span>

<span data-ttu-id="83b6b-110">다음 다시 작성 규칙을 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="83b6b-110">Consider the following rewrite rule:</span></span>

```xml
<rule name="MyRule" stopProcessing="true">
  <match url="^about" />
  <action type="Redirect" url="/contact" redirectType="Temporary" appendQueryString="true" />
</rule>
```

<span data-ttu-id="83b6b-111">위의 규칙에서는 쿼리 문자열을 추가하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="83b6b-111">The preceding rule doesn't append the query string.</span></span> <span data-ttu-id="83b6b-112">`/about?id=1`과 같은 URI는 `/contact?id=1`이 아니라 `/contact`로 리디렉션됩니다.</span><span class="sxs-lookup"><span data-stu-id="83b6b-112">A URI like `/about?id=1` redirects to `/contact` instead of `/contact?id=1`.</span></span> <span data-ttu-id="83b6b-113">`appendQueryString` 특성의 기본값도 `true`로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="83b6b-113">The `appendQueryString` attribute defaults to `true` as well.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="83b6b-114">새 동작</span><span class="sxs-lookup"><span data-stu-id="83b6b-114">New behavior</span></span>

<span data-ttu-id="83b6b-115">쿼리 문자열이 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="83b6b-115">The query string is preserved.</span></span> <span data-ttu-id="83b6b-116">[이전 동작](#old-behavior)의 예제에서 URI가 `/contact?id=1`이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83b6b-116">The URI from the example in [Old behavior](#old-behavior) would be `/contact?id=1`.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="83b6b-117">변경 이유</span><span class="sxs-lookup"><span data-stu-id="83b6b-117">Reason for change</span></span>

<span data-ttu-id="83b6b-118">이전 동작은 IIS UrlRewrite 모듈의 동작과 일치하지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="83b6b-118">The old behavior didn't match the IIS UrlRewrite Module's behavior.</span></span> <span data-ttu-id="83b6b-119">미들웨어와 모듈 간의 이식을 지원하기 위해서는 일관된 동작을 유지해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83b6b-119">To support porting between the middleware and module, the goal is to maintain consistent behaviors.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="83b6b-120">권장 조치</span><span class="sxs-lookup"><span data-stu-id="83b6b-120">Recommended action</span></span>

<span data-ttu-id="83b6b-121">쿼리 문자열을 제거하는 동작을 원하는 경우 `action` 요소를 `appendQueryString="false"`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="83b6b-121">If the behavior of removing the query string is preferred, set the `action` element to `appendQueryString="false"`.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="83b6b-122">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="83b6b-122">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Rewrite.IISUrlRewriteOptionsExtensions.AddIISUrlRewrite%2A?displayProperty=nameWithType>

<!--

### Category

ASP.NET Core

### Affected APIs

`Overload:Microsoft.AspNetCore.Rewrite.IISUrlRewriteOptionsExtensions.AddIISUrlRewrite`

-->
