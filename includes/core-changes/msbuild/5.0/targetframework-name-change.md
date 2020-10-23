---
ms.openlocfilehash: 1ddc2cea19872b44ff9659bcebd76117587ea89a
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "92159493"
---
### <a name="targetframework-change-from-netcoreapp-to-net"></a>netcoreapp에서 net으로 TargetFramework 변경

MSBuild `TargetFramework` 속성 값이 `netcoreapp3.1`에서 `net5.0`로 변경되었습니다. 이로 인해 `TargetFramework`의 값을 구문 분석하는 데 필요한 코드가 중단될 수 있습니다.

#### <a name="version-introduced"></a>도입된 버전

5.0

#### <a name="change-description"></a>변경 내용 설명

.NET Core 1.0 - 3.1에서 MSBuild `TargetFramework` 속성 값은 `netcoreapp`으로 시작합니다(예: .NET Core 3.1을 대상으로 하는 앱의 경우 `netcoreapp3.1`). .NET 5.0부터 이 값은 `net`으로만 시작하도록 단순화됩니다(예: .NET 5.0의 경우 `net5.0`).

자세한 내용은 [.NET Standard의 미래 ](https://devblogs.microsoft.com/dotnet/the-future-of-net-standard/) 및 [.NET 5의 대상 프레임워크 이름](https://github.com/dotnet/designs/blob/main/accepted/2020/net5/net5.md)을 참조하세요.

#### <a name="reason-for-change"></a>변경 이유

- `TargetFramework` 값을 단순화합니다.
- 프로젝트가 `TargetFramework` 특성에 `TargetPlatform`을 포함할 수 있도록 합니다.

#### <a name="recommended-action"></a>권장 조치

`TargetFramework`의 값을 구문 분석하는 논리가 있는 경우 업데이트해야 합니다. 예를 들어 다음 MSBuild 조건은 `TargetFramework` 값에 의존합니다.

```xml
<PropertyGroup Condition="$(TargetFramework.StartsWith('netcoreapp'))">
```

이 요구 사항에 대해 대상 프레임워크 식별자를 비교하기 위해 코드를 업데이트할 수 있습니다.

```xml
<PropertyGroup Condition="'$([MSBuild]::GetTargetFrameworkIdentifier('$(TargetFramework)'))' == '.NETCoreApp'">
```

#### <a name="category"></a>범주

MSBuild

#### <a name="affected-apis"></a>영향을 받는 API

N/A

<!--

#### Affected APIs

Not detectable via API analysis.

-->
