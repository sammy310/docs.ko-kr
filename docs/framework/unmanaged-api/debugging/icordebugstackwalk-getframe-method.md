---
description: '자세히 알아보기: ICorDebugStackWalk:: GetFrame 메서드'
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
ms.openlocfilehash: b00ddb6a475aff4263a922f5a20b866cd0e1b2ed
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794743"
---
# <a name="icordebugstackwalkgetframe-method"></a>ICorDebugStackWalk::GetFrame 메서드

[ICorDebugStackWalk](icordebugstackwalk-interface.md) 개체의 현재 프레임을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetFrame([out] ICorDebugFrame ** pFrame);  
```  
  
## <a name="parameters"></a>매개 변수  

 `pFrame`  
 진행 스택의 현재 프레임을 나타내는 만들어진 프레임 개체의 주소에 대 한 포인터입니다.  
  
## <a name="return-value"></a>Return Value  

 이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|런타임에서 현재 프레임을 성공적으로 반환 했습니다.|  
|E_FAIL|현재 프레임이 반환 되지 않았습니다.|  
|S_FALSE|현재 프레임은 네이티브 스택 프레임입니다.|  
|E_INVALIDARG|`pFrame`가 null입니다.|  
|CORDBG_E_PAST_END_OF_STACK|프레임 포인터가 이미 스택의 끝에 있습니다. 따라서 추가 프레임에는 액세스할 수 없습니다.|  
  
## <a name="exceptions"></a>예외  
  
## <a name="remarks"></a>설명  

 `ICorDebugStackWalk` 실제 스택 프레임만 반환 합니다. [ICorDebugThread3:: GetActiveInternalFrames](icordebugthread3-getactiveinternalframes-method.md) 메서드를 사용 하 여 내부 프레임을 반환 합니다. 내부 프레임은 런타임에서 임시 데이터를 저장 하기 위해 스택에 푸시되는 데이터 구조입니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorDebugStackWalk 인터페이스](icordebugstackwalk-interface.md)
- [디버깅 인터페이스](debugging-interfaces.md)
- [디버깅](index.md)
