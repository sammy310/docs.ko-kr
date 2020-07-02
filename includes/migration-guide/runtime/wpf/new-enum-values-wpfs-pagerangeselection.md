---
ms.openlocfilehash: bae6d7c0f8843211c721c68ce6f16000b35b4401
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620456"
---
### <a name="new-enum-values-in-wpfs-pagerangeselection"></a><span data-ttu-id="90a14-101">WPF의 PageRangeSelection에 새 열거형 값</span><span class="sxs-lookup"><span data-stu-id="90a14-101">New enum values in WPF's PageRangeSelection</span></span>

#### <a name="details"></a><span data-ttu-id="90a14-102">설명</span><span class="sxs-lookup"><span data-stu-id="90a14-102">Details</span></span>

<span data-ttu-id="90a14-103">두 개의 새 멤버(<xref:System.Windows.Controls.PageRangeSelection.CurrentPage?displayProperty=fullName> 및 <xref:System.Windows.Controls.PageRangeSelection.SelectedPages?displayProperty=fullName>)가 <xref:System.Windows.Controls.PageRangeSelection?displayProperty=fullName> 열거형에 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="90a14-103">Two new members (<xref:System.Windows.Controls.PageRangeSelection.CurrentPage?displayProperty=fullName> and <xref:System.Windows.Controls.PageRangeSelection.SelectedPages?displayProperty=fullName>) have been added to the <xref:System.Windows.Controls.PageRangeSelection?displayProperty=fullName> enum.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="90a14-104">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="90a14-104">Suggestion</span></span>

<span data-ttu-id="90a14-105">대부분의 경우 이러한 변경은 사용자 코드에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="90a14-105">In most cases, these changes won't impact user code.</span></span> <span data-ttu-id="90a14-106">다만 <xref:System.Windows.Controls.PageRangeSelection?displayProperty=fullName> 형식의 <xref:System.Enum.GetNames(System.Type)> 또는 <xref:System.Enum.GetValues(System.Type)> 호출에 존재하는 요소의 특정 수에 종속된 코드는 수정되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="90a14-106">Code that depends on a particular number of elements existing in <xref:System.Enum.GetNames(System.Type)> or <xref:System.Enum.GetValues(System.Type)> calls on the <xref:System.Windows.Controls.PageRangeSelection?displayProperty=fullName> type should be modified, though.</span></span>

| <span data-ttu-id="90a14-107">이름</span><span class="sxs-lookup"><span data-stu-id="90a14-107">Name</span></span>    | <span data-ttu-id="90a14-108">값</span><span class="sxs-lookup"><span data-stu-id="90a14-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="90a14-109">Scope</span><span class="sxs-lookup"><span data-stu-id="90a14-109">Scope</span></span>   |<span data-ttu-id="90a14-110">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="90a14-110">Edge</span></span>|
|<span data-ttu-id="90a14-111">버전</span><span class="sxs-lookup"><span data-stu-id="90a14-111">Version</span></span>|<span data-ttu-id="90a14-112">4.5</span><span class="sxs-lookup"><span data-stu-id="90a14-112">4.5</span></span>|
|<span data-ttu-id="90a14-113">형식</span><span class="sxs-lookup"><span data-stu-id="90a14-113">Type</span></span>|<span data-ttu-id="90a14-114">런타임</span><span class="sxs-lookup"><span data-stu-id="90a14-114">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="90a14-115">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="90a14-115">Affected APIs</span></span>

-<xref:System.Windows.Controls.PageRangeSelection?displayProperty=nameWithType></li></ul>|
