---
ms.openlocfilehash: edd194fef27d97976f1ff45daec1cd56382bbb55
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235468"
---
### <a name="new-enum-values-in-wpfs-pagerangeselection"></a><span data-ttu-id="0fdd2-101">WPF의 PageRangeSelection에 새 열거형 값</span><span class="sxs-lookup"><span data-stu-id="0fdd2-101">New enum values in WPF's PageRangeSelection</span></span>

|   |   |
|---|---|
|<span data-ttu-id="0fdd2-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="0fdd2-102">Details</span></span>|<span data-ttu-id="0fdd2-103">두 개의 새 멤버(<xref:System.Windows.Controls.PageRangeSelection.CurrentPage?displayProperty=name> 및 <xref:System.Windows.Controls.PageRangeSelection.SelectedPages?displayProperty=name>)가 <xref:System.Windows.Controls.PageRangeSelection?displayProperty=name> 열거형에 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0fdd2-103">Two new members (<xref:System.Windows.Controls.PageRangeSelection.CurrentPage?displayProperty=name> and <xref:System.Windows.Controls.PageRangeSelection.SelectedPages?displayProperty=name>) have been added to the <xref:System.Windows.Controls.PageRangeSelection?displayProperty=name> enum.</span></span>|
|<span data-ttu-id="0fdd2-104">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="0fdd2-104">Suggestion</span></span>|<span data-ttu-id="0fdd2-105">대부분의 경우 이러한 변경은 사용자 코드에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0fdd2-105">In most cases, these changes won't impact user code.</span></span> <span data-ttu-id="0fdd2-106">다만 <xref:System.Windows.Controls.PageRangeSelection?displayProperty=name> 형식의 <xref:System.Enum.GetNames(System.Type)> 또는 <xref:System.Enum.GetValues(System.Type)> 호출에 존재하는 요소의 특정 수에 종속된 코드는 수정되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fdd2-106">Code that depends on a particular number of elements existing in <xref:System.Enum.GetNames(System.Type)> or <xref:System.Enum.GetValues(System.Type)> calls on the <xref:System.Windows.Controls.PageRangeSelection?displayProperty=name> type should be modified, though.</span></span>|
|<span data-ttu-id="0fdd2-107">범위</span><span class="sxs-lookup"><span data-stu-id="0fdd2-107">Scope</span></span>|<span data-ttu-id="0fdd2-108">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="0fdd2-108">Edge</span></span>|
|<span data-ttu-id="0fdd2-109">버전</span><span class="sxs-lookup"><span data-stu-id="0fdd2-109">Version</span></span>|<span data-ttu-id="0fdd2-110">4.5</span><span class="sxs-lookup"><span data-stu-id="0fdd2-110">4.5</span></span>|
|<span data-ttu-id="0fdd2-111">형식</span><span class="sxs-lookup"><span data-stu-id="0fdd2-111">Type</span></span>|<span data-ttu-id="0fdd2-112">런타임</span><span class="sxs-lookup"><span data-stu-id="0fdd2-112">Runtime</span></span>|
|<span data-ttu-id="0fdd2-113">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="0fdd2-113">Affected APIs</span></span>|<ul><li><xref:System.Windows.Controls.PageRangeSelection?displayProperty=nameWithType></li></ul>|
