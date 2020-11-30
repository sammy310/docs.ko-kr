---
ms.openlocfilehash: 60ebcd9fc9ca18c33d31b82ba5020426d22a7d5a
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032489"
---
### <a name="authentication-httpcontextauthentication-property-removed"></a>인증: HttpContext.Authentication 인증 속성이 제거됨

`HttpContext`에서 사용되지 않는 `Authentication` 속성이 제거되었습니다.

#### <a name="change-description"></a>변경 내용 설명

[dotnet/aspnetcore#6504](https://github.com/dotnet/aspnetcore/pull/6504)의 일부로, `HttpContext`에서 사용되지 않는 `Authentication` 속성이 제거되었습니다. `Authentication` 속성은 2.0 이후 더 이상 사용되지 않습니다. 사용되지 않는 이 속성을 사용하여 코드를 새 대체 API로 마이그레이션하기 위해 [마이그레이션 가이드](/aspnet/core/migration/1x-to-2x/identity-2x?view=aspnetcore-2.2#use-httpcontext-authentication-extensions)가 게시되었습니다. 이전 ASP.NET Core 1.x 인증 스택과 관련된 사용되지 않는 나머지 클래스 / API는 커밋 [dotnet/aspnetcore@d7a7c65](https://github.com/dotnet/aspnetcore/commit/d7a7c65)에서 제거되었습니다.

토론은 [dotnet/aspnetcore#6533](https://github.com/dotnet/aspnetcore/issues/6533)을 참조하세요.

#### <a name="version-introduced"></a>도입된 버전

3.0

#### <a name="reason-for-change"></a>변경 이유

ASP.NET Core 1.0 API는 <xref:Microsoft.AspNetCore.Authentication.AuthenticationHttpContextExtensions?displayProperty=fullName>의 확장 메서드로 대체되었습니다.

#### <a name="recommended-action"></a>권장 조치

[마이그레이션 가이드](/aspnet/core/migration/1x-to-2x/identity-2x?view=aspnetcore-2.2#use-httpcontext-authentication-extensions)를 참조하세요.

#### <a name="category"></a>범주

ASP.NET Core

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:Microsoft.AspNetCore.Http.Authentication.AuthenticateInfo?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Authentication.AuthenticationManager?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Authentication.AuthenticationProperties?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Features.Authentication.AuthenticateContext?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Features.Authentication.ChallengeBehavior?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Features.Authentication.ChallengeContext?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Features.Authentication.DescribeSchemesContext?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Features.Authentication.IAuthenticationHandler?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Features.Authentication.IHttpAuthenticationFeature.Handler?displayProperty=fullName>
- <xref:Microsoft.AspNetCore.Http.Features.Authentication.SignInContext?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Features.Authentication.SignOutContext?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.HttpContext.Authentication?displayProperty=fullName>

<!-- 

#### Affected APIs

- `T:Microsoft.AspNetCore.Http.Authentication.AuthenticateInfo`
- `T:Microsoft.AspNetCore.Http.Authentication.AuthenticationManager`
- `T:Microsoft.AspNetCore.Http.Authentication.AuthenticationProperties`
- `T:Microsoft.AspNetCore.Http.Features.Authentication.AuthenticateContext`
- `T:Microsoft.AspNetCore.Http.Features.Authentication.ChallengeBehavior`
- `T:Microsoft.AspNetCore.Http.Features.Authentication.ChallengeContext`
- `T:Microsoft.AspNetCore.Http.Features.Authentication.DescribeSchemesContext`
- `T:Microsoft.AspNetCore.Http.Features.Authentication.IAuthenticationHandler`
- `P:Microsoft.AspNetCore.Http.Features.Authentication.IHttpAuthenticationFeature.Handler`
- `T:Microsoft.AspNetCore.Http.Features.Authentication.SignInContext`
- `T:Microsoft.AspNetCore.Http.Features.Authentication.SignOutContext`
- `P:Microsoft.AspNetCore.Http.HttpContext.Authentication`

-->
