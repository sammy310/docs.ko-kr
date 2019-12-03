---
title: 호출 자격 증명-WCF 개발자를 위한 gRPC
description: ASP.NET Core 3.0에서 gRPC 통화 자격 증명을 구현 하 고 사용 하는 방법입니다.
ms.date: 09/02/2019
ms.openlocfilehash: 01f21f58ed4235f45509c948c84653cd99d35618
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74711530"
---
# <a name="call-credentials"></a><span data-ttu-id="cf705-103">호출 자격 증명</span><span class="sxs-lookup"><span data-stu-id="cf705-103">Call credentials</span></span>

<span data-ttu-id="cf705-104">호출 자격 증명은 각 요청과 함께 메타 데이터에 전달 된 토큰을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf705-104">Call credentials are all based on a token passed in metadata with each request.</span></span>

## <a name="ws-federation"></a><span data-ttu-id="cf705-105">WS-Federation</span><span class="sxs-lookup"><span data-stu-id="cf705-105">WS-Federation</span></span>

<span data-ttu-id="cf705-106">ASP.NET Core는 [WsFederation](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.WsFederation) NuGet 패키지를 사용 하 여 ws-federation을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf705-106">ASP.NET Core supports WS-Federation using the [WsFederation](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.WsFederation) NuGet package.</span></span> <span data-ttu-id="cf705-107">WS-FEDERATION은 Windows 인증에 사용할 수 있는 가장 가까운 대안이 며,이는 HTTP/2를 통해 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cf705-107">WS-Federation is the closest available alternative to Windows Authentication, which isn't supported over HTTP/2.</span></span> <span data-ttu-id="cf705-108">사용자는 ASP.NET Core를 사용 하 여 인증 하는 데 사용할 수 있는 토큰을 제공 하는 Active Directory Federation Services (AD FS)를 사용 하 여 인증 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf705-108">Users are authenticated by using Active Directory Federation Services (AD FS), which provides a token that can be used to authenticate with ASP.NET Core.</span></span>

<span data-ttu-id="cf705-109">이 인증 방법을 시작 하는 방법에 대 한 자세한 내용은 [ASP.NET Core에서 ws-federation을 사용 하 여 사용자 인증](/aspnet/core/security/authentication/ws-federation)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cf705-109">For more information on how to get started with this authentication method, see [Authenticate users with WS-Federation in ASP.NET Core](/aspnet/core/security/authentication/ws-federation).</span></span>

## <a name="jwt-bearer-tokens"></a><span data-ttu-id="cf705-110">JWT 전달자 토큰</span><span class="sxs-lookup"><span data-stu-id="cf705-110">JWT Bearer tokens</span></span>

<span data-ttu-id="cf705-111">JWT ( [JSON Web Token](https://jwt.io) ) 표준은 인코딩된 문자열에서 사용자 및 해당 클레임에 대 한 정보를 인코딩하는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf705-111">The [JSON Web Token](https://jwt.io) (JWT) standard provides a way to encode information about a user and their claims in an encoded string.</span></span> <span data-ttu-id="cf705-112">또한 소비자가 공개 키 암호화를 사용 하 여 토큰의 무결성을 확인할 수 있도록 해당 토큰에 서명 하는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf705-112">It also provides a way to sign that token, so that the consumer can verify the integrity of the token by using public key cryptography.</span></span> <span data-ttu-id="cf705-113">IdentityServer4와 같은 다양 한 서비스를 사용 하 여 사용자를 인증 하 고 사용자를 인증 하 고 OIDC (Openid connect Connect) 토큰을 생성 하 여 gRPC 및 HTTP Api와 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf705-113">You can use various services, such as IdentityServer4, to authenticate users and generate OpenID Connect (OIDC) tokens to use with gRPC and HTTP APIs.</span></span>

<span data-ttu-id="cf705-114">ASP.NET Core 3.0는 JWT 전달자 패키지를 사용 하 여 JWTs를 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf705-114">ASP.NET Core 3.0 can handle JWTs by using the JWT Bearer package.</span></span> <span data-ttu-id="cf705-115">구성은 ASP.NET Core MVC 응용 프로그램의 경우와 동일 하 게 gRPC 응용 프로그램에 대해 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf705-115">The configuration is exactly the same for a gRPC application as it is for an ASP.NET Core MVC application.</span></span> <span data-ttu-id="cf705-116">여기서는 WS-FEDERATION을 사용 하 여 쉽게 개발할 수 있으므로 JWT 전달자 토큰에 대해 집중적으로 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf705-116">Here, we'll focus on JWT Bearer tokens, because they're easier to develop with than WS-Federation.</span></span>

## <a name="add-authentication-and-authorization-to-the-server"></a><span data-ttu-id="cf705-117">서버에 인증 및 권한 부여 추가</span><span class="sxs-lookup"><span data-stu-id="cf705-117">Add authentication and authorization to the server</span></span>

<span data-ttu-id="cf705-118">JWT 전달자 패키지는 기본적으로 ASP.NET Core 3.0에 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cf705-118">The JWT Bearer package isn't included in ASP.NET Core 3.0 by default.</span></span> <span data-ttu-id="cf705-119">앱에 [AspNetCore. JwtBearer](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.JwtBearer) NuGet 패키지를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf705-119">Install the [Microsoft.AspNetCore.Authentication.JwtBearer](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.JwtBearer) NuGet package in your app.</span></span>

<span data-ttu-id="cf705-120">시작 클래스에 인증 서비스를 추가 하 고 JWT 전달자 처리기를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf705-120">Add the Authentication service in the Startup class, and configure the JWT Bearer handler:</span></span>

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

<span data-ttu-id="cf705-121">`IssuerSigningKey` 속성을 사용 하려면 서명 된 토큰의 유효성을 검사 하는 데 필요한 암호화 데이터를 사용 하 여 `Microsoft.IdentityModels.Tokens.SecurityKey`를 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf705-121">The `IssuerSigningKey` property requires an implementation of `Microsoft.IdentityModels.Tokens.SecurityKey` with the cryptographic data necessary to validate the signed tokens.</span></span> <span data-ttu-id="cf705-122">Azure Key Vault와 같이 *비밀 서버*에 안전 하 게이 토큰을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf705-122">Store this token securely in a *secrets server*, like Azure Key Vault.</span></span>

<span data-ttu-id="cf705-123">다음으로 시스템에 대 한 액세스를 제어 하는 권한 부여 서비스를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf705-123">Next, add the Authorization service, which controls access to the system:</span></span>

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
> <span data-ttu-id="cf705-124">인증 및 권한 부여는 두 단계로 구분 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf705-124">Authentication and authorization are two separate steps.</span></span> <span data-ttu-id="cf705-125">인증을 사용 하 여 사용자의 id를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf705-125">You use authentication to determine the user's identity.</span></span> <span data-ttu-id="cf705-126">권한 부여를 사용 하 여 사용자가 시스템의 여러 부분에 액세스할 수 있는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf705-126">You use authorization to decide whether that user is allowed to access various parts of the system.</span></span>

<span data-ttu-id="cf705-127">이제 `Configure` 메서드에서 ASP.NET Core 파이프라인에 인증 및 권한 부여 미들웨어를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf705-127">Now add the authentication and authorization middleware to the ASP.NET Core pipeline in the `Configure` method:</span></span>

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

<span data-ttu-id="cf705-128">마지막으로, 보호할 모든 서비스 또는 메서드에 `[Authorize]` 특성을 적용 하 고 기본 `HttpContext`의 `User` 속성을 사용 하 여 권한을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf705-128">Finally, apply the `[Authorize]` attribute to any services or methods to be secured, and use the `User` property from the underlying `HttpContext` to verify permissions.</span></span>

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

## <a name="provide-call-credentials-in-the-client-application"></a><span data-ttu-id="cf705-129">클라이언트 응용 프로그램에서 호출 자격 증명 제공</span><span class="sxs-lookup"><span data-stu-id="cf705-129">Provide call credentials in the client application</span></span>

<span data-ttu-id="cf705-130">Id 서버에서 JWT 토큰을 가져온 후에는이 토큰을 사용 하 여 클라이언트에서 gRPC 호출을 다음과 같이 메타 데이터 헤더로 추가 하 여 인증할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf705-130">After you've obtained a JWT token from an identity server, you can use it to authenticate gRPC calls from the client by adding it as a metadata header on the call, as follows:</span></span>

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

<span data-ttu-id="cf705-131">이제 JWT 전달자 토큰을 호출 자격 증명으로 사용 하 여 gRPC 서비스의 보안을 설정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="cf705-131">Now you've secured your gRPC service by using JWT bearer tokens as call credentials.</span></span> <span data-ttu-id="cf705-132">[인증 및 권한 부여가 추가 된 포트폴리오 샘플 gRPC 응용 프로그램](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/PortfoliosSample/grpc/TraderSysAuth) 의 버전은 GitHub에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf705-132">A version of the [portfolios sample gRPC application with authentication and authorization added](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/PortfoliosSample/grpc/TraderSysAuth) is on GitHub.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="cf705-133">[이전](security.md)
>[다음](channel-credentials.md)</span><span class="sxs-lookup"><span data-stu-id="cf705-133">[Previous](security.md)
[Next](channel-credentials.md)</span></span>
