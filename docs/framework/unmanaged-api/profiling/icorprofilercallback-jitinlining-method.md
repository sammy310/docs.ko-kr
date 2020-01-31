---
title: ICorProfilerCallback::JITInlining 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITInlining
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITInlining
helpviewer_keywords:
- JITInlining method [.NET Framework profiling]
- ICorProfilerCallback::JITInlining method [.NET Framework profiling]
ms.assetid: c2f45801-dd38-4b78-b6b7-64397dc73f83
topic_type:
- apiref
ms.openlocfilehash: 3e13b17fb03530730a78f6889309f1993419574b
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866216"
---
# <a name="icorprofilercallbackjitinlining-method"></a>ICorProfilerCallback::JITInlining 메서드
JIT (just-in-time) 컴파일러가 다른 함수를 사용 하 여 함수를 삽입 하려고 함을 프로파일러에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT JITInlining(  
    [in]  FunctionID callerId,  
    [in]  FunctionID calleeId,  
    [out] BOOL      *pfShouldInline);  
```  
  
## <a name="parameters"></a>매개 변수  
 `callerId`  
 진행 `calleeId` 함수를 삽입할 함수의 ID입니다.  
  
 `calleeId`  
 진행 삽입할 함수의 ID입니다.  
  
 `pfShouldInline`  
 [out] 삽입을 수행할 수 있도록 `true` 합니다. 그렇지 않으면 `false`합니다.  
  
## <a name="remarks"></a>주의  
 프로파일러는 `false` `pfShouldInline`를 설정 하 여 `calleeId` 함수가 `callerId` 함수에 삽입 되지 않도록 할 수 있습니다. 또한 프로파일러는 [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) 열거형의 COR_PRF_DISABLE_INLINING 값을 사용 하 여 인라인 삽입을 전역적으로 사용 하지 않도록 설정할 수 있습니다.  
  
 인라인으로 삽입 된 함수는 시작 또는 종료에 대 한 이벤트를 발생 시 키 지 않습니다. 따라서 정확한 호출 그래프을 생성 하기 위해 프로파일러는 `false` `pfShouldInline` 설정 해야 합니다. 인라인 삽입은 일반적으로 속도가 향상 되 고 삽입 된 메서드에 대 한 별도의 JIT 컴파일 이벤트 수가 줄어들기 때문에 `pfShouldInline`를 `false`로 설정 하면 성능에 영향을 줍니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorProfilerCallback 인터페이스](icorprofilercallback-interface.md)
