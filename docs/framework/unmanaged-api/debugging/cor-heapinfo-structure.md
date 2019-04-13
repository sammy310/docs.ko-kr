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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 23bda470b8b5812b567081ba268ad503ac39ecaa
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59090357"
---
# <a name="corheapinfo-structure"></a>COR_HEAPINFO 구조체
가비지 수집 힙에 대한 일반 정보(열거 가능 여부 포함)를 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```  
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
|`areGCStructuresValid`|`true` 가비지 수집 구조 유효 하 고 힙을 열거할 수 있습니다. 그렇지 않으면 `false`합니다.|  
|`pointerSize`|대상 아키텍처에 대 한 포인터의 바이트 크기입니다.|  
|`numHeaps`|프로세스에 힙 논리 가비지 수집 횟수입니다.|  
|`concurrent`|`TRUE` 동시 경우 (백그라운드) 가비지 컬렉션이 설정 되었는지; 그렇지 않으면 `FALSE`합니다.|  
|`gcType`|멤버는 [CorDebugGCType](../../../../docs/framework/unmanaged-api/debugging/cordebuggctype-enumeration.md) 워크스테이션 또는 서버에서 가비지 수집기가 실행 중인지 여부를 나타내는 열거형입니다.|  
  
## <a name="remarks"></a>설명  
 인스턴스를 `COR_HEAPINFO` 구조 호출에서 반환 되는 [ICorDebugProcess5::GetGCHeapInformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) 메서드.  
  
 가비지 컬렉션 힙에 개체를 열거 하기 전에 항상 체크 합니다 `areGCStructuresValid` 필드 힙을 열거 가능한 상태 인지 확인 합니다. 자세한 내용은 참조는 [ICorDebugProcess5::GetGCHeapInformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) 메서드.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [디버깅 구조체](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [디버깅](../../../../docs/framework/unmanaged-api/debugging/index.md)
