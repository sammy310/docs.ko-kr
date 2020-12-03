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
# <a name="kestrel-default-supported-tls-protocol-versions-changed"></a>Kestrel: 지원되는 기본 TLS 프로토콜 버전 변경됨

이제 Kestrel에서는 이전과 같이 TLS 1.1 및 TLS 1.2 프로토콜로 연결을 제한하는 대신 시스템의 기본 TLS 프로토콜 버전을 사용합니다.

이 변경을 통해 다음이 가능합니다.

* 환경에서 지원하는 경우 기본적으로 TLS 1.3이 사용됩니다.
* 일부 환경(기본적으로 Windows Server 2016 등)에서는 TLS 1.0이 사용됩니다. 일반적으로 [바람직하지는 않습니다](/security/engineering/solving-tls1-problem).

자세한 내용은 이슈 [dotnet/aspnetcore#22563](https://github.com/dotnet/aspnetcore/issues/22563)을 참조하세요.

## <a name="version-introduced"></a>도입된 버전

5.0 미리 보기 6

## <a name="old-behavior"></a>이전 동작

Kestrel에서 기본적으로 연결에 TLS 1.1 또는 TLS 1.2를 사용해야 했습니다.

## <a name="new-behavior"></a>새 동작

Kestrel에서 운영 체제가 사용할 최적의 프로토콜을 선택하고 안전하지 않은 프로토콜을 차단할 수 있습니다. <xref:Microsoft.AspNetCore.Server.Kestrel.Https.HttpsConnectionAdapterOptions.SslProtocols%2A?displayProperty=nameWithType>가 이제 기본적으로 `SslProtocols.Tls12 | SslProtocols.Tls11`이 아니라 `SslProtocols.None`으로 설정됩니다.

## <a name="reason-for-change"></a>변경 이유

TLS 1.3 및 향후 TLS 버전을 사용할 수 있게 되면 이를 기본적으로 지원하기 위해 변경되었습니다.

## <a name="recommended-action"></a>권장 조치

앱에 특별한 이유가 없는 한 새 기본값을 사용해야 합니다. 시스템이 보안 프로토콜만 허용하도록 구성되어 있는지 확인합니다.

이전 프로토콜을 사용하지 않도록 설정하려면 다음 작업 중 하나를 수행합니다.

* 시스템 전체에서 [Windows 명령](../../../../framework/network-programming/tls.md#configuring-schannel-protocols-in-the-windows-registry)을 사용하여 TLS 1.0과 같은 이전 프로토콜을 사용하지 않도록 설정합니다. 현재는 모든 Windows 버전에서 기본적으로 사용하도록 설정되어 있습니다.
* 다음과 같이 코드로 지원할 프로토콜을 수동으로 선택합니다.

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

아쉽게도 특정 프로토콜을 제외하는 API는 없습니다.

## <a name="affected-apis"></a>영향을 받는 API

<xref:Microsoft.AspNetCore.Server.Kestrel.Https.HttpsConnectionAdapterOptions.SslProtocols%2A?displayProperty=nameWithType>

<!--

### Category

ASP.NET Core

### Affected APIs

`P:Microsoft.AspNetCore.Server.Kestrel.Https.HttpsConnectionAdapterOptions.SslProtocols`

-->
