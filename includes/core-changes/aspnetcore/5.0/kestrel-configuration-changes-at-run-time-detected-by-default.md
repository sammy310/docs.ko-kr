---
ms.openlocfilehash: d00b8ecaa61b358e062d85a2b68ca8a95cada442
ms.sourcegitcommit: 1eae045421d9ea2bfc82aaccfa5b1ff1b8c9e0e4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "84803252"
---
### <a name="kestrel-configuration-changes-at-run-time-detected-by-default"></a><span data-ttu-id="7d094-101">Kestrel: 런타임의 구성 변경 내용이 기본적으로 검색됨</span><span class="sxs-lookup"><span data-stu-id="7d094-101">Kestrel: Configuration changes at run time detected by default</span></span>

<span data-ttu-id="7d094-102">이제 Kestrel에서는 런타임에 수행된 프로젝트 `IConfiguration` 인스턴스 `Kestrel` 섹션(예: *appsettings.json*)의 변경 내용에 반응합니다.</span><span class="sxs-lookup"><span data-stu-id="7d094-102">Kestrel now reacts to changes made to the `Kestrel` section of the project's `IConfiguration` instance (for example, *appsettings.json*) at run time.</span></span> <span data-ttu-id="7d094-103">*appsettings.json*을 사용하여 Kestrel을 구성하는 방법에 대한 자세한 내용은 [엔드포인트 구성](/aspnet/core/fundamentals/servers/kestrel#endpoint-configuration)의 *appsettings.json* 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7d094-103">To learn more about how to configure Kestrel using *appsettings.json*, see the *appsettings.json* example in [Endpoint configuration](/aspnet/core/fundamentals/servers/kestrel#endpoint-configuration).</span></span>

<span data-ttu-id="7d094-104">Kestrel은 이러한 구성 변경 내용에 반응하기 위해 필요에 따라 엔드포인트를 바인딩, 바인딩 해제, 다시 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="7d094-104">Kestrel will bind, unbind, and rebind endpoints as necessary to react to these configuration changes.</span></span>

<span data-ttu-id="7d094-105">자세한 내용은 이슈 [dotnet/aspnetcore#22807](https://github.com/dotnet/aspnetcore/issues/22807)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7d094-105">For discussion, see issue [dotnet/aspnetcore#22807](https://github.com/dotnet/aspnetcore/issues/22807).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="7d094-106">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="7d094-106">Version introduced</span></span>

<span data-ttu-id="7d094-107">5.0 미리 보기 7</span><span class="sxs-lookup"><span data-stu-id="7d094-107">5.0 Preview 7</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="7d094-108">이전 동작</span><span class="sxs-lookup"><span data-stu-id="7d094-108">Old behavior</span></span>

<span data-ttu-id="7d094-109">ASP.NET Core 5.0 미리 보기 6 이전에는 Kestrel에서 런타임에 구성을 변경할 수 없었습니다.</span><span class="sxs-lookup"><span data-stu-id="7d094-109">Before ASP.NET Core 5.0 Preview 6, Kestrel didn't support changing configuration at run time.</span></span>

<span data-ttu-id="7d094-110">ASP.NET Core 5.0 미리 보기 6에서는 런타임의 구성 변경 내용에 반응하는 현재의 기본 동작을 옵트인할 수 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="7d094-110">In ASP.NET Core 5.0 Preview 6, you could opt into the now-default behavior of reacting to configuration changes at run time.</span></span> <span data-ttu-id="7d094-111">옵트인하려면 Kestrel의 구성을 수동으로 바인딩해야 했습니다.</span><span class="sxs-lookup"><span data-stu-id="7d094-111">Opting in required binding Kestrel's configuration manually:</span></span>

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

#### <a name="new-behavior"></a><span data-ttu-id="7d094-112">새 동작</span><span class="sxs-lookup"><span data-stu-id="7d094-112">New behavior</span></span>

<span data-ttu-id="7d094-113">Kestrel은 기본적으로 런타임의 구성 변경 내용에 반응합니다.</span><span class="sxs-lookup"><span data-stu-id="7d094-113">Kestrel reacts to configuration changes at run time by default.</span></span> <span data-ttu-id="7d094-114">이러한 변경을 지원하기 위해 <xref:Microsoft.Extensions.Hosting.GenericHostBuilderExtensions.ConfigureWebHostDefaults%2A>는 기본적으로 `KestrelServerOptions.Configure(IConfiguration, bool)`를 `reloadOnChange: true`로 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="7d094-114">To support that change, <xref:Microsoft.Extensions.Hosting.GenericHostBuilderExtensions.ConfigureWebHostDefaults%2A> calls `KestrelServerOptions.Configure(IConfiguration, bool)` with `reloadOnChange: true` by default.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="7d094-115">변경 이유</span><span class="sxs-lookup"><span data-stu-id="7d094-115">Reason for change</span></span>

<span data-ttu-id="7d094-116">서버를 완전히 다시 시작하지 않고도 런타임에 엔드포인트 재구성을 지원하도록 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7d094-116">The change was made to support endpoint reconfiguration at run time without completely restarting the server.</span></span> <span data-ttu-id="7d094-117">전체 서버를 다시 시작할 때와 달리 변경되지 않은 엔드포인트는 일시적으로라도 바인딩 해제되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7d094-117">Unlike with a full server restart, unchanged endpoints aren't unbound even temporarily.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="7d094-118">권장 조치</span><span class="sxs-lookup"><span data-stu-id="7d094-118">Recommended action</span></span>

* <span data-ttu-id="7d094-119">대부분의 시나리오에서 Kestrel의 기본 구성 섹션이 런타임에 변경되지 않으므로 이 변경 내용에 따른 영향이 없으며 아무 작업도 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7d094-119">For most scenarios in which Kestrel's default configuration section doesn't change at run time, this change has no impact and no action is needed.</span></span>
* <span data-ttu-id="7d094-120">Kestrel의 기본 구성 섹션이 런타임에 변경되고 Kestrel이 이에 반응해야 하는 시나리오에서는 기본적으로 이와 같이 동작합니다.</span><span class="sxs-lookup"><span data-stu-id="7d094-120">For scenarios in which Kestrel's default configuration section does change at run time and Kestrel should react to it, this is now the default behavior.</span></span>
* <span data-ttu-id="7d094-121">Kestrel의 기본 구성 섹션이 런타임에 변경되지만 Kestrel이 이에 반응하면 안 되는 시나리오에서는 다음과 같이 옵트아웃할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d094-121">For scenarios in which Kestrel's default configuration section changes at run time and Kestrel shouldn't react to it, you can opt out as follows:</span></span>

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

<span data-ttu-id="7d094-122">**참고:**</span><span class="sxs-lookup"><span data-stu-id="7d094-122">**Notes:**</span></span>

<span data-ttu-id="7d094-123">이 변경으로 `KestrelServerOptions.Configure(IConfiguration)` 오버로드의 동작은 수정되지 않고 계속 기본적으로 `reloadOnChange: false` 동작으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d094-123">This change doesn't modify the behavior of the `KestrelServerOptions.Configure(IConfiguration)` overload, which still defaults to the `reloadOnChange: false` behavior.</span></span>

<span data-ttu-id="7d094-124">구성 소스에서 다시 로드를 지원하는지 확인하는 것도 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="7d094-124">It's also important to make sure the configuration source supports reloading.</span></span> <span data-ttu-id="7d094-125">JSON 소스의 경우 `AddJsonFile(path, reloadOnChange: true)`를 호출하여 다시 로드를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="7d094-125">For JSON sources, reloading is configured by calling `AddJsonFile(path, reloadOnChange: true)`.</span></span> <span data-ttu-id="7d094-126">*appsettings.json* 및 *appsettings.{Environment}.json*의 경우 다시 로드가 이미 기본적으로 구성되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d094-126">Reloading is already configured by default for *appsettings.json* and *appsettings.{Environment}.json*.</span></span>

#### <a name="category"></a><span data-ttu-id="7d094-127">범주</span><span class="sxs-lookup"><span data-stu-id="7d094-127">Category</span></span>

<span data-ttu-id="7d094-128">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="7d094-128">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="7d094-129">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="7d094-129">Affected APIs</span></span>

<xref:Microsoft.Extensions.Hosting.GenericHostBuilderExtensions.ConfigureWebHostDefaults%2A?displayProperty=nameWithType>

<!-- 

#### Affected APIs

`Overload:Microsoft.Extensions.Hosting.GenericHostBuilderExtensions.ConfigureWebHostDefaults`

-->
