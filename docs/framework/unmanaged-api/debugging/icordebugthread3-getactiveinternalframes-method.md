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
ms.openlocfilehash: 680af5afa3ebef5bcaf9e34580e421dcc8093aaf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178461"
---
# <a name="icordebugthread3getactiveinternalframes-method"></a>ICorDebugThread3::GetActiveInternalFrames 메서드
스택에서 내부[프레임(ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) 개체)의 배열을 반환합니다.  
  
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
 【인】 에서 예상되는 내부 프레임 `ppInternalFrames`수입니다.  
  
 `pcInternalFrames`  
 【아웃】 스택의 내부 `ULONG32` 프레임 수를 포함하는 a에 대한 포인터입니다.  
  
 `ppInternalFrames`  
 【인, 아웃】 스택의 내부 프레임 배열주소에 대한 포인터입니다.  
  
## <a name="return-value"></a>Return Value  
 이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.  
  
|HRESULT|Description|  
|-------------|-----------------|  
|S_OK|[ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) 개체가 성공적으로 만들어졌습니다.|  
|E_INVALIDARG|`cInternalFrames`0이 `ppInternalFrames` 아니며 `null`은 `pcInternalFrames` . `null`|  
|HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)|`ppInternalFrames`는 내부 프레임의 개수보다 작습니다.|  
  
## <a name="exceptions"></a>예외  
  
## <a name="remarks"></a>설명  
 내부 프레임은 임시 데이터를 저장하기 위해 런타임에 의해 스택에 푸시된 데이터 구조입니다.  
  
 호출할 `GetActiveInternalFrames`때 매개 변수를 `cInternalFrames` 0(0)으로 설정하고 `ppInternalFrames` 매개 변수를 null로 설정해야 합니다. 처음 `GetActiveInternalFrames` 반환할 `pcInternalFrames` 때 스택의 내부 프레임 수가 포함됩니다.  
  
 `GetActiveInternalFrames`두 번째로 호출해야 합니다. 매개 변수에서 적절한`pcInternalFrames`개수 () 를 전달하고 에서 적절한 크기의 배열에 대한 포인터를 지정해야 합니다. `ppInternalFrames` `cInternalFrames`  
  
 [ICorDebugStackWalk::GetFrame](icordebugthread3-getactiveinternalframes-method.md) 메서드를 사용하여 실제 스택 프레임을 반환합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [디버깅 인터페이스](debugging-interfaces.md)
- [디버깅](index.md)
