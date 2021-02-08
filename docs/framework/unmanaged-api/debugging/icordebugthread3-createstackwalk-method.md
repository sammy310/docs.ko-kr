---
description: '자세히 알아보기: ICorDebugThread3:: CreateStackWalk 메서드'
title: ICorDebugThread3::CreateStackWalk 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugThread3.CreateStackWalk Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread3::CreateStackWalk
helpviewer_keywords:
- CreateStackWalk method [.NET Framework debugging]
- ICorDebugThread3::CreateStackWalk method [.NET Framework debugging]
ms.assetid: c55e35d9-f9aa-4268-94b5-dce44c61acf2
topic_type:
- apiref
ms.openlocfilehash: b36252160dbad14ca1bee0674b6d042072a36359
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800996"
---
# <a name="icordebugthread3createstackwalk-method"></a>ICorDebugThread3::CreateStackWalk 메서드

스택을 해제 하려는 스레드에 대 한 [ICorDebugStackWalk](icordebugstackwalk-interface.md) 개체를 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT CreateStackWalk([out] ICorDebugStackWalk **ppStackWalk);  
```  
  
## <a name="parameters"></a>매개 변수  

 `ppStackWalk`  
 제한이 스택을 해제 하려는 스레드에 대 한 [ICorDebugStackWalk](icordebugstackwalk-interface.md) 개체의 주소에 대 한 포인터입니다.  
  
## <a name="return-value"></a>Return Value  

 이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|`ICorDebugStackWalk`개체를 성공적으로 만들었습니다.|  
|E_FAIL|`ICorDebugStackWalk`개체를 만들지 못했습니다.|  
  
## <a name="exceptions"></a>예외  
  
## <a name="remarks"></a>설명  

 `CreateStackWalk`메서드가 성공 하면 반환 된 `ICorDebugStackWalk` 개체의 컨텍스트가 스레드의 현재 컨텍스트로 설정 됩니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [디버깅 인터페이스](debugging-interfaces.md)
- [디버깅](index.md)
