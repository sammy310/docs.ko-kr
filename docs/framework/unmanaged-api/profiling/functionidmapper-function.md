---
description: '자세한 정보: FunctionIDMapper 함수'
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
ms.openlocfilehash: 2db616509bf5dcb5b8aee9cea76a9841369ec49d
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/20/2021
ms.locfileid: "104759252"
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

`funcId` 진행 다시 매핑할 함수 식별자입니다.

`pbHookFunction` 제한이 , 및 콜백을 받으려는 경우 프로파일러가 설정 하는 값에 대 한 포인터이 고, `true` `FunctionEnter2` `FunctionLeave2` `FunctionTailcall2` 그렇지 않으면이 값을로 설정 `false` 합니다.

## <a name="return-value"></a>반환 값  

 프로파일러는 실행 엔진이 대체 함수 식별자로 사용하는 값을 반환합니다. `false`가 `pbHookFunction`에 반환되지 않는 한 반환 값은 null일 수 없습니다. 그렇지 않으면 null 반환 값이 프로세스 중지를 포함 하 여 예기치 않은 결과를 생성 합니다.  
  
## <a name="remarks"></a>설명  

 `FunctionIDMapper`함수는 콜백입니다. 프로파일러는 프로파일러에 더 유용한 다른 식별자로 함수 ID를 다시 매핑하기 위해 프로파일러에 의해 구현 됩니다. 는 `FunctionIDMapper` 지정 된 함수에 사용할 대체 ID를 반환 합니다. 그러면 실행 엔진이 기존 함수 ID 외에 `clientData` `FunctionEnter2` 도, 및 후크에 매개 변수의 프로파일러를 다시 전달 하 여 후크를 호출 하는 `FunctionLeave2` 함수를 식별 하는 방식으로 프로파일러 요청을 `FunctionTailcall2` 인식 합니다.  
  
 [ICorProfilerInfo:: SetFunctionIDMapper](icorprofilerinfo-setfunctionidmapper-method.md) 메서드를 사용 하 여 함수의 구현을 지정할 수 있습니다 `FunctionIDMapper` . `ICorProfilerInfo::SetFunctionIDMapper`메서드를 한 번만 호출할 수 있으며, [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md) 콜백에서이 작업을 수행 하는 것이 좋습니다.  
  
 기본적으로 [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md)를 사용 하 여 COR_PRF_MONITOR_ENTERLEAVE 플래그를 설정 하 고 [ICorProfilerInfo:: SetEnterLeaveFunctionHooks](icorprofilerinfo-setenterleavefunctionhooks-method.md) 또는 [ICorProfilerInfo2:: SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)를 통해 후크를 설정 하는 프로파일러는 `FunctionEnter2` `FunctionLeave2` `FunctionTailcall2` 모든 함수에 대해, 및 콜백을 받아야 한다고 가정 합니다. 그러나 프로파일러는 `FunctionIDMapper` 를로 설정 하 여 특정 함수에 대해 이러한 콜백을 수신 하지 않도록 선택적으로 구현할 수 있습니다 `pbHookFunction` `false` .  
  
 프로파일러는 프로 파일링 된 응용 프로그램의 여러 스레드가 동일한 메서드/함수를 동시에 호출 하는 경우를 허용 해야 합니다. 이러한 경우 프로파일러는 `FunctionIDMapper` 동일한에 대해 여러 콜백을 수신할 수 있습니다 `FunctionID` . 프로파일러에서는 동일한 값을 사용 하 여 여러 번 호출 될 때이 콜백에서 동일한 값을 반환 해야 합니다 `FunctionID` .  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Corprof.idl  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조

- [SetFunctionIDMapper 메서드](icorprofilerinfo-setfunctionidmapper-method.md)
- [FunctionIDMapper2 함수](functionidmapper2-function.md)
- [FunctionEnter2 함수](functionenter2-function.md)
- [FunctionLeave2 함수](functionleave2-function.md)
- [FunctionTailcall2 함수](functiontailcall2-function.md)
- [프로파일링 전역 정적 함수](profiling-global-static-functions.md)
