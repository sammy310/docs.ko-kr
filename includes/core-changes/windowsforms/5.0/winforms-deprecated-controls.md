---
ms.openlocfilehash: c9720f51e40ada4cd2cf6997ba7006a232893553
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2020
ms.locfileid: "83702490"
---
### <a name="removed-status-bar-controls"></a>상태 표시줄 컨트롤 제거

.NET 5.0 미리 보기 1부터 일부 Windows Forms 컨트롤을 더 이상 사용할 수 없습니다.

#### <a name="change-description"></a>변경 내용 설명

.NET 5.0 미리 보기 1부터 상태 표시줄 관련 Windows Forms 컨트롤 중 일부를 더 이상 사용할 수 없습니다. 향상된 디자인 및 지원을 제공하는 대체 컨트롤이 .NET Framework 2.0에 도입되었습니다. 사용되지 않는 컨트롤은 이전에 디자이너 도구 상자에서 제거되었지만, 여전히 사용할 수 있습니다. 이제 완전히 제거되었습니다.

다음 형식은 더 이상 사용할 수 없습니다.

* `StatusBar`
* `StatusBarDrawItemEventArgs`
* `StatusBarDrawItemEventHandler`
* `StatusBarPanel`
* `StatusBarPanelAutoSize`
* `StatusBarPanelBorderStyle`
* `StatusBarPanelClickEventArgs`
* `StatusBarPanelClickEventHandler`
* `StatusBarPanelStyle`

#### <a name="version-introduced"></a>도입된 버전

5.0 미리 보기 1

#### <a name="recommended-action"></a>권장 조치

이러한 컨트롤 및 해당 시나리오에 대한 대체 API로 이동합니다.

| 이전 컨트롤(API) | 권장 대체                          |
|-------------------|--------------------------------------------------|
| StatusBar         | <xref:System.Windows.Forms.StatusStrip>          |
| StatusBarPanel    | <xref:System.Windows.Forms.ToolStripStatusLabel> |

#### <a name="category"></a>범주

Windows Forms

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Windows.Forms.StatusBar?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarDrawItemEventArgs?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarDrawItemEventHandler?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarPanel?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarPanelAutoSize?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarPanelBorderStyle?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarPanelClickEventArgs?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarPanelClickEventHandler?displayProperty=fullName>
- <xref:System.Windows.Forms.StatusBarPanelStyle?displayProperty=fullName>

<!-- 

#### Affected APIs

- `T:System.Windows.Forms.StatusBar`
- `T:System.Windows.Forms.StatusBarDrawItemEventArgs`
- `T:System.Windows.Forms.StatusBarDrawItemEventHandler`
- `T:System.Windows.Forms.StatusBarPanel`
- `T:System.Windows.Forms.StatusBarPanelAutoSize`
- `T:System.Windows.Forms.StatusBarPanelBorderStyle`
- `T:System.Windows.Forms.StatusBarPanelClickEventArgs`
- `T:System.Windows.Forms.StatusBarPanelClickEventHandler`
- `T:System.Windows.Forms.StatusBarPanelStyle` 

-->
