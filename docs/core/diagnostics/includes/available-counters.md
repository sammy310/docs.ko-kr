---
ms.openlocfilehash: 4ffef401c07dbb27db7c0225acdc6817d95bfe11
ms.sourcegitcommit: b4a46f6d7ebf44c0035627d00924164bcae2db30
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91451574"
---
## <a name="available-counters"></a>사용 가능한 카운터

다양한 .NET 패키지에서 GC(가비지 수집), JIT(Just-in-time), 어셈블리, 예외, 스레딩, 네트워킹 및 웹 요청에 대한 기본 메트릭이 EventCounters를 사용하여 게시됩니다.

### <a name="systemruntime-counters"></a>“System.Runtime” 카운터

다음 카운터는 .NET 런타임의 일부로 게시되며 [`RuntimeEventSource.cs`](https://github.com/dotnet/coreclr/blob/master/src/System.Private.CoreLib/src/System/Diagnostics/Eventing/RuntimeEventSource.cs)에서 유지 관리됩니다.

| 카운터 | 설명 |
|--|--|
| :::no-loc text="% Time in GC since last GC"::: (`time-in-gc`) | 마지막 GC 이후 GC의 시간 비율 |
| :::no-loc text="Allocation Rate"::: (`alloc-rate`) | 할당률(바이트) |
| :::no-loc text="CPU Usage"::: (`cpu-usage`) | 프로세스의 CPU 사용률(%) |
| :::no-loc text="Exception Count"::: (`exception-count`) | 발생한 예외 수 |
| :::no-loc text="GC Heap Size"::: (`gc-heap-size`) | <xref:System.GC.GetTotalMemory(System.Boolean)?displayProperty=nameWithType>에 따라 할당된 것으로 간주하는 바이트 수 |
| :::no-loc text="Gen 0 GC Count"::: (`gen-0-gc-count`) | Gen 0에 대해 GC가 발생한 횟수 |
| :::no-loc text="Gen 0 Size"::: (`gen-0-size`) | Gen 0 GC의 바이트 수 |
| :::no-loc text="Gen 1 GC Count"::: (`gen-1-gc-count`) | Gen 1에 대해 GC가 발생한 횟수 |
| :::no-loc text="Gen 1 Size"::: (`gen-1-size`) | Gen 1 GC의 바이트 수 |
| :::no-loc text="Gen 2 GC Count"::: (`gen-2-gc-count`) | Gen 2에 대해 GC가 발생한 횟수 |
| :::no-loc text="Gen 2 Size"::: (`gen-2-size`) | Gen 2 GC의 바이트 수 |
| :::no-loc text="LOH Size"::: (`loh-size`) | Gen 3 GC의 바이트 수 |
| :::no-loc text="POH Size"::: (`poh-size`) | 고정된 개체 힙의 바이트 수(.NET 5 이상 버전에서 사용 가능) |
| :::no-loc text="GC Fragmentation"::: (`gc-fragmentation`) | GC 힙 조각화(.NET 5 이상 버전에서 사용 가능) |
| :::no-loc text="Monitor Lock Contention Count"::: (`monitor-lock-contention-count`) | <xref:System.Threading.Monitor.LockContentionCount?displayProperty=nameWithType>에 따라 모니터의 잠금을 시도할 때 경합이 발생한 횟수 |
| :::no-loc text="Number of Active Timers"::: (`active-timer-count`) | <xref:System.Threading.Timer.ActiveCount?displayProperty=nameWithType>에 따라 현재 활성화된 <xref:System.Threading.Timer> 인스턴스 수 |
| :::no-loc text="Number of Assemblies Loaded"::: (`assembly-count`) | 특정 시점에 프로세스에 로드된 <xref:System.Reflection.Assembly> 인스턴스의 수 |
| :::no-loc text="ThreadPool Completed Work Item Count"::: (`threadpool-completed-items-count`) | <xref:System.Threading.ThreadPool>에서 지금까지 처리된 작업 항목 수 |
| :::no-loc text="ThreadPool Queue Length"::: (`threadpool-queue-length`) | <xref:System.Threading.ThreadPool>에서 현재 처리 대기 중인 작업 항목의 수 |
| :::no-loc text="ThreadPool Thread Count"::: (`threadpool-thread-count`) | <xref:System.Threading.ThreadPool.ThreadCount?displayProperty=nameWithType>에 따라 현재 <xref:System.Threading.ThreadPool>에 존재하는 스레드 풀 스레드의 수 |
| :::no-loc text="Working Set"::: (`working-set`) | <xref:System.Environment.WorkingSet?displayProperty=nameWithType>에 따라 특정 시점에 프로세스 컨텍스트에 매핑되는 실제 메모리의 크기 |
| :::no-loc text="IL Bytes Jitted"::: (`il-bytes-jitted`) | JIT 컴파일된 IL의 총 크기(바이트)(.NET 5 이상 버전에서 사용 가능). |
| :::no-loc text="Method Jitted Count"::: (`method-jitted-count`) | JIT 컴파일된 메서드 수(.NET 5 이상 버전에서 사용 가능) |

### <a name="microsoftaspnetcorehosting-counters"></a>“Microsoft.AspNetCore.Hosting” 카운터

다음 카운터는 [ASP.NET Core](/aspnet/core)의 일부로 게시되며 [`HostingEventSource.cs`](https://github.com/dotnet/aspnetcore/blob/master/src/Hosting/Hosting/src/Internal/HostingEventSource.cs)에서 유지 관리됩니다.

| 카운터 | 설명 |
|--|--|
| :::no-loc text="Current Requests"::: (`current-requests`) | 시작되었지만 아직 중지되지 않은 총 요청 수 |
| :::no-loc text="Failed Requests"::: (`failed-requests`) | 앱의 수명 동안 발생한 실패한 총 요청 수 |
| :::no-loc text="Request Rate"::: (`requests-per-second`) | 초당 발생한 요청 수 |
| :::no-loc text="Total Requests"::: (`total-requests`) | 앱의 수명 동안 발생한 총 요청 수 |

### <a name="microsoftaspnetcorehttpconnections-counters"></a>“Microsoft.AspNetCore.Http.Connections” 카운터

다음 카운터는 [ASP.NET Core SignalR](/aspnet/core/signalr/introduction)의 일부로 게시되며 [`HttpConnectionsEventSource.cs`](https://github.com/dotnet/aspnetcore/blob/master/src/SignalR/common/Http.Connections/src/Internal/HttpConnectionsEventSource.cs)에서 유지 관리됩니다.

| 카운터 | 설명 |
|--|--|
| :::no-loc text="Average Connection Duration"::: (`connections-duration`) | 연결의 평균 기간(밀리초) |
| :::no-loc text="Current Connections"::: (`current-connections`) | 시작되었지만 아직 중지되지 않은 활성 연결 수 |
| :::no-loc text="Total Connections Started"::: (`connections-started`) | 시작된 총 연결 수 |
| :::no-loc text="Total Connections Stopped"::: (`connections-stopped`) | 중지된 총 연결 수 |
| :::no-loc text="Total Connections Timed Out"::: (`connections-timed-out`) | 시간이 초과한 총 연결 수 |

### <a name="microsoft-aspnetcore-server-kestrel-counters"></a>“Microsoft-AspNetCore-Server-Kestrel” 카운터

다음 카운터는 [ASP.NET Core Kestrel 웹 서버](/aspnet/core/fundamentals/servers/kestrel)의 일부로 게시되며 [`KestrelEventSource.cs`](https://github.com/dotnet/aspnetcore/blob/master/src/Servers/Kestrel/Core/src/Internal/Infrastructure/KestrelEventSource.cs)에서 유지 관리됩니다.

| 카운터 | 설명 |
|--|--|
| :::no-loc text="Connection Queue Length"::: (`connection-queue-length`) | 연결 큐의 현재 길이 |
| :::no-loc text="Connection Rate"::: (`connections-per-second`) | 웹 서버에 대한 초당 연결 수 |
| :::no-loc text="Current Connections"::: (`current-connections`) | 웹 서버에 대한 현재 활성 연결 수 |
| :::no-loc text="Current TLS Handshakes"::: (`current-tls-handshakes`) | 현재 TLS 핸드셰이크 수 |
| :::no-loc text="Current Upgraded Requests (WebSockets)"::: (`current-upgraded-requests`) | 현재 업그레이드된 요청 수(WebSocket) |
| :::no-loc text="Failed TLS Handshakes"::: (`failed-tls-handshakes`) | 실패한 TLS 핸드셰이크의 총 수 |
| :::no-loc text="Request Queue Length"::: (`request-queue-length`) | 요청 큐의 현재 길이 |
| :::no-loc text="TLS Handshake Rate"::: (`tls-handshakes-per-second`) | 초당 TLS 핸드셰이크 수 |
| :::no-loc text="Total Connections"::: (`total-connections`) | 웹 서버에 대한 총 연결 수 |
| :::no-loc text="Total TLS Handshakes"::: (`total-tls-handshakes`) | 웹 서버를 사용하는 TLS 핸드셰이크의 총 수 |
