---
title: .NET의 잘 알려진 이벤트 공급자
description: .NET 런타임 및 라이브러리에서 게시하는 공급자 및 이벤트를 검토합니다.
ms.topic: reference
ms.date: 12/21/2020
ms.openlocfilehash: 03d505f33e300b094958676bb768fb542d828aeb
ms.sourcegitcommit: c3093e9d106d8ca87cc86eef1f2ae4ecfb392118
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2020
ms.locfileid: "97738191"
---
# <a name="well-known-event-providers-in-net"></a>.NET의 잘 알려진 이벤트 공급자

.NET 런타임 및 라이브러리에서는 다양한 이벤트 공급자를 통해 진단 이벤트를 기록합니다. 진단 요구 사항에 따라 사용할 적절한 공급자를 선택할 수 있습니다. 이 문서에서는 .NET 런타임 및 라이브러리에서 일반적으로 사용되는 이벤트 공급자 중 일부를 설명합니다.

## <a name="coreclr"></a>CoreCLR

### <a name="microsoft-windows-dotnetruntime-provider"></a>“Microsoft-Windows-DotNETRuntime” 공급자

이 공급자는 .NET 런타임에서 GC, 로더, JIT, 예외, 기타 이벤트를 비롯한 다양한 이벤트를 내보냅니다. 이 공급자의 각 이벤트에 대한 자세한 내용은 [Runtime Provider Events List](../../fundamentals/diagnostics/runtime-events.md)(런타임 공급자 이벤트 목록)를 참조하세요.

### <a name="microsoft-dotnetcore-sampleprofiler-provider"></a>“Microsoft-DotNETCore-SampleProfiler” 공급자

이 공급자는 관리형 호출 스택의 CPU 샘플링에 사용되는 .NET 런타임 이벤트 공급자입니다. 사용하도록 설정하면 10밀리초마다 각 스레드의 관리형 호출 스택 스냅샷을 캡처합니다. 이 캡처를 사용하도록 설정하려면 `Informational` 이상의 <xref:System.Diagnostics.Tracing.EventLevel>을 지정해야 합니다.

## <a name="framework-libraries"></a>프레임워크 라이브러리

### <a name="microsoft-extensions-dependencyinjection-provider"></a>“Microsoft-Extensions-DependencyInjection” 공급자

이 공급자는 DependencyInjection의 정보를 로그합니다. 다음 표에서는 `Microsoft-Extensions-DependencyInjection` 공급자에서 로그하는 이벤트를 보여 줍니다.

|이벤트 이름|Level|설명|
|----------|-----|-----------|
|`CallSiteBuilt`|자세한 정보 표시(5)|호출 사이트가 빌드되었습니다.|
|`ServiceResolved`|자세한 정보 표시(5)|서비스가 해결되었습니다.|
|`ExpressionTreeGenerated`|자세한 정보 표시(5)|식 트리가 생성되었습니다.|
|`DynamicMethodBuilt`|자세한 정보 표시(5)|<xref:System.Reflection.Emit.DynamicMethod>가 빌드되었습니다.|

### <a name="systembuffersarraypooleventsource-provider"></a>“System.Buffers.ArrayPoolEventSource” 공급자

이 공급자는 ArrayPool의 정보를 로그합니다. 다음 표에서는 `ArrayPoolEventSource`에서 로그하는 이벤트를 보여 줍니다.

|이벤트 이름|Level|설명|
|----------|-----|-----------|
|`BufferRented`|자세한 정보 표시(5)|버퍼가 대여되었습니다.|
|`BufferAllocated`|정보(4)|풀에서 버퍼를 할당했습니다.|
|`BufferReturned`|자세한 정보 표시(5)|버퍼가 풀로 반환되었습니다.|
|`BufferTrimmed`|정보(4)|메모리 부족이나 비활성으로 인해 버퍼를 해제하려고 했습니다.|
|`BufferTrimPoll`|정보(4)|버퍼를 트리밍하기 위해 검사가 수행되고 있습니다.|

### <a name="systemnethttp-provider"></a>“System.Net.Http” 공급자

이 공급자는 HTTP 스택의 정보를 로그합니다. 다음 표에서는 `System.Net.Http` 공급자에서 로그하는 이벤트를 보여 줍니다.

|이벤트 이름|Level|설명|
|----------|-----|-----------|
|RequestStart|정보(4)|HTTP 요청이 시작되었습니다.|
|RequestStop|정보(4)|HTTP 요청이 완료되었습니다.|
|RequestFailed|오류(2)|HTTP 요청이 실패했습니다.|
|ConnectionEstablished|정보(4)|HTTP 연결이 설정되었습니다.|
|ConnectionClosed|정보(4)|HTTP 연결이 끊겼습니다.|
|RequestLeftQueue|정보(4)|HTTP 요청이 요청 큐에서 나갔습니다.|
|RequestHeadersStart|정보(4)|헤더의 HTTP 요청이 시작되었습니다.|
|RequestHeaderStop|정보(4)|헤더의 HTTP 요청이 완료되었습니다.|
|RequestContentStart|정보(4)|콘텐츠의 HTTP 요청이 시작되었습니다.|
|RequestContentStop|정보(4)|콘텐츠의 HTTP 요청이 완료되었습니다.|
|ResponseHeadersStart|정보(4)|헤더의 HTTP 응답이 시작되었습니다.|
|ResponseHeaderStop|정보(4)|헤더의 HTTP 응답이 완료되었습니다.|
|ResponseContentStart|정보(4)|콘텐츠의 HTTP 응답이 시작되었습니다.|
|ResponseContentStop|정보(4)|콘텐츠의 HTTP 응답이 완료되었습니다.|

### <a name="systemnetnameresolution-provider"></a>“System.Net.NameResolution” 공급자

이 공급자는 도메인 이름 확인과 관련된 정보를 로그합니다. 다음 표에서는 `System.Net.NameResolution`에서 로그하는 이벤트를 보여 줍니다.

|이벤트 이름|Level|설명|
|----------|-----|-----------|
|`ResolutionStart`|정보(4)|도메인 이름 확인이 시작되었습니다.|
|`ResolutionStop`|정보(4)|도메인 이름 확인이 완료되었습니다.|
|`ResolutionFailed`|정보(4)|도메인 이름 확인이 실패했습니다.|

### <a name="systemnetsockets-provider"></a>“System.Net.Sockets” 공급자

이 공급자는 <xref:System.Net.Sockets.Socket>의 정보를 로그합니다. 다음 표에서는 `System.Net.Sockets` 공급자에서 로그하는 이벤트를 보여 줍니다.

|이벤트 이름|Level|설명|
|----------|-----|-----------|
|`ConnectStart`|정보(4)|소켓 연결을 시작하려는 시도가 시작되었습니다.|
|`ConnectStop`|정보(4)|소켓 연결을 시작하려는 시도가 완료되었습니다.|
|`ConnectFailed`|정보(4)|소켓 연결을 시작하려는 시도가 실패했습니다.|
|`AcceptStart`|정보(4)|소켓 연결을 허용하려는 시도가 시작되었습니다.|
|`AcceptStop`|정보(4)|소켓 연결을 허용하려는 시도가 완료되었습니다.|
|`AcceptFailed`|정보(4)|소켓 연결을 허용하려는 시도가 실패했습니다.|

### <a name="systemthreadingtaskstpleventsource-provider"></a>“System.Threading.Tasks.TplEventSource” 공급자

이 공급자는 [작업 병렬 라이브러리](../../standard/parallel-programming/task-parallel-library-tpl.md)에 대한 정보(예: 작업 스케줄러 이벤트)를 로그합니다. 다음 표에서는 `TplEventSource`에서 로그하는 이벤트를 보여 줍니다.

|이벤트 이름|키워드|Level|설명|
|----------|-------|-----|-----------|
|`TaskScheduled`|`TaskTransfer`(`0x1`)<br /><br />`Tasks`(`0x2`)|정보(4)|<xref:System.Threading.Tasks.Task>가 작업 스케줄러에 대기 중입니다.|
|`TaskStarted`|`Tasks`(`0x2`)|정보(4)|<xref:System.Threading.Tasks.Task> 실행이 시작되었습니다.|
|`TaskCompleted`|`TaskStops`(`0x40`)|정보(4)|<xref:System.Threading.Tasks.Task> 실행이 완료되었습니다.|
|`TaskWaitBegin`|`TaskTransfer`(`0x1`)<br /><br />`TaskWait`(`0x2`)|정보(4)|<xref:System.Threading.Tasks.Task> 완료에 대한 암시적 또는 명시적 대기가 시작될 때 발생합니다.|
|`TaskWaitEnd`|`Tasks`(`0x2`)|자세한 정보 표시(5)|<xref:System.Threading.Tasks.Task> 완료에 대한 대기가 반환될 때 발생합니다.|
|`TaskWaitContinuationStarted`|`Tasks`(`0x2`)|자세한 정보 표시(5)|`TaskWaitEnd`와 연결된 작업(메서드)이 시작될 때 발생합니다.|
|`TaskWaitContinuationCompleted`|`TaskStops`(`0x40`)|자세한 정보 표시(5)|`TaskWaitEnd`와 연결된 작업(메서드)이 완료될 때 발생합니다.|
|`AwaitTaskContinuationScheduled`|`TaskTransfer`(`0x1`)<br /><br />`Tasks`(`0x2`)|정보(4)|<xref:System.Threading.Tasks.Task>에 대한 비동기 연속이 예약된 경우 발생합니다.|

## <a name="aspnet-core"></a>ASP.NET Core

ASP.NET Core에서는 ASP.NET Core 스택의 문제를 진단하는 데 도움이 되는 여러 이벤트도 제공합니다.

ASP.NET Core의 이벤트와 해당 이벤트를 사용하는 방법에 대한 자세한 내용은 [.NET Core 및 ASP.NET Core의 로깅](/aspnet/core/fundamentals/logging/)을 참조하세요.
