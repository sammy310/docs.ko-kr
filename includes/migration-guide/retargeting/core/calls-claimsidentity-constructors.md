---
ms.openlocfilehash: b88f7d4a17f885b687d99ab9410a56039e176080
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614638"
---
### <a name="calls-to-claimsidentity-constructors"></a>ClaimsIdentity 생성자 호출

#### <a name="details"></a>설명

.NET Framework 4.6.2부터는 <xref:System.Security.Principal.IIdentity?displayProperty=fullName> 매개 변수로 <xref:System.Security.Claims.ClaimsIdentity> 생성자가 <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> 속성을 설정하는 방법이 변경되었습니다. <xref:System.Security.Principal.IIdentity?displayProperty=fullName> 인수가 <xref:System.Security.Claims.ClaimsIdentity> 개체이고 해당 <xref:System.Security.Claims.ClaimsIdentity> 개체의 <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> 속성이 `null`이 아닌 경우 <xref:System.Security.Claims.ClaimsIdentity.Clone> 메서드를 사용하여 <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> 속성이 연결됩니다. Framework 4.6.1 이전 버전에서 <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> 속성은 기존 참조로 첨부됩니다. 이 변경으로 인해 .NET Framework 4.6.2부터는 새 <xref:System.Security.Claims.ClaimsIdentity> 개체의 <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> 속성이 생성자의 <xref:System.Security.Principal.IIdentity?displayProperty=fullName> 인수의 <xref:System.Security.Claims.ClaimsIdentity.Actor?displayProperty=fullName> 속성과 같지 않습니다. .NET Framework 4.6.1 이전 버전에서는 이 속성이 같습니다.

#### <a name="suggestion"></a>제안 해결 방법

이 동작을 원치 않을 경우 애플리케이션 구성 파일에서 `Switch.System.Security.ClaimsIdentity.SetActorAsReferenceWhenCopyingClaimsIdentity` 스위치를 `true`로 설정하여 이전 동작을 복원할 수 있습니다. 이렇게 하려면 web.config 파일의 `<runtime>` 섹션에 다음을 추가해야 합니다.

```xml
<configuration>
  <runtime>
    <AppContextSwitchOverrides value="Switch.System.Security.ClaimsIdentity.SetActorAsReferenceWhenCopyingClaimsIdentity=true" />
  </runtime>
</configuration>
```

| 이름    | 값       |
|:--------|:------------|
| Scope   | Microsoft Edge        |
| 버전 | 4.6.2       |
| 형식    | 대상 변경 |

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Security.Principal.IIdentity)>
- <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Security.Principal.IIdentity,System.Collections.Generic.IEnumerable{System.Security.Claims.Claim})>
- <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Security.Principal.IIdentity,System.Collections.Generic.IEnumerable{System.Security.Claims.Claim},System.String,System.String,System.String)>
