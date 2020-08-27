---
ms.openlocfilehash: a635e2ed6a735b5234c92fd8f5ffa1685fe9373e
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/18/2020
ms.locfileid: "88558184"
---
### <a name="microsoftdotnetplatformabstractions-package-removed"></a>Microsoft.DotNet.PlatformAbstractions 패키지 제거됨

[Microsoft.DotNet.PlatformAbstractions NuGet 패키지](https://www.nuget.org/packages/Microsoft.DotNet.PlatformAbstractions/)의 새 버전이 만들어지지 않습니다.

#### <a name="change-description"></a>변경 내용 설명

이전에는 <xref:Microsoft.DotNet.PlatformAbstractions?displayProperty=fullName> 라이브러리의 새 버전이 새 버전의 .NET Core와 함께 만들어졌습니다. 앞으로는 라이브러리에 새로운 기능이 추가되지 않으며 새로운 주 버전이 출시되지 않습니다. 그러나 라이브러리의 기존 버전은 계속 작동하고 서비스됩니다.

<xref:Microsoft.DotNet.PlatformAbstractions?displayProperty=fullName> 라이브러리는 System.\* 네임스페이스에 이미 설정된 API와 겹칩니다. 또한 일부 <xref:Microsoft.DotNet.PlatformAbstractions> API는 조사 및 장기 지원 수준이 나머지 System.\* API와 동일하게 설계되지 않았습니다. 예를 들어 <xref:Microsoft.DotNet.PlatformAbstractions>는 `Platform` 열거형을 사용하여 현재 운영 체제 플랫폼을 설명합니다. 이 열거형 설계는 <xref:System.Runtime.InteropServices.RuntimeInformation.IsOSPlatform(System.Runtime.InteropServices.OSPlatform)?displayProperty=nameWithType> API를 설계할 때 새로운 플랫폼과 향후 유연성을 위해 명시적으로 거부되었습니다.

<xref:Microsoft.DotNet.PlatformAbstractions?displayProperty=fullName> 라이브러리에서 사용하도록 설정된 시나리오를 이제 이 열거형 없이 사용할 수 있습니다. 기존 버전은 .NET 5.0 이상에서도 계속 작동하며, 이전 버전의 .NET Core와 함께 서비스됩니다. 그러나 라이브러리에 새로운 기능은 추가되지 않습니다. 대신, 새로운 기능은 다른 라이브러리와 API에 추가됩니다.

#### <a name="version-introduced"></a>도입된 버전

5.0 미리 보기 6

#### <a name="recommended-action"></a>권장 조치

- 요구 사항에 맞는 경우 이전 버전의 라이브러리를 계속 사용할 수 있습니다.

- 이전 버전이 요구 사항에 맞지 않으면 `PlatformAbstractions` API 사용을 권장되는 대체 항목으로 바꾸세요.

  | `PlatformAbstractions` API | 권장된 대체 |
  |-|-|
  | `ApplicationEnvironment.ApplicationBasePath` | <xref:System.AppContext.BaseDirectory?displayProperty=nameWithType> |
  | <xref:Microsoft.DotNet.PlatformAbstractions.HashCodeCombiner> | <xref:System.HashCode?displayProperty=nameWithType> |
  | `RuntimeEnvironment.GetRuntimeIdentifier()` | <xref:System.Runtime.InteropServices.RuntimeInformation.RuntimeIdentifier?displayProperty=nameWithType> |
  | `RuntimeEnvironment.OperatingSystemPlatform` | <xref:System.Runtime.InteropServices.RuntimeInformation.IsOSPlatform(System.Runtime.InteropServices.OSPlatform)?displayProperty=nameWithType> |
  | `RuntimeEnvironment.RuntimeArchitecture` | <xref:System.Runtime.InteropServices.RuntimeInformation.ProcessArchitecture?displayProperty=nameWithType> |
  | `RuntimeEnvironment.OperatingSystem` | <xref:System.Runtime.InteropServices.RuntimeInformation.OSDescription?displayProperty=nameWithType> |
  | `RuntimeEnvironment.OperatingSystemVersion` | <xref:System.Runtime.InteropServices.RuntimeInformation.OSDescription?displayProperty=nameWithType> 및 <xref:System.Environment.OSVersion?displayProperty=nameWithType> |

  > [!NOTE]
  > `RuntimeEnvironment.OperatingSystem` 및 `RuntimeEnvironment.OperatingSystemVersion`의 사용 사례 대부분은 표시(예: 사용자, 로깅 및 원격 분석에 표시)가 그 목적입니다. OS(운영 체제) 버전에 따라 런타임 결정을 내리는 것은 권장되지 않습니다. <xref:System.Environment.OSVersion?displayProperty=nameWithType>에서 이제 Windows 및 macOS 운영 체제의 [올바른 버전이 반환](../../../../docs/core/compatibility/corefx.md#environmentosversion-returns-the-correct-operating-system-version)됩니다. 그러나 대부분의 Unix 배포에서는 무엇을 “OS 버전”으로 간주할지가 간단하지 않습니다. 예를 들어 Linux 커널 버전이거나 배포판 버전이 될 수 있습니다. 대부분의 Unix 플랫폼에서 <xref:System.Environment.OSVersion?displayProperty=nameWithType> 및 <xref:System.Runtime.InteropServices.RuntimeInformation.OSDescription?displayProperty=nameWithType>는 `uname`에서 반환된 버전을 반환합니다. Linux 배포판 이름 및 버전 정보를 가져오려면 */etc/os-release* 파일을 읽는 것이 좋습니다.

#### <a name="category"></a>범주

핵심 .NET 라이브러리

#### <a name="affected-apis"></a>영향을 받는 API

- `Microsoft.DotNet.PlatformAbstractions.ApplicationEnvironment.ApplicationBasePath`
- <xref:Microsoft.DotNet.PlatformAbstractions.HashCodeCombiner?displayProperty=fullName>
- `Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.GetRuntimeIdentifier()`
- `Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.OperatingSystem`
- `Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.OperatingSystemPlatform`
- `Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.OperatingSystemVersion`
- `Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.RuntimeArchitecture`

<!--

#### Affected APIs

- `P:Microsoft.DotNet.PlatformAbstractions.ApplicationEnvironment.ApplicationBasePath`
- `T:Microsoft.DotNet.PlatformAbstractions.HashCodeCombiner`
- `M:Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.GetRuntimeIdentifier`
- `P:Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.OperatingSystem`
- `P:Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.OperatingSystemPlatform`
- `P:Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.OperatingSystemVersion`
- `P:Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.RuntimeArchitecture`

-->
