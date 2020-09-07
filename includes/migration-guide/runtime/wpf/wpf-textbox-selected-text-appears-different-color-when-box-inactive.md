---
ms.openlocfilehash: c01705002ad87a12389078d75ffd0f91f934d36e
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497949"
---
### <a name="wpf-textbox-selected-text-appears-a-different-color-when-the-text-box-is-inactive"></a><span data-ttu-id="cc68d-101">텍스트 상자가 비활성일 때 WPF TextBox가 선택한 텍스트가 다른 색으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc68d-101">WPF TextBox selected text appears a different color when the text box is inactive</span></span>

#### <a name="details"></a><span data-ttu-id="cc68d-102">설명</span><span class="sxs-lookup"><span data-stu-id="cc68d-102">Details</span></span>

<span data-ttu-id="cc68d-103">.NET Framework 4.5에서 WPF 텍스트 상자 컨트롤이 비활성화될 때(포커스가 없음) 상자 내의 선택된 텍스트는 컨트롤이 활성일 때와 다른 색을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="cc68d-103">In .NET Framework 4.5, when a WPF text box control is inactive (it doesn't have focus), the selected text inside the box will appear a different color than when the control is active.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="cc68d-104">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="cc68d-104">Suggestion</span></span>

<span data-ttu-id="cc68d-105"><xref:System.Windows.FrameworkCompatibilityPreferences.AreInactiveSelectionHighlightBrushKeysSupported> 속성을 <code>false</code>로 설정하여 이전(.NET Framework 4.0) 동작을 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc68d-105">The previous (.NET Framework 4.0) behavior may be restored by setting the <xref:System.Windows.FrameworkCompatibilityPreferences.AreInactiveSelectionHighlightBrushKeysSupported> property to <code>false</code>.</span></span>

| <span data-ttu-id="cc68d-106">이름</span><span class="sxs-lookup"><span data-stu-id="cc68d-106">Name</span></span>    | <span data-ttu-id="cc68d-107">값</span><span class="sxs-lookup"><span data-stu-id="cc68d-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="cc68d-108">Scope</span><span class="sxs-lookup"><span data-stu-id="cc68d-108">Scope</span></span>   |<span data-ttu-id="cc68d-109">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="cc68d-109">Edge</span></span>|
|<span data-ttu-id="cc68d-110">버전</span><span class="sxs-lookup"><span data-stu-id="cc68d-110">Version</span></span>|<span data-ttu-id="cc68d-111">4.5</span><span class="sxs-lookup"><span data-stu-id="cc68d-111">4.5</span></span>|
|<span data-ttu-id="cc68d-112">형식</span><span class="sxs-lookup"><span data-stu-id="cc68d-112">Type</span></span>|<span data-ttu-id="cc68d-113">런타임</span><span class="sxs-lookup"><span data-stu-id="cc68d-113">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="cc68d-114">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="cc68d-114">Affected APIs</span></span>

- <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:System.Windows.Controls.TextBox`

-->
