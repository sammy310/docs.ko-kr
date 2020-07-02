---
ms.openlocfilehash: 395463225e3c1f1d168dd019ea75966ad54e5a8a
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621261"
---
### <a name="changing-the-isenabled-property-of-the-parent-of-a-textblock-control-affects-any-child-controls"></a><span data-ttu-id="af032-101">모든 자식 컨트롤에 영향을 주는 TextBlock 컨트롤의 부모 IsEnabled 속성 변경</span><span class="sxs-lookup"><span data-stu-id="af032-101">Changing the IsEnabled property of the parent of a TextBlock control affects any child controls</span></span>

#### <a name="details"></a><span data-ttu-id="af032-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="af032-102">Details</span></span>

<span data-ttu-id="af032-103">.NET Framework 4.6.2부터 <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> 컨트롤의 부모 <xref:System.Windows.UIElement.IsEnabled?displayProperty=fullName> 속성을 변경하면 <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> 컨트롤의 모든 자식 컨트롤(예: 하이퍼링크 및 단추)에 영향이 있습니다. .NET Framework 4.6.1 및 이전 버전에서 <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> 내부의 컨트롤은 항상 <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> 부모의 <xref:System.Windows.UIElement.IsEnabled?displayProperty=fullName> 속성 상태를 반영하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="af032-103">Starting with the .NET Framework 4.6.2, changing the <xref:System.Windows.UIElement.IsEnabled?displayProperty=fullName> property of the parent of a <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> control affects any child controls (such as hyperlinks and buttons) of the <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> control.In the .NET Framework 4.6.1 and earlier versions, controls inside a <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> did not always reflect the state of the <xref:System.Windows.UIElement.IsEnabled?displayProperty=fullName> property of the <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> parent.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="af032-104">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="af032-104">Suggestion</span></span>

<span data-ttu-id="af032-105">없음</span><span class="sxs-lookup"><span data-stu-id="af032-105">None.</span></span> <span data-ttu-id="af032-106">이 변경은 <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> 컨트롤 내부에 있는 컨트롤의 정상적인 동작을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="af032-106">This change conforms to the expected behavior for controls inside a <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> control.</span></span>

| <span data-ttu-id="af032-107">이름</span><span class="sxs-lookup"><span data-stu-id="af032-107">Name</span></span>    | <span data-ttu-id="af032-108">값</span><span class="sxs-lookup"><span data-stu-id="af032-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="af032-109">Scope</span><span class="sxs-lookup"><span data-stu-id="af032-109">Scope</span></span>   |<span data-ttu-id="af032-110">부</span><span class="sxs-lookup"><span data-stu-id="af032-110">Minor</span></span>|
|<span data-ttu-id="af032-111">버전</span><span class="sxs-lookup"><span data-stu-id="af032-111">Version</span></span>|<span data-ttu-id="af032-112">4.6.2</span><span class="sxs-lookup"><span data-stu-id="af032-112">4.6.2</span></span>|
|<span data-ttu-id="af032-113">형식</span><span class="sxs-lookup"><span data-stu-id="af032-113">Type</span></span>|<span data-ttu-id="af032-114">런타임</span><span class="sxs-lookup"><span data-stu-id="af032-114">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="af032-115">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="af032-115">Affected APIs</span></span>

-<xref:System.Windows.UIElement.IsEnabled?displayProperty=nameWithType></li></ul>|
