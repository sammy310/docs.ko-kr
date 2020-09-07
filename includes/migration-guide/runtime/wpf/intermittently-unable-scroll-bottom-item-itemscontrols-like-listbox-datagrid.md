---
ms.openlocfilehash: bca76daca6e9c424377a80aa56e1a5ff191be5ca
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497861"
---
### <a name="intermittently-unable-to-scroll-to-bottom-item-in-itemscontrols-like-listbox-and-datagrid-when-using-custom-datatemplates"></a><span data-ttu-id="8d782-101">사용자 지정 DataTemplate를 사용하는 경우 일시적으로 ItemsControls에서(예: ListBox 및 DataGrid) 하위 항목으로 스크롤할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8d782-101">Intermittently unable to scroll to bottom item in ItemsControls (like ListBox and DataGrid) when using custom DataTemplates</span></span>

#### <a name="details"></a><span data-ttu-id="8d782-102">설명</span><span class="sxs-lookup"><span data-stu-id="8d782-102">Details</span></span>

<span data-ttu-id="8d782-103">일부 인스턴스에서 .NET Framework 4.5의 버그는 사용자 지정 DataTemplates를 사용할 때 ItemsControls(예: <xref:System.Windows.Controls.ListBox?displayProperty=fullName>, <xref:System.Windows.Controls.ComboBox?displayProperty=fullName>, <xref:System.Windows.Controls.DataGrid?displayProperty=fullName> 등)가 아래 항목으로 스크롤되지 않게 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d782-103">In some instances, a bug in the .NET Framework 4.5 is causing ItemsControls (like <xref:System.Windows.Controls.ListBox?displayProperty=fullName>, <xref:System.Windows.Controls.ComboBox?displayProperty=fullName>, <xref:System.Windows.Controls.DataGrid?displayProperty=fullName>, etc.) to not scroll to their bottom item when using custom DataTemplates.</span></span> <span data-ttu-id="8d782-104">스크롤이 두 번째 시도되는 경우(스크롤 백업 후) 그때에는 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="8d782-104">If the scrolling is attempted a second time (after scrolling back up), it will work then.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="8d782-105">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="8d782-105">Suggestion</span></span>

<span data-ttu-id="8d782-106">.NET Framework 4.5.2에서 이 문제가 수정되어 해당 버전(또는 이후 버전)의 .NET Framework로 업그레이드하여 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d782-106">This issue has been fixed in the .NET Framework 4.5.2 and may be addressed by upgrading to that version (or a later version) of the .NET Framework.</span></span> <span data-ttu-id="8d782-107">또는 사용자가 이러한 컬렉션의 마지막 항목까지 스크롤 막대를 끌 수 있지만 성공하려면 두 번 시도해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d782-107">Alternatively, users can still drag scroll bars to the final items in these collections, but may need to try twice to do so successfully.</span></span>

| <span data-ttu-id="8d782-108">이름</span><span class="sxs-lookup"><span data-stu-id="8d782-108">Name</span></span>    | <span data-ttu-id="8d782-109">값</span><span class="sxs-lookup"><span data-stu-id="8d782-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="8d782-110">Scope</span><span class="sxs-lookup"><span data-stu-id="8d782-110">Scope</span></span>   |<span data-ttu-id="8d782-111">부</span><span class="sxs-lookup"><span data-stu-id="8d782-111">Minor</span></span>|
|<span data-ttu-id="8d782-112">버전</span><span class="sxs-lookup"><span data-stu-id="8d782-112">Version</span></span>|<span data-ttu-id="8d782-113">4.5</span><span class="sxs-lookup"><span data-stu-id="8d782-113">4.5</span></span>|
|<span data-ttu-id="8d782-114">형식</span><span class="sxs-lookup"><span data-stu-id="8d782-114">Type</span></span>|<span data-ttu-id="8d782-115">런타임</span><span class="sxs-lookup"><span data-stu-id="8d782-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="8d782-116">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="8d782-116">Affected APIs</span></span>

<span data-ttu-id="8d782-117">API 분석을 통해 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8d782-117">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
