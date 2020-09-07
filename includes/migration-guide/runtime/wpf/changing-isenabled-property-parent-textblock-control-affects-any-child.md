---
ms.openlocfilehash: 12a26030a9a336d887ae9d53994a9daf13356618
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496547"
---
### <a name="changing-the-isenabled-property-of-the-parent-of-a-textblock-control-affects-any-child-controls"></a><span data-ttu-id="96bd9-101">모든 자식 컨트롤에 영향을 주는 TextBlock 컨트롤의 부모 IsEnabled 속성 변경</span><span class="sxs-lookup"><span data-stu-id="96bd9-101">Changing the IsEnabled property of the parent of a TextBlock control affects any child controls</span></span>

#### <a name="details"></a><span data-ttu-id="96bd9-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="96bd9-102">Details</span></span>

<span data-ttu-id="96bd9-103">.NET Framework 4.6.2부터 <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> 컨트롤의 부모 <xref:System.Windows.UIElement.IsEnabled?displayProperty=fullName> 속성을 변경하면 <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> 컨트롤의 모든 자식 컨트롤(예: 하이퍼링크 및 단추)에 영향이 있습니다. .NET Framework 4.6.1 및 이전 버전에서 <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> 내부의 컨트롤은 항상 <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> 부모의 <xref:System.Windows.UIElement.IsEnabled?displayProperty=fullName> 속성 상태를 반영하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="96bd9-103">Starting with the .NET Framework 4.6.2, changing the <xref:System.Windows.UIElement.IsEnabled?displayProperty=fullName> property of the parent of a <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> control affects any child controls (such as hyperlinks and buttons) of the <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> control.In the .NET Framework 4.6.1 and earlier versions, controls inside a <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> did not always reflect the state of the <xref:System.Windows.UIElement.IsEnabled?displayProperty=fullName> property of the <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> parent.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="96bd9-104">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="96bd9-104">Suggestion</span></span>

<span data-ttu-id="96bd9-105">없음</span><span class="sxs-lookup"><span data-stu-id="96bd9-105">None.</span></span> <span data-ttu-id="96bd9-106">이 변경은 <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> 컨트롤 내부에 있는 컨트롤의 정상적인 동작을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="96bd9-106">This change conforms to the expected behavior for controls inside a <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> control.</span></span>

| <span data-ttu-id="96bd9-107">Name</span><span class="sxs-lookup"><span data-stu-id="96bd9-107">Name</span></span>    | <span data-ttu-id="96bd9-108">값</span><span class="sxs-lookup"><span data-stu-id="96bd9-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="96bd9-109">Scope</span><span class="sxs-lookup"><span data-stu-id="96bd9-109">Scope</span></span>   |<span data-ttu-id="96bd9-110">부</span><span class="sxs-lookup"><span data-stu-id="96bd9-110">Minor</span></span>|
|<span data-ttu-id="96bd9-111">버전</span><span class="sxs-lookup"><span data-stu-id="96bd9-111">Version</span></span>|<span data-ttu-id="96bd9-112">4.6.2</span><span class="sxs-lookup"><span data-stu-id="96bd9-112">4.6.2</span></span>|
|<span data-ttu-id="96bd9-113">형식</span><span class="sxs-lookup"><span data-stu-id="96bd9-113">Type</span></span>|<span data-ttu-id="96bd9-114">런타임</span><span class="sxs-lookup"><span data-stu-id="96bd9-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="96bd9-115">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="96bd9-115">Affected APIs</span></span>

- <xref:System.Windows.UIElement.IsEnabled?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.Windows.UIElement.IsEnabled`

-->
