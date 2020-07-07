---
ms.openlocfilehash: 946e71f2f466664c8f9fcf4811288ce693a872eb
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616278"
---
### <a name="workflow-xaml-checksums-for-symbols-changed-from-sha1-to-sha256"></a>SHA1에서 SHA256으로 변경된 기호에 대한 워크플로 XAML 체크섬

#### <a name="details"></a>설명

Visual Studio로 디버깅을 지원하기 위해 워크플로 런타임은 해싱 알고리즘을 사용하여 워크플로 XAML 파일에 대한 체크섬을 생성합니다. .NET Framework 4.6.2 이전 버전에서 워크플로 체크섬 해시는 MD5 알고리즘을 사용하여 FIPS 지원 시스템에 문제가 발생했습니다. .NET Framework 4.7부터 기본 알고리즘이 SHA1로 변경되었습니다. .NET Framework 4.8부터 기본 알고리즘이 SHA256으로 변경되었습니다.

#### <a name="suggestion"></a>제안 해결 방법

체크섬 오류로 인해 코드가 워크플로 인스턴스를 로드할 수 없거나 적절한 기호를 찾을 수 없는 경우 `AppContext` 스위치 "Switch.System.Activities.UseSHA1HashForDebuggerSymbols"를 `true`로 설정합니다. 코드

```csharp
System.AppContext.SetSwitch("Switch.System.Activities.UseSHA1HashForDebuggerSymbols", true);
```

또는 다음 구성을 사용할 수도 있습니다.

```xml
<configuration>
  <runtime>
    <AppContextSwitchOverrides value="Switch.System.Activities.UseSHA1HashForDebuggerSymbols=true" />
  </runtime>
</configuration>
```

| 이름    | 값       |
|:--------|:------------|
| Scope   | 부       |
| 버전 | 4.8         |
| 형식    | 대상 변경 |
