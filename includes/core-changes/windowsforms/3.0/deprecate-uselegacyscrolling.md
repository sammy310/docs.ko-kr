---
ms.openlocfilehash: ee4a27dde9f1e7756401e3d8b709514082f5d3b1
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556212"
---
### <a name="domainupdownuselegacyscrolling-compatibility-switch-not-supported"></a>DomainUpDown.UseLegacyScrolling 호환성 스위치가 지원되지 않음

.NET Framework 4.7.1에서 도입된 `Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling` 호환성 스위치는 .NET Core 또는 .NET 5.0 이상의 Windows Forms에서 지원되지 않습니다.

#### <a name="change-description"></a>변경 내용 설명

.NET Framework 4.7.1부터는 개발자가 `Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling` 호환성 스위치를 통해 독립적인 <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> 및 <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> 작업을 옵트아웃할 수 있었습니다. 이 스위치는 컨텍스트 텍스트가 있는 경우 <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType>이 무시되고, 개발자가 컨트롤에서 <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> 작업을 <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> 작업 전에 사용해야 하는 레거시 동작을 복원했습니다. 자세한 내용은 [\<AppContextSwitchOverrides> 요소](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md)를 참조하세요.

.NET Core 및 .NET 5.0 이상에서는 `Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling` 스위치가 지원되지 않습니다.

#### <a name="version-introduced"></a>도입된 버전

3.0

#### <a name="recommended-action"></a>권장 조치

스위치를 제거합니다. 이 스위치는 지원되지 않으며, 사용 가능한 대체 기능이 없습니다.

#### <a name="category"></a>범주

Windows Forms

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType>

<!-- 

#### Affected APIs

- `M:System.Windows.Forms.DomainUpDown.DownButton`
- `M:System.Windows.Forms.DomainUpDown.UpButton`

-->
