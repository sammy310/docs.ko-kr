---
ms.openlocfilehash: a4e20e0468d861138ad801c9dbfa15340b3f388c
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394286"
---
### <a name="authentication-oauthhandler-exchangecodeasync-signature-changed"></a>인증: OAuthHandler ExchangeCodeAsync 서명이 변경됨

ASP.NET Core 3.0에서 `OAuthHandler.ExchangeCodeAsync`의 서명이 다음에서 변경되었습니다.

```csharp
protected virtual System.Threading.Tasks.Task<Microsoft.AspNetCore.Authentication.OAuth.OAuthTokenResponse> ExchangeCodeAsync(string code, string redirectUri) { throw null; }
```

대상:

```csharp
protected virtual System.Threading.Tasks.Task<Microsoft.AspNetCore.Authentication.OAuth.OAuthTokenResponse> ExchangeCodeAsync(Microsoft.AspNetCore.Authentication.OAuth.OAuthCodeExchangeContext context) { throw null; }
```

#### <a name="version-introduced"></a>도입된 버전

3.0

#### <a name="old-behavior"></a>이전 동작

`code` 및 `redirectUri` 문자열은 별도의 인수로 전달되었습니다.

#### <a name="new-behavior"></a>새 동작

`Code` 및 `RedirectUri`는 `OAuthCodeExchangeContext` 생성자를 통해 설정할 수 있는 `OAuthCodeExchangeContext`의 속성입니다. 새 `OAuthCodeExchangeContext` 형식은 `OAuthHandler.ExchangeCodeAsync`에 전달된 유일한 인수입니다.

#### <a name="reason-for-change"></a>변경 이유

이러한 변경으로 인해 추가 매개 변수가 중단되지 않은 방식으로 제공될 수 있습니다. 새 `ExchangeCodeAsync` 오버로드를 만들 필요가 없습니다.

#### <a name="recommended-action"></a>권장 작업

적절한 `code` 및 `redirectUri` 값을 사용하여 `OAuthCodeExchangeContext`를 구성합니다. <xref:Microsoft.AspNetCore.Authentication.AuthenticationProperties> 인스턴스를 제공해야 합니다. 이 단일 `OAuthCodeExchangeContext` 인스턴스는 여러 인수 대신 `OAuthHandler.ExchangeCodeAsync`에 전달할 수 있습니다.

#### <a name="category"></a>범주

ASP.NET Core

#### <a name="affected-apis"></a>영향을 받는 API

<xref:Microsoft.AspNetCore.Authentication.OAuth.OAuthHandler%601.ExchangeCodeAsync(System.String,System.String)?displayProperty=nameWithType>

<!--

#### Affected APIs

`M:Microsoft.AspNetCore.Authentication.OAuth.OAuthHandler`1.ExchangeCodeAsync(System.String,System.String)`

-->
