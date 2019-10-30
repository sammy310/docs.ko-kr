---
title: ICorDebugProcess5::EnumerateHeap 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.EnumerateHeap
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnumerateHeap
helpviewer_keywords:
- EnumerateHeap method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateHeap method [.NET Framework debugging]
ms.assetid: b0192104-6073-4089-a4df-dc29ee033074
topic_type:
- apiref
ms.openlocfilehash: c8cfc9cdf6580a002f6ac15080012a9e8c63be20
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129657"
---
# <a name="icordebugprocess5enumerateheap-method"></a>ICorDebugProcess5::EnumerateHeap 메서드
관리 되는 힙의 개체에 대 한 열거자를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT EnumerateHeap(  
    [out] ICorDebugHeapEnum **ppObjects  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `ppObject`  
 제한이 관리 되는 힙에 있는 개체의 열거자 인 [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) interface 개체의 주소에 대 한 포인터입니다.  
  
## <a name="remarks"></a>주의  
 `ICorDebugProcess5::EnumerateHeap` 메서드를 호출 하기 전에 [ICorDebugProcess5:: GetGCHeapInformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) 메서드를 호출 하 고 반환 된 [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) 개체의 `areGCStructuresValid` 필드 값을 검사 하 여 해당 개체의 가비지 수집 힙이 현재 상태는 열거 가능 합니다. 또한 관리 되는 힙의 메모리를 할당 하기 전에 프로세스의 수명 동안 너무 일찍 연결 하는 경우에는 `ICorDebugProcess5::EnumerateHeap` `E_FAIL`를 반환 합니다.  
  
 [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) interface 개체는 ICorDebugEnum 인터페이스에서 파생 된 표준 열거자로, [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) 개체를 열거 하는 데 사용할 수 있습니다. 이 메서드는 모든 개체에 대 한 정보를 제공 하는 [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) 인스턴스로 [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) collection 개체를 채웁니다. 컬렉션에는 개체에 의해 루 지는 않지만 가비지 수집기에서 아직 수집 되지 않은 개체에 대 한 정보를 제공 하는 [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) 인스턴스가 포함 될 수도 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorDebugProcess5 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
