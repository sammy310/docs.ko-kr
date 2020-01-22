---
ms.openlocfilehash: 3f0e8fb4d0d727b40cff5de7cfdc7529bf32dac4
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/14/2020
ms.locfileid: "75936992"
---
### <a name="donotloadlatestricheditcontrol-compatibility-switch-not-supported"></a>DoNotLoadLatestRichEditControl 호환성 스위치가 지원되지 않음

.NET Framework 4.7.1에서 도입된 `Switch.System.Windows.Forms.UseLegacyImages` 호환성 스위치는 .NET Core 3.0의 Windows Forms에서 지원되지 않습니다.

#### <a name="change-description"></a>변경 내용 설명

.NET Framework 4.6.2 및 이전 버전에서는 <xref:System.Windows.Forms.RichTextBox> 컨트롤이 Win32 RichEdit 컨트롤 v3.0을 인스턴스화하고, .NET Framework 4.7.1을 대상으로 하는 애플리케이션의 경우 <xref:System.Windows.Forms.RichTextBox> 컨트롤이 *msftedit.dll*에서 RichEdit v4.1을 인스턴스화합니다. `Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl` 호환성 스위치는 .NET Framework 4.7.1 이상 버전을 대상으로 하는 애플리케이션이 새 RichEdit v4.1 컨트롤을 옵트아웃하고 이전 RichEdit v3 컨트롤을 대신 사용할 수 있도록 하기 위해 도입되었습니다.

.NET Core에서는 `Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl` 스위치가 지원되지 않습니다. 새 버전의 <xref:System.Windows.Forms.RichTextBox> 컨트롤만 지원됩니다.

#### <a name="version-introduced"></a>도입된 버전

3.0 미리 보기 9

#### <a name="recommended-action"></a>권장 조치

스위치를 제거합니다. 이 스위치는 지원되지 않으며, 사용 가능한 대체 기능이 없습니다.

#### <a name="category"></a>범주

Windows Forms

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Windows.Forms.RichTextBox?displayProperty=nameWithType>

<!-- 

### Affected APIs

-  `T:System.Windows.Forms.RichTextBox` 

-->
