---
ms.openlocfilehash: c5a061dffa1deb66e1769d6ec70dfa2155ac6a31
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615710"
---
### <a name="calling-createdefaultauthorizationcontext-with-a-null-argument-has-changed"></a>Null 인수를 사용한 CreateDefaultAuthorizationContext 호출이 변경되었습니다.

#### <a name="details"></a>설명

Null authorizationPolicies를 사용하는 <xref:System.IdentityModel.Policy.AuthorizationContext.CreateDefaultAuthorizationContext(System.Collections.Generic.IList{System.IdentityModel.Policy.IAuthorizationPolicy})?displayProperty=fullName>에 대한 호출로 반환된 <xref:System.IdentityModel.Policy.AuthorizationContext?displayProperty=fullName>의 구현이 .NET Framework 4.6에서 변경되었습니다.

#### <a name="suggestion"></a>제안 해결 방법

드문 경우이지만 사용자 지정 인증을 사용하는 WCF 앱은 다르게 동작할 수 있습니다. 이러한 경우 두 가지 방법 중 하나로 이전 동작을 복원할 수 있습니다.

- 4\.6 이전 버전의 .NET Framework를 대상으로 사용하도록 앱을 다시 컴파일합니다. IIS 호스트 서비스의 경우 이전 버전의.NET Framework를 대상으로 하는 `<httpRuntime targetFramework="x.x">` 요소를 사용합니다.
- 다음 줄을 app.config 파일의 `<appSettings>` 섹션에 추가합니다.

    ```xml
    <add key="appContext.SetSwitch:Switch.System.IdentityModel.EnableCachedEmptyDefaultAuthorizationContext" value="true" />
    ```

| 이름    | 값       |
|:--------|:------------|
| Scope   | 부       |
| 버전 | 4.6         |
| 형식    | 대상 변경 |

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.IdentityModel.Policy.AuthorizationContext.CreateDefaultAuthorizationContext(System.Collections.Generic.IList{System.IdentityModel.Policy.IAuthorizationPolicy})?displayProperty=nameWithType>
