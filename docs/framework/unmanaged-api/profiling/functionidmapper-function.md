---
title: FunctionIDMapper 함수
ms.date: 03/30/2017
api_name:
- FunctionIDMapper
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionIDMapper
helpviewer_keywords:
- FunctionIDMapper function [.NET Framework profiling]
ms.assetid: b8205b60-1893-4303-8cff-7ac5a00892aa
topic_type:
- apiref
ms.openlocfilehash: d5bf6626e2c6ba15fa9a5da08bcf2d9052866750
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866946"
---
# <a name="functionidmapper-function"></a>FunctionIDMapper 함수
함수의 지정 된 식별자를 해당 함수의 [FunctionEnter2](functionenter2-function.md), [FunctionLeave2](functionleave2-function.md)및 [FunctionTailcall2](functiontailcall2-function.md) 콜백에서 사용할 대체 ID에 다시 매핑할 수 있음을 프로파일러에 알립니다. `FunctionIDMapper`를 통해 프로파일러는 해당 함수에 대한 콜백을 받을지 여부를 나타낼 수도 있습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
UINT_PTR __stdcall FunctionIDMapper (  
    [in]  FunctionID  funcId,   
    [out] BOOL       *pbHookFunction  
);  
```  
  
## <a name="parameters"></a>매개 변수

- `funcId`

  \[in] 다시 매핑할 함수 식별자입니다.

- `pbHookFunction`

  \[out] 프로파일러에서 `FunctionEnter2`, `FunctionLeave2`및 `FunctionTailcall2` 콜백을 받으려는 경우 `true` 설정 되는 값에 대 한 포인터입니다. 그렇지 않으면이 값을 `false`설정 합니다.

## <a name="return-value"></a>반환 값  
 프로파일러는 실행 엔진이 대체 함수 식별자로 사용하는 값을 반환합니다. `false`가 `pbHookFunction`에 반환되지 않는 한 반환 값은 null일 수 없습니다. 그렇지 않으면 null 반환 값이 프로세스 중지를 포함 하 여 예기치 않은 결과를 생성 합니다.  
  
## <a name="remarks"></a>주의  
 `FunctionIDMapper` 함수는 콜백입니다. 프로파일러는 프로파일러에 더 유용한 다른 식별자로 함수 ID를 다시 매핑하기 위해 프로파일러에 의해 구현 됩니다. `FunctionIDMapper`는 지정 된 함수에 사용할 대체 ID를 반환 합니다. 그런 다음 실행 엔진이 기존 함수 ID 외에도이 대체 ID를 전달 하 여 프로파일러 요청을 인식 하 고, `FunctionEnter2`, `FunctionLeave2`및 `FunctionTailcall2` 후크에 `clientData` 매개 변수의 프로파일러를 다시 전달 하 여 후크가 호출 되는 함수를 식별 합니다.  
  
 [ICorProfilerInfo:: SetFunctionIDMapper](icorprofilerinfo-setfunctionidmapper-method.md) 메서드를 사용 하 여 `FunctionIDMapper` 함수의 구현을 지정할 수 있습니다. `ICorProfilerInfo::SetFunctionIDMapper` 메서드를 한 번만 호출할 수 있으며, [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md) 콜백에서이 작업을 수행 하는 것이 좋습니다.  
  
 기본적으로 [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md)를 사용 하 여 COR_PRF_MONITOR_ENTERLEAVE 플래그를 설정 하 고 [ICorProfilerInfo:: SetEnterLeaveFunctionHooks](icorprofilerinfo-setenterleavefunctionhooks-method.md) 또는 [ICorProfilerInfo2:: SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)를 통해 후크를 설정 하는 프로파일러는 모든 함수에 대해 `FunctionEnter2`, `FunctionLeave2`및 `FunctionTailcall2` 콜백을 받아야 한다고 가정 합니다. 그러나 프로파일러는 `pbHookFunction`를 `false`로 설정 하 여 특정 함수에 대해 이러한 콜백을 선택적으로 수신 하지 않도록 `FunctionIDMapper`를 구현할 수 있습니다.  
  
 프로파일러는 프로 파일링 된 응용 프로그램의 여러 스레드가 동일한 메서드/함수를 동시에 호출 하는 경우를 허용 해야 합니다. 이러한 경우 프로파일러는 동일한 `FunctionID`에 대해 여러 개의 `FunctionIDMapper` 콜백을 받을 수 있습니다. 프로파일러는 동일한 `FunctionID`사용 하 여 여러 번 호출 될 때이 콜백에서 동일한 값을 반환 해야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Corprof.idl  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조

- [SetFunctionIDMapper 메서드](icorprofilerinfo-setfunctionidmapper-method.md)
- [FunctionIDMapper2 함수](functionidmapper2-function.md)
- [FunctionEnter2 함수](functionenter2-function.md)
- [FunctionLeave2 함수](functionleave2-function.md)
- [FunctionTailcall2 함수](functiontailcall2-function.md)
- [프로파일링 전역 정적 함수](profiling-global-static-functions.md)
