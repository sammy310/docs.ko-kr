---
title: COR_HEAPOBJECT 구조체
ms.date: 03/30/2017
api_name:
- COR_HEAPOBJECT
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_HEAPOBJECT
helpviewer_keywords:
- COR_HEAPOBJECT structure [.NET Framework debugging]
ms.assetid: a92fdf95-492b-49ae-a741-2186e5c1d7c5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f179b58ff8eb51e2843780d3212cf38ed7d13216
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61609452"
---
# <a name="corheapobject-structure"></a>COR_HEAPOBJECT 구조체
관리되는 힙의 개체에 대한 정보를 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef struct _COR_HEAPOBJECT {  
    CORDB_ADDRESS address;    
    ULONG64 size;             
    COR_TYPEID type;          
} COR_HEAPOBJECT;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`address`|메모리에 있는 개체의 주소입니다.|  
|`size`|총 크기 (바이트)는 개체입니다.|  
|`type`|A [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) 개체의 형식을 나타내는 토큰입니다.|  
  
## <a name="remarks"></a>설명  
 `COR_HEAPOBJECT` 인스턴스를 열거 하 여 검색할 수는 [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) 를 호출 하 여 채워지는 인터페이스 개체를 [ICorDebugProcess5::EnumerateHeap](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheap-method.md) 메서드.  
  
 `COR_HEAPOBJECT` 인스턴스 또는 관리 되는 힙에 대 한 활성 개체에 대 한 모든 개체에서 루 팅 되지 않지만 가비지 수집기에 의해 아직 수집 되지 않았습니다 하는 개체에 대 한 정보를 제공 합니다.  
  
 성능 향상을 위해 합니다 `COR_HEAPOBJECT.address` 필드는는 `CORDB_ADDRESS` 는 ICorDebugValue이 아닌 값 인터페이스 디버깅 API의 대부분에서 사용 되는 값입니다. ICorDebugValue 개체에 지정 된 개체 주소를 가져오려면 전달할 수 있습니다 합니다 `CORDB_ADDRESS` 값을 [ICorDebugProcess5::GetObject](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getobject-method.md) 메서드.  
  
 성능 향상을 위해 합니다 `COR_HEAPOBJECT.type` 필드는는 `COR_TYPEID` ICorDebugType이 아닌 값 인터페이스 디버깅 API의 대부분에서 사용 되는 값입니다. ICorDebugType 개체로 지정 된 형식 id를 가져오려면 전달할 수 있습니다 합니다 `COR_TYPEID` 값을 [ICorDebugProcess5::GetTypeForTypeID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md) 메서드.  
  
 `COR_HEAPOBJECT` 구조 참조 횟수가 계산 되는 COM 인터페이스를 포함 합니다. 검색 하는 경우는 `COR_HEAPOBJECT` 를 호출 하 여 열거자 인스턴스를 [icordebugheapenum:: Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-next-method.md) 메서드를 이후에 대 한 참조를 해제 해야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [디버깅 구조체](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [디버깅](../../../../docs/framework/unmanaged-api/debugging/index.md)
