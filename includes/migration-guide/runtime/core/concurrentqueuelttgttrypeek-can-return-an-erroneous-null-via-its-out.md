---
ms.openlocfilehash: a93fbbd787aa50f080337a6170cf8f56d0d24e31
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59236713"
---
### <a name="concurrentqueuettrypeek-can-return-an-erroneous-null-via-its-out-parameter"></a><span data-ttu-id="24d1b-101">ConcurrentQueue\<T>.TryPeek는 out 매개 변수를 통해 잘못된 null을 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24d1b-101">ConcurrentQueue\<T>.TryPeek can return an erroneous null via its out parameter</span></span>

|   |   |
|---|---|
|<span data-ttu-id="24d1b-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="24d1b-102">Details</span></span>|<span data-ttu-id="24d1b-103">일부 다중 스레드 시나리오에서 <xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=name> true를 반환할 수 있지만 (올바르고 미리 본 값 대신) null 값으로 out 매개 변수를 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="24d1b-103">In some multi-threaded scenarios, <xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=name> can return true, but populate the out parameter with a null value (instead of the correct, peeked value).</span></span>|
|<span data-ttu-id="24d1b-104">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="24d1b-104">Suggestion</span></span>|<span data-ttu-id="24d1b-105">이 문제는 .NET Framework 4.5.1에서 수정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="24d1b-105">This issue is fixed in the .NET Framework 4.5.1.</span></span> <span data-ttu-id="24d1b-106">해당 프레임워크로 업그레이드하면 문제가 해결됩니다.</span><span class="sxs-lookup"><span data-stu-id="24d1b-106">Upgrading to that Framework will solve the issue.</span></span>|
|<span data-ttu-id="24d1b-107">범위</span><span class="sxs-lookup"><span data-stu-id="24d1b-107">Scope</span></span>|<span data-ttu-id="24d1b-108">주요함</span><span class="sxs-lookup"><span data-stu-id="24d1b-108">Major</span></span>|
|<span data-ttu-id="24d1b-109">버전</span><span class="sxs-lookup"><span data-stu-id="24d1b-109">Version</span></span>|<span data-ttu-id="24d1b-110">4.5</span><span class="sxs-lookup"><span data-stu-id="24d1b-110">4.5</span></span>|
|<span data-ttu-id="24d1b-111">형식</span><span class="sxs-lookup"><span data-stu-id="24d1b-111">Type</span></span>|<span data-ttu-id="24d1b-112">런타임</span><span class="sxs-lookup"><span data-stu-id="24d1b-112">Runtime</span></span>|
|<span data-ttu-id="24d1b-113">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="24d1b-113">Affected APIs</span></span>|<ul><li><xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=nameWithType></li></ul>|
