---
title: ICorProfilerCallback4::ReJITCompilationStarted 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4.ReJITCompilationStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::ReJITCompilationStarted
helpviewer_keywords:
- ReJITCompilationStarted method, ICorProfilerCallback4 interface [.NET Framework profiling]
- ICorProfilerCallback4::ReJITCompilationStarted method [.NET Framework profiling]
ms.assetid: 512fdd00-262a-4456-a075-365ef4133c4d
topic_type:
- apiref
ms.openlocfilehash: be257930ca0fad658afa75d6efa4573d4f888a2b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177087"
---
# <a name="icorprofilercallback4rejitcompilationstarted-method"></a>ICorProfilerCallback4::ReJITCompilationStarted 메서드
JIT(적정 시) 컴파일러가 함수를 다시 컴파일하기 시작했다는 것을 프로파일러에 알린다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT ReJITCompilationStarted(
    [in] FunctionID functionId,  
    [in] ReJITID    rejitId,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a>매개 변수  
 `functionId`  
 【인】 JIT 컴파일러가 다시 컴파일하기 시작한 함수의 ID입니다.  
  
 `rejitId`  
 【인】 함수의 새 버전의 재컴파일 ID입니다.  
  
 `fIsSafeToBlock`  
 【인】 `true` 차단으로 인해 런타임이 호출 스레드가 이 콜백에서 반환될 때까지 기다릴 수 있음을 나타냅니다. `false` 을 사용하여 차단이 런타임 작업에 영향을 미치지 않음을 나타냅니다. 값은 `true` 런타임에 해를 끼치지 않지만 프로파일링 결과에 영향을 줄 수 있습니다.  
  
## <a name="remarks"></a>설명  
 런타임이 클래스 생성기를 처리하는 `ReJITCompilationStarted` 방식으로 인해 두 쌍 이상의 [ReJITCompilation 완료](icorprofilercallback4-rejitcompilationfinished-method.md) 메서드 호출을 각 함수에 대해 수신할 수 있습니다. 예를 들어 런타임은 메서드 A를 다시 컴파일하기 시작하지만 클래스 B에 대한 클래스 생성자는 실행되어야 합니다. 따라서 런타임클래스 B에 대한 생성자다시 컴파일하고 실행합니다. 생성자가 실행되는 동안 메서드 A를 호출하여 메서드 A를 다시 컴파일합니다. 이 시나리오에서는 메서드 A의 첫 번째 재컴파일이 중지 됩니다. 그러나 메서드 A를 다시 컴파일하려는 두 시도는 JIT 재컴파일 이벤트와 함께 보고됩니다.  
  
 프로파일러는 두 스레드가 동시에 콜백을 만드는 경우 JIT 재컴파일 콜백 시퀀스를 지원해야 합니다. 예를 들어, 스레드 `ReJITCompilationStarted`A 호출 ; 그러나 스레드 A가 [ReJITCompilation을](icorprofilercallback4-rejitcompilationfinished-method.md)호출하기 전에 완료된 스레드 B는 스레드 A에 대한 `ReJITCompilationStarted` 콜백의 함수 ID를 사용하여 [ICorProfilerCallback을](icorprofilercallback-exceptionsearchfunctionenter-method.md) 호출합니다. [ReJITCompilationFinished에](icorprofilercallback4-rejitcompilationfinished-method.md) 대한 호출이 프로파일러에서 아직 수신되지 않았기 때문에 함수 ID가 아직 유효하지 않은 것처럼 보일 수 있습니다. 그러나 이 경우 함수 ID는 유효합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorProfilerCallback 인터페이스](icorprofilercallback-interface.md)
- [ICorProfilerCallback4 인터페이스](icorprofilercallback4-interface.md)
- [JITCompilationFinished 메서드](icorprofilercallback-jitcompilationfinished-method.md)
- [ReJITCompilationFinished 메서드](icorprofilercallback4-rejitcompilationfinished-method.md)
