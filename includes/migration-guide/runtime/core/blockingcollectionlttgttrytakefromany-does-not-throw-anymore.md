---
ms.openlocfilehash: 277a91fbfbf0c6aaaa0dc044ef0c079ad8607699
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497855"
---
### <a name="blockingcollectionlttgttrytakefromany-does-not-throw-anymore"></a><span data-ttu-id="b1733-101">BlockingCollection&lt;T&gt;.TryTakeFromAny는 더 이상 throw하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b1733-101">BlockingCollection&lt;T&gt;.TryTakeFromAny does not throw anymore</span></span>

#### <a name="details"></a><span data-ttu-id="b1733-102">설명</span><span class="sxs-lookup"><span data-stu-id="b1733-102">Details</span></span>

<span data-ttu-id="b1733-103">입력 컬렉션 중 하나가 완료됨으로 표시될 경우 <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@)>은 더이상 -1을 반환하지 않고 <xref:System.Collections.Concurrent.BlockingCollection%601.TakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@)>는 더 이상 예외를 throw하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b1733-103">If one of the input collections is marked completed, <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@)> no longer returns -1 and <xref:System.Collections.Concurrent.BlockingCollection%601.TakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@)> no longer throws an exception.</span></span> <span data-ttu-id="b1733-104">이러한 변경을 통해 컬렉션 중 하나가 비어 있거나 완료되었더라도 나머지 컬렉션에는 검색할 수 있는 항목이 아직 있는 경우 컬렉션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1733-104">This change makes it possible to work with collections when one of the collections is either empty or completed, but the other collection still has items that can be retrieved.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="b1733-105">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="b1733-105">Suggestion</span></span>

<span data-ttu-id="b1733-106">차단 컬렉션 완료 시 제어 흐름 목적으로 -1을 반환하는 TryTakeFromAny 또는 throw하는 TakeFromAny가 사용된 경우, 이러한 코드는 <code>.Any(b =&gt; b.IsCompleted)</code>를 사용하도록 변경되어 해당 조건을 검색하도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1733-106">If TryTakeFromAny returning -1 or TakeFromAny throwing were used for control-flow purposes in cases of a blocking collection being completed, such code should now be changed to use <code>.Any(b =&gt; b.IsCompleted)</code> to detect that condition.</span></span>

| <span data-ttu-id="b1733-107">이름</span><span class="sxs-lookup"><span data-stu-id="b1733-107">Name</span></span>    | <span data-ttu-id="b1733-108">값</span><span class="sxs-lookup"><span data-stu-id="b1733-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="b1733-109">Scope</span><span class="sxs-lookup"><span data-stu-id="b1733-109">Scope</span></span>   |<span data-ttu-id="b1733-110">부</span><span class="sxs-lookup"><span data-stu-id="b1733-110">Minor</span></span>|
|<span data-ttu-id="b1733-111">버전</span><span class="sxs-lookup"><span data-stu-id="b1733-111">Version</span></span>|<span data-ttu-id="b1733-112">4.5</span><span class="sxs-lookup"><span data-stu-id="b1733-112">4.5</span></span>|
|<span data-ttu-id="b1733-113">형식</span><span class="sxs-lookup"><span data-stu-id="b1733-113">Type</span></span>|<span data-ttu-id="b1733-114">런타임</span><span class="sxs-lookup"><span data-stu-id="b1733-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="b1733-115">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="b1733-115">Affected APIs</span></span>

- <xref:System.Collections.Concurrent.BlockingCollection%601.TakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@)?displayProperty=nameWithType>
- <xref:System.Collections.Concurrent.BlockingCollection%601.TakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@,System.Threading.CancellationToken)?displayProperty=nameWithType>
- <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@)?displayProperty=nameWithType>
- <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@,System.Int32)?displayProperty=nameWithType>
- <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@,System.TimeSpan)?displayProperty=nameWithType>
- <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@,System.TimeSpan)?displayProperty=nameWithType>

<!--

#### Affected APIs

- ``M:System.Collections.Concurrent.BlockingCollection`1.TakeFromAny(System.Collections.Concurrent.BlockingCollection{`0}[],`0@)``
- ``M:System.Collections.Concurrent.BlockingCollection`1.TakeFromAny(System.Collections.Concurrent.BlockingCollection{`0}[],`0@,System.Threading.CancellationToken)``
- ``M:System.Collections.Concurrent.BlockingCollection`1.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{`0}[],`0@)``
- ``M:System.Collections.Concurrent.BlockingCollection`1.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{`0}[],`0@,System.Int32)``
- ``M:System.Collections.Concurrent.BlockingCollection`1.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{`0}[],`0@,System.TimeSpan)``
- ``M:System.Collections.Concurrent.BlockingCollection`1.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{`0}[],`0@,System.TimeSpan)``

-->
