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
ms.openlocfilehash: 37659262695b63a6dd6390c62c4bb7e04fdadca4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179305"
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
  
## <a name="members"></a>구성원  
  
|멤버|Description|  
|------------|-----------------|  
|`areGCStructuresValid`|`true`가비지 수집 구조가 유효하고 힙을 열거할 수 있는 경우 그렇지 `false`않으면 .|  
|`pointerSize`|대상 아키텍처에 대한 포인터의 크기(바이트)입니다.|  
|`numHeaps`|프로세스의 논리 가비지 수집 힙 수입니다.|  
|`concurrent`|`TRUE`동시(백그라운드) 가비지 수집이 활성화된 경우 그렇지 `FALSE`않으면 .|  
|`gcType`|가비지 수집기또는 서버에서 실행 중인지 여부를 나타내는 [CorDebugGCType](cordebuggctype-enumeration.md) 열거형의 멤버입니다.|  
  
## <a name="remarks"></a>설명  
 `COR_HEAPINFO` 구조의 인스턴스는 [ICorDebugProcess5:GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) 메서드를 호출 하여 반환 됩니다.  
  
 가비지 수집 힙의 개체를 열거하기 전에 `areGCStructuresValid` 항상 필드를 확인하여 힙이 열거 가능한 상태인지 확인해야 합니다. 자세한 내용은 [ICorDebugProcess5:GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) 메서드를 참조하십시오.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [디버깅 구조체](debugging-structures.md)
- [디버깅](index.md)
