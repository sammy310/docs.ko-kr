---
ms.openlocfilehash: 7d40324e6b0bc4afab9dd39b236f0909f360cc9b
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394191"
---
### <a name="caching-compactonmemorypressure-property-removed"></a><span data-ttu-id="d1f14-101">캐싱: CompactOnMemoryPressure 속성이 제거됨</span><span class="sxs-lookup"><span data-stu-id="d1f14-101">Caching: CompactOnMemoryPressure property removed</span></span>

<span data-ttu-id="d1f14-102">ASP.NET Core 3.0 릴리스에서는 [사용되지 않는 MemoryCacheOptions API](https://github.com/aspnet/Extensions/blob/dc5c593da7b72c82e6fe85abb91d03818f9b700c/src/Caching/Memory/src/MemoryCacheOptions.cs#L17-L18)를 제거했습니다.</span><span class="sxs-lookup"><span data-stu-id="d1f14-102">The ASP.NET Core 3.0 release removed the [obsolete MemoryCacheOptions APIs](https://github.com/aspnet/Extensions/blob/dc5c593da7b72c82e6fe85abb91d03818f9b700c/src/Caching/Memory/src/MemoryCacheOptions.cs#L17-L18).</span></span>

#### <a name="change-description"></a><span data-ttu-id="d1f14-103">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="d1f14-103">Change description</span></span>

<span data-ttu-id="d1f14-104">이 변경 내용은 [aspnet/Caching#221](https://github.com/aspnet/Caching/issues/221)에 대한 후속 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="d1f14-104">This change is a follow-up to [aspnet/Caching#221](https://github.com/aspnet/Caching/issues/221).</span></span> <span data-ttu-id="d1f14-105">자세한 내용은 [aspnet/Extensions#1062](https://github.com/aspnet/Extensions/issues/1062)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d1f14-105">For discussion, see [aspnet/Extensions#1062](https://github.com/aspnet/Extensions/issues/1062).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="d1f14-106">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="d1f14-106">Version introduced</span></span>

<span data-ttu-id="d1f14-107">3.0</span><span class="sxs-lookup"><span data-stu-id="d1f14-107">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="d1f14-108">이전 동작</span><span class="sxs-lookup"><span data-stu-id="d1f14-108">Old behavior</span></span>

<span data-ttu-id="d1f14-109">`MemoryCacheOptions.CompactOnMemoryPressure` 속성을 사용할 수 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="d1f14-109">`MemoryCacheOptions.CompactOnMemoryPressure` property was available.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="d1f14-110">새 동작</span><span class="sxs-lookup"><span data-stu-id="d1f14-110">New behavior</span></span>

<span data-ttu-id="d1f14-111">`MemoryCacheOptions.CompactOnMemoryPressure` 속성이 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d1f14-111">The `MemoryCacheOptions.CompactOnMemoryPressure` property has been removed.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="d1f14-112">변경 이유</span><span class="sxs-lookup"><span data-stu-id="d1f14-112">Reason for change</span></span>

<span data-ttu-id="d1f14-113">자동으로 캐시를 압축하면 문제가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f14-113">Automatically compacting the cache caused problems.</span></span> <span data-ttu-id="d1f14-114">예기치 않은 동작을 방지하려면 필요한 경우에만 캐시를 압축해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f14-114">To avoid unexpected behavior, the cache should only be compacted when needed.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="d1f14-115">권장 작업</span><span class="sxs-lookup"><span data-stu-id="d1f14-115">Recommended action</span></span>

<span data-ttu-id="d1f14-116">캐시를 압축하려면 `MemoryCache`를 다운캐스트하고 필요한 경우 `Compact`를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f14-116">To compact the cache, downcast to `MemoryCache` and call `Compact` when needed.</span></span>

#### <a name="category"></a><span data-ttu-id="d1f14-117">범주</span><span class="sxs-lookup"><span data-stu-id="d1f14-117">Category</span></span>

<span data-ttu-id="d1f14-118">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="d1f14-118">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="d1f14-119">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="d1f14-119">Affected APIs</span></span>

<xref:Microsoft.Extensions.Caching.Memory.MemoryCacheOptions.CompactOnMemoryPressure%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

`Overload:Microsoft.Extensions.Caching.Memory.MemoryCacheOptions.CompactOnMemoryPressure`

-->
