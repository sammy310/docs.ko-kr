---
title: 채널 자격 증명-WCF 개발자를 위한 gRPC
description: ASP.NET Core 3.0에서 gRPC 채널 자격 증명을 구현 하 고 사용 하는 방법입니다.
ms.date: 12/15/2020
ms.openlocfilehash: 3663bbf061156db957241e2a32dbb9c64562ade2
ms.sourcegitcommit: 655f8a16c488567dfa696fc0b293b34d3c81e3df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/06/2021
ms.locfileid: "97938639"
---
# <a name="channel-credentials"></a><span data-ttu-id="e3373-103">채널 자격 증명</span><span class="sxs-lookup"><span data-stu-id="e3373-103">Channel credentials</span></span>

<span data-ttu-id="e3373-104">이름에서 알 수 있듯이 채널 자격 증명은 기본 gRPC 채널에 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3373-104">As the name implies, channel credentials are attached to the underlying gRPC channel.</span></span> <span data-ttu-id="e3373-105">채널 자격 증명의 표준 형식은 클라이언트 인증서 인증을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3373-105">The standard form of channel credentials uses client certificate authentication.</span></span> <span data-ttu-id="e3373-106">이 프로세스에서 클라이언트는 연결을 만들 때 TLS 인증서를 제공 하 고 서버는이 인증서를 확인 한 후에 호출을 수행 하도록 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3373-106">In this process, the client provides a TLS certificate when it's making the connection, and then the server verifies this certificate before allowing any calls to be made.</span></span>

<span data-ttu-id="e3373-107">채널 자격 증명과 통화 자격 증명을 결합 하 여 gRPC 서비스에 대 한 포괄적인 보안을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3373-107">You can combine channel credentials with call credentials to provide comprehensive security for a gRPC service.</span></span> <span data-ttu-id="e3373-108">채널 자격 증명은 클라이언트 응용 프로그램에서 서비스에 액세스할 수 있음을 입증 하 고 호출 자격 증명은 클라이언트 응용 프로그램을 사용 하는 사용자에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3373-108">The channel credentials prove that the client application is allowed to access the service, and the call credentials provide information about the person who is using the client application.</span></span>

<span data-ttu-id="e3373-109">클라이언트 인증서 인증은 ASP.NET Core에 대해 작동 하는 것과 동일한 방식으로 gRPC에 대해 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3373-109">Client certificate authentication works for gRPC the same way it works for ASP.NET Core.</span></span> <span data-ttu-id="e3373-110">자세한 내용은 [ASP.NET Core에서 인증서 인증 구성](/aspnet/core/security/authentication/certauth)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e3373-110">For more information, see [Configure certificate authentication in ASP.NET Core](/aspnet/core/security/authentication/certauth).</span></span>

<span data-ttu-id="e3373-111">개발 목적으로 자체 서명 된 인증서를 사용할 수 있지만 프로덕션의 경우 신뢰할 수 있는 기관에서 서명 된 적절 한 HTTPS 인증서를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3373-111">For development purposes you can use a self-signed certificate, but for production you should use a proper HTTPS certificate signed by a trusted authority.</span></span>

## <a name="add-certificate-authentication-to-the-server"></a><span data-ttu-id="e3373-112">서버에 인증서 인증 추가</span><span class="sxs-lookup"><span data-stu-id="e3373-112">Add certificate authentication to the server</span></span>

<span data-ttu-id="e3373-113">호스트 수준 (예: Kestrel 서버) 및 ASP.NET Core 파이프라인에서 인증서 인증을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3373-113">Configure certificate authentication both at the host level (for example, on the Kestrel server), and in the ASP.NET Core pipeline.</span></span>

### <a name="configure-certificate-validation-on-kestrel"></a><span data-ttu-id="e3373-114">Kestrel에서 인증서 유효성 검사 구성</span><span class="sxs-lookup"><span data-stu-id="e3373-114">Configure certificate validation on Kestrel</span></span>

<span data-ttu-id="e3373-115">클라이언트 인증서를 요구 하도록 Kestrel (ASP.NET Core HTTP 서버)을 구성 하 고, 들어오는 연결을 수락 하기 전에 제공 된 인증서의 일부 유효성 검사를 수행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3373-115">You can configure Kestrel (the ASP.NET Core HTTP server) to require a client certificate, and optionally to carry out some validation of the supplied certificate, before accepting incoming connections.</span></span> <span data-ttu-id="e3373-116">이 구성은 `CreateWebHostBuilder` 가 아닌 클래스의 메서드에서 지정 `Program` `Startup` 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3373-116">You specify this configuration in the `CreateWebHostBuilder` method of the `Program` class, rather than in `Startup`.</span></span>

```csharp
public static IHostBuilder CreateHostBuilder(string[] args) =>
    Host.CreateDefaultBuilder(args)
        .ConfigureWebHostDefaults(webBuilder =>
        {
            var serverCert = ObtainServerCertificate();
            webBuilder.UseStartup<Startup>()
                .ConfigureKestrel(kestrelServerOptions => {
                    kestrelServerOptions.ConfigureHttpsDefaults(opt =>
                    {
                        opt.ClientCertificateMode = ClientCertificateMode.RequireCertificate;

                        // Verify that client certificate was issued by same CA as server certificate
                        opt.ClientCertificateValidation = (certificate, chain, errors) =>
                            certificate.Issuer == serverCert.Issuer;
                    });
                });
        });

```

<span data-ttu-id="e3373-117">`ClientCertificateMode.RequireCertificate`설정으로 인해 Kestrel이 클라이언트 인증서를 제공 하지 않는 연결 요청을 즉시 거부 하지만이 설정은 자체적으로 제공 된 인증서의 유효성을 검사 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e3373-117">The `ClientCertificateMode.RequireCertificate` setting causes Kestrel to immediately reject any connection request that doesn't provide a client certificate, but this setting by itself won't validate a certificate that is provided.</span></span> <span data-ttu-id="e3373-118">`ClientCertificateValidation`ASP.NET Core 파이프라인이 사용 되기 전에 Kestrel을 사용 하 여 연결 된 시점에 클라이언트 인증서의 유효성을 검사할 수 있도록 콜백을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3373-118">Add the `ClientCertificateValidation` callback to enable Kestrel to validate the client certificate at the point the connection is made, before the ASP.NET Core pipeline is engaged.</span></span> <span data-ttu-id="e3373-119">이 경우 콜백은 서버 인증서와 동일한 *인증 기관* 에서 발급 된 것을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3373-119">(In this case, the callback ensures that it was issued by the same *Certificate Authority* as the server certificate.)</span></span>

### <a name="add-aspnet-core-certificate-authentication"></a><span data-ttu-id="e3373-120">ASP.NET Core 인증서 인증 추가</span><span class="sxs-lookup"><span data-stu-id="e3373-120">Add ASP.NET Core certificate authentication</span></span>

<span data-ttu-id="e3373-121">[AspNetCore](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.Certificate) NuGet 패키지는 인증서 인증을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3373-121">The [Microsoft.AspNetCore.Authentication.Certificate](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.Certificate) NuGet package provides certificate authentication.</span></span>

<span data-ttu-id="e3373-122">메서드에 인증서 인증 서비스를 추가 `ConfigureServices` 하 고 메서드의 ASP.NET Core 파이프라인에 인증 및 권한 부여를 추가 `Configure` 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3373-122">Add the certificate authentication service in the `ConfigureServices` method, and add authentication and authorization to the ASP.NET Core pipeline in the `Configure` method.</span></span>

```csharp
public class Startup
{
    private readonly bool _isDevelopment;

    public Startup(IWebHostEnvironment env)
    {
        _isDevelopment = env.IsDevelopment();
    }

    public void ConfigureServices(IServiceCollection services)
    {
        services.AddAuthentication(CertificateAuthenticationDefaults.AuthenticationScheme)
            .AddCertificate(options =>
            {
                if (_isDevelopment)
                {
                    // DO NOT DO THIS IN PRODUCTION!
                    options.RevocationMode = X509RevocationMode.NoCheck;
                }
            });
        services.AddAuthorization();
        services.AddGrpc();
    }

    public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
    {
        app.UseRouting();

        app.UseAuthentication();
        app.UseAuthorization();

        app.UseEndpoints(endpoints => { endpoints.MapGrpcService<GreeterService>(); });
    }
}
```

## <a name="provide-channel-credentials-in-the-client-application"></a><span data-ttu-id="e3373-123">클라이언트 응용 프로그램에서 채널 자격 증명 제공</span><span class="sxs-lookup"><span data-stu-id="e3373-123">Provide channel credentials in the client application</span></span>

<span data-ttu-id="e3373-124">패키지를 사용 하 여 연결에 사용 되는에 제공 되는 `Grpc.Net.Client` 인스턴스에서 인증서를 구성 <xref:System.Net.Http.HttpClient> `GrpcChannel` 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3373-124">With the `Grpc.Net.Client` package, you configure certificates on an <xref:System.Net.Http.HttpClient> instance that is provided to the `GrpcChannel` used for the connection.</span></span>

```csharp
class Program
{
    static async Task Main(string[] args)
    {
        // Assume path to a client .pfx file and password are passed from command line
        // On Windows this would probably be a reference to the Certificate Store
        var cert = new X509Certificate2(args[0], args[1]);

        var handler = new HttpClientHandler();
        handler.ClientCertificates.Add(cert);
        var httpClient = new HttpClient(handler);

        var channel = GrpcChannel.ForAddress("https://localhost:5001/", new GrpcChannelOptions
        {
            HttpClient = httpClient
        });

        var grpc = new Greeter.GreeterClient(channel);
        var response = await grpc.SayHelloAsync(new HelloRequest { Name = "Bob" });
        System.Console.WriteLine(response.Message);
    }
}
```

## <a name="combine-channelcredentials-and-callcredentials"></a><span data-ttu-id="e3373-125">ChannelCredentials 및 CallCredentials 결합</span><span class="sxs-lookup"><span data-stu-id="e3373-125">Combine ChannelCredentials and CallCredentials</span></span>

<span data-ttu-id="e3373-126">인증서와 토큰 인증을 모두 사용 하도록 서버를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3373-126">You can configure your server to use both certificate and token authentication.</span></span> <span data-ttu-id="e3373-127">이렇게 하려면 Kestrel 서버에 인증서 변경 내용을 적용 하 고 ASP.NET Core JWT 전달자 미들웨어를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3373-127">To do this, apply the certificate changes to the Kestrel server, and use the JWT bearer middleware in ASP.NET Core.</span></span>

<span data-ttu-id="e3373-128">클라이언트에서 및를 모두 제공 하려면 메서드를 사용 하 여 `ChannelCredentials` `CallCredentials` `ChannelCredentials.Create` 호출 자격 증명을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3373-128">To provide both `ChannelCredentials` and `CallCredentials` on the client, use the `ChannelCredentials.Create` method to apply the call credentials.</span></span> <span data-ttu-id="e3373-129">인스턴스를 사용 하 여 인증서 인증을 적용 해야 <xref:System.Net.Http.HttpClient> 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3373-129">You still need to apply certificate authentication by using the <xref:System.Net.Http.HttpClient> instance.</span></span> <span data-ttu-id="e3373-130">생성자에 인수를 전달 하면 `SslCredentials` 내부 클라이언트 코드에서 예외를 throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3373-130">If you pass any arguments to the `SslCredentials` constructor, the internal client code throws an exception.</span></span> <span data-ttu-id="e3373-131">패키지 `SslCredentials` `Grpc.Net.Client` `Create` 와의 호환성을 유지 하기 위해 매개 변수는 패키지의 메서드에만 포함 됩니다 `Grpc.Core` .</span><span class="sxs-lookup"><span data-stu-id="e3373-131">The `SslCredentials` parameter is only included in the `Grpc.Net.Client` package's `Create` method to maintain compatibility with the `Grpc.Core` package.</span></span>

```csharp
var handler = new HttpClientHandler();
handler.ClientCertificates.Add(cert);

var httpClient = new HttpClient(handler);

var callCredentials = CallCredentials.FromInterceptor(((context, metadata) =>
    {
        metadata.Add("Authorization", $"Bearer {_token}");
    }));

var channelCredentials = ChannelCredentials.Create(new SslCredentials(), callCredentials);

var channel = GrpcChannel.ForAddress("https://localhost:5001/", new GrpcChannelOptions
{
    HttpClient = httpClient,
    Credentials = channelCredentials
});

var grpc = new Portfolios.PortfoliosClient(channel);
```

> [!TIP]
> <span data-ttu-id="e3373-132">`ChannelCredentials.Create`인증서 인증 없이 클라이언트에 대해 메서드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3373-132">You can use the `ChannelCredentials.Create` method for a client without certificate authentication.</span></span> <span data-ttu-id="e3373-133">채널에 대 한 모든 호출에서 토큰 자격 증명을 전달 하는 유용한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="e3373-133">This is a useful way to pass token credentials with every call made on the channel.</span></span>

<span data-ttu-id="e3373-134">[인증서 인증을 추가한 FullStockTicker 샘플 gRPC 응용 프로그램](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/grpc/FullStockTickerAuth/FullStockTicker) 의 버전은 GitHub에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3373-134">A version of the [FullStockTicker sample gRPC application with certificate authentication added](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/grpc/FullStockTickerAuth/FullStockTicker) is on GitHub.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="e3373-135">[이전](call-credentials.md)
>[다음](encryption.md)</span><span class="sxs-lookup"><span data-stu-id="e3373-135">[Previous](call-credentials.md)
[Next](encryption.md)</span></span>
