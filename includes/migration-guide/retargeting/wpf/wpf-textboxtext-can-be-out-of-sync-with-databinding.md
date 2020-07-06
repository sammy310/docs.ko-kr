---
ms.openlocfilehash: d0de1a262d57c67dd4dfb258d5ac013af5d8783d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617233"
---
### <a name="wpf-textboxtext-can-be-out-of-sync-with-databinding"></a><span data-ttu-id="51aae-101">WPF TextBox.Text가 데이터 바인딩과 비동기화될 수 있음</span><span class="sxs-lookup"><span data-stu-id="51aae-101">WPF TextBox.Text can be out-of-sync with databinding</span></span>

#### <a name="details"></a><span data-ttu-id="51aae-102">설명</span><span class="sxs-lookup"><span data-stu-id="51aae-102">Details</span></span>

<span data-ttu-id="51aae-103">경우에 따라 <xref:System.Windows.Controls.TextBox.Text> 속성은 데이터 바인딩 쓰기 작업 중 속성이 수정되면 데이터 바인딩된 속성 값의 이전 값을 반영합니다.</span><span class="sxs-lookup"><span data-stu-id="51aae-103">In some cases, the <xref:System.Windows.Controls.TextBox.Text> property reflects a previous value of the databound property value if the property is modified during a databinding write operation.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="51aae-104">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="51aae-104">Suggestion</span></span>

<span data-ttu-id="51aae-105">이는 부정적인 영향을 주어서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="51aae-105">This should have no negative impact.</span></span> <span data-ttu-id="51aae-106">그러나 <xref:System.Windows.FrameworkCompatibilityPreferences.KeepTextBoxDisplaySynchronizedWithTextProperty> 속성을 `false`로 설정하여 이전 동작을 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51aae-106">However, you can restore the previous behavior by setting the <xref:System.Windows.FrameworkCompatibilityPreferences.KeepTextBoxDisplaySynchronizedWithTextProperty> property to `false`.</span></span>

| <span data-ttu-id="51aae-107">이름</span><span class="sxs-lookup"><span data-stu-id="51aae-107">Name</span></span>    | <span data-ttu-id="51aae-108">값</span><span class="sxs-lookup"><span data-stu-id="51aae-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="51aae-109">Scope</span><span class="sxs-lookup"><span data-stu-id="51aae-109">Scope</span></span>   | <span data-ttu-id="51aae-110">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="51aae-110">Edge</span></span>        |
| <span data-ttu-id="51aae-111">버전</span><span class="sxs-lookup"><span data-stu-id="51aae-111">Version</span></span> | <span data-ttu-id="51aae-112">4.5</span><span class="sxs-lookup"><span data-stu-id="51aae-112">4.5</span></span>         |
|<span data-ttu-id="51aae-113">형식</span><span class="sxs-lookup"><span data-stu-id="51aae-113">Type</span></span>|<span data-ttu-id="51aae-114">대상 변경</span><span class="sxs-lookup"><span data-stu-id="51aae-114">Retargeting</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="51aae-115">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="51aae-115">Affected APIs</span></span>

- <xref:System.Windows.Controls.TextBox.Text?displayProperty=nameWithType>
