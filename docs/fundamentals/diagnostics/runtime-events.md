---
title: 런타임 이벤트
description: ETW, LTTng 또는 EventPipe에서 사용할 수 있는 .NET runtime (CoreCLR)에서 내보낸 진단 이벤트를 검토 합니다.
ms.date: 11/13/2020
ms.topic: reference
helpviewer_keywords:
- runtime events (CoreCLR)
- ETW, EventPipe runtime events (CoreCLR)
ms.openlocfilehash: 33fa7275ce40934ce043b4d0dba5749c37515755
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2020
ms.locfileid: "96594051"
---
# <a name="net-runtime-events"></a>.NET 런타임 이벤트

CoreCLR (.NET 런타임)은, 및와 같은 다양 한 메커니즘을 통해 사용 될 수 있는 .NET 응용 프로그램의 문제를 진단 하는 데 사용할 수 있는 다양 한 이벤트를 내보냅니다 `ETW` `LTTng` `EventPipe` .

이 문서는 .NET Core 런타임에서 발생 하는 이벤트에 대 한 참조로 사용 됩니다.

.NET Framework의 런타임 이벤트는 [CLR ETW 이벤트](../../framework/performance/clr-etw-events.md)를 참조 하세요.

## <a name="in-this-section"></a>섹션 내용

[경합 이벤트](runtime-contention-events.md)\
이러한 이벤트는 모니터 잠금 경합에 대 한 정보를 수집 합니다.

[가비지 수집 이벤트](runtime-garbage-collection-events.md)\
이들 이벤트는 가비지 수집과 관련된 정보를 수집합니다. 가비지 수집 수행 횟수, 가비지 수집 중에 해제 된 메모리 양 등을 확인 하는 등 진단 및 디버깅에 도움이 됩니다.

[예외 이벤트](runtime-exception-events.md)\
이러한 런타임 이벤트는 throw 되는 예외에 대 한 정보를 캡처합니다.

[Interop 이벤트](runtime-interop-events.md)\
이러한 런타임 이벤트는 CIL (공용 중간 언어) 스텁 생성에 대 한 정보를 캡처합니다.

[로더 및 바인더 이벤트](runtime-loader-binder-events.md)\
이러한 이벤트는 어셈블리 및 모듈 로드 및 언로드와 관련 된 정보를 수집 합니다.

[메서드 이벤트](runtime-method-events.md)\
이들 이벤트는 메서드와 관련된 정보를 수집합니다. 이들 이벤트의 페이로드는 기호 확인을 위해 필요합니다. 또한 이들 이벤트는 메서드를 호출한 횟수와 같은 유용한 정보를 제공합니다.

[스레드 이벤트](runtime-thread-events.md)\
이러한 이벤트는 작업자 스레드 및 I/O 스레드에 대한 정보를 수집합니다.

[유형 이벤트](runtime-type-events.md)\
이러한 이벤트는 형식 시스템에 대 한 정보를 수집 합니다.
