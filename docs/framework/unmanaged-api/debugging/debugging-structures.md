---
title: 디버깅 구조체
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged structures [.NET Framework], debugging
- debugging structures [.NET Framework]
- structures [.NET Framework debugging]
ms.assetid: 173ba2c2-ab34-49ae-b6a8-e5c49882bf05
ms.openlocfilehash: a18094fb2621478dbdb4bbf672df436234112ed0
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793749"
---
# <a name="debugging-structures"></a>디버깅 구조체

이 섹션에서는 디버깅 API에서 사용하는 관리되지 않는 구조체에 대해 설명합니다.

## <a name="in-this-section"></a>섹션 내용
 [CLRDATA_ADDRESS_RANGE 구조체](clrdata-address-range-structure.md) 주소 범위를 정의 합니다.

 [CLRDATA_IL_ADDRESS_MAP 구조체](clrdata-il-address-map-structure.md) 매핑을 처리할 IL을 정의 합니다.

 [CLR_DEBUGGING_VERSION 구조체](clr-debugging-version-structure.md) 디버깅 목적으로 CLR (공용 언어 런타임)의 제품 버전을 정의 합니다.

 [CodeChunkInfo 구조체](codechunkinfo-structure.md) 메모리의 단일 코드 청크를 나타냅니다.

 [COR_ACTIVE_FUNCTION](cor-active-function-structure.md) 스레드의 프레임에서 현재 활성화 된 함수에 대 한 정보를 포함 합니다.

 [COR_ARRAY_LAYOUT 구조체](cor-array-layout-structure.md) 메모리에 있는 배열 개체의 레이아웃에 대 한 정보를 제공 합니다.

 [COR_DEBUG_IL_TO_NATIVE_MAP](cor-debug-il-to-native-map-structure.md) MSIL (Microsoft 중간 언어) 코드를 네이티브 코드에 매핑하는 데 사용 되는 오프셋을 포함 합니다.

 [COR_DEBUG_STEP_RANGE](cor-debug-step-range-structure.md) 코드 범위에 대 한 오프셋 정보를 포함 합니다.

 [COR_FIELD 구조체](cor-field-structure.md) 개체의 필드에 대 한 정보를 제공 합니다.

 [COR_GC_REFERENCE 구조체](cor-gc-reference-structure.md) 가비지 수집 되는 개체에 대 한 정보를 포함 합니다.

 [COR_HEAPINFO 구조체](cor-heapinfo-structure.md) 열거 가능한 지 여부를 비롯 하 여 가비지 컬렉션 힙에 대 한 일반 정보를 제공 합니다.

 [COR_HEAPOBJECT 구조체](cor-heapobject-structure.md) 관리 되는 힙의 개체에 대 한 정보를 제공 합니다.

 [COR_IL_MAP](cor-il-map-structure.md) 함수의 상대 오프셋에 대 한 변경 내용을 지정 합니다.

 [COR_SEGMENT 구조체](cor-segment-structure.md) 관리 되는 힙의 메모리 영역에 대 한 정보를 포함 합니다.

 [COR_TYPEID 구조체](cor-typeid-structure.md) 형식 식별자를 포함 합니다.

 [COR_TYPE_LAYOUT 구조체](cor-type-layout-structure.md) 메모리에 있는 개체의 레이아웃에 대 한 정보를 제공 합니다.

 [COR_VERSION](cor-version-structure.md) 공용 언어 런타임의 네 부분으로 구성 된 표준 버전 번호를 저장 합니다.

 [CorDebugBlockingObject 구조체](cordebugblockingobject-structure.md) 스레드를 차단 하는 개체와 스레드가 차단 되는 이유를 정의 합니다.

 [CorDebugEHClause 구조체](cordebugehclause-structure.md) 지정 된 IL (중간 언어) 부분에 대 한 EH (예외 처리) 절을 나타냅니다.

 [Cordebugexceptionobjectstackframe 구조체](cordebugexceptionobjectstackframe-structure.md) 예외 개체의 스택 프레임 정보를 나타냅니다.

 [CorDebugGuidToTypeMapping 구조체](cordebugguidtotypemapping-structure.md) Windows 런타임 GUID를 해당 [ICorDebugType](icordebugtype-interface.md) 개체에 매핑합니다.

 [DacpGetModuleAddress 구조체](dacpgetmoduleaddress-structure.md) 모듈 주소 요청에 대 한 컨테이너를 정의 합니다.

 [DacpMethodDescData 구조체](dacpmethoddescdata-structure.md) 메서드의 런타임 정보에 대 한 전송 버퍼를 정의 합니다.

 [DacpModuleData 구조체](dacpmoduledata-structure.md) 모듈의 런타임 정보에 대 한 전송 버퍼를 정의 합니다.

 [DacpReJitData 구조체](dacprejitdata-structure.md) 지정 된 프로파일러 계측 된 메서드에 대 한 기본 정보를 정의 합니다.

 [StackTrace_SimpleContext 구조체](stacktrace-simplecontext-structure.md) 전체 `CONTEXT` 구조 대신 사용할 수 있는 간단한 컨텍스트를 제공 합니다.

## <a name="related-sections"></a>관련 섹션

 [디버깅 Coclass](debugging-coclasses.md)

 [디버깅 인터페이스](debugging-interfaces.md)

 [디버깅 전역 정적 함수](debugging-global-static-functions.md)

 [디버깅 열거형](debugging-enumerations.md)

 [디버깅](index.md)
