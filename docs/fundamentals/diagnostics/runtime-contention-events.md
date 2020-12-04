---
title: 잠금 경합 런타임 이벤트 모니터링
description: 모니터 잠금 경합에 대 한 정보를 수집 하는 ETW 이벤트를 참조 하세요.
ms.date: 11/13/2020
ms.topic: reference
helpviewer_keywords:
- monitor lock contention events (CoreCLR)
- ETW, EventPipe, LTTng contention events (CoreCLR)
ms.openlocfilehash: 38e5f493d4b223b4839dbd6f814cf656722189b2
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2020
ms.locfileid: "96594052"
---
# <a name="net-runtime-contention-events"></a>.NET 런타임 경합 이벤트

이러한 런타임 이벤트는 `Monitor.Enter` 또는 c # lock 키워드와 같은 모니터 잠금 경합에 대 한 정보를 캡처합니다. 진단 목적으로 이러한 이벤트를 사용 하는 방법에 대 한 자세한 내용은 [.net 응용 프로그램 로깅 및 추적](../../core/diagnostics/logging-tracing.md) 을 참조 하세요.

## <a name="contentionstart_v1-event"></a>ContentionStart_V1 이벤트

이 이벤트는 모니터 잠금 경합이 시작 될 때 내보내집니다.

|이벤트를 발생시키기 위한 키워드|수준|
|-----------------------------------|-----------|
|`ContentionKeyword`(0x4000)|정보(4)|

 다음 표에서는 이벤트 정보를 보여 줍니다.

|이벤트|이벤트 ID|발생 시기|
|-----------|--------------|-----------------|
|`ContentionStart_V1`|81|모니터 잠금 경합이 시작 됩니다.|

|필드 이름|데이터 형식|Description|
|----------------|---------------|-----------------|
|`Flags`|`win:UInt8`|`0` 관리 되는 경우 `1` 네이티브의 경우|
|`ClrInstanceID`|`win:UInt16`|CoreCLR 인스턴스에 대 한 고유 ID입니다.|

## <a name="contentionstop_v1-event"></a>ContentionStop_V1 이벤트

이 이벤트는 모니터 잠금 경합이 끝날 때 내보내집니다.

|이벤트를 발생시키기 위한 키워드|수준|
|-----------------------------------|-----------|
|`ContentionKeyword`(0x4000)|정보(4)|

 다음 표에서는 이벤트 정보를 보여 줍니다.

|이벤트|이벤트 ID|발생 시기|
|-----------|--------------|-----------------|
|`ContentionStop_V1`|91|모니터 잠금 경합이 종료 됩니다.|

|필드 이름|데이터 형식|Description|
|----------------|---------------|-----------------|
|`Flags`|`win:UInt8`|`0` 관리 되는 경우 `1` 네이티브의 경우|
|`ClrInstanceID`|`win:UInt16`|CoreCLR 인스턴스에 대 한 고유 ID입니다.|
|`DurationNs`|`win:Double`|경합의 시간 (나노초)입니다.|
