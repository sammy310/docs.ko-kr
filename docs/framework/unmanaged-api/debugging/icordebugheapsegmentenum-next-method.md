---
title: ICorDebugHeapSegmentEnum::Next 메서드
ms.date: 03/30/2017
api_name:
- Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapSegmentEnum::Next
helpviewer_keywords:
- ICorDebugHeapSegmentEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugHeapSegmentEnum interface [.NET Framework debugging]
ms.assetid: 51625fd0-7399-49c7-b22b-5dfb05451fe6
topic_type:
- apiref
ms.openlocfilehash: 89ce4eafa46be3e9ba7cdb06884034a521e43bca
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777532"
---
# <a name="icordebugheapsegmentenumnext-method"></a>ICorDebugHeapSegmentEnum::Next 메서드
관리 되는 힙의 메모리 영역에 대 한 정보를 포함 하는 지정 된 수의 [COR_HEAPOBJECT](cor-heapobject-structure.md) 인스턴스를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_SEGMENT segments[],   
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 celt  
 진행 검색할 세그먼트 수입니다.  
  
 세그먼트  
 제한이 각각 관리 되는 힙에서 메모리 영역에 대 한 정보를 제공 하는 [COR_HEAPOBJECT](cor-heapobject-structure.md) 개체를 가리키는 포인터의 배열입니다.  
  
 pceltFetched  
 제한이 `segments`에서 실제로 반환 된 [COR_HEAPOBJECT](cor-heapobject-structure.md) 개체 수에 대 한 포인터입니다. `celt`가 1이면 이 값은 `null`일 수 있습니다.  
  
## <a name="remarks"></a>주의  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorDebugHeapSegmentEnum 인터페이스](icordebugheapsegmentenum-interface.md)
- [디버깅 인터페이스](debugging-interfaces.md)
