---
ms.openlocfilehash: d69f619522c7abc3171f1c089e53cc2754899f93
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556208"
---
### <a name="uselegacyimages-compatibility-switch-not-supported"></a>UseLegacyImages 호환성 스위치가 지원되지 않음

.NET Framework 4.8에서 도입된 `Switch.System.Windows.Forms.UseLegacyImages` 호환성 스위치는 .NET Core 또는 .NET 5.0의 Windows Forms에서 지원되지 않습니다.

#### <a name="change-description"></a>변경 내용 설명

.NET Framework 4.8부터는 `Switch.System.Windows.Forms.UseLegacyImages` 호환성 스위치가 높은 DPI 환경의 ClickOnce 시나리오에서 가능한 이미지 크기 조정 문제를 해결했습니다. `true`로 설정하면, 사용자가 이 스위치를 통해 배율이 100%보다 큰 값으로 설정된 높은 DPI 디스플레이에서 레거시 이미지 크기 조정을 복원할 수 있습니다. 자세한 내용은 GitHub에서 [.NET Framework 4.8 릴리스 정보](https://github.com/microsoft/dotnet/blob/master/releases/net48/dotnet48-changes.md#clickonce)를 참조하세요.

.NET Core 및 .NET 5.0 이상에서는 `Switch.System.Windows.Forms.UseLegacyImages` 스위치가 지원되지 않습니다.

#### <a name="version-introduced"></a>도입된 버전

3.0

#### <a name="recommended-action"></a>권장 조치

스위치를 제거합니다. 이 스위치는 지원되지 않으며, 사용 가능한 대체 기능이 없습니다.

#### <a name="category"></a>범주

Windows Forms

#### <a name="affected-apis"></a>영향을 받는 API

- None

<!-- 

#### Affected APIs

- Not detectable via API analysis

-->
