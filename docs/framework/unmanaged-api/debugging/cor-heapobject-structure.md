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
ms.openlocfilehash: efb3d913e1d8ef0c486d7e5e1d9777ae7d88bc71
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179332"
---
# <a name="cor_heapobject-structure"></a>COR_HEAPOBJECT 구조체
관리되는 힙의 개체에 대한 정보를 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef struct _COR_HEAPOBJECT {  
    CORDB_ADDRESS address;
    ULONG64 size;
    COR_TYPEID type;
} COR_HEAPOBJECT;  
```  
  
## <a name="members"></a>구성원  
  
|멤버|Description|  
|------------|-----------------|  
|`address`|메모리에 있는 개체의 주소입니다.|  
|`size`|개체의 총 크기(바이트)입니다.|  
|`type`|개체의 형식을 나타내는 [COR_TYPEID](cor-typeid-structure.md) 토큰입니다.|  
  
## <a name="remarks"></a>설명  
 `COR_HEAPOBJECT`인스턴스는 [ICorDebugProcess5::열거Heap](icordebugprocess5-enumerateheap-method.md) 메서드를 호출하여 채워진 [ICorDebugHeapEnum](icordebugheapenum-interface.md) 인터페이스 개체를 열거하여 검색할 수 있습니다.  
  
 인스턴스는 `COR_HEAPOBJECT` 관리되는 힙의 라이브 개체또는 개체에 의해 루팅되지 않지만 가비지 수집기에서 아직 수집되지 않은 개체에 대한 정보를 제공합니다.  
  
 더 나은 성능을 `COR_HEAPOBJECT.address` 위해 `CORDB_ADDRESS` 필드는 디버깅 API의 대부분에 사용되는 ICorDebugValue 인터페이스 값이 아닌 값입니다. 지정된 개체 주소에 대한 ICorDebugValue 개체를 가져오려면 `CORDB_ADDRESS` [값을 ICorDebugProcess5:GetObject](icordebugprocess5-getobject-method.md) 메서드에 전달할 수 있습니다.  
  
 더 나은 성능을 `COR_HEAPOBJECT.type` 위해 `COR_TYPEID` 필드는 디버깅 API의 대부분에 사용되는 ICorDebugType 인터페이스 값이 아니라 값입니다. 지정된 형식 ID에 대한 ICorDebugType 개체를 가져오려면 `COR_TYPEID` [값을 ICorDebugProcess5:GetTypeForTypeID](icordebugprocess5-gettypefortypeid-method.md) 메서드에 전달할 수 있습니다.  
  
 구조에는 `COR_HEAPOBJECT` 참조 계수 COM 인터페이스가 포함됩니다. `COR_HEAPOBJECT` [ICorDebugHeapEnum::Next](icordebugheapenum-next-method.md) 메서드를 호출하여 열거자에서 인스턴스를 검색하는 경우 이후에 참조를 해제해야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [디버깅 구조체](debugging-structures.md)
- [디버깅](index.md)
