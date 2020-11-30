---
ms.openlocfilehash: 6679e38aefa7d61ce430dc5375ff3b35c641ea27
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032550"
---
### <a name="identity-signinasync-throws-exception-for-unauthenticated-identity"></a>ID: SignInAsync는 인증되지 않은 ID에 대해 예외를 throw합니다.

기본적으로 `SignInAsync`는 `IsAuthenticated`가 `false`인 보안 주체/ID에 대해 예외를 throw합니다.

#### <a name="version-introduced"></a>도입된 버전

3.0

#### <a name="old-behavior"></a>이전 동작

`SignInAsync`는 `IsAuthenticated`가 `false`인 ID를 포함하여 모든 보안 주체/ID를 허용합니다.

#### <a name="new-behavior"></a>새 동작

기본적으로 `SignInAsync`는 `IsAuthenticated`가 `false`인 보안 주체/ID에 대해 예외를 throw합니다. 이 동작을 표시하지 않는 새로운 플래그가 있지만 기본 동작이 변경되었습니다.

#### <a name="reason-for-change"></a>변경 이유

기본적으로 이러한 보안 주체는 `[Authorize]` / `RequireAuthenticatedUser()`에 의해 거부되었기 때문에 이전 동작은 문제가 있었습니다.

#### <a name="recommended-action"></a>권장 조치

ASP.NET Core 3.0 Preview 6에서는 기본적으로 `true`인 `AuthenticationOptions`에 `RequireAuthenticatedSignIn` 플래그가 있습니다. 이전 동작을 복원하려면 이 플래그를 `false`로 설정합니다.

#### <a name="category"></a>범주

ASP.NET Core

#### <a name="affected-apis"></a>영향을 받는 API

없음

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
