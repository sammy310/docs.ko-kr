---
ms.openlocfilehash: b0d093cc30a09b3248cc57a521b386bf581b5451
ms.sourcegitcommit: 93762e1a0dae1b5f64d82eebb7b705a6d566d839
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/27/2019
ms.locfileid: "74552158"
---
### <a name="http-browser-samesite-changes-impact-authentication"></a>HTTP: 브라우저 SameSite 변경 내용이 인증에 영향

Chrome 및 Firefox와 같은 일부 브라우저에서는 쿠키에 대한 `SameSite`의 구현에 호환성이 손상되는 변경이 수행되었습니다. 이 변경 사항은 `SameSite=None`을 전송하여 옵트아웃해야 하는 OpenID Connect 및 WS-Federation과 같은 원격 인증 시나리오에 영향을 줍니다. 그러나 `SameSite=None`이(가) iOS 12 및 일부 이전 버전의 기타 브라우저에서 중단됩니다. 이 앱에서 이 버전을 찾아 `SameSite`를 생략해야 합니다.

이 문제에 대한 자세한 내용은 [aspnet/AspNetCore#14996](https://github.com/aspnet/AspNetCore/issues/14996)을 참조하세요.

#### <a name="version-introduced"></a>도입된 버전

3.1 미리 보기 1

#### <a name="old-behavior"></a>이전 동작

`SameSite`은(는) HTTP 쿠키의 2016 초안 표준 확장입니다. CSRF(교차 사이트 요청 위조)를 완화하기 위한 것입니다. 원래는 새 매개 변수를 추가하여 서버에서 옵트인하는 기능으로 설계되었습니다. ASP.NET Core 2.0에서 `SameSite`에 대한 초기 지원을 추가했습니다.

#### <a name="new-behavior"></a>새 동작

Google은 이전 버전과 호환되지 않는 새 초안 표준을 제안했습니다. 이 표준은 기본 모드를 `Lax`으로 변경하고 옵트아웃할 새 항목 `None`을 추가합니다. 대부분의 앱 쿠키의 경우 `Lax`가 충분하지만, OpenID Connect 및 WS-Federation 로그인과 같은 교차 사이트 시나리오는 방해합니다. 대부분의 OAuth 로그인은 요청 진행 방법의 차이로 인해 영향을 받지 않습니다. 새 `None` 매개 변수로 인해 이전 초안 표준(예: iOS 12)을 구현한 클라이언트에 호환성 문제가 발생합니다. Chrome 80에는 변경 내용이 포함됩니다. Chrome 제품 출시 타임라인을 보려면 [SameSite 업데이트](https://www.chromium.org/updates/same-site)를 참조하세요.

ASP.NET Core 3.1이 새 `SameSite` 동작을 구현하도록 업데이트되었습니다. 업데이트는 `SameSiteMode.None`의 동작을 재정의하여 `SameSite=None`을 내보내고 새 값 `SameSiteMode.Unspecified`를 추가하여 `SameSite` 특성을 생략합니다. 일부 구성 요소에서 OpenID Connect 상관 관계 및 nonce 쿠키와 같은 특정 시나리오와 관련된 값을 설정하지만 이제 모든 쿠키 API는 `Unspecified`를 기본값으로 설정됩니다.

이 영역에 대한 기타 최근 변경 사항은 [HTTP: 일부 쿠키 SameSite 기본값이 없음으로 변경됨](/dotnet/core/compatibility/2.2-3.0#http-some-cookie-samesite-defaults-changed-to-none)을 참조하세요. ASP.NET Core 3.0에서 대부분의 기본값이 <xref:Microsoft.AspNetCore.Http.SameSiteMode.Lax?displayProperty=nameWithType>에서 <xref:Microsoft.AspNetCore.Http.SameSiteMode.None?displayProperty=nameWithType>(으)로 변경되었지만, 이전 표준은 여전히 사용됩니다.

#### <a name="reason-for-change"></a>변경 이유

이전 텍스트에서 설명한 대로 브라우저 및 사양이 변경됩니다.

#### <a name="recommended-action"></a>권장 작업

타사 로그인 등 원격 사이트와 상호 작용하는 앱은 다음 작업을 수행해야 합니다.

* 이 시나리오를 여러 브라우저에서 테스트합니다.
* [이전 브라우저 지원](#support-older-browsers)에서 설명된 대로 쿠키 정책 브라우저 검색 완화를 적용합니다.

테스트 및 브라우저 검색 지침은 다음 섹션을 참조하세요.

##### <a name="determine-if-youre-affected"></a>사용자가 영향을 받는지 확인합니다.

새 동작을 옵트인할 수 있는 클라이언트 버전을 사용하여 웹앱을 테스트합니다. Chrome, Firefox 및 Microsoft Edge Chromium에는 테스트에 사용할 수 있는 새 옵트인 기능 플래그가 있습니다. 패치, 특히 Safari를 적용한 후 앱이 이전 클라이언트 버전과 호환되는지 확인합니다. 자세한 내용은 [이전 브라우저 지원](#support-older-browsers)을 참조하세요.

##### <a name="chrome"></a>Chrome

Chrome 78 이상에서는 잘못된 테스트 결과를 생성합니다. 이러한 버전에는 임시 해결 방법이 있으며 2분 이내 쿠키를 허용합니다. 적절한 테스트 플래그를 사용하도록 설정하면 Chrome 76 및 77에서 더 정확한 결과를 생성합니다. 새 동작을 테스트하려면 `chrome://flags/#same-site-by-default-cookies`를 사용으로 토글합니다. Chrome 75 이전 버전이 새 `None` 설정에서 실패한다고 보고됩니다. 자세한 내용은 [이전 브라우저 지원](#support-older-browsers)을 참조하세요.

Google은 이전 Chrome 버전을 사용하도록 설정할 수 없습니다. 그러나 테스트에 충분한 이전 버전의 Chromium을를 다운로드할 수 있습니다. [Chromium 다운로드](https://www.chromium.org/getting-involved/download-chromium)에 있는 지침을 따릅니다.

* [Chromium 76 Win64](https://commondatastorage.googleapis.com/chromium-browser-snapshots/index.html?prefix=Win_x64/664998/)
* [Chromium 74 Win64](https://commondatastorage.googleapis.com/chromium-browser-snapshots/index.html?prefix=Win_x64/638880/)

##### <a name="safari"></a>Safari

Safari 12는 이전 초안을 엄격하게 구현했으며 쿠키에 새 `None` 값이 표시되는 경우 실패합니다. [이전 브라우저 지원](#support-older-browsers)에 표시된 브라우저 검색 코드를 통해 이를 방지해야 합니다. MSAL(Microsoft Authentication Library), ADAL(Active Directory 인증 라이브러리) 또는 사용 중인 라이브러리를 사용하여 WebKit 기반 OS 스타일뿐 아니라 Safari 12 및 13을 테스트해야 합니다. 문제는 기본 OS 버전에 따라 달라집니다. OSX Mojave 10.14 및 iOS 12는 새 동작에 호환성 문제가 있는 것으로 알려져 있습니다. OSX Catalina 10.15 또는 iOS 13으로 업그레이드하면 문제가 해결됩니다. Safari에는 현재 새 사양 동작을 테스트하기 위한 옵트인 플래그가 없습니다.

##### <a name="firefox"></a>Firefox

새 표준에 대한 Firefox 지원은 기능 플래그 `network.cookie.sameSite.laxByDefault`를 사용하여 `about:config` 페이지에서 옵트인하여 버전 68 이상에서 테스트할 수 있습니다. 이전 버전의 Firefox에서는 호환성 문제가 보고되지 않았습니다.

##### <a name="microsoft-edge"></a>Microsoft Edge

Microsoft Edge는 이전 `SameSite` 표준을 지원하지만, 버전 44부터 새 표준에 호환성 문제가 없습니다.

##### <a name="microsoft-edge-chromium"></a>Microsoft Edge Chromium

기능 플래그는 `edge://flags/#same-site-by-default-cookies`입니다. Microsoft Edge Chromium 78을 사용하여 테스트할 때 호환성 문제가 관찰되지 않았습니다.

##### <a name="electron"></a>Electron

Electron 버전에는 이전 버전의 Chromium이 포함되어 있습니다. 예를 들어, Microsoft Teams에서 사용하는 Electron의 버전은 Chromium 66이며, 이는 이전 동작을 보입니다. 사용자의 제품에서 사용하는 Electron 버전으로 자체 호환성 테스트를 수행합니다. 자세한 내용은 [이전 브라우저 지원](#support-older-browsers)을 참조하세요.

##### <a name="support-older-browsers"></a>이전 브라우저 지원

2016 `SameSite` 표준에 따라 알 수 없는 값을 `SameSite=Strict` 값으로 처리합니다. 따라서 원래 표준을 지원하는 모든 이전 브라우저는 값이 `None`인 `SameSite` 속성이 표시될 때 중단될 수 있습니다. 이러한 이전 브라우저를 지원하려는 경우 웹앱은 브라우저 검색을 구현해야 합니다. `User-Agent` 요청 헤더 값이 매우 불안정하고 매주 변경되기 때문에 ASP.NET Core에서 브라우저 검색을 구현하지 않습니다. 대신, 쿠키 정책의 확장 지점을 사용하여 `User-Agent`별 논리를 추가할 수 있습니다.

*Startup.cs*에서 다음 코드를 추가합니다.

```csharp
private void CheckSameSite(HttpContext httpContext, CookieOptions options)
{
    if (options.SameSite == SameSiteMode.None) 
    { 
        var userAgent = httpContext.Request.Headers["User-Agent"].ToString();
        // TODO: Use your User Agent library of choice here. 
        if (/* UserAgent doesn't support new behavior */) 
        { 
            options.SameSite = SameSiteMode.Unspecified;
        }
    }
}

public void ConfigureServices(IServiceCollection services) 
{ 
    services.Configure<CookiePolicyOptions>(options => 
    { 
        options.MinimumSameSitePolicy = SameSiteMode.Unspecified;
        options.OnAppendCookie = cookieContext =>
            CheckSameSite(cookieContext.Context, cookieContext.CookieOptions);
        options.OnDeleteCookie = cookieContext =>
            CheckSameSite(cookieContext.Context, cookieContext.CookieOptions);
    }); 
} 

public void Configure(IApplicationBuilder app) 
{ 
    // Before UseAuthentication or anything else that writes cookies.
    app.UseCookiePolicy();

    app.UseAuthentication(); 
    // code omitted for brevity
}
```

##### <a name="opt-out-switches"></a>옵트아웃 스위치

`Microsoft.AspNetCore.SuppressSameSiteNone` 호환성 스위치를 사용하면 새 ASP.NET Core 쿠키 동작을 임시로 옵트아웃할 수 있습니다. 프로젝트에서 *runtimeconfig.template.json* 파일에 다음 JSON을 추가합니다.

```json
{ 
  "configProperties": { 
    "Microsoft.AspNetCore.SuppressSameSiteNone": "true" 
  } 
}
```

##### <a name="other-versions"></a>다른 버전

관련 `SameSite` 패치가 곧 출시될 예정입니다.

* ASP.NET Core 2.1, 2.2 및 3.0
* `Microsoft.Owin` 4.1
* `System.Web`(.NET Framework 4.7.2 이상)

#### <a name="category"></a>범주

ASP.NET

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:Microsoft.AspNetCore.Builder.CookiePolicyOptions.MinimumSameSitePolicy%2A?displayProperty=fullName>
- <xref:Microsoft.AspNetCore.Http.CookieBuilder.SameSite%2A?displayProperty=fullName>
- <xref:Microsoft.AspNetCore.Http.CookieOptions.SameSite%2A?displayProperty=fullName>
- <xref:Microsoft.AspNetCore.Http.SameSiteMode?displayProperty=fullName>
- <xref:Microsoft.Net.Http.Headers.SameSiteMode?displayProperty=fullName>
- <xref:Microsoft.Net.Http.Headers.SetCookieHeaderValue.SameSite%2A?displayProperty=fullName>

<!--

#### Affected APIs

- `Overload:Microsoft.AspNetCore.Builder.CookiePolicyOptions.MinimumSameSitePolicy`
- `Overload:Microsoft.AspNetCore.Http.CookieBuilder.SameSite`
- `Overload:Microsoft.AspNetCore.Http.CookieOptions.SameSite`
- `T:Microsoft.AspNetCore.Http.SameSiteMode`
- `T:Microsoft.Net.Http.Headers.SameSiteMode`
- `Overload:Microsoft.Net.Http.Headers.SetCookieHeaderValue.SameSite`

-->
