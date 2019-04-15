---
ms.openlocfilehash: 8b0617d8f021a9534289fd7ae8539cd054684862
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234688"
---
### <a name="wpf-textboxtext-can-be-out-of-sync-with-databinding"></a><span data-ttu-id="a2d93-101">WPF TextBox.Text가 데이터 바인딩과 비동기화될 수 있음</span><span class="sxs-lookup"><span data-stu-id="a2d93-101">WPF TextBox.Text can be out-of-sync with databinding</span></span>

|   |   |
|---|---|
|<span data-ttu-id="a2d93-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="a2d93-102">Details</span></span>|<span data-ttu-id="a2d93-103">경우에 따라 <xref:System.Windows.Controls.TextBox.Text> 속성은 데이터 바인딩 쓰기 작업 중 속성이 수정되면 데이터 바인딩된 속성 값의 이전 값을 반영합니다.</span><span class="sxs-lookup"><span data-stu-id="a2d93-103">In some cases, the <xref:System.Windows.Controls.TextBox.Text> property reflects a previous value of the databound property value if the property is modified during a databinding write operation.</span></span>|
|<span data-ttu-id="a2d93-104">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="a2d93-104">Suggestion</span></span>|<span data-ttu-id="a2d93-105">이는 부정적인 영향을 주어서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2d93-105">This should have no negative impact.</span></span> <span data-ttu-id="a2d93-106">그러나 <xref:System.Windows.FrameworkCompatibilityPreferences.KeepTextBoxDisplaySynchronizedWithTextProperty> 속성을 <code>false</code>로 설정하여 이전 동작을 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2d93-106">However, you can restore the previous behavior by setting the <xref:System.Windows.FrameworkCompatibilityPreferences.KeepTextBoxDisplaySynchronizedWithTextProperty> property to <code>false</code>.</span></span>|
|<span data-ttu-id="a2d93-107">범위</span><span class="sxs-lookup"><span data-stu-id="a2d93-107">Scope</span></span>|<span data-ttu-id="a2d93-108">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="a2d93-108">Edge</span></span>|
|<span data-ttu-id="a2d93-109">버전</span><span class="sxs-lookup"><span data-stu-id="a2d93-109">Version</span></span>|<span data-ttu-id="a2d93-110">4.5</span><span class="sxs-lookup"><span data-stu-id="a2d93-110">4.5</span></span>|
|<span data-ttu-id="a2d93-111">형식</span><span class="sxs-lookup"><span data-stu-id="a2d93-111">Type</span></span>|<span data-ttu-id="a2d93-112">대상 변경</span><span class="sxs-lookup"><span data-stu-id="a2d93-112">Retargeting</span></span>|
|<span data-ttu-id="a2d93-113">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="a2d93-113">Affected APIs</span></span>|<ul><li><xref:System.Windows.Controls.TextBox.Text?displayProperty=nameWithType></li></ul>|
