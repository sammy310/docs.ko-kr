---
ms.openlocfilehash: 7bf5f7e8a49acc2918dd0d68a1c54a5c277091b0
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496460"
---
### <a name="chained-popups-with-staysopenfalse"></a><span data-ttu-id="735e9-101">StaysOpen = False인 연결된 팝업</span><span class="sxs-lookup"><span data-stu-id="735e9-101">Chained Popups with StaysOpen=False</span></span>

#### <a name="details"></a><span data-ttu-id="735e9-102">설명</span><span class="sxs-lookup"><span data-stu-id="735e9-102">Details</span></span>

<span data-ttu-id="735e9-103">StaysOpen = False인 팝업은 팝업 외부를 클릭하면 닫히게 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="735e9-103">A Popup with StaysOpen=False is supposed to close when you click outside the Popup.</span></span> <span data-ttu-id="735e9-104">이러한 팝업이 두 개 이상 연결된 경우(즉, 한 팝업에 다른 팝업이 포함된 경우) 다음과 같은 여러 문제가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="735e9-104">When two or more such Popups are chained (i.e. one contains another), there were many problems, including:</span></span><ul><li><span data-ttu-id="735e9-105">두 수준을 열고 P2의 외부이면서 P1의 내부인 부분을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="735e9-105">Open two levels, click outside P2 but inside P1.</span></span>  <span data-ttu-id="735e9-106">아무 반응이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="735e9-106">Nothing happens.</span></span></li><li><span data-ttu-id="735e9-107">두 수준을 열고 P1 외부를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="735e9-107">Open two levels, click outside P1.</span></span>  <span data-ttu-id="735e9-108">두 팝업이 닫힙니다.</span><span class="sxs-lookup"><span data-stu-id="735e9-108">Both popups close.</span></span></li><li><span data-ttu-id="735e9-109">두 수준을 열고 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="735e9-109">Open and close two levels.</span></span>  <span data-ttu-id="735e9-110">그런 다음, P2를 다시 열어봅니다.</span><span class="sxs-lookup"><span data-stu-id="735e9-110">Then try to open P2 again.</span></span>  <span data-ttu-id="735e9-111">아무 반응이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="735e9-111">Nothing happens.</span></span></li><li><span data-ttu-id="735e9-112">세 가지 수준을 열어봅니다.</span><span class="sxs-lookup"><span data-stu-id="735e9-112">Try to open three levels.</span></span>  <span data-ttu-id="735e9-113">열리지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="735e9-113">You can't.</span></span>  <span data-ttu-id="735e9-114">(클릭한 위치에 따라 아무 일도 일어나지 않거나 처음 두 수준이 닫힙니다.) 이러한 경우(및 다른 변형)는 이제 정상적으로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="735e9-114">(Either nothing happens or the first two levels close, depending on where you click.) These cases (and other variants) now work as expected.</span></span></li></ul>

| <span data-ttu-id="735e9-115">Name</span><span class="sxs-lookup"><span data-stu-id="735e9-115">Name</span></span>    | <span data-ttu-id="735e9-116">값</span><span class="sxs-lookup"><span data-stu-id="735e9-116">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="735e9-117">Scope</span><span class="sxs-lookup"><span data-stu-id="735e9-117">Scope</span></span>   |<span data-ttu-id="735e9-118">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="735e9-118">Edge</span></span>|
|<span data-ttu-id="735e9-119">버전</span><span class="sxs-lookup"><span data-stu-id="735e9-119">Version</span></span>|<span data-ttu-id="735e9-120">4.7.1</span><span class="sxs-lookup"><span data-stu-id="735e9-120">4.7.1</span></span>|
|<span data-ttu-id="735e9-121">형식</span><span class="sxs-lookup"><span data-stu-id="735e9-121">Type</span></span>|<span data-ttu-id="735e9-122">런타임</span><span class="sxs-lookup"><span data-stu-id="735e9-122">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="735e9-123">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="735e9-123">Affected APIs</span></span>

- <xref:System.Windows.Controls.Primitives.Popup.StaysOpen?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.Windows.Controls.Primitives.Popup.StaysOpen`

-->
