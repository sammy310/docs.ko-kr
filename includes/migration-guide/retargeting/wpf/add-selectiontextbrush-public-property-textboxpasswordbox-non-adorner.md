---
ms.openlocfilehash: aade03c29ff16053a97683499cf719a98ae33f3f
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616282"
---
### <a name="add-selectiontextbrush-public-property-to-textboxpasswordbox-non-adorner-selection"></a>TextBox/PasswordBox 비표시기 선택 영역에 SelectionTextBrush 공용 속성 추가

#### <a name="details"></a>설명

<xref:System.Windows.Controls.TextBox> 및 <xref:System.Windows.Controls.PasswordBox>에 대해 [비표시기 기반 텍스트 선택](https://github.com/Microsoft/dotnet/blob/master/Documentation/compatibility/wpf-TextBox-PasswordBox-text-selection-does-not-follow-system-colors.md)을 사용하는 WPF 애플리케이션에서 개발자는 이제 새로 추가된 SelectionTextBrush 속성을 설정하여 선택한 텍스트의 렌더링을 변경할 수 있습니다.  기본적으로 이 색은 <xref:System.Windows.SystemColors.HighlightTextBrushKey>와 함께 변경됩니다.  비표시기 기반 텍스트 선택 영역이 활성화되지 않은 경우 이 속성은 아무 작업도 수행하지 않습니다.

#### <a name="suggestion"></a>제안 해결 방법

비표시기 기반 텍스트 선택이 활성화되면 <xref:System.Windows.Controls.PasswordBox.SelectionTextBrush?displayProperty=nameWithType> 및 <xref:System.Windows.Controls.Primitives.TextBoxBase.SelectionTextBrush> 속성을 사용하여 선택한 텍스트의 모양을 변경할 수 있습니다. 이는 XAML을 사용하여 달성할 수 있습니다.

<pre><code class="lang-xaml">&lt;TextBox SelectionBrush=&quot;Red&quot; SelectionTextBrush=&quot;White&quot;  SelectionOpacity=&quot;0.5&quot;&#13;&#10;Foreground=&quot;Blue&quot; CaretBrush=&quot;Blue&quot;&gt;&#13;&#10;This is some text.&#13;&#10;&lt;/TextBox&gt;&#13;&#10;</code></pre>

| 이름    | 값       |
|:--------|:------------|
| Scope   | 주요함       |
| 버전 | 4.8         |
| 형식    | 대상 변경 |

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Windows.Controls.Primitives.TextBoxBase.SelectionTextBrushProperty?displayProperty=nameWithType>
- <xref:System.Windows.Controls.Primitives.TextBoxBase.SelectionTextBrush?displayProperty=nameWithType>
- [System.Windows.Controls.TextBox](xref:System.Windows.Controls.TextBox)
- [System.Windows.Controls.PasswordBox](xref:System.Windows.Controls.PasswordBox)
