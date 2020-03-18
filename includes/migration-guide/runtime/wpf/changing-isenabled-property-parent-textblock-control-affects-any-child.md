---
ms.openlocfilehash: 735278848cb7399e414a128afc650a0a1f882337
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2020
ms.locfileid: "67857507"
---
### <a name="changing-the-isenabled-property-of-the-parent-of-a-textblock-control-affects-any-child-controls"></a><span data-ttu-id="cd653-101">모든 자식 컨트롤에 영향을 주는 TextBlock 컨트롤의 부모 IsEnabled 속성 변경</span><span class="sxs-lookup"><span data-stu-id="cd653-101">Changing the IsEnabled property of the parent of a TextBlock control affects any child controls</span></span>

|   |   |
|---|---|
|<span data-ttu-id="cd653-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="cd653-102">Details</span></span>|<span data-ttu-id="cd653-103">.NET Framework 4.6.2부터 <xref:System.Windows.UIElement.IsEnabled?displayProperty=name> 컨트롤의 부모 <xref:System.Windows.Controls.TextBlock?displayProperty=name> 속성을 변경하면 <xref:System.Windows.Controls.TextBlock?displayProperty=name> 컨트롤의 모든 자식 컨트롤(예: 하이퍼링크 및 단추)에 영향이 있습니다. .NET Framework 4.6.1 및 이전 버전에서 <xref:System.Windows.Controls.TextBlock?displayProperty=name> 내부의 컨트롤은 항상 <xref:System.Windows.UIElement.IsEnabled?displayProperty=name> 부모의 <xref:System.Windows.Controls.TextBlock?displayProperty=name> 속성 상태를 반영하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cd653-103">Starting with the .NET Framework 4.6.2, changing the <xref:System.Windows.UIElement.IsEnabled?displayProperty=name> property of the parent of a <xref:System.Windows.Controls.TextBlock?displayProperty=name> control affects any child controls (such as hyperlinks and buttons) of the <xref:System.Windows.Controls.TextBlock?displayProperty=name> control.In the .NET Framework 4.6.1 and earlier versions, controls inside a <xref:System.Windows.Controls.TextBlock?displayProperty=name> did not always reflect the state of the <xref:System.Windows.UIElement.IsEnabled?displayProperty=name> property of the <xref:System.Windows.Controls.TextBlock?displayProperty=name> parent.</span></span>|
|<span data-ttu-id="cd653-104">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="cd653-104">Suggestion</span></span>|<span data-ttu-id="cd653-105">없음</span><span class="sxs-lookup"><span data-stu-id="cd653-105">None.</span></span> <span data-ttu-id="cd653-106">이 변경은 <xref:System.Windows.Controls.TextBlock?displayProperty=name> 컨트롤 내부에 있는 컨트롤의 정상적인 동작을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="cd653-106">This change conforms to the expected behavior for controls inside a <xref:System.Windows.Controls.TextBlock?displayProperty=name> control.</span></span>|
|<span data-ttu-id="cd653-107">범위</span><span class="sxs-lookup"><span data-stu-id="cd653-107">Scope</span></span>|<span data-ttu-id="cd653-108">사소함</span><span class="sxs-lookup"><span data-stu-id="cd653-108">Minor</span></span>|
|<span data-ttu-id="cd653-109">Version</span><span class="sxs-lookup"><span data-stu-id="cd653-109">Version</span></span>|<span data-ttu-id="cd653-110">4.6.2</span><span class="sxs-lookup"><span data-stu-id="cd653-110">4.6.2</span></span>|
|<span data-ttu-id="cd653-111">형식</span><span class="sxs-lookup"><span data-stu-id="cd653-111">Type</span></span>|<span data-ttu-id="cd653-112">런타임</span><span class="sxs-lookup"><span data-stu-id="cd653-112">Runtime</span></span>|
|<span data-ttu-id="cd653-113">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="cd653-113">Affected APIs</span></span>|<ul><li><xref:System.Windows.UIElement.IsEnabled?displayProperty=nameWithType></li></ul>|
