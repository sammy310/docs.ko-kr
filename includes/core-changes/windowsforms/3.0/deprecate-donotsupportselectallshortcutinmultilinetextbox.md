---
ms.openlocfilehash: 9631e64bb403a3fe7b1b91e8ac592b57ce8068d9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "75937018"
---
### <a name="donotsupportselectallshortcutinmultilinetextbox-compatibility-switch-not-supported"></a><span data-ttu-id="73bcc-101">DoNotSupportSelectAllShortcutInMultilineTextBox 호환성 스위치가 지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="73bcc-101">DoNotSupportSelectAllShortcutInMultilineTextBox compatibility switch not supported</span></span>

<span data-ttu-id="73bcc-102">.NET Framework 4.6.1에서 도입된 `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox` 호환성 스위치는 .NET Core 3.0의 Windows Forms에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="73bcc-102">The `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox` compatibility switch, which was introduced in .NET Framework 4.6.1, is not supported in Windows Forms on .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="73bcc-103">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="73bcc-103">Change description</span></span>

<span data-ttu-id="73bcc-104">.NET Framework 4.6.1부터 <xref:System.Windows.Forms.TextBox> 컨트롤에서 <kbd>Ctrl</kbd> + <kbd>A</kbd> 바로 가기 키를 선택하면 모든 텍스트가 선택되었습니다.</span><span class="sxs-lookup"><span data-stu-id="73bcc-104">Starting with .NET Framework 4.6.1, selecting the <kbd>Ctrl</kbd> + <kbd>A</kbd> shortcut key in a <xref:System.Windows.Forms.TextBox> control selected all text.</span></span> <span data-ttu-id="73bcc-105">.NET Framework 4.6 및 이전 버전에서는 [Textbox.ShortcutsEnabled](xref:System.Windows.Forms.TextBoxBase.ShortcutsEnabled) 및 <xref:System.Windows.Forms.TextBox.Multiline?displayProperty=nameWithType> 속성이 모두 `true`로 설정된 경우, <kbd>Ctrl</kbd> + <kbd>A</kbd> 바로 가기 키를 선택해도 모든 텍스트가 선택되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="73bcc-105">In .NET Framework 4.6 and previous versions, selecting the <kbd>Ctrl</kbd> + <kbd>A</kbd> shortcut key failed to select all text if the [Textbox.ShortcutsEnabled](xref:System.Windows.Forms.TextBoxBase.ShortcutsEnabled) and <xref:System.Windows.Forms.TextBox.Multiline?displayProperty=nameWithType> properties were both set to `true`.</span></span> <span data-ttu-id="73bcc-106">`Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox` 호환성 스위치는 원래 동작을 유지하기 위해 .NET Framework 4.6.1에서 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="73bcc-106">The `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox` compatibility switch was introduced in .NET Framework 4.6.1 to retain the original behavior.</span></span> <span data-ttu-id="73bcc-107">자세한 내용은 <xref:System.Windows.Forms.TextBox.ProcessCmdKey%2A?displayProperty=nameWithType>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="73bcc-107">For more information see <xref:System.Windows.Forms.TextBox.ProcessCmdKey%2A?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="73bcc-108">.NET Core에서는 `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox` 스위치가 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="73bcc-108">In .NET Core, the `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="73bcc-109">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="73bcc-109">Version introduced</span></span>

<span data-ttu-id="73bcc-110">3.0 미리 보기 9</span><span class="sxs-lookup"><span data-stu-id="73bcc-110">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="73bcc-111">권장 조치</span><span class="sxs-lookup"><span data-stu-id="73bcc-111">Recommended action</span></span>

<span data-ttu-id="73bcc-112">스위치를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="73bcc-112">Remove the switch.</span></span> <span data-ttu-id="73bcc-113">이 스위치는 지원되지 않으며, 사용 가능한 대체 기능이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="73bcc-113">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="73bcc-114">범주</span><span class="sxs-lookup"><span data-stu-id="73bcc-114">Category</span></span>

<span data-ttu-id="73bcc-115">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="73bcc-115">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="73bcc-116">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="73bcc-116">Affected APIs</span></span>

- <span data-ttu-id="73bcc-117">없음</span><span class="sxs-lookup"><span data-stu-id="73bcc-117">None</span></span>

<!-- 

### Affected APIs

- Not detectable via API analysis

-->
