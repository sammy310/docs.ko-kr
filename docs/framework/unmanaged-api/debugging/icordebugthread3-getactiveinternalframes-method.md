---
title: ICorDebugThread3::GetActiveInternalFrames 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugThread3.GetActiveInternalFrames Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread3::GetActiveInternalFrames
helpviewer_keywords:
- ICorDebugThread3::GetActiveInternalFrames method [.NET Framework debugging]
- GetActiveInternalFrames method [.NET Framework debugging]
ms.assetid: d69796b4-5b6d-457c-85f6-2cf42e8a8773
topic_type:
- apiref
ms.openlocfilehash: 25cd3e05bc80dd39d2ca558bb4dd5fb77d255f5a
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791406"
---
# <a name="icordebugthread3getactiveinternalframes-method"></a>ICorDebugThread3::GetActiveInternalFrames 메서드
스택에서 내부 프레임 ([ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) 개체)의 배열을 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp 
HRESULT GetActiveInternalFrames  
      (  
      [in] ULONG32 cInternalFrames,  
      [out] ULONG32 *pcInternalFrames,  
      [in, out,size_is(cInternalFrames), length_is(*pcInternalFrames)]  
            ICorDebugInternalFrame2 * ppInternalFrames[]  
      );  
```  
  
## <a name="parameters"></a>매개 변수  
 `cInternalFrames`  
 진행 `ppInternalFrames`에 필요한 내부 프레임 수입니다.  
  
 `pcInternalFrames`  
 제한이 스택의 내부 프레임 수를 포함 하는 `ULONG32`에 대 한 포인터입니다.  
  
 `ppInternalFrames`  
 [in, out] 스택의 내부 프레임 배열 주소에 대 한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|[ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) 개체를 만들었습니다.|  
|E_INVALIDARG|`cInternalFrames` 0이 아니고 `ppInternalFrames` `null`되거나 `pcInternalFrames` `null`입니다.|  
|HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)|`ppInternalFrames` 내부 프레임 수 보다 작습니다.|  
  
## <a name="exceptions"></a>예외  
  
## <a name="remarks"></a>주의  
 내부 프레임은 런타임에서 임시 데이터를 저장 하기 위해 스택에 푸시되는 데이터 구조입니다.  
  
 `GetActiveInternalFrames`를 처음 호출 하는 경우 `cInternalFrames` 매개 변수를 0 (영)으로 설정 하 고 `ppInternalFrames` 매개 변수를 null로 설정 해야 합니다. `GetActiveInternalFrames` 처음 반환 될 때 `pcInternalFrames`는 스택의 내부 프레임 수를 포함 합니다.  
  
 그런 다음 `GetActiveInternalFrames`를 두 번째로 호출 해야 합니다. `cInternalFrames` 매개 변수에서 적절 한 개수 (`pcInternalFrames`)를 전달 하 고 `ppInternalFrames`에서 적절 하 게 크기가 지정 된 배열에 대 한 포인터를 지정 해야 합니다.  
  
 [ICorDebugStackWalk:: GetFrame](icordebugthread3-getactiveinternalframes-method.md) 메서드를 사용 하 여 실제 스택 프레임을 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참조

- [디버깅 인터페이스](debugging-interfaces.md)
- [디버깅](index.md)
