---
title: .NET Core 2.2의 새로운 기능
description: .NET Core 2.2에 있는 새로운 기능에 대해 알아봅니다.
dev_langs:
- csharp
- vb
ms.date: 12/04/2018
ms.openlocfilehash: 64cb561acd72ff5d4a11fcae7ce59eaad750f74e
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2020
ms.locfileid: "81644367"
---
# <a name="whats-new-in-net-core-22"></a><span data-ttu-id="83384-103">.NET Core 2.2의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="83384-103">What's new in .NET Core 2.2</span></span>

<span data-ttu-id="83384-104">.NET Core 2.2에는 애플리케이션 배포, 런타임 서비스에 대한 이벤트 처리, Azure SQL 데이터베이스에 인증, JIT 컴파일러 성능 및 `Main` 메서드 실행 전에 코드 삽입 개선 사항이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83384-104">.NET Core 2.2 includes enhancements in application deployment, event handling for runtime services, authentication to Azure SQL databases, JIT compiler performance, and code injection prior to the execution of the `Main` method.</span></span>

## <a name="new-deployment-mode"></a><span data-ttu-id="83384-105">새 배포 모드</span><span class="sxs-lookup"><span data-stu-id="83384-105">New deployment mode</span></span>

<span data-ttu-id="83384-106">.NET Core 2.2부터 **.dll** 파일 대신 **.exe** 파일인 [프레임워크 종속 실행 파일](../deploying/index.md#publish-runtime-dependent)을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83384-106">Starting with .NET Core 2.2, you can deploy [framework-dependent executables](../deploying/index.md#publish-runtime-dependent), which are **.exe** files instead of **.dll** files.</span></span> <span data-ttu-id="83384-107">프레임워크 종속 배포와 기능이 유사한 FDE(프레임워크 종속 실행 파일)를 실행하려면 여전히 공유 시스템 수준의 .NET Core 버전이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83384-107">Functionally similar to framework-dependent deployments, framework-dependent executables (FDE) still rely on the presence of a shared system-wide version of .NET Core to run.</span></span> <span data-ttu-id="83384-108">앱에는 코드와 타사 종속성만 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="83384-108">Your app contains only your code and any third-party dependencies.</span></span> <span data-ttu-id="83384-109">프레임워크 종속 배포와 달리 FDE는 플랫폼에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="83384-109">Unlike framework-dependent deployments, FDEs are platform-specific.</span></span>

<span data-ttu-id="83384-110">이 새로운 배포 모드는 라이브러리 대신 실행 파일을 빌드하는 고유한 장점이 있으므로, `dotnet`을 먼저 호출하지 않고 앱을 직접 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83384-110">This new deployment mode has the distinct advantage of building an executable instead of a library, which means you can run your app directly without invoking `dotnet` first.</span></span>

## <a name="core"></a><span data-ttu-id="83384-111">코어</span><span class="sxs-lookup"><span data-stu-id="83384-111">Core</span></span>

<span data-ttu-id="83384-112">**런타임 서비스에서 이벤트 처리**</span><span class="sxs-lookup"><span data-stu-id="83384-112">**Handling events in runtime services**</span></span>

<span data-ttu-id="83384-113">GC, JIT, ThreadPool 등의 런타임 서비스에 대한 애플리케이션 사용을 자주 모니터링하여 해당 서비스가 애플리케이션에 미치는 영향을 파악하고 싶을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83384-113">You may often want to monitor your application's use of runtime services, such as the GC, JIT, and ThreadPool, to understand how they impact your application.</span></span><span data-ttu-id="83384-114"> Windows 시스템에서 이 작업은 일반적으로 현재 프로세스의 ETW 이벤트를 모니터링하여 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="83384-114"> On Windows systems, this is commonly done by monitoring the ETW events of the current process.</span></span><span data-ttu-id="83384-115"> 이 방법을 계속 사용할 수도 있지만, 낮은 권한 환경이나 Linux 또는 macOS에서 실행하는 경우 항상 ETW를 사용할 수 있는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="83384-115"> While this continues to work well, it's not always possible to use ETW if you're running in a low-privilege environment or on Linux or macOS.</span></span>

<span data-ttu-id="83384-116">.NET Core 2.2부터 이제 <xref:System.Diagnostics.Tracing.EventListener?displayProperty=nameWithType> 클래스를 사용하여 CoreCLR 이벤트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83384-116">Starting with .NET Core 2.2, CoreCLR events can now be consumed using the <xref:System.Diagnostics.Tracing.EventListener?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="83384-117">이러한 이벤트는 GC, JIT, ThreadPool 및 interop와 같은 런타임 서비스의 동작을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="83384-117">These events describe the behavior of such runtime services as GC, JIT, ThreadPool, and interop.</span></span> <span data-ttu-id="83384-118">이는 CoreCLR ETW 공급자의 일부로 공개되는 동일한 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="83384-118">These are the same events that are exposed as part of the CoreCLR ETW provider.</span></span><span data-ttu-id="83384-119">  이 공급자를 통해 애플리케이션은 이러한 이벤트를 이용하거나, 전송 메커니즘을 사용하여 원격 분석 집계 서비스에 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83384-119">  This allows for applications to consume these events or use a transport mechanism to send them to a telemetry aggregation service.</span></span> <span data-ttu-id="83384-120">다음 코드 샘플에서 이벤트 구독 방법을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83384-120">You can see how to subscribe to events in the following code sample:</span></span>

```csharp
internal sealed class SimpleEventListener : EventListener
{
    // Called whenever an EventSource is created.
    protected override void OnEventSourceCreated(EventSource eventSource)
    {
        // Watch for the .NET runtime EventSource and enable all of its events.
        if (eventSource.Name.Equals("Microsoft-Windows-DotNETRuntime"))
        {
            EnableEvents(eventSource, EventLevel.Verbose, (EventKeywords)(-1));
        }
    }

    // Called whenever an event is written.
    protected override void OnEventWritten(EventWrittenEventArgs eventData)
    {
        // Write the contents of the event to the console.
        Console.WriteLine($"ThreadID = {eventData.OSThreadId} ID = {eventData.EventId} Name = {eventData.EventName}");
        for (int i = 0; i < eventData.Payload.Count; i++)
        {
            string payloadString = eventData.Payload[i]?.ToString() ?? string.Empty;
            Console.WriteLine($"\tName = \"{eventData.PayloadNames[i]}\" Value = \"{payloadString}\"");
        }
        Console.WriteLine("\n");
    }
}
```

<span data-ttu-id="83384-121">또한 .NET Core 2.2에서는 ETW 이벤트에 대한 추가 정보를 제공하기 위해 <xref:System.Diagnostics.Tracing.EventWrittenEventArgs> 클래스에 다음 두 가지 속성이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="83384-121">In addition, .NET Core 2.2 adds the following two properties to the <xref:System.Diagnostics.Tracing.EventWrittenEventArgs> class to provide additional information about ETW events:</span></span>

- <xref:System.Diagnostics.Tracing.EventWrittenEventArgs.OSThreadId?displayProperty=nameWithType>

- <xref:System.Diagnostics.Tracing.EventWrittenEventArgs.TimeStamp?displayProperty=nameWithType>

## <a name="data"></a><span data-ttu-id="83384-122">데이터</span><span class="sxs-lookup"><span data-stu-id="83384-122">Data</span></span>

<span data-ttu-id="83384-123">**SqlConnection.AccessToken 속성이 있는 Azure SQL 데이터베이스에 대한 AAD 인증**</span><span class="sxs-lookup"><span data-stu-id="83384-123">**AAD authentication to Azure SQL databases with the SqlConnection.AccessToken property**</span></span>

<span data-ttu-id="83384-124">.NET Core 2.2부터 Azure Active Directory에서 발급된 액세스 토큰을 사용하여 Azure SQL 데이터베이스에 인증할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83384-124">Starting with .NET Core 2.2, an access token issued by Azure Active Directory can be used to authenticate to an Azure SQL database.</span></span> <span data-ttu-id="83384-125">액세스 토큰을 지원하기 위해 <xref:System.Data.SqlClient.SqlConnection.AccessToken> 속성이 <xref:System.Data.SqlClient.SqlConnection> 클래스에 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="83384-125">To support access tokens, the <xref:System.Data.SqlClient.SqlConnection.AccessToken> property has been added to the <xref:System.Data.SqlClient.SqlConnection> class.</span></span> <span data-ttu-id="83384-126">AAD 인증을 활용하려면 System.Data.SqlClient NuGet 패키지 버전 4.6을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="83384-126">To take advantage of AAD authentication, download version 4.6 of the System.Data.SqlClient NuGet package.</span></span> <span data-ttu-id="83384-127">이 기능을 사용하려면 [`Microsoft.IdentityModel.Clients.ActiveDirectory`](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/) NuGet 패키지에 포함된 [.NET용 Active Directory 인증 라이브러리](https://github.com/AzureAD/azure-activedirectory-library-for-dotnet)를 통해 액세스 토큰 값을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83384-127">In order to use the feature, you can obtain the access token value using the [Active Directory Authentication Library for .NET](https://github.com/AzureAD/azure-activedirectory-library-for-dotnet) contained in the [`Microsoft.IdentityModel.Clients.ActiveDirectory`](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/) NuGet package.</span></span>

## <a name="jit-compiler-improvements"></a><span data-ttu-id="83384-128">JIT 컴파일러 개선</span><span class="sxs-lookup"><span data-stu-id="83384-128">JIT compiler improvements</span></span>

<span data-ttu-id="83384-129">**계층화된 컴파일은 옵트인 기능으로 유지됨**</span><span class="sxs-lookup"><span data-stu-id="83384-129">**Tiered compilation remains an opt-in feature**</span></span>

<span data-ttu-id="83384-130">.NET Core 2.1에서 JIT 컴파일러는 새로운 컴파일러 기술인 ‘계층화된 컴파일’을 옵트인 기능으로 구현했습니다. </span><span class="sxs-lookup"><span data-stu-id="83384-130">In .NET Core 2.1, the JIT compiler implemented a new compiler technology, *tiered compilation*, as an opt-in feature.</span></span> <span data-ttu-id="83384-131">계층화된 컴파일의 목표는 성능 향상입니다.</span><span class="sxs-lookup"><span data-stu-id="83384-131">The goal of tiered compilation is improved performance.</span></span> <span data-ttu-id="83384-132">JIT 컴파일러가 수행하는 중요한 작업 중 하나는 코드 실행을 최적화하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="83384-132">One of the important tasks performed by the JIT compiler is optimizing code execution.</span></span> <span data-ttu-id="83384-133">그러나 자주 사용되지 않는 코드 경로의 경우 컴파일러가 코드 최적화에 사용하는 시간이 런타임이 최적화되지 않은 코드 실행에 사용하는 시간보다 길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83384-133">For little-used code paths, however, the compiler may spend more time optimizing code than the runtime spends executing unoptimized code.</span></span> <span data-ttu-id="83384-134">계층화된 컴파일은 JIT 컴파일에 다음과 같은 두 단계를 도입합니다.</span><span class="sxs-lookup"><span data-stu-id="83384-134">Tiered compilation introduces two stages in JIT compilation:</span></span>

- <span data-ttu-id="83384-135">가능한 한 빨리 코드를 생성하는 **첫 번째 계층**.</span><span class="sxs-lookup"><span data-stu-id="83384-135">A **first tier**, which generates code as quickly as possible.</span></span>

- <span data-ttu-id="83384-136">자주 실행되는 메서드에 대한 최적화된 코드를 생성하는 **두 번째 계층**.</span><span class="sxs-lookup"><span data-stu-id="83384-136">A **second tier**, which generates optimized code for those methods that are executed frequently.</span></span> <span data-ttu-id="83384-137">컴파일의 두 번째 계층은 성능 향상을 위해 병렬로 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="83384-137">The second tier of compilation is performed in parallel for enhanced performance.</span></span>

<span data-ttu-id="83384-138">계층화된 컴파일을 통한 성능 향상에 대한 자세한 내용은 [.NET Core 2.2 Preview 2 알림](https://devblogs.microsoft.com/dotnet/announcing-net-core-2-2-preview-2/)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="83384-138">For information on the performance improvement that can result from tiered compilation, see [Announcing .NET Core 2.2 Preview 2](https://devblogs.microsoft.com/dotnet/announcing-net-core-2-2-preview-2/).</span></span>

<span data-ttu-id="83384-139">.NET Core 2.2 Preview 2에서는 계층화된 컴파일을 기본적으로 사용할 수 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="83384-139">In .NET Core 2.2 Preview 2, tiered compilation was enabled by default.</span></span> <span data-ttu-id="83384-140">그러나 계층화된 컴파일을 기본적으로 사용할 준비가 되지 않았다고 결정하여,</span><span class="sxs-lookup"><span data-stu-id="83384-140">However, we've decided that we are still not ready to enable tiered compilation by default.</span></span> <span data-ttu-id="83384-141">.NET Core 2.2에서도 계층화된 컴파일이 계속 옵트인 기능으로 유지되었습니다.</span><span class="sxs-lookup"><span data-stu-id="83384-141">So in .NET Core 2.2, tiered compilation continues to be an opt-in feature.</span></span> <span data-ttu-id="83384-142">계층화된 컴파일을 옵트인하는 방법에 대한 자세한 내용은 [.NET Core 2.1의 새로운 기능](dotnet-core-2-1.md)에서 [JIT 컴파일러 개선](dotnet-core-2-1.md#jit-compiler-improvements)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="83384-142">For information on opting in to tiered compilation, see [Jit compiler improvements](dotnet-core-2-1.md#jit-compiler-improvements) in [What's new in .NET Core 2.1](dotnet-core-2-1.md).</span></span>

## <a name="runtime"></a><span data-ttu-id="83384-143">런타임</span><span class="sxs-lookup"><span data-stu-id="83384-143">Runtime</span></span>

<span data-ttu-id="83384-144">**Main 메서드 실행 전에 코드 삽입**</span><span class="sxs-lookup"><span data-stu-id="83384-144">**Injecting code prior to executing the Main method**</span></span>

<span data-ttu-id="83384-145">.NET Core 2.2부터 시작 후크를 사용하여 애플리케이션의 Main 메서드를 실행하기 전에 코드를 삽입할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83384-145">Starting with .NET Core 2.2, you can use a startup hook to inject code prior to running an application's Main method.</span></span> <span data-ttu-id="83384-146">시작 후크를 사용하면 호스트가 애플리케이션을 다시 컴파일하거나 변경하지 않고도 배포된 후 애플리케이션의 동작을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83384-146">Startup hooks make it possible for a host to customize the behavior of applications after they have been deployed without needing to recompile or change the application.</span></span>

<span data-ttu-id="83384-147">호스팅 공급자는 <xref:System.Runtime.Loader.AssemblyLoadContext?displayProperty=nameWithType> 동작과 같은 주 진입점의 로드 동작에 영향을 미칠 수 있는 설정을 포함하여 사용자 지정 구성 및 정책을 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83384-147">We expect hosting providers to define custom configuration and policy, including settings that potentially influence the load behavior of the main entry point, such as the <xref:System.Runtime.Loader.AssemblyLoadContext?displayProperty=nameWithType> behavior.</span></span> <span data-ttu-id="83384-148">후크를 사용하여 추적 또는 원격 분석 삽입을 설정하거나, 처리할 콜백을 설정하거나, 기타 환경 종속 동작을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83384-148">The hook can be used to set up tracing or telemetry injection, to set up callbacks for handling, or to define other environment-dependent behavior.</span></span> <span data-ttu-id="83384-149">후크는 진입점과 별개이므로 사용자 코드를 수정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="83384-149">The hook is separate from the entry point, so that user code doesn't need to be modified.</span></span>

<span data-ttu-id="83384-150">자세한 내용은 [호스트 시작 후크](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/host-startup-hook.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="83384-150">See [Host startup hook](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/host-startup-hook.md) for more information.</span></span>

## <a name="see-also"></a><span data-ttu-id="83384-151">참조</span><span class="sxs-lookup"><span data-stu-id="83384-151">See also</span></span>

- [<span data-ttu-id="83384-152">.NET Core 3.1의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="83384-152">What's new in .NET Core 3.1</span></span>](dotnet-core-3-1.md)
- [<span data-ttu-id="83384-153">ASP.NET Core 2.2의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="83384-153">What's new in ASP.NET Core 2.2</span></span>](/aspnet/core/release-notes/aspnetcore-2.2)
- [<span data-ttu-id="83384-154">EF Core 2.2의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="83384-154">New features in EF Core 2.2</span></span>](/ef/core/what-is-new/ef-core-2.2)
