---
ms.openlocfilehash: aade03c29ff16053a97683499cf719a98ae33f3f
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616282"
---
### <a name="add-selectiontextbrush-public-property-to-textboxpasswordbox-non-adorner-selection"></a><span data-ttu-id="448a0-101">TextBox/PasswordBox 비표시기 선택 영역에 SelectionTextBrush 공용 속성 추가</span><span class="sxs-lookup"><span data-stu-id="448a0-101">Add SelectionTextBrush public property to TextBox/PasswordBox non-adorner selection</span></span>

#### <a name="details"></a><span data-ttu-id="448a0-102">설명</span><span class="sxs-lookup"><span data-stu-id="448a0-102">Details</span></span>

<span data-ttu-id="448a0-103"><xref:System.Windows.Controls.TextBox> 및 <xref:System.Windows.Controls.PasswordBox>에 대해 [비표시기 기반 텍스트 선택](https://github.com/Microsoft/dotnet/blob/master/Documentation/compatibility/wpf-TextBox-PasswordBox-text-selection-does-not-follow-system-colors.md)을 사용하는 WPF 애플리케이션에서 개발자는 이제 새로 추가된 SelectionTextBrush 속성을 설정하여 선택한 텍스트의 렌더링을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="448a0-103">In WPF applications using [non-adorner based text selection](https://github.com/Microsoft/dotnet/blob/master/Documentation/compatibility/wpf-TextBox-PasswordBox-text-selection-does-not-follow-system-colors.md) for <xref:System.Windows.Controls.TextBox> and <xref:System.Windows.Controls.PasswordBox>, developers may now set the newly added SelectionTextBrush property in order to alter the rendering of the selected text.</span></span>  <span data-ttu-id="448a0-104">기본적으로 이 색은 <xref:System.Windows.SystemColors.HighlightTextBrushKey>와 함께 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="448a0-104">By default, this color changes with <xref:System.Windows.SystemColors.HighlightTextBrushKey>.</span></span>  <span data-ttu-id="448a0-105">비표시기 기반 텍스트 선택 영역이 활성화되지 않은 경우 이 속성은 아무 작업도 수행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="448a0-105">If non-adorner based text selection is not enabled, this property does nothing.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="448a0-106">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="448a0-106">Suggestion</span></span>

<span data-ttu-id="448a0-107">비표시기 기반 텍스트 선택이 활성화되면 <xref:System.Windows.Controls.PasswordBox.SelectionTextBrush?displayProperty=nameWithType> 및 <xref:System.Windows.Controls.Primitives.TextBoxBase.SelectionTextBrush> 속성을 사용하여 선택한 텍스트의 모양을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="448a0-107">Once non-adorner based text selection is enabled, you can use the <xref:System.Windows.Controls.PasswordBox.SelectionTextBrush?displayProperty=nameWithType> and <xref:System.Windows.Controls.Primitives.TextBoxBase.SelectionTextBrush> property to change the appearance of the selected text.</span></span> <span data-ttu-id="448a0-108">이는 XAML을 사용하여 달성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="448a0-108">This can be achieved using XAML:</span></span>

<pre><code class="lang-xaml">&lt;TextBox SelectionBrush=&quot;Red&quot; SelectionTextBrush=&quot;White&quot;  SelectionOpacity=&quot;0.5&quot;&#13;&#10;Foreground=&quot;Blue&quot; CaretBrush=&quot;Blue&quot;&gt;&#13;&#10;This is some text.&#13;&#10;&lt;/TextBox&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="448a0-109">이름</span><span class="sxs-lookup"><span data-stu-id="448a0-109">Name</span></span>    | <span data-ttu-id="448a0-110">값</span><span class="sxs-lookup"><span data-stu-id="448a0-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="448a0-111">Scope</span><span class="sxs-lookup"><span data-stu-id="448a0-111">Scope</span></span>   | <span data-ttu-id="448a0-112">주요함</span><span class="sxs-lookup"><span data-stu-id="448a0-112">Major</span></span>       |
| <span data-ttu-id="448a0-113">버전</span><span class="sxs-lookup"><span data-stu-id="448a0-113">Version</span></span> | <span data-ttu-id="448a0-114">4.8</span><span class="sxs-lookup"><span data-stu-id="448a0-114">4.8</span></span>         |
| <span data-ttu-id="448a0-115">형식</span><span class="sxs-lookup"><span data-stu-id="448a0-115">Type</span></span>    | <span data-ttu-id="448a0-116">대상 변경</span><span class="sxs-lookup"><span data-stu-id="448a0-116">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="448a0-117">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="448a0-117">Affected APIs</span></span>

- <xref:System.Windows.Controls.Primitives.TextBoxBase.SelectionTextBrushProperty?displayProperty=nameWithType>
- <xref:System.Windows.Controls.Primitives.TextBoxBase.SelectionTextBrush?displayProperty=nameWithType>
- [<span data-ttu-id="448a0-118">System.Windows.Controls.TextBox</span><span class="sxs-lookup"><span data-stu-id="448a0-118">System.Windows.Controls.TextBox</span></span>](xref:System.Windows.Controls.TextBox)
- [<span data-ttu-id="448a0-119">System.Windows.Controls.PasswordBox</span><span class="sxs-lookup"><span data-stu-id="448a0-119">System.Windows.Controls.PasswordBox</span></span>](xref:System.Windows.Controls.PasswordBox)
