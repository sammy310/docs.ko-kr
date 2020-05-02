---
ms.openlocfilehash: 5212c5d9513a8ef5f51693857d0ddb60db4e49b9
ms.sourcegitcommit: c2c1269a81ffdcfc8675bcd9a8505b1a11ffb271
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/25/2020
ms.locfileid: "82158404"
---
### <a name="winforms-methods-now-throw-argumentexception"></a>WinForms 메서드는 이제 ArgumentException을 throw함

이제 일부 Windows Forms 메서드에서는 이전에는 없었던 잘못된 인수에 대한 <xref:System.ArgumentException>을 throw합니다.

#### <a name="change-description"></a>변경 내용 설명

이전에는 예기치 않거나 잘못된 형식의 인수를 특정 Windows Forms 메서드에 전달하면 불분명한 상태가 되었습니다. .NET 5.0부터 이러한 메서드는 잘못된 인수를 전달하면 <xref:System.ArgumentException>을 throw합니다.

<xref:System.ArgumentException> throw는 .NET 런타임의 동작을 따릅니다. 또한 잘못된 인수를 명확하게 전달하여 디버깅 환경을 개선합니다.

다음 표에서는 영향을 받는 메서드 및 매개 변수를 보여줍니다.

| 메서드 | 매개 변수 이름 | 조건 | 추가된 버전 |
|-|-|-|
| <xref:System.Windows.Forms.TabControl.GetToolTipText(System.Object)?displayProperty=fullName> | `item` | 인수가 <xref:System.Windows.Forms.TabPage> 형식이 아닙니다. | 5.0 미리 보기 1 |

#### <a name="version-introduced"></a>도입된 버전

.NET 5.0 미리 보기 1

#### <a name="recommended-action"></a>권장 조치

- 잘못된 인수가 전달되지 않도록 코드를 업데이트합니다.
- 필요한 경우 메서드를 호출할 때 <xref:System.ArgumentException>을 처리합니다.

#### <a name="category"></a>범주

Windows Forms

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Windows.Forms.TabControl.GetToolTipText(System.Object)?displayProperty=fullName>

<!-- 

### Affected APIs

- `M:System.Windows.Forms.TabControl.GetToolTipText(System.Object)`

-->
