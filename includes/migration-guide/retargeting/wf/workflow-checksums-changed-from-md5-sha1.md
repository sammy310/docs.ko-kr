---
ms.openlocfilehash: 72d48d1daa85b6891c122f2fcc5279642253b926
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614837"
---
### <a name="workflow-checksums-changed-from-md5-to-sha1"></a>워크플로 체크섬이 MD5에서 SHA1로 변경됨

#### <a name="details"></a>설명

Visual Studio로 디버깅을 지원하기 위해 워크플로 런타임은 해싱 알고리즘을 사용하여 워크플로 인스턴스에 대한 체크섬을 생성합니다. .NET Framework 4.6.2 이전 버전에서 워크플로 체크섬 해시는 MD5 알고리즘을 사용하여 FIPS 지원 시스템에 문제가 발생했습니다. .NET Framework 4.7부터 알고리즘은 SHA1입니다. 코드가 이러한 체크섬을 지속하면 호환되지 않습니다.

#### <a name="suggestion"></a>제안 해결 방법

체크섬 오류로 인해 코드가 워크플로 인스턴스를 로드할 수 없는 경우 `AppContext` switch &quot; Switch.System.Activities.UseMD5ForWFDebugger &quot;을 true.In code로 설정합니다.

```csharp
System.AppContext.SetSwitch("Switch.System.Activities.UseMD5ForWFDebugger", true);
```

또는 다음 구성을 사용할 수도 있습니다.

```xml
<configuration>
  <runtime>
    <AppContextSwitchOverrides value="Switch.System.Activities.UseMD5ForWFDebugger=true" />
  </runtime>
</configuration>
```

| 이름    | 값       |
|:--------|:------------|
| Scope   | 부       |
| 버전 | 4.7         |
| 형식    | 대상 변경 |
