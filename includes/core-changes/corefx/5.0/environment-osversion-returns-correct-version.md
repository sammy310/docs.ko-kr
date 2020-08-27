---
ms.openlocfilehash: ccd056f23d26e6cce4cc691542784792bffe9fc6
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/18/2020
ms.locfileid: "88558185"
---
### <a name="environmentosversion-returns-the-correct-operating-system-version"></a>Environment.OSVersion에서 올바른 운영 체제 버전이 반환됨

<xref:System.Environment.OSVersion?displayProperty=nameWithType>에서 애플리케이션 호환성을 위해 선택된 OS 등이 아닌 실제 OS(운영 체제) 버전이 반환됩니다.

#### <a name="change-description"></a>변경 내용 설명

이전 .NET 버전에서는 <xref:System.Environment.OSVersion?displayProperty=nameWithType>이 Windows 호환 모드에서 애플리케이션을 실행할 경우 부정확할 수 있는 OS 버전을 반환합니다. 자세한 내용은 [GetVersionExA 함수 설명](/windows/win32/api/sysinfoapi/nf-sysinfoapi-getversionexa#remarks)을 참조하세요.

.NET 5.0부터 <xref:System.Environment.OSVersion?displayProperty=nameWithType>에서 실제 운영 체제 버전이 반환됩니다.

#### <a name="reason-for-change"></a>변경 이유

이 속성의 사용자는 실제 운영 체제 버전이 반환될 것으로 예상합니다. 대부분의 .NET 앱은 애플리케이션 매니페스트에서 지원되는 버전을 지정하지 않으므로 dotnet 호스트에서 지원되는 기본 버전을 가져옵니다. 따라서 호환성 shim은 실행 중인 앱에서 거의 의미가 없습니다. Windows에서 새 버전을 릴리스할 때 이전 dotnet 호스트를 아직 사용 중인 경우 해당 앱이 잘못된 OS 버전을 가져올 수 있습니다. 실제 버전을 반환하는 것이 이 API에 대한 개발자의 기대와 좀 더 부합됩니다.

#### <a name="version-introduced"></a>도입된 버전

5.0

#### <a name="recommended-action"></a>권장 조치

<xref:System.Environment.OSVersion?displayProperty=nameWithType>을 사용하는 코드를 검토하고 테스트하여 원하는 대로 작동하는지 확인합니다.

#### <a name="category"></a>범주

핵심 .NET 라이브러리

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Environment.OSVersion?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Environment.OSVersion`

-->
