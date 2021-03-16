---
title: .NET의 잘 알려진 EventCounters
description: .NET 런타임 및 라이브러리에서 게시하는 EventCounters를 검토합니다.
ms.topic: reference
ms.date: 12/17/2020
ms.openlocfilehash: db7417993786eae18c9d7b6cc3bb79284d543dd3
ms.sourcegitcommit: e3cf8227573e13b8e1f4e3dc007404881cdafe47
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2021
ms.locfileid: "103189945"
---
# <a name="well-known-eventcounters-in-net"></a>.NET의 잘 알려진 EventCounters

.NET 런타임 및 라이브러리에서는 다양한 성능 문제를 식별하고 진단하는 데 사용할 수 있는 여러 [`EventCounter`](./event-counters.md)를 구현하고 게시합니다. 이 문서는 이러한 `EventCounters`를 모니터링하는 데 사용할 수 있는 공급자와 해당 설명에 관한 참조입니다.

## <a name="systemruntime-counters"></a>System.Runtime 카운터

다음 카운터는 .NET 런타임(CoreCLR)의 일부로 게시되며 [`RuntimeEventSource.cs`](https://github.com/dotnet/runtime/blob/main/src/libraries/System.Private.CoreLib/src/System/Diagnostics/Tracing/RuntimeEventSource.cs)에서 유지 관리됩니다.

| 카운터 | 설명 |
|--|--|
| :::no-loc text="% Time in GC since last GC"::: (`time-in-gc`) | 마지막 GC 이후 GC의 시간 비율 |
| :::no-loc text="Allocation Rate"::: (`alloc-rate`) | 업데이트 간격당 할당된 바이트 수 |
| :::no-loc text="CPU Usage"::: (`cpu-usage`) | 모든 시스템 CPU 리소스를 기준으로 프로세스의 CPU 사용량 백분율 |
| :::no-loc text="Exception Count"::: (`exception-count`) | 발생한 예외 수 |
| :::no-loc text="GC Heap Size"::: (`gc-heap-size`) | <xref:System.GC.GetTotalMemory(System.Boolean)?displayProperty=nameWithType>에 따라 할당된 것으로 간주하는 바이트 수 |
| :::no-loc text="Gen 0 GC Count"::: (`gen-0-gc-count`) | 업데이트 간격당 Gen 0에 대해 GC가 발생한 횟수 |
| :::no-loc text="Gen 0 Size"::: (`gen-0-size`) | Gen 0 GC의 바이트 수 |
| :::no-loc text="Gen 1 GC Count"::: (`gen-1-gc-count`) | 업데이트 간격당 Gen 1에 대해 GC가 발생한 횟수 |
| :::no-loc text="Gen 1 Size"::: (`gen-1-size`) | Gen 1 GC의 바이트 수 |
| :::no-loc text="Gen 2 GC Count"::: (`gen-2-gc-count`) | 업데이트 간격당 Gen 2에 대해 GC가 발생한 횟수 |
| :::no-loc text="Gen 2 Size"::: (`gen-2-size`) | Gen 2 GC의 바이트 수 |
| :::no-loc text="LOH Size"::: (`loh-size`) | 대형 개체 힙의 바이트 수 |
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

## <a name="microsoftaspnetcorehosting-counters"></a>“Microsoft.AspNetCore.Hosting” 카운터

다음 카운터는 [ASP.NET Core](/aspnet/core)의 일부로 게시되며 [`HostingEventSource.cs`](https://github.com/dotnet/aspnetcore/blob/master/src/Hosting/Hosting/src/Internal/HostingEventSource.cs)에서 유지 관리됩니다.

| 카운터 | 설명 |
|--|--|
| :::no-loc text="Current Requests"::: (`current-requests`) | 시작되었지만 아직 중지되지 않은 총 요청 수 |
| :::no-loc text="Failed Requests"::: (`failed-requests`) | 앱의 수명 동안 발생한 실패한 총 요청 수 |
| :::no-loc text="Request Rate"::: (`requests-per-second`) | 업데이트 간격당 발생한 요청 수 |
| :::no-loc text="Total Requests"::: (`total-requests`) | 앱의 수명 동안 발생한 총 요청 수 |

## <a name="microsoftaspnetcorehttpconnections-counters"></a>“Microsoft.AspNetCore.Http.Connections” 카운터

다음 카운터는 [ASP.NET Core SignalR](/aspnet/core/signalr/introduction)의 일부로 게시되며 [`HttpConnectionsEventSource.cs`](https://github.com/dotnet/aspnetcore/blob/master/src/SignalR/common/Http.Connections/src/Internal/HttpConnectionsEventSource.cs)에서 유지 관리됩니다.

| 카운터 | 설명 |
|--|--|
| :::no-loc text="Average Connection Duration"::: (`connections-duration`) | 연결의 평균 기간(밀리초) |
| :::no-loc text="Current Connections"::: (`current-connections`) | 시작되었지만 아직 중지되지 않은 활성 연결 수 |
| :::no-loc text="Total Connections Started"::: (`connections-started`) | 시작된 총 연결 수 |
| :::no-loc text="Total Connections Stopped"::: (`connections-stopped`) | 중지된 총 연결 수 |
| :::no-loc text="Total Connections Timed Out"::: (`connections-timed-out`) | 시간이 초과한 총 연결 수 |

## <a name="microsoft-aspnetcore-server-kestrel-counters"></a>“Microsoft-AspNetCore-Server-Kestrel” 카운터

다음 카운터는 [ASP.NET Core Kestrel 웹 서버](/aspnet/core/fundamentals/servers/kestrel)의 일부로 게시되며 [`KestrelEventSource.cs`](https://github.com/dotnet/aspnetcore/blob/master/src/Servers/Kestrel/Core/src/Internal/Infrastructure/KestrelEventSource.cs)에서 유지 관리됩니다.

| 카운터 | 설명 |
|--|--|
| :::no-loc text="Connection Queue Length"::: (`connection-queue-length`) | 연결 큐의 현재 길이 |
| :::no-loc text="Connection Rate"::: (`connections-per-second`) | 웹 서버에 대한 업데이트 간격당 연결 수 |
| :::no-loc text="Current Connections"::: (`current-connections`) | 웹 서버에 대한 현재 활성 연결 수 |
| :::no-loc text="Current TLS Handshakes"::: (`current-tls-handshakes`) | 현재 TLS 핸드셰이크 수 |
| :::no-loc text="Current Upgraded Requests (WebSockets)"::: (`current-upgraded-requests`) | 현재 업그레이드된 요청 수(WebSocket) |
| :::no-loc text="Failed TLS Handshakes"::: (`failed-tls-handshakes`) | 실패한 TLS 핸드셰이크의 총 수 |
| :::no-loc text="Request Queue Length"::: (`request-queue-length`) | 요청 큐의 현재 길이 |
| :::no-loc text="TLS Handshake Rate"::: (`tls-handshakes-per-second`) | 업데이트 간격당 TLS 핸드셰이크 수 |
| :::no-loc text="Total Connections"::: (`total-connections`) | 웹 서버에 대한 총 연결 수 |
| :::no-loc text="Total TLS Handshakes"::: (`total-tls-handshakes`) | 웹 서버를 사용하는 TLS 핸드셰이크의 총 수 |

## <a name="systemnethttp-counters"></a>“System.Net.Http” 카운터

다음 카운터는 HTTP 스택에서 게시합니다.  해당 카운터는 .NET 5 이상 버전에서만 사용할 수 있습니다.

| 카운터 | 설명 |
|--|--|
| :::no-loc text="Requests Started"::: (`requests-started`) | 프로세스가 시작된 이후 시작된 요청 수 |
| :::no-loc text="Requests Started Rate"::: (`requests-started-rate`) | 업데이트 간격당 시작된 요청 수 |
| :::no-loc text="Requests Failed"::: (`requests-failed`) | 프로세스가 시작된 이후 실패한 요청 수 |
| :::no-loc text="Requests Failed Rate"::: (`requests-failed-rate`) | 업데이트 간격당 실패한 요청 수 |
| :::no-loc text="Current Requests"::: (`current-requests`) | 시작되었지만 아직 완료되거나 실패하지 않은 현재 활성 HTTP 요청 수 |
| :::no-loc text="Current HTTP 1.1 Connections"::: (`http11-connections-current-total`) | 시작되었지만 아직 완료되거나 실패하지 않은 현재 HTTP 1.1 연결 수 |
| :::no-loc text="Current HTTP 2.0 Connections"::: (`http20-connections-current-total`) | 시작되었지만 아직 완료되거나 실패하지 않은 현재 HTTP 2.0 연결 수 |
| :::no-loc text="HTTP 1.1 Requests Queue Duration"::: (`http11-requests-queue-duration`) | 요청 큐에서 HTTP 1.1 요청에 소요된 평균 기간 |
| :::no-loc text="HTTP 2.0 Requests Queue Duration"::: (`http20-requests-queue-duration`) | 요청 큐에서 HTTP 2.0 요청에 소요된 평균 기간 |

## <a name="systemnetnameresolution-counters"></a>“System.Net.NameResolution” 카운터

다음 카운터는 DNS 조회와 관련된 메트릭을 추적합니다. 해당 카운터는 .NET 5 이상 버전에서만 사용할 수 있습니다.

| 카운터 | 설명 |
|--|--|
| :::no-loc text="DNS Lookups Requested"::: (`dns-lookups-requested`) | 프로세스가 시작된 이후 요청된 DNS 조회 수 |
| :::no-loc text="Average DNS Lookup Duration"::: (`dns-lookups-duration`) | DNS 조회에 소요된 평균 시간 |

## <a name="systemnetsecurity-counters"></a>“System.Net.Security” 카운터

다음 카운터는 전송 계층 보안 프로토콜과 관련된 메트릭을 추적합니다.  해당 카운터는 .NET 5 이상 버전에서만 사용할 수 있습니다.

| 카운터 | 설명 |
|--|--|
| :::no-loc text="TLS handshakes completed"::: (`tls-handshake-rate`) | 업데이트 간격당 완료된 TLS 핸드셰이크 수 |
| :::no-loc text="Total TLS handshakes completed"::: (`total-tls-handshakes`) | 프로세스가 시작된 이후 완료된 TLS 핸드셰이크의 총수 |
| :::no-loc text="Current TLS handshakes"::: (`current-tls-handshakes`) | 시작되었지만 아직 완료되지 않은 TLS 핸드셰이크의 현재 수 |
| :::no-loc text="Total TLS handshakes failed"::: (`failed-tls-handshakes`) | 프로세스가 시작된 이후 실패한 TLS 핸드셰이크의 총수 |
| :::no-loc text="All TLS Sessions Active"::: (`all-tls-sessions-open`) | 모든 버전의 활성 TLS 세션 수 |
| :::no-loc text="TLS 1.0 Sessions Active"::: (`tls10-sessions-open`) | 활성 TLS 1.0 세션 수 |
| :::no-loc text="TLS 1.1 Sessions Active"::: (`tls11-sessions-open`) | 활성 TLS 1.1 세션 수 |
| :::no-loc text="TLS 1.2 Sessions Active"::: (`tls12-sessions-open`) | 활성 TLS 1.2 세션 수 |
| :::no-loc text="TLS 1.3 Sessions Active"::: (`tls13-sessions-open`) | 활성 TLS 1.3 세션 수 |
| :::no-loc text="TLS Handshake Duration"::: (`all-tls-handshake-duration`) | 모든 TLS 핸드셰이크의 평균 기간 |
| :::no-loc text="TLS 1.0 Handshake Duration"::: (`tls10-handshake-duration`) | TLS 1.0 핸드셰이크의 평균 기간 |
| :::no-loc text="TLS 1.1 Handshake Duration"::: (`tls11-handshake-duration`) | TLS 1.1 핸드셰이크의 평균 기간 |
| :::no-loc text="TLS 1.2 Handshake Duration"::: (`tls12-handshake-duration`) | TLS 1.2 핸드셰이크의 평균 기간 |
| :::no-loc text="TLS 1.3 Handshake Duration"::: (`tls13-handshake-duration`) | TLS 1.3 핸드셰이크의 평균 기간 |

## <a name="systemnetsockets-counters-available-on-net-5-and-later-versions"></a>“System.Net.Sockets” 카운터(.NET 5 이상 버전에서 사용 가능)

다음 카운터는 <xref:System.Net.Sockets.Socket>관련 메트릭을 추적합니다.

| 카운터 | 설명 |
|--|--|
| :::no-loc text="Outgoing Connections Established"::: (`outgoing-connections-established`) | 프로세스가 시작된 이후 설정된 나가는 연결의 총수 |
| :::no-loc text="Incoming Connections Established"::: (`incoming-connections-established`) | 프로세스가 시작된 이후 설정된 들어오는 연결의 총수 |
| :::no-loc text="Bytes Received"::: (`bytes-received`) | 프로세스가 시작된 이후 받은 총 바이트 수 |
| :::no-loc text="Bytes Sent"::: (`bytes-sent`) | 프로세스가 시작된 이후 보낸 총 바이트 수 |
| :::no-loc text="Datagrams Received"::: (`datagrams-received`) | 프로세스가 시작된 이후 받은 데이터그램의 총수 |
| :::no-loc text="Datagrams Sent"::: (`datagrams-sent`) | 프로세스가 시작된 이후 보낸 데이터그램의 총수 |
