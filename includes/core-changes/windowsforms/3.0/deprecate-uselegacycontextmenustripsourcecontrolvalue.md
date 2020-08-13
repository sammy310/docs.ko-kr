---
ms.openlocfilehash: df6169289fb96df5f7daf8bd58ccaeebc33ad87c
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556211"
---
### <a name="uselegacycontextmenustripsourcecontrolvalue-compatibility-switch-not-supported"></a>UseLegacyContextMenuStripSourceControlValue 호환성 스위치가 지원되지 않음

.NET Framework 4.7.2에서 도입된 `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` 호환성 스위치는 .NET Core 또는 .NET 5.0 이상의 Windows Forms에서 지원되지 않습니다.

#### <a name="change-description"></a>변경 내용 설명

.NET Framework 4.7.2부터는 개발자가 `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` 호환성 스위치를 통해 소스 제어에 대한 참조를 반환하는 <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType> 속성의 새 동작을 옵트아웃할 수 있습니다. 이 속성의 이전 동작은 `null`을 반환하는 것이었습니다. 자세한 내용은 [\<AppContextSwitchOverrides> 요소](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)를 참조하세요.

.NET Core 및 .NET 5.0 이상에서는 `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` 스위치가 지원되지 않습니다.

#### <a name="version-introduced"></a>도입된 버전

3.0

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
