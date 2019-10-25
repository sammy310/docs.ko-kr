---
ms.openlocfilehash: 65bac44c84589fb55d2b04c39088c2825c451a6b
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394267"
---
### <a name="authorization-addauthorization-overload-moved-to-different-assembly"></a>권한 부여: AddAuthorization 오버로드가 다른 어셈블리로 이동됨

`Microsoft.AspNetCore.Authorization`에 상주하는 데 사용되는 핵심 `AddAuthorization` 메서드가 `AddAuthorizationCore`로 이름이 변경되었습니다. 이전 `AddAuthorization` 메서드는 여전히 존재하지만 대신 `Microsoft.AspNetCore.Authorization.Policy` 패키지에 있습니다. 두 방법을 모두 사용하는 앱은 영향을 받지 않아야 합니다. 정책 패키지를 사용하지 않는 앱은 `AddAuthorizationCore`를 사용하도록 전환해야 합니다.

#### <a name="version-introduced"></a>도입된 버전

3.0

#### <a name="old-behavior"></a>이전 동작

`AddAuthorization` 메서드가 `Microsoft.AspNetCore.Authorization`에 있었습니다.

#### <a name="new-behavior"></a>새 동작

`AddAuthorization` 메서드가 `Microsoft.AspNetCore.Authorization.Policy`에 있습니다. `AddAuthorizationCore`는 이전 메서드의 새 이름입니다.

#### <a name="reason-for-change"></a>변경 이유

`AddAuthorization`는 권한 부여에 필요한 모든 일반 서비스를 추가하는 데 더 나은 메서드 이름입니다.

#### <a name="recommended-action"></a>권장 작업

`Microsoft.AspNetCore.Authorization.Policy`에 대한 참조를 추가하거나 대신 `AddAuthorizationCore`를 사용합니다.

#### <a name="category"></a>범주

ASP.NET Core

#### <a name="affected-apis"></a>영향을 받는 API

<xref:Microsoft.Extensions.DependencyInjection.AuthorizationServiceCollectionExtensions.AddAuthorization(Microsoft.Extensions.DependencyInjection.IServiceCollection,System.Action{Microsoft.AspNetCore.Authorization.AuthorizationOptions})?displayProperty=fullName>

<!--

#### Affected APIs

`M:Microsoft.Extensions.DependencyInjection.AuthorizationServiceCollectionExtensions.AddAuthorization(Microsoft.Extensions.DependencyInjection.IServiceCollection,System.Action{Microsoft.AspNetCore.Authorization.AuthorizationOptions})`

-->
