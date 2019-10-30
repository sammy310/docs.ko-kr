---
title: ICorDebugStackWalk::SetContext 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk.SetContext Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk::SetContext
helpviewer_keywords:
- SetContext method [.NET Framework debugging]
- ICorDebugStackWalk::SetContext method [.NET Framework debugging]
ms.assetid: bac0b156-31a3-4e7f-be4d-ab21789c81f1
topic_type:
- apiref
ms.openlocfilehash: 90156152a2c133446dedbe22426785ab63f8dfb9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131807"
---
# <a name="icordebugstackwalksetcontext-method"></a>ICorDebugStackWalk::SetContext 메서드
[ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) 개체의 현재 컨텍스트를 스레드의 올바른 컨텍스트로 설정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetContext([in] CorDebugSetContextFlag flag,  
                   [in] ULONG32 contextSize,  
                   [in, size_is(contextSize)] BYTE context[]);  
```  
  
## <a name="parameters"></a>매개 변수  
 `flag`  
 진행 컨텍스트가 스택의 활성 프레임에서 온 것인지 아니면 스택을 해제 하 여 얻은 컨텍스트를 가져왔는지 나타내는 [Cordebugsetcontextflag](../../../../docs/framework/unmanaged-api/debugging/cordebugsetcontextflag-enumeration.md) 플래그입니다.  
  
 `contextSize`  
 진행 할당 된 `CONTEXT` 버퍼 크기입니다.  
  
 `context`  
 진행 `CONTEXT` 버퍼입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|`ICorDebugStackWalk` 개체의 컨텍스트가 성공적으로 설정 되었습니다.|  
|E_FAIL|`ICorDebugStackWalk` 개체의 컨텍스트가 설정 되지 않았습니다.|  
|E_INVALIDARG|컨텍스트가 null 인 경우|  
|HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)|컨텍스트 버퍼가 너무 작습니다.|  
  
## <a name="exceptions"></a>예외  
  
## <a name="remarks"></a>주의  
 이 메서드는 스레드의 현재 컨텍스트를 변경 하지 않습니다.  
  
 현재 컨텍스트를 잘못 된 컨텍스트로 설정 하면 stack walker에서 예기치 않은 결과가 발생할 수 있습니다.  
  
 [ICorDebugStackWalk:: GetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md) 메서드를 즉시 호출 하 여이 컨텍스트의 정확한 비트 복사를 검색할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참조

- [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [디버깅](../../../../docs/framework/unmanaged-api/debugging/index.md)
