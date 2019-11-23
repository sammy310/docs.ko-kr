---
title: 호출 자격 증명-WCF 개발자를 위한 gRPC
description: ASP.NET Core 3.0에서 gRPC 통화 자격 증명을 구현 하 고 사용 하는 방법입니다.
ms.date: 09/02/2019
ms.openlocfilehash: 2588fe3590a63ea6071b85ff29b3685efbfa25db
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73967993"
---
# <a name="call-credentials"></a>호출 자격 증명

호출 자격 증명은 각 요청과 함께 메타 데이터에 전달 된 일종의 토큰을 기반으로 합니다.

## <a name="ws-federation"></a>WS-Federation

ASP.NET Core는 [WsFederation](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.WsFederation) NuGet 패키지를 사용 하 여 ws-federation을 지원 합니다. WS-FEDERATION은 Windows 인증에 사용할 수 있는 가장 가까운 대안이 며,이는 HTTP/2를 통해 지원 되지 않습니다. 사용자는 ASP.NET Core를 사용 하 여 인증 하는 데 사용할 수 있는 토큰을 제공 하는 Active Directory Federation Services (ADFS)를 사용 하 여 인증 됩니다.

이 인증 방법을 시작 하는 방법에 대 한 자세한 내용은 [ASP.NET Core에서 ws-federation을 사용 하 여 사용자 인증](https://docs.microsoft.com/aspnet/core/security/authentication/ws-federation?view=aspnetcore-3.0) 문서를 참조 하세요.

## <a name="jwt-bearer-tokens"></a>JWT 전달자 토큰

[JSON Web Token](https://jwt.io) 표준은 사용자와 해당 클레임에 대 한 정보를 인코딩된 문자열로 인코딩하고 소비자가 공개 키 암호화를 사용 하 여 토큰의 무결성을 확인할 수 있는 방식으로 해당 토큰에 서명 하는 방법을 제공 합니다. IdentityServer4와 같은 다양 한 서비스를 사용 하 여 사용자를 인증 하 고 사용자를 인증 하 고 OIDC (Openid connect Connect) 토큰을 생성 하 여 gRPC 및 HTTP Api와 함께 사용할 수 있습니다.

ASP.NET Core 3.0는 JWT 전달자 패키지를 사용 하 여 JSON 웹 토큰을 처리할 수 있습니다. 이 구성은 gRPC 응용 프로그램에 대 한 ASP.NET Core MVC 응용 프로그램의 경우와 동일 합니다.

이 장은 WS-FEDERATION 보다 쉽게 개발할 수 있으므로 JWT 전달자 토큰에 집중 합니다.

## <a name="adding-authentication-and-authorization-to-the-server"></a>서버에 인증 및 권한 부여 추가

JWT 전달자 패키지는 기본적으로 ASP.NET Core 3.0에 포함 되지 않습니다. 앱에 [AspNetCore. JwtBearer](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.JwtBearer) NuGet 패키지를 설치 합니다.

Startup 클래스에 인증 서비스를 추가 하 고 JWT 전달자 처리기를 구성 합니다.

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddGrpc();

    var signingKey = ObtainSigningKeySomehow();

    services.AddAuthentication(JwtBearerDefaults.AuthenticationScheme)
        .AddJwtBearer(options =>
        {
            options.TokenValidationParameters =
                new TokenValidationParameters
                {
                    ValidateAudience = false,
                    ValidateIssuer = false,
                    ValidateActor = false,
                    ValidateLifetime = true,
                    IssuerSigningKey = signingKey
                };
        });

}
```

`IssuerSigningKey` 속성을 사용 하려면 서명 된 토큰의 유효성을 검사 하는 데 필요한 암호화 데이터를 사용 하 여 `Microsoft.IdentityModels.Tokens.SecurityKey`를 구현 해야 합니다. 이 토큰은 Azure KeyVault와 같은 *암호 서버* 에 안전 하 게 저장 해야 합니다.

다음으로 시스템에 대 한 액세스를 제어 하는 권한 부여 서비스를 추가 합니다.

```csharp
    services.AddAuthorization(options =>
    {
        options.AddPolicy(JwtBearerDefaults.AuthenticationScheme, policy =>
        {
            policy.AddAuthenticationSchemes(JwtBearerDefaults.AuthenticationScheme);
            policy.RequireClaim(ClaimTypes.Name);
        });
    });

```

> [!TIP]
> 인증 및 권한 부여는 두 단계로 구분 됩니다. 인증은 사용자의 id를 확인 하는 데 사용 됩니다. 권한 부여는 해당 사용자가 시스템의 여러 부분에 액세스할 수 있는지 여부를 결정 합니다.

이제 `Configure` 메서드의 ASP.NET Core 파이프라인에 인증 및 권한 부여 미들웨어를 추가 합니다.

```csharp
public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
{
    if (env.IsDevelopment())
    {
        app.UseDeveloperExceptionPage();
    }

    app.UseRouting();

    // Authenticate, then Authorize
    app.UseAuthentication();
    app.UseAuthorization();

    app.UseEndpoints(endpoints =>
    {
        endpoints.MapGrpcService<PortfolioService>();
    });
}
```

마지막으로, 보호할 모든 서비스 또는 메서드에 `[Authorize]` 특성을 적용 하 고 기본 `HttpContext`의 `User` 속성을 사용 하 여 권한을 확인 합니다.

```csharp
[Authorize]
public override async Task<GetResponse> Get(GetRequest request, ServerCallContext context)
{
    if (!TryValidateUser(request.TraderId, context.GetHttpContext().User))
    {
        throw new RpcException(new Status(StatusCode.PermissionDenied, "Denied."));
    }

    var portfolio = await _repository.GetAsync(traderId, request.PortfolioId);

    return new GetResponse
    {
        Portfolio = Portfolio.FromRepositoryModel(portfolio)
    };
}
```

## <a name="providing-call-credentials-in-the-client-application"></a>클라이언트 응용 프로그램에서 호출 자격 증명 제공

Id 서버에서 JWT 토큰을 가져온 후에는이 토큰을 사용 하 여 클라이언트에서 gRPC 호출을 인증 하는 데 사용할 수 있습니다 .이는 다음과 같이 호출에 메타 데이터 헤더로 추가 됩니다.

```csharp
public async Task ShowPortfolioAsync(int portfolioId)
{
    var headers = new Grpc.Core.Metadata
    {
        { "Authorization", $"Bearer {_userToken}" }
    };
    var request = new GetRequest
    {
        TraderId = _userId,
        PortfolioId = portfolioId
    };
    var response = await _portfoliosClient.GetAsync(request, headers);

    // Display portfolio
}
```

이제 JWT 전달자 토큰을 호출 자격 증명으로 사용 하 여 gRPC 서비스의 보안을 설정 했습니다. [인증 및 권한 부여가 추가 된 포트폴리오 샘플 gRPC 응용 프로그램](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/PortfoliosSample/grpc/TraderSysAuth) 의 버전은 GitHub에 있습니다.

>[!div class="step-by-step"]
>[이전](security.md)
>[다음](channel-credentials.md)
