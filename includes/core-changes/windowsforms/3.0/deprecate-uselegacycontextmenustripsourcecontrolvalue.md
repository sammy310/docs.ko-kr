---
ms.openlocfilehash: 3ada05a13ec7acde1d8374ed733d0d51cdfb408c
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721463"
---
### <a name="uselegacycontextmenustripsourcecontrolvalue-compatibility-switch-not-supported"></a>UseLegacyContextMenuStripSourceControlValue 호환성 스위치가 지원되지 않음

.NET Framework 4.7.2에서 도입된 `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` 호환성 스위치는 .NET Core 3.0의 Windows Forms에서 지원되지 않습니다.

#### <a name="change-description"></a>변경 내용 설명

.NET Framework 4.7.2부터는 개발자가 `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` 호환성 스위치를 통해 소스 제어에 대한 참조를 반환하는 <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType> 속성의 새 동작을 옵트아웃할 수 있습니다. 이 속성의 이전 동작은 `null`을 반환하는 것이었습니다. 자세한 내용은 [\<AppContextSwitchOverrides> 요소](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)를 참조하세요.

.NET Core에서는 `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` 스위치가 지원되지 않습니다.

#### <a name="version-introduced"></a>도입된 버전

3.0 미리 보기 9

#### <a name="recommended-action"></a>권장 조치

스위치를 제거합니다. 이 스위치는 지원되지 않으며, 사용 가능한 대체 기능이 없습니다.

#### <a name="category"></a>범주

Windows Forms

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType>

<!-- 

#### Affected APIs

- `P:System.Windows.Forms.ContextMenuStrip.SourceControl`

-->
