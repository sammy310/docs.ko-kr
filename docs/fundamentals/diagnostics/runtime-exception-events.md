---
title: 예외 런타임 이벤트
description: 예외 및 예외 처리와 관련 된 진단 정보를 수집 하는 .NET 런타임 이벤트를 참조 하세요.
ms.date: 11/13/2020
ms.topic: reference
helpviewer_keywords:
- exception events (CoreCLR)
- exception handling events (CoreCLR)
- ETW, EventPipe, LTTng exception events (CoreCLR)
ms.openlocfilehash: f4f63c8469f9c734b872ddaec8d1d7f7f0427576
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96594105"
---
# <a name="net-runtime-exception-events"></a>.NET 런타임 예외 이벤트

이러한 런타임 이벤트는 throw 되는 예외에 대 한 정보를 캡처합니다. 진단 목적으로 이러한 이벤트를 사용 하는 방법에 대 한 자세한 내용은 [.net 응용 프로그램 로깅 및 추적](../../core/diagnostics/logging-tracing.md) 을 참조 하세요.

## <a name="exceptionthrown_v1-event"></a>ExceptionThrown_V1 이벤트

|이벤트를 발생시키기 위한 키워드|수준|
|-----------------------------------|-----------|
|`ExceptionKeyword`(0x8000)|오류 (1)|

 다음 표에서는 이벤트 정보를 보여 줍니다.

|이벤트|이벤트 ID|발생 시기|
|-----------|--------------|-----------------|
|`ExceptionThrown_V1`|80|관리되는 예외가 throw됩니다.|

|필드 이름|데이터 형식|Description|
|----------------|---------------|-----------------|
|`ExceptionType`|`win:UnicodeString`|예외 형식, 예: `System.NullReferenceException`.|
|`ExceptionMessage`|`win:UnicodeString`|실제 예외 메시지입니다.|
|`EIPCodeThrow`|`win:Pointer`|예외가 발생한 명령 포인터입니다.|
|`ExceptionHR`|`win:UInt32`|예외 [HRESULT](/openspecs/windows_protocols/ms-erref/0642cb2f-2075-4469-918c-4441e69c548a)입니다.|
|`ExceptionFlags`|`win:UInt16`|`0x01`: HasInnerException.<br /><br /> `0x02`: IsNestedException.<br /><br /> `0x04`: IsRethrownException.<br /><br /> `0x08`: IsCorruptedStateException (프로세스 상태가 손상 되었음을 나타냅니다. [손상 된 상태 예외 처리](/archive/msdn-magazine/2009/february/clr-inside-out-handling-corrupted-state-exceptions)를 참조 하세요.)<br /><br /> `0x10`: IsCLSCompliant (에서 파생 되는 예외는 <xref:System.Exception> cls 규격입니다. 그렇지 않으면 cls 규격이 아닙니다.)|
|`ClrInstanceID`|`win:UInt16`|CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.|

## <a name="exceptioncatchstart-event"></a>ExceptionCatchStart 이벤트

이 이벤트는 관리 되는 예외 catch 처리기가 시작 될 때 내보내집니다.

|이벤트를 발생시키기 위한 키워드|수준|
|-----------------------------------|-----------|
|`ExceptionKeyword`(0x8000)|정보(4)|

 다음 표에서는 이벤트 정보를 보여 줍니다.

|이벤트|이벤트 ID|발생 시기|
|-----------|--------------|-----------------|
|`ExceptionCatchStart`|250|관리 되는 예외는 런타임에 의해 처리 됩니다.|

|필드 이름|데이터 형식|Description|
|----------------|---------------|-----------------|
|`EIPCodeThrow`|`win:Pointer`|예외가 발생한 명령 포인터입니다.|
|`MethodID`|`win:Pointer`|예외가 발생 한 메서드의 메서드 설명자에 대 한 포인터입니다.|
|`MethodName`|`win:UnicodeString`|예외가 발생 한 메서드의 이름입니다.|
|`ClrInstanceID`|`win:UInt16`|CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.|

## <a name="exceptioncatchstop-event"></a>ExceptionCatchStop 이벤트

이 이벤트는 관리 되는 예외 catch 처리기가 종료 될 때 내보내집니다.

|이벤트를 발생시키기 위한 키워드|수준|
|-----------------------------------|-----------|
|`ExceptionKeyword`(0x8000)|정보(4)|

 다음 표에서는 이벤트 정보를 보여 줍니다.

|이벤트|이벤트 ID|발생 시기|
|-----------|--------------|-----------------|
|`ExceptionCatchStop`|251|관리 되는 예외 catch 처리기가 완료 되었습니다.|

## <a name="exceptionfinallystart-event"></a>ExceptionFinallyStart 이벤트

이 이벤트는 관리 되는 예외 finally 처리기가 시작 될 때 내보내집니다.

|이벤트를 발생시키기 위한 키워드|수준|
|-----------------------------------|-----------|
|`ExceptionKeyword`(0x8000)|정보(4)|

 다음 표에서는 이벤트 정보를 보여 줍니다.

|이벤트|이벤트 ID|발생 시기|
|-----------|--------------|-----------------|
|`ExceptionFinallyStart`|252|관리 되는 예외는 런타임에 의해 처리 됩니다.|

|필드 이름|데이터 형식|Description|
|----------------|---------------|-----------------|
|`EIPCodeThrow`|`win:Pointer`|예외가 발생한 명령 포인터입니다.|
|`MethodID`|`win:Pointer`|예외가 발생 한 메서드의 메서드 설명자에 대 한 포인터입니다.|
|`MethodName`|`win:UnicodeString`|예외가 발생 한 메서드의 이름입니다.|
|`ClrInstanceID`|`win:UInt16`|CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.|

## <a name="exceptionfinallystop-event"></a>ExceptionFinallyStop 이벤트

이 이벤트는 관리 되는 예외 catch 처리기가 종료 될 때 내보내집니다.

|이벤트를 발생시키기 위한 키워드|수준|
|-----------------------------------|-----------|
|`ExceptionKeyword`(0x8000)|정보(4)|

 다음 표에서는 이벤트 정보를 보여 줍니다.

|이벤트|이벤트 ID|발생 시기|
|-----------|--------------|-----------------|
|`ExceptionFinallyStop`|253|관리 되는 예외 finally 처리기가 완료 되었습니다.|

## <a name="exceptionfilterstart-event"></a>ExceptionFilterStart 이벤트

이 이벤트는 관리 되는 예외 필터링이 시작 될 때 내보내집니다.

|이벤트를 발생시키기 위한 키워드|수준|
|-----------------------------------|-----------|
|`ExceptionKeyword`(0x8000)|정보(4)|

 다음 표에서는 이벤트 정보를 보여 줍니다.

|이벤트|이벤트 ID|발생 시기|
|-----------|--------------|-----------------|
|`ExceptionFilterStart`|254|관리 되는 예외 필터링이 시작 됩니다.|

|필드 이름|데이터 형식|Description|
|----------------|---------------|-----------------|
|`EIPCodeThrow`|`win:Pointer`|예외가 발생한 명령 포인터입니다.|
|`MethodID`|`win:Pointer`|예외가 발생 한 메서드의 메서드 설명자에 대 한 포인터입니다.|
|`MethodName`|`win:UnicodeString`|예외가 발생 한 메서드의 이름입니다.|
|`ClrInstanceID`|`win:UInt16`|CoreCLR 인스턴스에 대 한 고유 ID입니다.|

## <a name="exceptionfilterstop-event"></a>ExceptionFilterStop 이벤트

이 이벤트는 관리 되는 예외 필터링이 종료 될 때 내보내집니다.

|이벤트를 발생시키기 위한 키워드|수준|
|-----------------------------------|-----------|
|`ExceptionKeyword`(0x8000)|정보(4)|

 다음 표에서는 이벤트 정보를 보여 줍니다.

|이벤트|이벤트 ID|발생 시기|
|-----------|--------------|-----------------|
|`ExceptionFilteringStart`|255|관리 되는 예외 필터링이 종료 됩니다.|

## <a name="exceptionthrownstop-event"></a>ExceptionThrownStop 이벤트

이 이벤트는 런타임에 throw 된 관리 되는 예외를 처리할 때 내보내집니다.

|이벤트를 발생시키기 위한 키워드|수준|
|-----------------------------------|-----------|
|`ExceptionKeyword`(0x8000)|정보(4)|
  
 다음 표에서는 이벤트 정보를 보여 줍니다.

|이벤트|이벤트 ID|발생 시기|
|-----------|--------------|-----------------|
|`ExceptionThrownStop`|256|관리 되는 예외 필터링이 종료 됩니다.|
