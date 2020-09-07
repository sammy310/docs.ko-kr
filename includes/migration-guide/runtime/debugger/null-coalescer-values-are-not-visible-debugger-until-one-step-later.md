---
ms.openlocfilehash: af8de731ee93d0bfb01042d894f5730570dcdd78
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496383"
---
### <a name="null-coalescer-values-are-not-visible-in-debugger-until-one-step-later"></a><span data-ttu-id="89bc4-101">디버거에서 한 단계가 지날 때까지 null 병합기 값을 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="89bc4-101">Null coalescer values are not visible in debugger until one step later</span></span>

#### <a name="details"></a><span data-ttu-id="89bc4-102">설명</span><span class="sxs-lookup"><span data-stu-id="89bc4-102">Details</span></span>

<span data-ttu-id="89bc4-103">.NET Framework 4.5의 버그로 인해 64 비트 버전의 Framework에서 실행 중인 경우 할당 작업이 실행된 직후 null 병합 작업을 통해 설정된 값이 디버거에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="89bc4-103">A bug in the .NET Framework 4.5 causes values set via a null coalescing operation to not be visible in the debugger immediately after the assignment operation is executed when running on the 64-bit version of the Framework.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="89bc4-104">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="89bc4-104">Suggestion</span></span>

<span data-ttu-id="89bc4-105">디버거에서 한 단계 더 실행하면 로컬/필드의 값이 올바르게 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="89bc4-105">Stepping one additional time in the debugger will cause the local/field's value to be correctly updated.</span></span> <span data-ttu-id="89bc4-106">또한 이 문제는 .NET Framework 4.6에서 해결되어 해당 버전의 Framework로 업그레이드하여 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89bc4-106">Also, this issue has been fixed in the .NET Framework 4.6; upgrading to that version of the Framework should solve the issue.</span></span>

| <span data-ttu-id="89bc4-107">이름</span><span class="sxs-lookup"><span data-stu-id="89bc4-107">Name</span></span>    | <span data-ttu-id="89bc4-108">값</span><span class="sxs-lookup"><span data-stu-id="89bc4-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="89bc4-109">Scope</span><span class="sxs-lookup"><span data-stu-id="89bc4-109">Scope</span></span>   |<span data-ttu-id="89bc4-110">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="89bc4-110">Edge</span></span>|
|<span data-ttu-id="89bc4-111">버전</span><span class="sxs-lookup"><span data-stu-id="89bc4-111">Version</span></span>|<span data-ttu-id="89bc4-112">4.5</span><span class="sxs-lookup"><span data-stu-id="89bc4-112">4.5</span></span>|
|<span data-ttu-id="89bc4-113">형식</span><span class="sxs-lookup"><span data-stu-id="89bc4-113">Type</span></span>|<span data-ttu-id="89bc4-114">런타임</span><span class="sxs-lookup"><span data-stu-id="89bc4-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="89bc4-115">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="89bc4-115">Affected APIs</span></span>

<span data-ttu-id="89bc4-116">API 분석을 통해 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="89bc4-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
