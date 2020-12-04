---
title: Interop 런타임 이벤트
description: Interop와 관련 된 진단 정보를 수집 하는 .NET 런타임 이벤트를 참조 하세요.
ms.date: 11/13/2020
ms.topic: reference
helpviewer_keywords:
- Interop events (CoreCLR)
- ETW, EventPipe, LTTng interop events (CoreCLR)
ms.openlocfilehash: 5635fb55b3a6ffa3f5611da80cdb2909e226e2ea
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2020
ms.locfileid: "96594046"
---
# <a name="net-runtime-interop-events"></a>.NET 런타임 interop 이벤트

이러한 런타임 이벤트는 CIL (공용 중간 언어) 스텁 생성에 대 한 정보를 캡처합니다. 진단 목적으로 이러한 이벤트를 사용 하는 방법에 대 한 자세한 내용은 [.net 응용 프로그램 로깅 및 추적](../../core/diagnostics/logging-tracing.md) 을 참조 하세요.

## <a name="ilstubgenerated-event"></a>ILStubGenerated 이벤트

|이벤트를 발생시키기 위한 키워드|수준|
|-----------------------------------|-----------|
|`InteropKeyword` (0x2000)|정보 제공(4)|
  
|이벤트|이벤트 ID|발생 시기|
|-----------|--------------|-----------------|
|`ILStubGenerated`|88|IL 스텁이 생성 됩니다.|

|필드 이름|데이터 형식|Description|
|----------------|---------------|-----------------|
|`ModuleID`|`win:UInt16`|모듈 식별자입니다.|
|`StubMethodID`|`win:UInt64`|스텁 메서드 식별자입니다.|
|`StubFlags`|`win:UInt32`|스텁에 대한 플래그:<br /><br /> `0x1` -역방향 interop<br /><br /> `0x2` -COM interop 합니다.<br /><br /> `0x4` -NGen.exe에 의해 생성 된 스텁입니다.<br /><br /> `0x8` 대리자나.<br /><br /> `0x10` -변수 인수입니다.<br /><br /> `0x20` -관리 되지 않는 호출 수신자.<br /><br /> `0x40` -구조체 마샬링|
|`ManagedInteropMethodToken`|`win:UInt32`|관리되는 interop 메서드의 토큰입니다.|
|`ManagedInteropMethodNameSpace`|`win:UnicodeString`|관리 되는 interop 메서드의 네임 스페이스 및 바깥쪽 형식입니다.|
|`ManagedInteropMethodName`|`win:UnicodeString`|관리되는 interop 메서드의 이름입니다.|
|`ManagedInteropMethodSignature`|`win:UnicodeString`|관리되는 interop 메서드의 서명입니다.|
|`NativeMethodSignature`|`win:UnicodeString`|네이티브 메서드 서명입니다.|
|`StubMethodSignature`|`win:UnicodeString`|스텁 메서드 서명입니다.|
|`StubMethodILCode`|`win:UnicodeString`|스텁 메서드의 CIL (공용 중간 언어) 코드입니다.|
|`ClrInstanceID`|`win:UInt16`|CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.|
