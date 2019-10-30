---
title: ICorDebugNativeFrame2::GetStackParameterSize 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame2.GetStackParameterSize Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame2::GetStackParameterSize
helpviewer_keywords:
- ICorDebugNativeFrame2::GetStackParameterSize method [.NET Framework debugging]
- GetStackParameterSize method [.NET Framework debugging]
ms.assetid: f6a449c8-a941-43ba-9a90-c98b29ae3c36
topic_type:
- apiref
ms.openlocfilehash: 4dd9760c347bbc23f3e8225c1ff748c6b7b8bfe1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73096534"
---
# <a name="icordebugnativeframe2getstackparametersize-method"></a>ICorDebugNativeFrame2::GetStackParameterSize 메서드
X86 운영 체제의 스택에 있는 매개 변수의 누적 크기를 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetStackParameterSize([out] ULONG32 * pSize)  
```  
  
## <a name="parameters"></a>매개 변수  
 `pSize`  
 제한이 스택에 있는 매개 변수의 누적 크기에 대 한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|스택 크기가 성공적으로 반환 되었습니다.|  
|S_FALSE|x86 이외의 플랫폼에서 `GetStackParameterSize`가 호출 되었습니다.|  
|E_FAIL|`The size of the parameters could not be returned`|  
|E_INVALIDARG|`pSize` `null`입니다.|  
  
## <a name="exceptions"></a>예외  
  
## <a name="remarks"></a>주의  
 [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) 메서드는 스택에 푸시되는 매개 변수에 대 한 스택 포인터를 조정 하지 않습니다. 대신 `GetStackParameterSize`에서 반환 하는 값을 사용 하 여 스택 포인터를 조정 하 여 기본 해제기 초기값을 설정할 수 있습니다 .이는 매개 변수를 조정 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorDebugNativeFrame2 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-interface.md)
- [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [디버깅](../../../../docs/framework/unmanaged-api/debugging/index.md)
