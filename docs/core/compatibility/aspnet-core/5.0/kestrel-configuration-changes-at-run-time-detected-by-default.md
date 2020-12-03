---
title: '호환성이 손상되는 변경: Kestrel: 런타임의 구성 변경 내용이 기본적으로 검색됨'
description: 'ASP.NET Core 5.0의 호환성이 손상되는 변경에 대해 알아보기. Kestrel: 런타임의 구성 변경 내용이 기본적으로 검색됨'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: 2e879f020dd108baa14fa8ff67dee7b948209faf
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759599"
---
# <a name="kestrel-configuration-changes-at-run-time-detected-by-default"></a>Kestrel: 런타임의 구성 변경 내용이 기본적으로 검색됨

이제 Kestrel에서는 런타임에 수행된 프로젝트 `IConfiguration` 인스턴스 `Kestrel` 섹션(예: *appsettings.json*)의 변경 내용에 반응합니다. *appsettings.json* 을 사용하여 Kestrel을 구성하는 방법에 대한 자세한 내용은 [엔드포인트 구성](/aspnet/core/fundamentals/servers/kestrel#endpoint-configuration)의 *appsettings.json* 예제를 참조하세요.

Kestrel은 이러한 구성 변경 내용에 반응하기 위해 필요에 따라 엔드포인트를 바인딩, 바인딩 해제, 다시 바인딩합니다.

자세한 내용은 이슈 [dotnet/aspnetcore#22807](https://github.com/dotnet/aspnetcore/issues/22807)을 참조하세요.

## <a name="version-introduced"></a>도입된 버전

5.0 미리 보기 7

## <a name="old-behavior"></a>이전 동작

ASP.NET Core 5.0 미리 보기 6 이전에는 Kestrel에서 런타임에 구성을 변경할 수 없었습니다.

ASP.NET Core 5.0 미리 보기 6에서는 런타임의 구성 변경 내용에 반응하는 현재의 기본 동작을 옵트인할 수 있었습니다. 옵트인하려면 Kestrel의 구성을 수동으로 바인딩해야 했습니다.

```csharp
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
                webBuilder.UseKestrel((builderContext, kestrelOptions) =>
                {
                    kestrelOptions.Configure(
                        builderContext.Configuration.GetSection("Kestrel"), reloadOnChange: true);
                });

                webBuilder.UseStartup<Startup>();
            });
}
```

## <a name="new-behavior"></a>새 동작

Kestrel은 기본적으로 런타임의 구성 변경 내용에 반응합니다. 이러한 변경을 지원하기 위해 <xref:Microsoft.Extensions.Hosting.GenericHostBuilderExtensions.ConfigureWebHostDefaults%2A>는 기본적으로 `KestrelServerOptions.Configure(IConfiguration, bool)`를 `reloadOnChange: true`로 호출합니다.

## <a name="reason-for-change"></a>변경 이유

서버를 완전히 다시 시작하지 않고도 런타임에 엔드포인트 재구성을 지원하도록 변경되었습니다. 전체 서버를 다시 시작할 때와 달리 변경되지 않은 엔드포인트는 일시적으로라도 바인딩 해제되지 않습니다.

## <a name="recommended-action"></a>권장 조치

* 대부분의 시나리오에서 Kestrel의 기본 구성 섹션이 런타임에 변경되지 않으므로 이 변경 내용에 따른 영향이 없으며 아무 작업도 필요하지 않습니다.
* Kestrel의 기본 구성 섹션이 런타임에 변경되고 Kestrel이 이에 반응해야 하는 시나리오에서는 기본적으로 이와 같이 동작합니다.
* Kestrel의 기본 구성 섹션이 런타임에 변경되지만 Kestrel이 이에 반응하면 안 되는 시나리오에서는 다음과 같이 옵트아웃할 수 있습니다.

    ```csharp
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
                    webBuilder.UseKestrel((builderContext, kestrelOptions) =>
                    {
                        kestrelOptions.Configure(
                            builderContext.Configuration.GetSection("Kestrel"), reloadOnChange: false);
                    });

                    webBuilder.UseStartup<Startup>();
                });
    }
    ```

**참고:**

이 변경으로 `KestrelServerOptions.Configure(IConfiguration)` 오버로드의 동작은 수정되지 않고 계속 기본적으로 `reloadOnChange: false` 동작으로 설정됩니다.

구성 소스에서 다시 로드를 지원하는지 확인하는 것도 중요합니다. JSON 소스의 경우 `AddJsonFile(path, reloadOnChange: true)`를 호출하여 다시 로드를 구성합니다. *appsettings.json* 및 *appsettings.{Environment}.json* 의 경우 다시 로드가 이미 기본적으로 구성되어 있습니다.

## <a name="affected-apis"></a>영향을 받는 API

<xref:Microsoft.Extensions.Hosting.GenericHostBuilderExtensions.ConfigureWebHostDefaults%2A?displayProperty=nameWithType>

<!--

### Category

ASP.NET Core

### Affected APIs

`Overload:Microsoft.Extensions.Hosting.GenericHostBuilderExtensions.ConfigureWebHostDefaults`

-->
