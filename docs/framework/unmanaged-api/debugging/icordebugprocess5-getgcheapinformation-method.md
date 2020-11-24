---
title: ICorDebugProcess5::GetGCHeapInformation 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetGCHeapInformation
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetGCHeapInformation
helpviewer_keywords:
- ICorDebugProcess5::GetGCHeapInformation method [.NET Framework debugging]
- GetGCHeapInformation method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: b9538ceb-230a-4079-9cb2-903dbf5c1848
topic_type:
- apiref
ms.openlocfilehash: 43054a71445193bae7a74e0ed6785cccd1d02dc2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95670994"
---
# <a name="icordebugprocess5getgcheapinformation-method"></a>ICorDebugProcess5::GetGCHeapInformation 메서드

가비지 수집 힙에 대 한 일반 정보를 제공 합니다 (현재 열거 가능한 지 여부 포함).  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetGCHeapInformation(  
    [out] COR_HEAPINFO *pHeapInfo  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `pHeapInfo`  
 제한이 가비지 수집 힙에 대 한 일반 정보를 제공 하는 [COR_HEAPINFO](cor-heapinfo-structure.md) 값에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  

 `ICorDebugProcess5::GetGCHeapInformation`프로세스의 가비지 수집 구조가 현재 유효한 지 확인 하기 위해 힙 또는 개별 힙 영역을 열거 하기 전에 메서드를 호출 해야 합니다. 컬렉션이 진행 중인 동안에는 가비지 컬렉션 힙을 만들 수 없습니다. 그렇지 않으면 열거에서 잘못 된 가비지 수집 구조를 캡처할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorDebugProcess5 인터페이스](icordebugprocess5-interface.md)
- [디버깅 인터페이스](debugging-interfaces.md)
