---
ms.openlocfilehash: 74ce1bbc9a887aee3a33eaf05084e8c2000967c2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804577"
---
### <a name="wpf-textbox-selected-text-appears-a-different-color-when-the-text-box-is-inactive"></a><span data-ttu-id="dabe1-101">텍스트 상자가 비활성일 때 WPF TextBox가 선택한 텍스트가 다른 색으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="dabe1-101">WPF TextBox selected text appears a different color when the text box is inactive</span></span>

|   |   |
|---|---|
|<span data-ttu-id="dabe1-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="dabe1-102">Details</span></span>|<span data-ttu-id="dabe1-103">.NET Framework 4.5에서 WPF 텍스트 상자 컨트롤이 비활성화될 때(포커스가 없음) 상자 내의 선택된 텍스트는 컨트롤이 활성일 때와 다른 색을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="dabe1-103">In .NET Framework 4.5, when a WPF text box control is inactive (it doesn't have focus), the selected text inside the box will appear a different color than when the control is active.</span></span>|
|<span data-ttu-id="dabe1-104">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="dabe1-104">Suggestion</span></span>|<span data-ttu-id="dabe1-105"><xref:System.Windows.FrameworkCompatibilityPreferences.AreInactiveSelectionHighlightBrushKeysSupported> 속성을 <code>false</code>로 설정하여 이전(.NET Framework 4.0) 동작을 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dabe1-105">The previous (.NET Framework 4.0) behavior may be restored by setting the <xref:System.Windows.FrameworkCompatibilityPreferences.AreInactiveSelectionHighlightBrushKeysSupported> property to <code>false</code>.</span></span>|
|<span data-ttu-id="dabe1-106">범위</span><span class="sxs-lookup"><span data-stu-id="dabe1-106">Scope</span></span>|<span data-ttu-id="dabe1-107">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="dabe1-107">Edge</span></span>|
|<span data-ttu-id="dabe1-108">버전</span><span class="sxs-lookup"><span data-stu-id="dabe1-108">Version</span></span>|<span data-ttu-id="dabe1-109">4.5</span><span class="sxs-lookup"><span data-stu-id="dabe1-109">4.5</span></span>|
|<span data-ttu-id="dabe1-110">형식</span><span class="sxs-lookup"><span data-stu-id="dabe1-110">Type</span></span>|<span data-ttu-id="dabe1-111">런타임</span><span class="sxs-lookup"><span data-stu-id="dabe1-111">Runtime</span></span>|
|<span data-ttu-id="dabe1-112">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="dabe1-112">Affected APIs</span></span>|<ul><li><xref:System.Windows.Controls.TextBox?displayProperty=nameWithType></li></ul>|
