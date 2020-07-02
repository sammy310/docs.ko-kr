---
ms.openlocfilehash: 29908ed916690e67db3cc5d72ebe1b1c6aea45c6
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325240"
---
### <a name="iis-urlrewrite-middleware-query-strings-are-preserved"></a><span data-ttu-id="a28f8-101">IIS: UrlRewrite 미들웨어 쿼리 문자열이 유지됨</span><span class="sxs-lookup"><span data-stu-id="a28f8-101">IIS: UrlRewrite middleware query strings are preserved</span></span>

<span data-ttu-id="a28f8-102">IIS UrlRewrite 미들웨어 결함으로 인해 쿼리 문자열이 다시 쓰기 규칙에서 유지되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="a28f8-102">An IIS UrlRewrite middleware defect prevented the query string from being preserved in rewrite rules.</span></span> <span data-ttu-id="a28f8-103">IIS UrlRewrite 모듈 동작과 일관성을 유지하기 위해 해당 결함이 수정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a28f8-103">That defect has been fixed to maintain consistency with the IIS UrlRewrite Module's behavior.</span></span>

<span data-ttu-id="a28f8-104">자세한 내용은 이슈 [dotnet/aspnetcore#22972](https://github.com/dotnet/aspnetcore/issues/22972)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a28f8-104">For discussion, see issue [dotnet/aspnetcore#22972](https://github.com/dotnet/aspnetcore/issues/22972).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="a28f8-105">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="a28f8-105">Version introduced</span></span>

<span data-ttu-id="a28f8-106">ASP.NET Core 5.0 미리 보기 7</span><span class="sxs-lookup"><span data-stu-id="a28f8-106">ASP.NET Core 5.0 Preview 7</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="a28f8-107">이전 동작</span><span class="sxs-lookup"><span data-stu-id="a28f8-107">Old behavior</span></span>

<span data-ttu-id="a28f8-108">다음 다시 작성 규칙을 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="a28f8-108">Consider the following rewrite rule:</span></span>

```xml
<rule name="MyRule" stopProcessing="true">
  <match url="^about" />
  <action type="Redirect" url="/contact" redirectType="Temporary" appendQueryString="true" />
</rule>
```

<span data-ttu-id="a28f8-109">위의 규칙에서는 쿼리 문자열을 추가하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a28f8-109">The preceding rule doesn't append the query string.</span></span> <span data-ttu-id="a28f8-110">`/about?id=1`과 같은 URI는 `/contact?id=1`이 아니라 `/contact`로 리디렉션됩니다.</span><span class="sxs-lookup"><span data-stu-id="a28f8-110">A URI like `/about?id=1` redirects to `/contact` instead of `/contact?id=1`.</span></span> <span data-ttu-id="a28f8-111">`appendQueryString` 특성의 기본값도 `true`로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="a28f8-111">The `appendQueryString` attribute defaults to `true` as well.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="a28f8-112">새 동작</span><span class="sxs-lookup"><span data-stu-id="a28f8-112">New behavior</span></span>

<span data-ttu-id="a28f8-113">쿼리 문자열이 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="a28f8-113">The query string is preserved.</span></span> <span data-ttu-id="a28f8-114">[이전 동작](#old-behavior)의 예제에서 URI가 `/contact?id=1`이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a28f8-114">The URI from the example in [Old behavior](#old-behavior) would be `/contact?id=1`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="a28f8-115">변경 이유</span><span class="sxs-lookup"><span data-stu-id="a28f8-115">Reason for change</span></span>

<span data-ttu-id="a28f8-116">이전 동작은 IIS UrlRewrite 모듈의 동작과 일치하지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="a28f8-116">The old behavior didn't match the IIS UrlRewrite Module's behavior.</span></span> <span data-ttu-id="a28f8-117">미들웨어와 모듈 간의 이식을 지원하기 위해서는 일관된 동작을 유지해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a28f8-117">To support porting between the middleware and module, the goal is to maintain consistent behaviors.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="a28f8-118">권장 조치</span><span class="sxs-lookup"><span data-stu-id="a28f8-118">Recommended action</span></span>

<span data-ttu-id="a28f8-119">쿼리 문자열을 제거하는 동작을 원하는 경우 `action` 요소를 `appendQueryString="false"`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a28f8-119">If the behavior of removing the query string is preferred, set the `action` element to `appendQueryString="false"`.</span></span>

#### <a name="category"></a><span data-ttu-id="a28f8-120">범주</span><span class="sxs-lookup"><span data-stu-id="a28f8-120">Category</span></span>

<span data-ttu-id="a28f8-121">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="a28f8-121">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="a28f8-122">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="a28f8-122">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Rewrite.IISUrlRewriteOptionsExtensions.AddIISUrlRewrite%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

`Overload:Microsoft.AspNetCore.Rewrite.IISUrlRewriteOptionsExtensions.AddIISUrlRewrite`

-->
