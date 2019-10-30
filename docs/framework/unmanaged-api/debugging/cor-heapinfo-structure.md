---
title: COR_HEAPINFO 구조체
ms.date: 03/30/2017
api_name:
- COR_HEAPINFO
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_HEAPINFO
helpviewer_keywords:
- COR_HEAPINFO structure [.NET Framework debugging]
ms.assetid: bfb2cd39-3e0b-4d51-ba0c-f009755c1456
topic_type:
- apiref
ms.openlocfilehash: b6fd3682290c9752125aed7b9663c6704ade25de
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132329"
---
# <a name="cor_heapinfo-structure"></a>COR_HEAPINFO 구조체
가비지 수집 힙에 대한 일반 정보(열거 가능 여부 포함)를 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef struct _COR_HEAPINFO {  
    BOOL areGCStructuresValid;   
    DWORD pointerSize;   
    DWORD numHeaps;  
    BOOL concurrent;   
    CorDebugGCType gcType;   
} COR_HEAPINFO;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`areGCStructuresValid`|가비지 수집 구조가 유효 하 고 힙을 열거할 수 있는지 여부를 `true` 합니다. 그렇지 않으면 `false`합니다.|  
|`pointerSize`|대상 아키텍처에 대 한 포인터의 크기 (바이트)입니다.|  
|`numHeaps`|프로세스의 논리적 가비지 수집 힙 수입니다.|  
|`concurrent`|동시 (백그라운드) 가비지 수집을 사용 하는 경우 `TRUE` 합니다. 그렇지 않으면 `FALSE`합니다.|  
|`gcType`|가비지 수집기가 워크스테이션 또는 서버에서 실행 중인지 여부를 나타내는 [CorDebugGCType](cordebuggctype-enumeration.md) 열거의 멤버입니다.|  
  
## <a name="remarks"></a>주의  
 [ICorDebugProcess5:: GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) 메서드를 호출 하 여 `COR_HEAPINFO` 구조체의 인스턴스를 반환 합니다.  
  
 가비지 컬렉션 힙에서 개체를 열거 하기 전에 항상 `areGCStructuresValid` 필드를 확인 하 여 힙이 열거 가능한 상태 인지 확인 해야 합니다. 자세한 내용은 [ICorDebugProcess5:: GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) 메서드를 참조 하세요.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참조

- [디버깅 구조체](debugging-structures.md)
- [디버깅](index.md)
