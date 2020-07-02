---
ms.openlocfilehash: 02a15f6b9c02002b60c568b9e1d871af49744092
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622147"
---
### <a name="concurrentqueuelttgttrypeek-can-return-an-erroneous-null-via-its-out-parameter"></a><span data-ttu-id="73b44-101">ConcurrentQueue&lt;T&gt;.TryPeek는 out 매개 변수를 통해 잘못된 null을 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73b44-101">ConcurrentQueue&lt;T&gt;.TryPeek can return an erroneous null via its out parameter</span></span>

#### <a name="details"></a><span data-ttu-id="73b44-102">설명</span><span class="sxs-lookup"><span data-stu-id="73b44-102">Details</span></span>

<span data-ttu-id="73b44-103">일부 다중 스레드 시나리오에서 <xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=fullName> true를 반환할 수 있지만 (올바르고 미리 본 값 대신) null 값으로 out 매개 변수를 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="73b44-103">In some multi-threaded scenarios, <xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=fullName> can return true, but populate the out parameter with a null value (instead of the correct, peeked value).</span></span>

#### <a name="suggestion"></a><span data-ttu-id="73b44-104">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="73b44-104">Suggestion</span></span>

<span data-ttu-id="73b44-105">이 문제는 .NET Framework 4.5.1에서 수정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="73b44-105">This issue is fixed in the .NET Framework 4.5.1.</span></span> <span data-ttu-id="73b44-106">해당 프레임워크로 업그레이드하면 문제가 해결됩니다.</span><span class="sxs-lookup"><span data-stu-id="73b44-106">Upgrading to that Framework will solve the issue.</span></span>

| <span data-ttu-id="73b44-107">이름</span><span class="sxs-lookup"><span data-stu-id="73b44-107">Name</span></span>    | <span data-ttu-id="73b44-108">값</span><span class="sxs-lookup"><span data-stu-id="73b44-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="73b44-109">Scope</span><span class="sxs-lookup"><span data-stu-id="73b44-109">Scope</span></span>   |<span data-ttu-id="73b44-110">주요함</span><span class="sxs-lookup"><span data-stu-id="73b44-110">Major</span></span>|
|<span data-ttu-id="73b44-111">버전</span><span class="sxs-lookup"><span data-stu-id="73b44-111">Version</span></span>|<span data-ttu-id="73b44-112">4.5</span><span class="sxs-lookup"><span data-stu-id="73b44-112">4.5</span></span>|
|<span data-ttu-id="73b44-113">형식</span><span class="sxs-lookup"><span data-stu-id="73b44-113">Type</span></span>|<span data-ttu-id="73b44-114">런타임</span><span class="sxs-lookup"><span data-stu-id="73b44-114">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="73b44-115">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="73b44-115">Affected APIs</span></span>

-<xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=nameWithType></li></ul>|
