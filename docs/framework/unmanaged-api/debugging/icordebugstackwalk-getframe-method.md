---
title: ICorDebugStackWalk::GetFrame 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk.GetFrame Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk::GetFrame
helpviewer_keywords:
- GetFrame method [.NET Framework debugging]
- ICorDebugStackWalk::GetFrame method [.NET Framework debugging]
ms.assetid: 4083b505-5b59-44fb-8c5d-129db6a96c10
topic_type:
- apiref
ms.openlocfilehash: 77210edfdc954f38ff06bc43a8b41a6abe8dc3d6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131832"
---
# <a name="icordebugstackwalkgetframe-method"></a>ICorDebugStackWalk::GetFrame 메서드
[ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) 개체의 현재 프레임을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetFrame([out] ICorDebugFrame ** pFrame);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pFrame`  
 진행 스택의 현재 프레임을 나타내는 만들어진 프레임 개체의 주소에 대 한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|런타임에서 현재 프레임을 성공적으로 반환 했습니다.|  
|E_FAIL|현재 프레임이 반환 되지 않았습니다.|  
|S_FALSE|현재 프레임은 네이티브 스택 프레임입니다.|  
|E_INVALIDARG|`pFrame`가 null입니다.|  
|CORDBG_E_PAST_END_OF_STACK|프레임 포인터가 이미 스택의 끝에 있습니다. 따라서 추가 프레임에는 액세스할 수 없습니다.|  
  
## <a name="exceptions"></a>예외  
  
## <a name="remarks"></a>주의  
 `ICorDebugStackWalk`는 실제 스택 프레임만 반환 합니다. [ICorDebugThread3:: GetActiveInternalFrames](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-getactiveinternalframes-method.md) 메서드를 사용 하 여 내부 프레임을 반환 합니다. 내부 프레임은 런타임에서 임시 데이터를 저장 하기 위해 스택에 푸시되는 데이터 구조입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorDebugStackWalk 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)
- [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [디버깅](../../../../docs/framework/unmanaged-api/debugging/index.md)
