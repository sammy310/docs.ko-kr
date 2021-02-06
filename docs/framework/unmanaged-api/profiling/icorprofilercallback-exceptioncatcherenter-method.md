---
description: '자세히 알아보기: ICorProfilerCallback:: ExceptionCatcherEnter 메서드'
title: ICorProfilerCallback::ExceptionCatcherEnter 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionCatcherEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionCatcherEnter
helpviewer_keywords:
- ICorProfilerCallback::ExceptionCatcherEnter method [.NET Framework profiling]
- ExceptionCatcherEnter method [.NET Framework profiling]
ms.assetid: 41462329-a648-46f0-ae6d-728b94c31aa9
topic_type:
- apiref
ms.openlocfilehash: 3a813936a7d1f3a5041e192c85d02b37976e3388
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99657634"
---
# <a name="icorprofilercallbackexceptioncatcherenter-method"></a>ICorProfilerCallback::ExceptionCatcherEnter 메서드

컨트롤이 적절 한 블록에 전달 되 고 있음을 프로파일러에 알립니다 `catch` .  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT ExceptionCatcherEnter(  
    [in] FunctionID functionId,  
    [in] ObjectID   objectId);  
```  
  
## <a name="parameters"></a>매개 변수

- `functionId`

  \[in] 블록을 포함 하는 함수의 식별자입니다 `catch` .
  
- `objectId`

  \[in] 처리 되는 예외의 식별자입니다.

## <a name="remarks"></a>설명  

 `ExceptionCatcherEnter`메서드는 catch 지점이 JIT (just-in-time) 컴파일러를 사용 하 여 컴파일된 코드에 있는 경우에만 호출 됩니다. 비관리 코드나 런타임의 내부 코드에서 catch 된 예외는이 알림을 호출 하지 않습니다. `objectId`이 값은 알림 이후 가비지 수집에서 개체를 이동 했을 수 있으므로 다시 전달 됩니다 `ExceptionThrown` .  
  
 스택은 가비지 수집을 허용 하는 상태가 아닐 수 있으므로 선점형 가비지 수집을 사용 하도록 설정할 수 없기 때문에 프로파일러는이 메서드의 구현에서 차단 해서는 안 됩니다. 프로파일러가 여기에서 차단 되 고 가비지 수집이 시도 되는 경우이 콜백이 반환 될 때까지 런타임이 차단 됩니다.  
  
 이 메서드의 프로파일러 구현은 관리 코드를 호출 하거나 관리 되는 메모리 할당을 발생 시 키 지 않아야 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorProfilerCallback 인터페이스](icorprofilercallback-interface.md)
- [ExceptionCatcherLeave 메서드](icorprofilercallback-exceptioncatcherleave-method.md)
