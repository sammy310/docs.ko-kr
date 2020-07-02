---
ms.openlocfilehash: 1be68c2968d0eaa9024007bcf37abf9e44c36f1c
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622148"
---
### <a name="scrolling-a-wpf-treeview-or-grouped-listbox-in-a-virtualizingstackpanel-can-cause-a-hang"></a><span data-ttu-id="fc1d0-101">VirtualizingStackPanel에서 WPF TreeView 또는 그룹화된 ListBox를 스크롤하면 중단될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc1d0-101">Scrolling a WPF TreeView or grouped ListBox in a VirtualizingStackPanel can cause a hang</span></span>

#### <a name="details"></a><span data-ttu-id="fc1d0-102">설명</span><span class="sxs-lookup"><span data-stu-id="fc1d0-102">Details</span></span>

<span data-ttu-id="fc1d0-103">.NET Framework v4.5에서 뷰포트에 여백이 있는 경우 가상화된 스택 패널의 WPF <xref:System.Windows.Controls.TreeView?displayProperty=fullName>을 스크롤하면 중단이 발생할 수 있습니다(예: 항목 간 <xref:System.Windows.Controls.TreeView?displayProperty=fullName> 또는 ItemsPresenter 요소).</span><span class="sxs-lookup"><span data-stu-id="fc1d0-103">In the .NET Framework v4.5, scrolling a WPF <xref:System.Windows.Controls.TreeView?displayProperty=fullName> in a virtualized stack panel can cause hangs if there are margins in the viewport (between the items in the <xref:System.Windows.Controls.TreeView?displayProperty=fullName>, for example, or on an ItemsPresenter element).</span></span> <span data-ttu-id="fc1d0-104">또한 일부 경우에는 보기에서 다양한 크기의 항목은 여백이 없더라도 불안정해 보일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc1d0-104">Additionally, in some cases, different sized items in the view can cause instability even if there are no margins.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="fc1d0-105">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="fc1d0-105">Suggestion</span></span>

<span data-ttu-id="fc1d0-106">.NET Framework 4.5.1로 업그레이드하여 이 버그를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc1d0-106">This bug can be avoided by upgrading to .NET Framework 4.5.1.</span></span> <span data-ttu-id="fc1d0-107">또는 포함된 모든 항목이 같은 크기인 경우 가상화된 스택 패널 내에서 여백을 보기 컬렉션(예: <xref:System.Windows.Controls.TreeView?displayProperty=fullName>)으로부터 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc1d0-107">Alternatively, margins can be removed from view collections (like <xref:System.Windows.Controls.TreeView?displayProperty=fullName>s) within virtualized stack panels if all contained items are the same size.</span></span>

| <span data-ttu-id="fc1d0-108">이름</span><span class="sxs-lookup"><span data-stu-id="fc1d0-108">Name</span></span>    | <span data-ttu-id="fc1d0-109">값</span><span class="sxs-lookup"><span data-stu-id="fc1d0-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="fc1d0-110">Scope</span><span class="sxs-lookup"><span data-stu-id="fc1d0-110">Scope</span></span>   |<span data-ttu-id="fc1d0-111">주요함</span><span class="sxs-lookup"><span data-stu-id="fc1d0-111">Major</span></span>|
|<span data-ttu-id="fc1d0-112">버전</span><span class="sxs-lookup"><span data-stu-id="fc1d0-112">Version</span></span>|<span data-ttu-id="fc1d0-113">4.5</span><span class="sxs-lookup"><span data-stu-id="fc1d0-113">4.5</span></span>|
|<span data-ttu-id="fc1d0-114">형식</span><span class="sxs-lookup"><span data-stu-id="fc1d0-114">Type</span></span>|<span data-ttu-id="fc1d0-115">런타임</span><span class="sxs-lookup"><span data-stu-id="fc1d0-115">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="fc1d0-116">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="fc1d0-116">Affected APIs</span></span>

-<xref:System.Windows.Controls.VirtualizingStackPanel.SetIsVirtualizing(System.Windows.DependencyObject,System.Boolean)?displayProperty=nameWithType></li></ul>|
