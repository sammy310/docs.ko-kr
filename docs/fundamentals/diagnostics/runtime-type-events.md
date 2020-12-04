---
title: 형식 시스템 런타임 이벤트
description: '.NET 형식 시스템과 관련 된 진단 정보를 수집 하는 .NET 런타임 이벤트 (예: TypeLoadStart 및 Typeloadstart)를 참조 하세요.'
ms.date: 11/13/2020
ms.topic: reference
helpviewer_keywords:
- type system events (CoreCLR)
- ETW, EventPipe, LTTng type system events (CoreCLR)
ms.openlocfilehash: 8eee89cddb0098da2cb449a4be21945adac725e3
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2020
ms.locfileid: "96594039"
---
# <a name="net-runtime-type-events"></a>.NET 런타임 형식 이벤트

이러한 이벤트는 형식 로드와 관련 된 정보를 수집 합니다. 진단 목적으로 이러한 이벤트를 사용 하는 방법에 대 한 자세한 내용은 [.net 응용 프로그램 로깅 및 추적](../../core/diagnostics/logging-tracing.md) 을 참조 하세요.

## <a name="typeloadstart-event"></a>TypeLoadStart 이벤트

|이벤트를 발생시키기 위한 키워드|이벤트|수준|  
|-----------------------------------|-----------|-----------|  
|`TypeDiagnosticKeyword` (0x8000000000)|정보(4)|  

|이벤트|이벤트 ID|Description|  
|-----------|--------------|-----------------|  
|`TypeLoadStart`|73|유형 로드가 시작 되었습니다.|

|필드 이름|데이터 형식|Description|  
|----------------|---------------|-----------------|  
|`TypeLoadStartID`|`win:UInt32`|유형 로드 작업의 ID입니다.|
|`ClrInstanceID`|`win:UInt16`|CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.|  

## <a name="typeloadstop-event"></a>TypeLoadStop 이벤트

|이벤트를 발생시키기 위한 키워드|수준|  
|-----------------------------------|-----------|-----------|  
|`TypeDiagnosticKeyword` (0x8000000000)|정보(4)|  

|이벤트|이벤트 ID|Description|  
|-----------|--------------|-----------------|  
|`TypeLoadStop`|74|유형 로드가 완료 되었습니다.|

|필드 이름|데이터 형식|Description|  
|----------------|---------------|-----------------|  
|`TypeLoadStartID`|`win:UInt32`|유형 로드 작업의 ID입니다. 해당 TypeLoadStart 이벤트의 TypeLoadStartID와 일치 합니다.|
|`LoadLevel`|`win:UInt16`|로드 수준을 입력 합니다.|
|`TypeID`|`win:UInt64`|형식 핸들에 대 한 포인터입니다.|
|`TypeName`|`win:UnicodeString`|형식의 이름입니다.|
|`ClrInstanceID`|`win:UInt16`|CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.|  
