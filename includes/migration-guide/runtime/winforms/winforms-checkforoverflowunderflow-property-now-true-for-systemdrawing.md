---
ms.openlocfilehash: 68b0c4bb032b9744ef585eaef3d68e31afebee24
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496440"
---
### <a name="winforms-checkforoverflowunderflow-property-is-now-true-for-systemdrawing"></a><span data-ttu-id="3d242-101">WinForm의 CheckForOverflowUnderflow 속성은 이제 System.Drawing에 대해 true입니다.</span><span class="sxs-lookup"><span data-stu-id="3d242-101">WinForm's CheckForOverflowUnderflow property is now true for System.Drawing</span></span>

#### <a name="details"></a><span data-ttu-id="3d242-102">설명</span><span class="sxs-lookup"><span data-stu-id="3d242-102">Details</span></span>

<span data-ttu-id="3d242-103">System.Drawing.dll 어셈블리의 CheckForOverflowUnderflow 속성이 true로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d242-103">The CheckForOverflowUnderflow property for the System.Drawing.dll assembly is set to true.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="3d242-104">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="3d242-104">Suggestion</span></span>

<span data-ttu-id="3d242-105">이전에 오버플로가 발생했을 때는 결과가 자동으로 잘렸습니다.</span><span class="sxs-lookup"><span data-stu-id="3d242-105">Previously when overflows occurred, the result would be silently truncated.</span></span> <span data-ttu-id="3d242-106">이제 <xref:System.OverflowException?displayProperty=fullName> 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d242-106">Now an <xref:System.OverflowException?displayProperty=fullName> exception is thrown.</span></span>

| <span data-ttu-id="3d242-107">이름</span><span class="sxs-lookup"><span data-stu-id="3d242-107">Name</span></span>    | <span data-ttu-id="3d242-108">값</span><span class="sxs-lookup"><span data-stu-id="3d242-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="3d242-109">Scope</span><span class="sxs-lookup"><span data-stu-id="3d242-109">Scope</span></span>   |<span data-ttu-id="3d242-110">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="3d242-110">Edge</span></span>|
|<span data-ttu-id="3d242-111">버전</span><span class="sxs-lookup"><span data-stu-id="3d242-111">Version</span></span>|<span data-ttu-id="3d242-112">4.5</span><span class="sxs-lookup"><span data-stu-id="3d242-112">4.5</span></span>|
|<span data-ttu-id="3d242-113">형식</span><span class="sxs-lookup"><span data-stu-id="3d242-113">Type</span></span>|<span data-ttu-id="3d242-114">런타임</span><span class="sxs-lookup"><span data-stu-id="3d242-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="3d242-115">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="3d242-115">Affected APIs</span></span>

<span data-ttu-id="3d242-116">API 분석을 통해 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3d242-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
