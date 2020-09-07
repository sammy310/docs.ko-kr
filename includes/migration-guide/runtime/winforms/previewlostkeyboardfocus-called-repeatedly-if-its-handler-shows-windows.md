---
ms.openlocfilehash: c4a3d903894027a01d32ca132d1233da9d9c3ee5
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496468"
---
### <a name="previewlostkeyboardfocus-is-called-repeatedly-if-its-handler-shows-a-windows-forms-message-box"></a><span data-ttu-id="4d046-101">PreviewLostKeyboardFocus는 처리기가 Windows Forms 메시지 상자를 표시하는 경우 반복적으로 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d046-101">PreviewLostKeyboardFocus is called repeatedly if its handler shows a Windows Forms message box</span></span>

#### <a name="details"></a><span data-ttu-id="4d046-102">설명</span><span class="sxs-lookup"><span data-stu-id="4d046-102">Details</span></span>

<span data-ttu-id="4d046-103">.NET Framework 4.5부터 <xref:System.Windows.UIElement.PreviewLostKeyboardFocus> 처리기에서 <xref:System.Windows.Forms.MessageBox.Show%2A?displayProperty=nameWithType>를 호출하면 메시지 상자가 닫힐 때 처리기가 다시 발생하여 잠재적으로 메시지 상자의 무한 루프를 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="4d046-103">Beginning in the .NET Framework 4.5, calling <xref:System.Windows.Forms.MessageBox.Show%2A?displayProperty=nameWithType> from a <xref:System.Windows.UIElement.PreviewLostKeyboardFocus> handler will cause the handler to re-fire when the message box is closed, potentially resulting in an infinite loop of message boxes.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="4d046-104">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="4d046-104">Suggestion</span></span>

<span data-ttu-id="4d046-105">이 문제는 다음 두 가지 옵션으로 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d046-105">There are two options to work around this issue:</span></span><ol><li><span data-ttu-id="4d046-106">이것은 <xref:System.Windows.Forms.MessageBox.Show%2A?displayProperty=nameWithType> 대신 <xref:System.Windows.MessageBox.Show%2A?displayProperty=nameWithType>를 호출하여 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d046-106">It may be avoided by calling <xref:System.Windows.MessageBox.Show%2A?displayProperty=nameWithType> instead of <xref:System.Windows.Forms.MessageBox.Show%2A?displayProperty=nameWithType>.</span></span></li><li><span data-ttu-id="4d046-107">이것은 <xref:System.Windows.UIElement.LostKeyboardFocus> 이벤트 처리기에서 메시지 박스를 표시하여 방지할 수 있습니다(<xref:System.Windows.UIElement.PreviewLostKeyboardFocus?displayProperty=fullName> 이벤트 처리기와 반대).</span><span class="sxs-lookup"><span data-stu-id="4d046-107">It may be avoided by showing the message box from a <xref:System.Windows.UIElement.LostKeyboardFocus> event handler (as opposed to a <xref:System.Windows.UIElement.PreviewLostKeyboardFocus?displayProperty=fullName> event handler).</span></span></li></ol>

| <span data-ttu-id="4d046-108">이름</span><span class="sxs-lookup"><span data-stu-id="4d046-108">Name</span></span>    | <span data-ttu-id="4d046-109">값</span><span class="sxs-lookup"><span data-stu-id="4d046-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="4d046-110">Scope</span><span class="sxs-lookup"><span data-stu-id="4d046-110">Scope</span></span>   |<span data-ttu-id="4d046-111">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="4d046-111">Edge</span></span>|
|<span data-ttu-id="4d046-112">버전</span><span class="sxs-lookup"><span data-stu-id="4d046-112">Version</span></span>|<span data-ttu-id="4d046-113">4.5</span><span class="sxs-lookup"><span data-stu-id="4d046-113">4.5</span></span>|
|<span data-ttu-id="4d046-114">형식</span><span class="sxs-lookup"><span data-stu-id="4d046-114">Type</span></span>|<span data-ttu-id="4d046-115">런타임</span><span class="sxs-lookup"><span data-stu-id="4d046-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="4d046-116">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="4d046-116">Affected APIs</span></span>

- <xref:System.Windows.ContentElement.PreviewLostKeyboardFocus?displayProperty=nameWithType>
- <xref:System.Windows.IInputElement.PreviewLostKeyboardFocus?displayProperty=nameWithType>
- <xref:System.Windows.UIElement.PreviewLostKeyboardFocus?displayProperty=nameWithType>
- <xref:System.Windows.UIElement3D.PreviewLostKeyboardFocus?displayProperty=nameWithType>

<!--

#### Affected APIs

- `E:System.Windows.ContentElement.PreviewLostKeyboardFocus`
- `E:System.Windows.IInputElement.PreviewLostKeyboardFocus`
- `E:System.Windows.UIElement.PreviewLostKeyboardFocus`
- `E:System.Windows.UIElement3D.PreviewLostKeyboardFocus`

-->
