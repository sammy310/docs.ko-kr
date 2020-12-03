---
title: '호환성이 손상되는 변경: Kestrel: 지원되는 기본 TLS 프로토콜 버전 변경됨'
description: 'ASP.NET Core 5.0의 호환성이 손상되는 변경에 대해 알아보기. Kestrel: 지원되는 기본 TLS 프로토콜 버전 변경됨'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: d7018be7cc778560b7b9c65472d42d7e0fbf623d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759592"
---
# <a name="kestrel-default-supported-tls-protocol-versions-changed"></a><span data-ttu-id="ed5dd-103">Kestrel: 지원되는 기본 TLS 프로토콜 버전 변경됨</span><span class="sxs-lookup"><span data-stu-id="ed5dd-103">Kestrel: Default supported TLS protocol versions changed</span></span>

<span data-ttu-id="ed5dd-104">이제 Kestrel에서는 이전과 같이 TLS 1.1 및 TLS 1.2 프로토콜로 연결을 제한하는 대신 시스템의 기본 TLS 프로토콜 버전을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ed5dd-104">Kestrel now uses the system default TLS protocol versions rather than restricting connections to the TLS 1.1 and TLS 1.2 protocols like it did previously.</span></span>

<span data-ttu-id="ed5dd-105">이 변경을 통해 다음이 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="ed5dd-105">This change allows:</span></span>

* <span data-ttu-id="ed5dd-106">환경에서 지원하는 경우 기본적으로 TLS 1.3이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed5dd-106">TLS 1.3 to be used by default in environments that support it.</span></span>
* <span data-ttu-id="ed5dd-107">일부 환경(기본적으로 Windows Server 2016 등)에서는 TLS 1.0이 사용됩니다. 일반적으로 [바람직하지는 않습니다](/security/engineering/solving-tls1-problem).</span><span class="sxs-lookup"><span data-stu-id="ed5dd-107">TLS 1.0 to be used in some environments (such as Windows Server 2016 by default), which is usually [not desirable](/security/engineering/solving-tls1-problem).</span></span>

<span data-ttu-id="ed5dd-108">자세한 내용은 이슈 [dotnet/aspnetcore#22563](https://github.com/dotnet/aspnetcore/issues/22563)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ed5dd-108">For discussion, see issue [dotnet/aspnetcore#22563](https://github.com/dotnet/aspnetcore/issues/22563).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="ed5dd-109">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="ed5dd-109">Version introduced</span></span>

<span data-ttu-id="ed5dd-110">5.0 미리 보기 6</span><span class="sxs-lookup"><span data-stu-id="ed5dd-110">5.0 Preview 6</span></span>

## <a name="old-behavior"></a><span data-ttu-id="ed5dd-111">이전 동작</span><span class="sxs-lookup"><span data-stu-id="ed5dd-111">Old behavior</span></span>

<span data-ttu-id="ed5dd-112">Kestrel에서 기본적으로 연결에 TLS 1.1 또는 TLS 1.2를 사용해야 했습니다.</span><span class="sxs-lookup"><span data-stu-id="ed5dd-112">Kestrel required that connections use TLS 1.1 or TLS 1.2 by default.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="ed5dd-113">새 동작</span><span class="sxs-lookup"><span data-stu-id="ed5dd-113">New behavior</span></span>

<span data-ttu-id="ed5dd-114">Kestrel에서 운영 체제가 사용할 최적의 프로토콜을 선택하고 안전하지 않은 프로토콜을 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed5dd-114">Kestrel allows the operating system to choose the best protocol to use and to block insecure protocols.</span></span> <span data-ttu-id="ed5dd-115"><xref:Microsoft.AspNetCore.Server.Kestrel.Https.HttpsConnectionAdapterOptions.SslProtocols%2A?displayProperty=nameWithType>가 이제 기본적으로 `SslProtocols.Tls12 | SslProtocols.Tls11`이 아니라 `SslProtocols.None`으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed5dd-115"><xref:Microsoft.AspNetCore.Server.Kestrel.Https.HttpsConnectionAdapterOptions.SslProtocols%2A?displayProperty=nameWithType> now defaults to `SslProtocols.None` instead of `SslProtocols.Tls12 | SslProtocols.Tls11`.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="ed5dd-116">변경 이유</span><span class="sxs-lookup"><span data-stu-id="ed5dd-116">Reason for change</span></span>

<span data-ttu-id="ed5dd-117">TLS 1.3 및 향후 TLS 버전을 사용할 수 있게 되면 이를 기본적으로 지원하기 위해 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ed5dd-117">The change was made to support TLS 1.3 and future TLS versions by default as they become available.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="ed5dd-118">권장 조치</span><span class="sxs-lookup"><span data-stu-id="ed5dd-118">Recommended action</span></span>

<span data-ttu-id="ed5dd-119">앱에 특별한 이유가 없는 한 새 기본값을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed5dd-119">Unless your app has a specific reason not to, you should use the new defaults.</span></span> <span data-ttu-id="ed5dd-120">시스템이 보안 프로토콜만 허용하도록 구성되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ed5dd-120">Verify your system is configured to allow only secure protocols.</span></span>

<span data-ttu-id="ed5dd-121">이전 프로토콜을 사용하지 않도록 설정하려면 다음 작업 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="ed5dd-121">To disable older protocols, take one of the following actions:</span></span>

* <span data-ttu-id="ed5dd-122">시스템 전체에서 [Windows 명령](../../../../framework/network-programming/tls.md#configuring-schannel-protocols-in-the-windows-registry)을 사용하여 TLS 1.0과 같은 이전 프로토콜을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ed5dd-122">Disable older protocols, such as TLS 1.0, system-wide with the [Windows instructions](../../../../framework/network-programming/tls.md#configuring-schannel-protocols-in-the-windows-registry).</span></span> <span data-ttu-id="ed5dd-123">현재는 모든 Windows 버전에서 기본적으로 사용하도록 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed5dd-123">It's currently enabled by default on all Windows versions.</span></span>
* <span data-ttu-id="ed5dd-124">다음과 같이 코드로 지원할 프로토콜을 수동으로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ed5dd-124">Manually select which protocols you want to support in code as follows:</span></span>

    ```csharp
    using System.Security.Authentication;
    using Microsoft.AspNetCore.Hosting;
    using Microsoft.Extensions.Hosting;

    public class Program
    {
        public static void Main(string[] args) =>
            CreateHostBuilder(args).Build().Run();

        public static IHostBuilder CreateHostBuilder(string[] args) =>
            Host.CreateDefaultBuilder(args)
                .ConfigureWebHostDefaults(webBuilder =>
                {
                    webBuilder.UseKestrel(kestrelOptions =>
                    {
                        kestrelOptions.ConfigureHttpsDefaults(httpsOptions =>
                        {
                            httpsOptions.SslProtocols = SslProtocols.Tls12 | SslProtocols.Tls13;
                        });
                    });

                    webBuilder.UseStartup<Startup>();
                });
    }
    ```

<span data-ttu-id="ed5dd-125">아쉽게도 특정 프로토콜을 제외하는 API는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ed5dd-125">Unfortunately, there's no API to exclude specific protocols.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="ed5dd-126">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="ed5dd-126">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Server.Kestrel.Https.HttpsConnectionAdapterOptions.SslProtocols%2A?displayProperty=nameWithType>

<!--

### Category

ASP.NET Core

### Affected APIs

`P:Microsoft.AspNetCore.Server.Kestrel.Https.HttpsConnectionAdapterOptions.SslProtocols`

-->
