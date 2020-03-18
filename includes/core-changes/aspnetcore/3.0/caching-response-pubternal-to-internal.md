---
ms.openlocfilehash: ae5a5fbf97ed4a03de7d35b9d5d5ca8de3aebc39
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "72393890"
---
### <a name="caching-responsecaching-pubternal-types-changed-to-internal"></a><span data-ttu-id="b2982-101">캐싱: ResponseCaching "pubternal" 유형이 내부로 변경됨</span><span class="sxs-lookup"><span data-stu-id="b2982-101">Caching: ResponseCaching "pubternal" types changed to internal</span></span>

<span data-ttu-id="b2982-102">ASP.NET Core 3.0에서는 `ResponseCaching`의 "pubternal" 유형이 `internal`로 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b2982-102">In ASP.NET Core 3.0, "pubternal" types in `ResponseCaching` have been changed to `internal`.</span></span>

<span data-ttu-id="b2982-103">또한 `IResponseCachingPolicyProvider` 및 `IResponseCachingKeyProvider`의 기본 구현은 더 이상 `AddResponseCaching` 메서드의 일부로 서비스에 추가되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b2982-103">In addition, default implementations of `IResponseCachingPolicyProvider` and `IResponseCachingKeyProvider` are no longer added to services as part of the `AddResponseCaching` method.</span></span>

#### <a name="change-description"></a><span data-ttu-id="b2982-104">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="b2982-104">Change description</span></span>

<span data-ttu-id="b2982-105">ASP.NET Core에서 "pubternal" 유형은 `public`으로 선언되지만 `.Internal`로 접미사가 지정된 네임스페이스에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2982-105">In ASP.NET Core, "pubternal" types are declared as `public` but reside in a namespace suffixed with `.Internal`.</span></span> <span data-ttu-id="b2982-106">이러한 형식은 공용이지만 지원 정책이 없으며 호환성이 손상되는 변경이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2982-106">While these types are public, they have no support policy and are subject to breaking changes.</span></span> <span data-ttu-id="b2982-107">아쉽게도 이러한 형식의 우발적 사용이 일반적으로 발생하므로 이러한 프로젝트에 대한 호환성이 손상되는 변경이 발생하고 프레임워크를 유지 관리하는 기능이 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2982-107">Unfortunately, accidental use of these types has been common, resulting in breaking changes to these projects and limiting the ability to maintain the framework.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="b2982-108">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="b2982-108">Version introduced</span></span>

<span data-ttu-id="b2982-109">3.0</span><span class="sxs-lookup"><span data-stu-id="b2982-109">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="b2982-110">이전 동작</span><span class="sxs-lookup"><span data-stu-id="b2982-110">Old behavior</span></span>

<span data-ttu-id="b2982-111">이러한 형식은 공개적으로 표시되지만 지원되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b2982-111">These types were publicly visible, but unsupported.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="b2982-112">새 동작</span><span class="sxs-lookup"><span data-stu-id="b2982-112">New behavior</span></span>

<span data-ttu-id="b2982-113">이러한 유형은 이제는 `internal`입니다.</span><span class="sxs-lookup"><span data-stu-id="b2982-113">These types are now `internal`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="b2982-114">변경 이유</span><span class="sxs-lookup"><span data-stu-id="b2982-114">Reason for change</span></span>

<span data-ttu-id="b2982-115">`internal` 범위는 지원되지 않는 정책을 더 잘 반영합니다.</span><span class="sxs-lookup"><span data-stu-id="b2982-115">The `internal` scope better reflects the unsupported policy.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="b2982-116">권장 조치</span><span class="sxs-lookup"><span data-stu-id="b2982-116">Recommended action</span></span>

<span data-ttu-id="b2982-117">앱 또는 라이브러리에서 사용하는 형식을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="b2982-117">Copy types that are used by your app or library.</span></span>

#### <a name="category"></a><span data-ttu-id="b2982-118">범주</span><span class="sxs-lookup"><span data-stu-id="b2982-118">Category</span></span>

<span data-ttu-id="b2982-119">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="b2982-119">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="b2982-120">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="b2982-120">Affected APIs</span></span>

- `Microsoft.AspNetCore.ResponseCaching.Internal.CachedResponse`
- `Microsoft.AspNetCore.ResponseCaching.Internal.CachedVaryByRules`
- `Microsoft.AspNetCore.ResponseCaching.Internal.IResponseCache`
- `Microsoft.AspNetCore.ResponseCaching.Internal.IResponseCacheEntry`
- `Microsoft.AspNetCore.ResponseCaching.Internal.IResponseCachingKeyProvider`
- `Microsoft.AspNetCore.ResponseCaching.Internal.IResponseCachingPolicyProvider`
- `Microsoft.AspNetCore.ResponseCaching.Internal.MemoryResponseCache`
- `Microsoft.AspNetCore.ResponseCaching.Internal.ResponseCachingContext`
- `Microsoft.AspNetCore.ResponseCaching.Internal.ResponseCachingKeyProvider`
- `Microsoft.AspNetCore.ResponseCaching.Internal.ResponseCachingPolicyProvider`
- <xref:Microsoft.AspNetCore.ResponseCaching.ResponseCachingMiddleware.%23ctor(Microsoft.AspNetCore.Http.RequestDelegate,Microsoft.Extensions.Options.IOptions{Microsoft.AspNetCore.ResponseCaching.ResponseCachingOptions},Microsoft.Extensions.Logging.ILoggerFactory,Microsoft.AspNetCore.ResponseCaching.Internal.IResponseCachingPolicyProvider,Microsoft.AspNetCore.ResponseCaching.Internal.IResponseCache,Microsoft.AspNetCore.ResponseCaching.Internal.IResponseCachingKeyProvider)?displayProperty=fullName>

<!-- 

#### Affected APIs

- `T:Microsoft.AspNetCore.ResponseCaching.Internal.CachedResponse`
- `T:Microsoft.AspNetCore.ResponseCaching.Internal.CachedVaryByRules`
- `T:Microsoft.AspNetCore.ResponseCaching.Internal.IResponseCache`
- `T:Microsoft.AspNetCore.ResponseCaching.Internal.IResponseCacheEntry`
- `T:Microsoft.AspNetCore.ResponseCaching.Internal.IResponseCachingKeyProvider`
- `T:Microsoft.AspNetCore.ResponseCaching.Internal.IResponseCachingPolicyProvider`
- `T:Microsoft.AspNetCore.ResponseCaching.Internal.MemoryResponseCache`
- `T:Microsoft.AspNetCore.ResponseCaching.Internal.ResponseCachingContext`
- `T:Microsoft.AspNetCore.ResponseCaching.Internal.ResponseCachingKeyProvider`
- `T:Microsoft.AspNetCore.ResponseCaching.Internal.ResponseCachingPolicyProvider`
- `M:Microsoft.AspNetCore.ResponseCaching.ResponseCachingMiddleware.#ctor(Microsoft.AspNetCore.Http.RequestDelegate,Microsoft.Extensions.Options.IOptions{Microsoft.AspNetCore.ResponseCaching.ResponseCachingOptions},Microsoft.Extensions.Logging.ILoggerFactory,Microsoft.AspNetCore.ResponseCaching.Internal.IResponseCachingPolicyProvider,Microsoft.AspNetCore.ResponseCaching.Internal.IResponseCache,Microsoft.AspNetCore.ResponseCaching.Internal.IResponseCachingKeyProvider)",
"nameWithType": "ResponseCachingMiddleware.ResponseCachingMiddleware(RequestDelegate, IOptions<ResponseCachingOptions>, ILoggerFactory, IResponseCachingPolicyProvider, IResponseCache, IResponseCachingKeyProvider)`

-->
