---
title: ThreadPool 런타임 이벤트
description: .NET Core의 스레드 풀에 대 한 진단 정보를 수집 하는 .NET 런타임 스레드 풀 이벤트를 참조 하세요. 스레드 풀 이벤트는 작업자 스레드 풀 이벤트 또는 i/o 스레드 풀 이벤트입니다.
ms.date: 11/13/2020
ms.topic: reference
helpviewer_keywords:
- ThreadPool events (CoreCLR)
- ETW, thread pool events (CoreCLR)
ms.openlocfilehash: cdd6041c5842d4922c60e33daf6db366f7d35327
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96594123"
---
# <a name="net-runtime-thread-pool-events"></a>.NET 런타임 스레드 풀 이벤트

이러한 이벤트는 threadpool의 작업자 및 i/o 스레드에 대 한 정보를 수집 합니다. 진단 목적으로 이러한 이벤트를 사용 하는 방법에 대 한 자세한 내용은 [.net 응용 프로그램 로깅 및 추적](../../core/diagnostics/logging-tracing.md) 을 참조 하세요.

## <a name="iothreadcreate_v1-event"></a>IOThreadCreate_V1 이벤트

 다음 표에서는 키워드와 수준을 보여 줍니다.

|이벤트를 발생시키기 위한 키워드|수준|
|-----------------------------------|-----------|
|`ThreadingKeyword` (0x10000)|정보(4)|

 다음 표에서는 이벤트 정보를 보여 줍니다.

|이벤트|이벤트 ID|발생 시기|
|-----------------------------------|-----------|
|`IOThreadCreate_V1`|44|스레드 풀에서 I/O 스레드가 생성됩니다.|

 다음 표에서는 이벤트 데이터를 보여 줍니다.

|필드 이름|데이터 형식|Description|
|----------------|---------------|-----------------|
|`Count`|`win:UInt64`|새로 생성된 스레드를 포함한 I/O 스레드의 수입니다.|
|`NumRetired`|`win:UInt64`|만료된 작업자 스레드의 수입니다.|
|`ClrInstanceID`|`win:UInt16`|CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.|

## <a name="iothreadterminate_v1-event"></a>IOThreadTerminate_V1 이벤트

 다음 표에서는 키워드와 수준을 보여 줍니다.

|이벤트를 발생시키기 위한 키워드|수준
|-----------------------------------|-----------
|`ThreadingKeyword` (0x10000)|정보(4)

 다음 표에서는 이벤트 정보를 보여 줍니다.

|이벤트|이벤트 ID|발생 시기|
|-----------|--------------|-----------------|
|`IOThreadTerminate`|45|스레드 풀에서 i/o 스레드가 종료 됩니다.|

 다음 표에서는 이벤트 데이터를 보여 줍니다.

|필드 이름|데이터 형식|Description|
|----------------|---------------|-----------------|
|`Count`|`win:UInt64`|스레드 풀에 남아 있는 I/O 스레드의 수입니다.|
|`NumRetired`|`win:UInt64`|만료된 I/O 스레드의 수입니다.|
|`ClrInstanceID`|`win:UInt16`|CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.|

## <a name="iothreadretire_v1-event"></a>IOThreadRetire_V1 이벤트

 다음 표에서는 키워드와 수준을 보여 줍니다.

|이벤트를 발생시키기 위한 키워드|수준|
|-----------------------------------|-----------|
|`ThreadingKeyword` (0x10000)|정보(4)|

 다음 표에서는 이벤트 정보를 보여 줍니다.

|이벤트|이벤트 ID|발생 시기|
|-----------|--------------|-----------------|
|`IOThreadRetire_V1`|46|I/O 스레드가 만료 후보가 됩니다.|

 다음 표에서는 이벤트 데이터를 보여 줍니다.

|필드 이름|데이터 형식|Description|
|----------------|---------------|-----------------|
|`Count`|`win:UInt64`|스레드 풀에 남아 있는 I/O 스레드의 수입니다.|
|`NumRetired`|`win:UInt64`|만료된 I/O 스레드의 수입니다.|
|`ClrInstanceID`|`win:UInt16`|CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.|

## <a name="iothreadunretire_v1-event"></a>IOThreadUnretire_V1 이벤트

 다음 표에서는 키워드와 수준을 보여 줍니다.

|이벤트를 발생시키기 위한 키워드|수준|
|-----------------------------------|-----------|
|`ThreadingKeyword` (0x10000)|정보(4)|

 다음 표에서는 이벤트 정보를 보여 줍니다.

|이벤트|이벤트 ID|발생 시기|
|-----------|--------------|-----------------|
|`IOThreadUnretire_V1`|47|스레드가 만료 후보가 된 후 대기 기간 내에 도착하는 I/O 때문에 I/O 스레드가 만료 취소됩니다.|

 다음 표에서는 이벤트 데이터를 보여 줍니다.

|필드 이름|데이터 형식|Description|
|----------------|---------------|-----------------|
|`Count`|`win:UInt64`|이 스레드를 포함하여 스레드 풀에 있는 I/O 스레드의 수입니다.|
|`NumRetired`|`win:UInt64`|만료된 I/O 스레드의 수입니다.|
|`ClrInstanceID`|`Win:UInt16`|CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.|

## <a name="threadpoolworkerthreadstart-event"></a>ThreadPoolWorkerThreadStart 이벤트

|이벤트를 발생시키기 위한 키워드|수준|
|-----------------------------------|-----------|-----------|
|`ThreadingKeyword` (0x10000)|정보(4)|

|이벤트|이벤트 ID|Description|
|-----------|--------------|-----------------|
|`ThreadPoolWorkerThreadStart`|50|작업자 스레드가 생성됩니다.|

|필드 이름|데이터 형식|Description|
|----------------|---------------|-----------------|
|`ActiveWorkerThreadCount`|`win:UInt32`|이미 작업을 처리하고 있는 작업자 스레드를 포함하여 작업을 처리할 수 있는 작업자 스레드의 개수입니다.|
|`RetiredWorkerThreadCount`|`win:UInt32`|작업을 처리할 수 없지만, 나중에 더 많은 스레드가 필요할 때를 대비하여 유지하고 있는 작업자 스레드의 개수입니다.|
|`ClrInstanceID`|`win:UInt16`|CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.|

## <a name="threadpoolworkerthreadstop-event"></a>ThreadPoolWorkerThreadStop 이벤트

|이벤트를 발생시키기 위한 키워드|수준|
|-----------------------------------|-----------|-----------|
|`ThreadingKeyword` (0x10000)|정보(4)|

|이벤트|이벤트 ID|Description|
|-----------|--------------|-----------------|
|`ThreadPoolWorkerThreadStop`|51|작업자 스레드가 중지됩니다.|

|필드 이름|데이터 형식|Description|
|----------------|---------------|-----------------|
|`ActiveWorkerThreadCount`|`win:UInt32`|이미 작업을 처리하고 있는 작업자 스레드를 포함하여 작업을 처리할 수 있는 작업자 스레드의 개수입니다.|
|`RetiredWorkerThreadCount`|`win:UInt32`|작업을 처리할 수 없지만, 나중에 더 많은 스레드가 필요할 때를 대비하여 유지하고 있는 작업자 스레드의 개수입니다.|
|`ClrInstanceID`|`win:UInt16`|CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.|

## <a name="threadpoolworkerthreadwait-event"></a>ThreadPoolWorkerThreadWait 이벤트

|이벤트를 발생시키기 위한 키워드|수준|
|-----------------------------------|-----------|-----------|
|`ThreadingKeyword` (0x10000)|정보(4)|

|이벤트|이벤트 ID|Description|
|-----------|--------------|-----------------|
|`ThreadPoolWorkerThreadWait`|57|작업자 스레드가 작업 대기를 시작 합니다.|

|필드 이름|데이터 형식|Description|
|----------------|---------------|-----------------|
|`ActiveWorkerThreadCount`|`win:UInt32`|이미 작업을 처리하고 있는 작업자 스레드를 포함하여 작업을 처리할 수 있는 작업자 스레드의 개수입니다.|
|`RetiredWorkerThreadCount`|`win:UInt32`|작업을 처리할 수 없지만, 나중에 더 많은 스레드가 필요할 때를 대비하여 유지하고 있는 작업자 스레드의 개수입니다.|
|`ClrInstanceID`|`win:UInt16`|CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.|

## <a name="threadpoolworkerthreadretirementstart-event"></a>ThreadPoolWorkerThreadRetirementStart 이벤트

|이벤트를 발생시키기 위한 키워드|수준|
|-----------------------------------|-----------|-----------|
|`ThreadingKeyword` (0x10000)|정보(4)|

|이벤트|이벤트 ID|Description|
|-----------|--------------|-----------------|
|`ThreadPoolWorkerThreadRetirementStart`|52|작업자 스레드가 만료됩니다.|

|필드 이름|데이터 형식|Description|
|----------------|---------------|-----------------|
|`ActiveWorkerThreadCount`|`win:UInt32`|이미 작업을 처리하고 있는 작업자 스레드를 포함하여 작업을 처리할 수 있는 작업자 스레드의 개수입니다.|
|`RetiredWorkerThreadCount`|`win:UInt32`|작업을 처리할 수 없지만, 나중에 더 많은 스레드가 필요할 때를 대비하여 유지하고 있는 작업자 스레드의 개수입니다.|
|`ClrInstanceID`|`win:UInt16`|CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.|

## <a name="threadpoolworkerthreadretirementstop-event"></a>ThreadPoolWorkerThreadRetirementStop 이벤트

|이벤트를 발생시키기 위한 키워드|수준|
|-----------------------------------|-----------|-----------|
|`ThreadingKeyword` (0x10000)|정보(4)|

|이벤트|이벤트 ID|Description|
|-----------|--------------|-----------------|
|`ThreadPoolWorkerThreadRetirementStop`|53|만료된 작업자 스레드가 다시 활성 상태가 됩니다.|

|필드 이름|데이터 형식|Description|
|----------------|---------------|-----------------|
|`ActiveWorkerThreadCount`|`win:UInt32`|이미 작업을 처리하고 있는 작업자 스레드를 포함하여 작업을 처리할 수 있는 작업자 스레드의 개수입니다.|
|`RetiredWorkerThreadCount`|`win:UInt32`|작업을 처리할 수 없지만, 나중에 더 많은 스레드가 필요할 때를 대비하여 유지하고 있는 작업자 스레드의 개수입니다.|
|`ClrInstanceID`|`win:UInt16`|CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.|

## <a name="threadpoolworkerthreadadjustmentsample-event"></a>ThreadPoolWorkerThreadAdjustmentSample 이벤트

 다음 표에서는 키워드와 수준을 보여 줍니다.

|이벤트를 발생시키기 위한 키워드|수준|
|-----------------------------------|-----------|
|`ThreadingKeyword` (0x10000)|정보(4)|

 다음 표에서는 이벤트 정보를 보여 줍니다.

|이벤트|이벤트 ID|Description|
|-----------|--------------|-----------------|
|`ThreadPoolWorkerThreadAdjustmentSample`|54|한 샘플의 정보 컬렉션을 나타냅니다. 즉, 특정 시점에 특정 동시성 수준으로 처리량을 측정한 것입니다.|

 다음 표에서는 이벤트 데이터를 보여 줍니다.

|필드 이름|데이터 형식|Description|
|----------------|---------------|-----------------|
|`Throughput`|`win:Double`|시간 단위당 완료 수입니다.|
|`ClrInstanceID`|`win:UInt16`|CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.|

## <a name="threadpoolworkerthreadadjustmentadjustment-event"></a>ThreadPoolWorkerThreadAdjustmentAdjustment 이벤트

 다음 표에서는 키워드와 수준을 보여 줍니다.

|이벤트를 발생시키기 위한 키워드|수준|
|-----------------------------------|-----------|
|`ThreadingKeyword` (0x10000)|정보(4)|

 다음 표에서는 이벤트 정보를 보여 줍니다.

|이벤트|이벤트 ID|Description|
|-----------|--------------|-----------------|
|`ThreadPoolWorkerThreadAdjustmentAdjustment`|55|스레드 삽입(언덕 오르기) 알고리즘이 동시성 수준에서 변화를 감지할 때 제어의 변경을 기록합니다.|

 다음 표에서는 이벤트 데이터를 보여 줍니다.

|필드 이름|데이터 형식|Description|
|----------------|---------------|-----------------|
|`AverageThroughput`|`win:Double`|측정 샘플의 평균 처리량입니다.|
|`NewWorkerThreadCount`|`win:UInt32`|새로운 활성 작업자 스레드의 수입니다.|
|`Reason`|`win:UInt32`|조정의 원인입니다.<br /><br /> `0x0` 워밍업.<br /><br /> `0x1` 도중.<br /><br /> `0x2` -임의 이동.<br /><br /> `0x3` -이동 합니다.<br /><br /> `0x4` -Point를 변경 합니다.<br /><br /> `0x5` 안정화.<br /><br /> `0x6` 고갈.<br /><br /> `0x7` -스레드 시간이 초과 되었습니다.|
|`ClrInstanceID`|`win:UInt16`|CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.|

## <a name="threadpoolworkerthreadadjustmentstats-event"></a>ThreadPoolWorkerThreadAdjustmentStats 이벤트

 다음 표에서는 키워드와 수준을 보여 줍니다.

|이벤트를 발생시키기 위한 키워드|수준|
|-----------------------------------|-----------|
|`ThreadingKeyword` (0x10000)|자세한 정보 표시(5)

 다음 표에서는 이벤트 정보를 보여 줍니다.

|이벤트|이벤트 ID|Description|
|-----------|--------------|-----------------|
|`ThreadPoolWorkerThreadAdjustmentStats`|56|스레드 풀의 데이터를 수집합니다.|

 다음 표에서는 이벤트 데이터를 보여 줍니다.

|필드 이름|데이터 형식|Description|
|----------------|---------------|-----------------|
|`Duration`|`win:Double`|이러한 통계가 수집된 시간(초)입니다.|
|`Throughput`|`win:Double`|이 간격 동안의 초당 평균 완료 수입니다.|
|`ThreadWave`|`win:Double`|내부용으로 예약된 속성입니다.|
|`ThroughputWave`|`win:Double`|내부용으로 예약된 속성입니다.|
|`ThroughputErrorEstimate`|`win:Double`|내부용으로 예약된 속성입니다.|
|`AverageThroughputErrorEstimate`|`win:Double`|내부용으로 예약된 속성입니다.|
|`ThroughputRatio`|`win:Double`|이 간격 동안 활성 작업자 스레드 수의 변화로 인해 발생한 처리량의 상대적인 증가량입니다.|
|`Confidence`|`win:Double`|ThroughputRatio 필드의 유효성 측정값입니다.|
|`NewcontrolSetting`|`win:Double`|활성 스레드 개수에서 미래의 변동에 대한 기준으로 사용될 활성 작업자 스레드 수입니다.|
|`NewThreadWaveMagnitude`|`win:UInt16`|활성 스레드 개수에서 미래 변동의 크기입니다.|
|`ClrInstanceID`|`win:UInt16`|CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.|

## <a name="threadpoolenqueue-event"></a>ThreadPoolEnqueue 이벤트

 다음 표에서는 키워드와 수준을 보여 줍니다.

|이벤트를 발생시키기 위한 키워드|수준|
|-----------------------------------|-----------|
|`ThreadingKeyword` (0x10000)|자세한 정보 표시(5)

 다음 표에서는 이벤트 정보를 보여 줍니다.

|이벤트|이벤트 ID|Description|
|-----------|--------------|-----------------|
|`ThreadPoolEnqueue`|61|스레드 풀 큐에서 작업 항목을 큐에 넣었습니다.|

 다음 표에서는 이벤트 데이터를 보여 줍니다.

|필드 이름|데이터 형식|Description|
|----------------|---------------|-----------------|
|`WorkID`|`win:Pointer`|작업 요청에 대 한 포인터입니다.|
|`ClrInstanceID`|`win:UInt16`|CoreCLR 인스턴스에 대 한 고유 ID입니다.|

## <a name="threadpooldequeue-event"></a>ThreadPoolDequeue 이벤트

 다음 표에서는 키워드와 수준을 보여 줍니다.

|이벤트를 발생시키기 위한 키워드|수준|
|-----------------------------------|-----------|
|`ThreadingKeyword` (0x10000)|자세한 정보 표시(5)

 다음 표에서는 이벤트 정보를 보여 줍니다.

|이벤트|이벤트 ID|Description|
|-----------|--------------|-----------------|
|`ThreadPoolDequeue`|62|작업 항목이 스레드 풀 큐에서 큐에서 제거 되었습니다.|

 다음 표에서는 이벤트 데이터를 보여 줍니다.

|필드 이름|데이터 형식|Description|
|----------------|---------------|-----------------|
|`WorkID`|`win:Pointer`|작업 요청에 대 한 포인터입니다.|
|`ClrInstanceID`|`win:UInt16`|CoreCLR 인스턴스에 대 한 고유 ID입니다.|

## <a name="threadpoolioenqueue-event"></a>ThreadPoolIOEnqueue 이벤트

 다음 표에서는 키워드와 수준을 보여 줍니다.

|이벤트를 발생시키기 위한 키워드|수준|
|-----------------------------------|-----------|
|`ThreadingKeyword` (0x10000)|자세한 정보 표시(5)

 다음 표에서는 이벤트 정보를 보여 줍니다.

|이벤트|이벤트 ID|Description|
|-----------|--------------|-----------------|
|`ThreadPoolIOEnqueue`|63|비동기 IO 완료가 발생 한 후에는 스레드가 IO 완료 알림을 큐 합니다.|

 다음 표에서는 이벤트 데이터를 보여 줍니다.

|필드 이름|데이터 형식|Description|
|----------------|---------------|-----------------|
|`NativeOverlapped`|`win:Pointer`|내부용으로 예약된 속성입니다.|
|`Overlapped`|`win:Pointer`|내부용으로 예약된 속성입니다.|
|`MultiDequeues`|`win:Boolean`|내부용으로 예약된 속성입니다.|
|`ClrInstanceID`|`win:UInt16`|CoreCLR 인스턴스에 대 한 고유 ID입니다.|

## <a name="threadpooliodequeue-event"></a>ThreadPoolIODequeue 이벤트

 다음 표에서는 키워드와 수준을 보여 줍니다.

|이벤트를 발생시키기 위한 키워드|수준|
|-----------------------------------|-----------|
|`ThreadingKeyword` (0x10000)|자세한 정보 표시(5)

 다음 표에서는 이벤트 정보를 보여 줍니다.

|이벤트|이벤트 ID|Description|
|-----------|--------------|-----------------|
|`ThreadPoolIODequeue`|64|스레드가 IO 완료 알림을 큐에 대기 시킵니다.|

 다음 표에서는 이벤트 데이터를 보여 줍니다.

|필드 이름|데이터 형식|Description|
|----------------|---------------|-----------------|
|`NativeOverlapped`|`win:Pointer`|내부용으로 예약된 속성입니다.|
|`Overlapped`|`win:Pointer`|내부용으로 예약된 속성입니다.|
|`MultiDequeues`|`win:Boolean`|내부용으로 예약된 속성입니다.|
|`ClrInstanceID`|`win:UInt16`|CoreCLR 인스턴스에 대 한 고유 ID입니다.|

## <a name="threadpooliopack-event"></a>ThreadPoolIOPack 이벤트

 다음 표에서는 키워드와 수준을 보여 줍니다.

|이벤트를 발생시키기 위한 키워드|수준|
|-----------------------------------|-----------|
|`ThreadingKeyword` (0x10000)|자세한 정보 표시(5)|

 다음 표에서는 이벤트 정보를 보여 줍니다.

|이벤트|이벤트 ID|Description|
|-----------|--------------|-----------------|
|`ThreadPoolIOPack`|65|ThreadPool 겹친 IO pack이 호출 됩니다.|

 다음 표에서는 이벤트 데이터를 보여 줍니다.

|필드 이름|데이터 형식|Description|
|----------------|---------------|-----------------|
|`NativeOverlapped`|`win:Pointer`|내부용으로 예약된 속성입니다.|
|`Overlapped`|`win:Pointer`|내부용으로 예약된 속성입니다.|
|`ClrInstanceID`|`win:UInt16`|CoreCLR 인스턴스에 대 한 고유 ID입니다.|

## <a name="threadcreating-event"></a>ThreadCreating 이벤트

 다음 표에서는 키워드와 수준을 보여 줍니다.

|이벤트를 발생시키기 위한 키워드|수준|
|-----------------------------------|-----------|
|`ThreadingKeyword` (0x10000)|정보(4)|

 다음 표에서는 이벤트 정보를 보여 줍니다.

|이벤트|이벤트 ID|Description|
|----------------|---------------|-----------------|
|`ThreadCreating`|70|스레드를 만들었습니다.|

 다음 표에서는 이벤트 데이터를 보여 줍니다.

|필드 이름|데이터 형식|Description|
|----------------|---------------|-----------------|
|`ID`|`win:Pointer`|스레드 ID|
|`ClrInstanceID`|`win:UInt16`|CoreCLR 인스턴스에 대 한 고유 ID입니다.|

## <a name="threadrunning-event"></a>ThreadRunning 이벤트

 다음 표에서는 키워드와 수준을 보여 줍니다.

|이벤트를 발생시키기 위한 키워드|수준|
|-----------------------------------|-----------|
|`ThreadingKeyword` (0x10000)|정보(4)|

 다음 표에서는 이벤트 정보를 보여 줍니다.

|이벤트|이벤트 ID|Description|
|----------------|---------------|-----------------|
|`ThreadRunning`|71|스레드의 실행이 시작 되었습니다.|

 다음 표에서는 이벤트 데이터를 보여 줍니다.

|필드 이름|데이터 형식|Description|
|----------------|---------------|-----------------|
|`ID`|`win:Pointer`|스레드 ID|
|`ClrInstanceID`|`win:UInt16`|CoreCLR 인스턴스에 대 한 고유 ID입니다.|
