---
ms.openlocfilehash: 14d80f25c34465caa6dec10e5704fe0a3cbccc71
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96477945"
---
### <a name="authentication-google-deprecated-and-replaced"></a>인증: Google+가 더 이상 사용되지 않고 대체됨

Google은 2019년 1월 28일부터 앱에 대한 Google+ 로그인을 [종료](https://developers.google.com/+/api-shutdown)하기 시작했습니다.

#### <a name="change-description"></a>변경 내용 설명

ASP.NET 4.x 및 ASP.NET Core는 Google+ 로그인 API를 사용하여 웹앱에서 Google 계정 사용자를 인증하고 있습니다. 영향을 받는 NuGet 패키지는 [Microsoft.AspNetCore.Authentication.Google](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.Google/)이며 ASP.NET Web Forms 및 MVC가 있는 `Microsoft.Owin`의 경우 [Microsoft.Owin.Security.Google](https://www.nuget.org/packages/Microsoft.Owin.Security.Google/)입니다.

Google의 대체 API는 다른 데이터 원본 및 형식을 사용합니다. 아래에 제공된 완화 및 솔루션은 구조적 변경을 제공합니다. 앱은 데이터 자체가 여전히 요구 사항을 충족하는지 확인해야 합니다. 예를 들어 이름, 이메일 주소, 프로필 링크 및 프로필 사진은 이전과는 약간 다른 값을 제공할 수 있습니다.

#### <a name="version-introduced"></a>도입된 버전

모든 버전. 이 변경 내용은 ASP.NET Core 외부에 있습니다.

#### <a name="recommended-action"></a>권장 조치

##### <a name="owin-with-aspnet-web-forms-and-mvc"></a>ASP.NET Web Forms 및 MVC를 사용한 Owin

`Microsoft.Owin` 3.1.0 이상의 경우 임시 완화가 [여기에](https://github.com/aspnet/AspNetKatana/issues/251#issuecomment-449587635) 간략하게 설명되어 있습니다. 앱은 데이터 형식의 변경 내용을 확인하기 위해 완화를 사용하여 테스트를 완료해야 합니다. 수정 내용이 있는 `Microsoft.Owin` 4.0.1을 릴리스할 계획이 있습니다. 이전 버전을 사용하는 앱은 버전 4.0.1로 업데이트해야 합니다.

##### <a name="aspnet-core-1x"></a>ASP.NET Core 1.x

[ASP.NET Web Forms 및 MVC를 사용한 Owin](#owin-with-aspnet-web-forms-and-mvc)의 완화를 ASP.NET Core 1.x에 맞게 조정할 수 있습니다. 1\.x가 [수명 종료](https://dotnet.microsoft.com/platform/support-policy) 상태에 도달했기 때문에 NuGet 패키지 패치가 계획되지 않았습니다.

##### <a name="aspnet-core-2x"></a>ASP.NET Core 2.x

`Microsoft.AspNetCore.Authentication.Google` 버전 2.x의 경우 `Startup.ConfigureServices`의 `AddGoogle`에 대한 기존 호출을 다음 코드로 바꿉니다.

```csharp
.AddGoogle(o =>
{
    o.ClientId = Configuration["Authentication:Google:ClientId"];
    o.ClientSecret = Configuration["Authentication:Google:ClientSecret"];
    o.UserInformationEndpoint = "https://www.googleapis.com/oauth2/v2/userinfo";
    o.ClaimActions.Clear();
    o.ClaimActions.MapJsonKey(ClaimTypes.NameIdentifier, "id");
    o.ClaimActions.MapJsonKey(ClaimTypes.Name, "name");
    o.ClaimActions.MapJsonKey(ClaimTypes.GivenName, "given_name");
    o.ClaimActions.MapJsonKey(ClaimTypes.Surname, "family_name");
    o.ClaimActions.MapJsonKey("urn:google:profile", "link");
    o.ClaimActions.MapJsonKey(ClaimTypes.Email, "email");
});
```

2월 2.1 및 2.2 패치는 이전의 재구성을 새 기본값으로 통합했습니다. [수명 종료](https://dotnet.microsoft.com/platform/support-policy)에 도달했기 때문에 ASP.NET Core 2.0의 패치가 계획되지 않았습니다.

##### <a name="aspnet-core-30"></a>ASP.NET Core 3.0

ASP.NET Core 2.x에 제공된 완화는 ASP.NET Core 3.0에도 사용할 수 있습니다. 향후 3.0 미리 보기에서 `Microsoft.AspNetCore.Authentication.Google` 패키지가 제거될 수 있습니다. 사용자는 대신 `Microsoft.AspNetCore.Authentication.OpenIdConnect`로 이동해야 합니다. 다음 코드는 `Startup.ConfigureServices`에서 `AddGoogle`을 `AddOpenIdConnect`로 바꾸는 방법을 보여줍니다. 이 대체 항목은 ASP.NET Core 2.0 이상에서 사용할 수 있으며, 필요에 따라 ASP.NET Core 1.x에 맞게 조정할 수 있습니다.

```csharp
.AddOpenIdConnect("Google", o =>
{
    o.ClientId = Configuration["Authentication:Google:ClientId"];
    o.ClientSecret = Configuration["Authentication:Google:ClientSecret"];
    o.Authority = "https://accounts.google.com";
    o.ResponseType = OpenIdConnectResponseType.Code;
    o.CallbackPath = "/signin-google"; // Or register the default "/signin-oidc"
    o.Scope.Add("email");
});
JwtSecurityTokenHandler.DefaultInboundClaimTypeMap.Clear();
```

#### <a name="category"></a>범주

ASP.NET Core

#### <a name="affected-apis"></a>영향을 받는 API

<xref:Microsoft.AspNetCore.Authentication.Google?displayProperty=fullName>

<!-- 

#### Affected APIs

`N:Microsoft.AspNetCore.Authentication.Google`

-->
