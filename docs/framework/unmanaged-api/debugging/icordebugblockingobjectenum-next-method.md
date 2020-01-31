---
title: ICorDebugBlockingObjectEnum::Next 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugBlockingObjectEnum.Next Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBlockingObjectEnum::Next
helpviewer_keywords:
- Next method, ICorDebugBlockingObjectEnum interface [.NET Framework debugging]
- ICorDebugBlockingObjectEnum::Next method [.NET Framework debugging]
ms.assetid: 0121753f-ebea-48d0-aeb2-ed7fda76dc60
topic_type:
- apiref
ms.openlocfilehash: c25f26bb0f1f34e3799bab4bec7e697d393cccb4
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784522"
---
# <a name="icordebugblockingobjectenumnext-method"></a>ICorDebugBlockingObjectEnum::Next 메서드
현재 위치에서 시작 하 여 열거형에서 지정 된 수의 [CorDebugBlockingObject](cordebugblockingobject-structure.md) 개체를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT Next([in] ULONG  celt,  
             [out, size_is(celt), length_is(*pceltFetched)]  
                           CorDebugBlockingObject values[],  
             [out] ULONG *pceltFetched;  
```  
  
## <a name="parameters"></a>매개 변수  
 `celt`  
 진행 검색할 개체의 수입니다.  
  
 `values`  
 제한이 [CorDebugBlockingObject](cordebugblockingobject-structure.md) 개체에 대 한 포인터의 배열입니다.  
  
 `pceltFetched`  
 제한이 검색 된 개체의 수에 대 한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 다음과 같은 특정 HRESULT를 반환합니다.  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|메서드가 성공적으로 완료되었습니다.|  
|S_FALSE|`pceltFetched`이 `celt`와 다른 경우|  
  
## <a name="remarks"></a>주의  
 이 메서드는 일반적인 COM 열거자 처럼 작동 합니다.  
  
 입력 배열 값의 크기는 `celt`이상 이어야 합니다. 배열은 열거형의 다음 `celt` 값으로 채워지거나 `celt` 보다 작은 경우에는 나머지 모든 값으로 채워집니다. 이 메서드가 반환 될 때 `pceltFetched`은 검색 된 값의 수로 채워집니다. `values`에 `celt`보다 작은 버퍼에 대 한 잘못 된 포인터나 점이 있거나 `pceltFetched` 잘못 된 포인터인 경우 결과가 정의 되지 않습니다.  
  
> [!NOTE]
> [CorDebugBlockingObject](cordebugblockingobject-structure.md) 구조를 해제할 필요는 없지만 그 안에 있는 "ICorDebugValue" 인터페이스를 해제 해야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorDebugDataTarget 인터페이스](icordebugdatatarget-interface.md)
- [디버깅 인터페이스](debugging-interfaces.md)
- [디버깅](index.md)
