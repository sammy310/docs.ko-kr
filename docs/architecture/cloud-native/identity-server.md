---
title: 클라우드 네이티브 앱에 대 한 IdentityServer
description: Azure 용 클라우드 네이티브 .NET 앱 설계 | IdentityServer
ms.date: 06/30/2019
ms.openlocfilehash: 48d0b95a40682f3127127851781b4d0e26e44630
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728585"
---
# <a name="identityserver-for-cloud-native-applications"></a>클라우드 네이티브 응용 프로그램에 대 한 IdentityServer

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

IdentityServer는 ASP.NET Core에 대 한 OIDC (Openid connect Connect) 및 OAuth 2.0 표준을 구현 하는 오픈 소스 인증 서버입니다. 웹, 네이티브, 모바일 또는 API 끝점 인지 여부에 관계 없이 모든 응용 프로그램에 대 한 요청을 인증 하는 일반적인 방법을 제공 하도록 설계 되었습니다. IdentityServer를 사용 하 여 여러 응용 프로그램 및 응용 프로그램 유형에 SSO (Single Sign-on)를 구현할 수 있습니다. 로그인 양식 및 비슷한 사용자 인터페이스를 통해 실제 사용자를 인증 하는 데 사용할 수 있으며, 일반적으로 토큰 발급, 확인 및 사용자 인터페이스 없이 갱신을 포함 하는 서비스 기반 인증에도 사용할 수 있습니다. IdentityServer은 사용자 지정이 가능한 솔루션으로 설계 되었습니다. 각 인스턴스는 일반적으로 개별 조직 및/또는 응용 프로그램의 요구 사항 집합에 맞게 사용자 지정 됩니다.

## <a name="common-web-app-scenarios"></a>일반적인 웹 앱 시나리오

일반적으로 응용 프로그램은 다음 시나리오 중 일부 또는 모두를 지원 해야 합니다.

- 사용자가 브라우저를 사용 하 여 웹 응용 프로그램에 액세스 합니다.
- 브라우저 기반 앱에서 백 엔드 웹 Api에 액세스 하는 휴먼 사용자입니다.
- 백 엔드 웹 Api에 액세스 하는 모바일/네이티브 클라이언트의 사용자입니다.
- 활성 사용자 또는 사용자 인터페이스 없이 백 엔드 웹 Api에 액세스 하는 다른 응용 프로그램입니다.
- 모든 응용 프로그램은 자체 id를 사용 하거나 사용자의 id에 위임 하 여 다른 웹 Api와 상호 작용 해야 할 수 있습니다.

**그림 8-1**](./media/application-types.png)
응용 프로그램 유형 및 시나리오를 ![합니다. 응용 프로그램 유형 및 시나리오.

이러한 각 시나리오에서 노출 된 기능을 무단 사용 으로부터 보호 해야 합니다. 일반적으로이 작업은 일반적으로 리소스에 대 한 요청을 수행 하는 사용자 또는 보안 주체를 인증 해야 합니다. 이 인증은 SAML2p, WS 또는 Openid connect Connect와 같은 몇 가지 일반적인 프로토콜 중 하나를 사용할 수 있습니다. Api와의 통신은 일반적으로 OAuth2 프로토콜을 사용 하 고 보안 토큰에 대 한 지원을 제공 합니다. 이러한 중요 한 교차를 교차 하는 보안 문제와 해당 구현 세부 사항을 응용 프로그램 자체에서 분리 하면 일관성을 유지 하 고 보안 및 유지 관리 용이성을 향상 시킵니다. 이러한 문제를 IdentityServer와 같은 전용 제품으로 아웃소싱 하면 모든 응용 프로그램에서 이러한 문제를 해결 하는 데 도움이 됩니다.

IdentityServer는 ASP.NET Core 응용 프로그램 내에서 실행 되 고 Openid connect Connect 및 OAuth2에 대 한 지원을 추가 하는 미들웨어를 제공 합니다 ( [지원 되는 사양](http://docs.identityserver.io/en/latest/intro/specs.html)참조). 조직에서는 IdentityServer 미들웨어를 사용 하 여 자체 ASP.NET Core 앱을 만들어 모든 토큰 기반 보안 프로토콜에 대 한 STS 역할을 수행 합니다. IdentityServer 미들웨어는 끝점을 노출 하 여 다음과 같은 표준 기능을 지원 합니다.

- 권한 부여 (최종 사용자 인증)
- 토큰 (프로그래밍 방식으로 토큰 요청)
- 검색 (서버에 대 한 메타 데이터)
- 사용자 정보 (유효한 액세스 토큰을 사용 하 여 사용자 정보 가져오기)
- 장치 권한 부여 (장치 흐름 권한 부여를 시작 하는 데 사용 됨)
- 검사 (토큰 유효성 검사)
- 해지 (토큰 해지)
- 세션 종료 (모든 앱에서 single sign-on 트리거)

## <a name="getting-started"></a>시작

IdentityServer4은 오픈 소스 이며 무료로 사용할 수 있습니다. NuGet 패키지를 사용 하 여 응용 프로그램에 추가할 수 있습니다. 주 패키지는 400만 번 이상 다운로드 된 [IdentityServer4](https://www.nuget.org/packages/IdentityServer4/) 입니다. 기본 패키지는 사용자 인터페이스 코드를 포함 하지 않고 메모리 구성 에서만 지원 합니다. 데이터베이스와 함께 사용 하려면 Entity Framework Core을 사용 하 여 IdentityServer에 대 한 구성 및 운영 데이터를 저장 하는 [IdentityServer4](https://www.nuget.org/packages/IdentityServer4.EntityFramework) 와 같은 데이터 공급자를 사용 하려고 합니다. 사용자 인터페이스의 경우 IdentityServer 미들웨어를 사용 하 여 로그인 및 로그 아웃에 대 한 지원을 추가 하기 위해 [빠른 시작 UI 리포지토리에서](https://github.com/IdentityServer/IdentityServer4.Quickstart.UI) 파일을 ASP.NET Core MVC 응용 프로그램으로 복사할 수 있습니다.

## <a name="configuration"></a>구성

IdentityServer는 각 사용자 지정 설치의 일부로 구성할 수 있는 다양 한 종류의 프로토콜과 소셜 인증 공급자를 지원 합니다. 이는 일반적으로 `ConfigureServices` 메서드의 ASP.NET Core 응용 프로그램 `Startup` 클래스에서 수행 됩니다. 구성에는 지원 되는 프로토콜과 사용할 서버 및 끝점의 경로를 지정 하는 작업이 포함 됩니다. 그림 8-2에서는 IdentityServer4 빠른 시작 UI 프로젝트에서 가져온 구성 예제를 보여 줍니다.

```csharp
public class Startup
{
    public void ConfigureServices(IServiceCollection services)
    {
        services.AddMvc();

        // some details omitted
        services.AddIdentityServer();

          services.AddAuthentication()
            .AddGoogle("Google", options =>
            {
                options.SignInScheme = IdentityServerConstants.ExternalCookieAuthenticationScheme;

                options.ClientId = "<insert here>";
                options.ClientSecret = "<insert here>";
            })
            .AddOpenIdConnect("demoidsrv", "IdentityServer", options =>
            {
                options.SignInScheme = IdentityServerConstants.ExternalCookieAuthenticationScheme;
                options.SignOutScheme = IdentityServerConstants.SignoutScheme;

                options.Authority = "https://demo.identityserver.io/";
                options.ClientId = "implicit";
                options.ResponseType = "id_token";
                options.SaveTokens = true;
                options.CallbackPath = new PathString("/signin-idsrv");
                options.SignedOutCallbackPath = new PathString("/signout-callback-idsrv");
                options.RemoteSignOutPath = new PathString("/signout-idsrv");

                options.TokenValidationParameters = new TokenValidationParameters
                {
                    NameClaimType = "name",
                    RoleClaimType = "role"
                };
            });
    }
}
```

**그림 8-2**. IdentityServer 구성.

또한 IdentityServer는 다양 한 프로토콜 및 구성을 테스트 하는 데 사용할 수 있는 공개 데모 사이트를 호스팅합니다. [https://demo.identityserver.io/](https://demo.identityserver.io/) 에 있으며 제공 된 `client_id` 에 따라 동작을 구성 하는 방법에 대 한 정보를 포함 합니다.

## <a name="javascript-clients"></a>JavaScript 클라이언트

많은 클라우드 네이티브 응용 프로그램은 프런트 엔드에서 서버 쪽 Api 및 리치 클라이언트 SPAs (단일 페이지 응용 프로그램)를 활용 합니다. IdentityServer는 NPM를 통해 웹 Api의 로그인, 로그 아웃 및 토큰 기반 인증에 IdentityServer를 사용할 수 있도록 하는를 통해 [JavaScript 클라이언트](http://docs.identityserver.io/en/latest/quickstarts/4_javascript_client.html) (`oidc-client.js`)를 제공 합니다.

## <a name="references"></a>참조

- [IdentityServer 설명서](http://docs.identityserver.io/en/latest/)
- [응용 프로그램 종류](https://docs.microsoft.com/azure/active-directory/develop/app-types)
- [JavaScript OIDC 클라이언트](http://docs.identityserver.io/en/latest/quickstarts/4_javascript_client.html)

>[!div class="step-by-step"]
>[이전](azure-active-directory.md)
>[다음](security.md)
