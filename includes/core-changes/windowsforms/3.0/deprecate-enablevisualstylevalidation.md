---
ms.openlocfilehash: 196a26bd235e5e2556baa7fac979b3316ff81e1f
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556207"
---
### <a name="enablevisualstylevalidation-compatibility-switch-not-supported"></a>EnableVisualStyleValidation 호환성 스위치가 지원되지 않음

`Switch.System.Windows.Forms.EnableVisualStyleValidation` 호환성 스위치는 .NET Core 또는 .NET 5.0 이상의 Windows Forms에서 지원되지 않습니다.

#### <a name="change-description"></a>변경 내용 설명

.NET Framework에서는 애플리케이션이 `Switch.System.Windows.Forms.EnableVisualStyleValidation` 호환성 스위치를 통해 숫자 형태로 제공된 시각적 개체 스타일의 유효성 검사를 옵트아웃할 수 있었습니다.

.NET Core 및 .NET 5.0 이상에서는 `Switch.System.Windows.Forms.EnableVisualStyleValidation` 스위치가 지원되지 않습니다.

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
