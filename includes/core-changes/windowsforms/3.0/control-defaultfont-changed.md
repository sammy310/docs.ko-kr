---
ms.openlocfilehash: b0c4e9617677cf95e3a059b57f3d50ddfb072f4a
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937114"
---
### <a name="default-control-font-changed-to-segoe-ui-9-pt"></a>기본 컨트롤 글꼴이 맑은 고딕 9pt로 변경되었습니다.

#### <a name="change-description"></a>변경 내용 설명

.NET Framework에서는 <xref:System.Windows.Forms.Control.DefaultFont?displayProperty=nameWithType> 속성이 `Microsoft Sans Serif 8 pt`로 설정되었습니다. 다음 이미지에서는 기본 글꼴을 사용하는 창을 보여 줍니다.

![.NET Framework의 기본 컨트롤 글꼴](~/docs/images/core-changes/windowsforms/control-defaultfont-changed/defaultfont-framework.png)

.NET Core 3.0부터 기본 글꼴은 `Segoe UI 9 pt`(<xref:System.Drawing.SystemFonts.MessageBoxFont?displayProperty=nameWithType>과 동일한 글꼴)으로 설정됩니다. 이 변경으로 인해 양식 및 컨트롤의 크기가 새 기본 글꼴의 더 큰 크기를 고려하여 약 27% 커졌습니다. 예:

![.NET Core의 기본 컨트롤 글꼴](~/docs/images/core-changes/windowsforms/control-defaultfont-changed/defaultfont-core.png)

이 변경은 [Windows 사용자 환경(UX) 지침](/windows/win32/uxguide/vis-fonts#fonts-and-colors)에 맞게 변경되었습니다.

#### <a name="version-introduced"></a>도입된 버전

3.0

#### <a name="recommended-action"></a>권장 조치

양식 및 컨트롤의 크기가 변경되므로 애플리케이션이 올바르게 렌더링되는지 확인합니다.

원래 글꼴을 유지하려면 양식의 기본 글꼴을 `Microsoft Sans Serif 8 pt`로 설정합니다. 예:

```csharp
public MyForm()
{
    InitializeComponent();
    Font = new Font(new FontFamily("Microsoft Sans Serif"), 8f);
}
```

#### <a name="category"></a>범주

- Windows Forms

#### <a name="affected-apis"></a>영향을 받는 API

없음

<!--

### Affected APIs

- Not detectable via API analysis

-->
