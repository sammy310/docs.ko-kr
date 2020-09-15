---
ms.openlocfilehash: 21921156295d89aad04f3197fef9fa322f3c8c87
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614662"
---
### <a name="ensure-systemuri-uses-a-consistent-reserved-character-set"></a>System.Uri가 일관된 예약된 문자 집합을 사용하는지 확인합니다.

#### <a name="details"></a>세부 정보

<xref:System.Uri?displayProperty=fullName>에서 때로는 디코딩되는 특정 백분율로 인코딩된 문자는 이제 일관되게 인코딩됩니다. 이는 URI의 경로, 쿼리, 조각 또는 사용자 정보 구성 요소에 액세스하는 속성 및 메서드에서 발생합니다. 이 동작은 다음 두 항목 모두가 true인 경우에만 변경됩니다.

- URI는 다음 예약된 문자의 인코딩된 형식을 포함합니다. `:`, `'`, `(`, `)`, `!` 또는 `*`
- URI는 유니코드 또는 인코딩된 예약되지 않은 문자를 포함합니다. 위의 두 항목 모두가 true인 경우 인코딩된 예약된 문자는 인코딩됩니다. 이전 버전의 .NET Framework에서는 디코딩됩니다.

#### <a name="suggestion"></a>제안 해결 방법

4\.7.2 이상의 .NET Framework 버전을 대상으로 하는 애플리케이션의 경우 새로운 디코딩 동작이 기본적으로 활성화됩니다. 이 변경을 원치 않는 경우 다음 [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) 스위치를 애플리케이션 구성 파일의 `<runtime>` 섹션에 추가하여 비활성화할 수 있습니다.

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Uri.DontEnableStrictRFC3986ReservedCharacterSets=true" />
</runtime>
```

이전 버전의 .NET Framework를 대상으로 하지만 .NET Framework 4.7.2 이상 버전에서 실행되는 애플리케이션의 경우 새로운 디코딩 동작이 기본적으로 비활성화됩니다. 다음 [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) 스위치를 애플리케이션 구성 파일의 `<runtime>` 섹션에 추가하여 활성화할 수 있습니다.

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Uri.DontEnableStrictRFC3986ReservedCharacterSets=false" />
</runtime>
```

| 이름    | 값       |
|:--------|:------------|
| Scope   | 부       |
| 버전 | 4.7.2       |
| 형식    | 대상 변경 |

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Uri?displayProperty=nameWithType>
