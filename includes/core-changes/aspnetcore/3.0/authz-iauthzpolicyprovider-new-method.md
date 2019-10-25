---
ms.openlocfilehash: a16d443a37fb0bb5f6bdc4a39e7dcb4f91c54ead
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394248"
---
### <a name="authorization-iauthorizationpolicyprovider-implementations-require-new-method"></a>권한 부여: IAuthorizationPolicyProvider 구현에는 새 메서드가 필요합니다.

ASP.NET Core 3.0에서는 새 `GetFallbackPolicyAsync` 메서드가 `IAuthorizationPolicyProvider`에 추가되었습니다. 이 대체 정책은 정책이 지정되지 않은 경우 권한 부여 미들웨어에서 사용됩니다.

자세한 내용은 [aspnet/AspNetCore#9759](https://github.com/aspnet/AspNetCore/pull/9759)를 참조하세요. 

#### <a name="version-introduced"></a>도입된 버전

3.0

#### <a name="old-behavior"></a>이전 동작

`IAuthorizationPolicyProvider`의 구현에는 `GetFallbackPolicyAsync` 메서드가 필요하지 않습니다.

#### <a name="new-behavior"></a>새 동작

`IAuthorizationPolicyProvider`의 구현에는 `GetFallbackPolicyAsync` 메서드가 필요합니다.

#### <a name="reason-for-change"></a>변경 이유

정책이 지정되지 않은 경우 새 `AuthorizationMiddleware`를 사용할 수 있는 새로운 메서드가 필요했습니다.

#### <a name="recommended-action"></a>권장 작업

`IAuthorizationPolicyProvider`의 구현에 `GetFallbackPolicyAsync` 메서드를 추가합니다.

#### <a name="category"></a>범주

ASP.NET Core

#### <a name="affected-apis"></a>영향을 받는 API

<xref:Microsoft.AspNetCore.Authorization.IAuthorizationPolicyProvider?displayProperty=fullName>

<!-- 

#### Affected APIs

`T:Microsoft.AspNetCore.Authorization.IAuthorizationPolicyProvider`

-->
