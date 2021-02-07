---
description: '자세히 알아보기: ICorProfilerCallback:: JITCompilationStarted 메서드'
title: ICorProfilerCallback::JITCompilationStarted 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITCompilationStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITCompilationStarted
helpviewer_keywords:
- JITCompilationStarted method [.NET Framework profiling]
- ICorProfilerCallback::JITCompilationStarted method [.NET Framework profiling]
ms.assetid: 31782b36-d311-4518-8f45-25f65385af5b
topic_type:
- apiref
ms.openlocfilehash: 984c19e1601f83cc0f52145403ad85affc158050
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99705735"
---
# <a name="icorprofilercallbackjitcompilationstarted-method"></a>ICorProfilerCallback::JITCompilationStarted 메서드

JIT (just-in-time) 컴파일러가 함수 컴파일을 시작 했음을 프로파일러에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT JITCompilationStarted(  
    [in] FunctionID functionId,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a>매개 변수  

 `functionId`  
 진행 컴파일을 시작 하는 함수의 ID입니다.  
  
 `fIsSafeToBlock`  
 진행 차단이 런타임 작업에 영향을 주는지 여부를 프로파일러에 나타내는 값입니다. `true`차단 하면 호출 스레드가이 콜백에서 반환 될 때까지 런타임이 대기 하 게 될 수 있으면 값이이 고, 그렇지 않으면 `false` 입니다.  
  
 값은 `true` 런타임에 영향을 주지 않지만 프로 파일링 결과를 기울일 수 있습니다.  
  
## <a name="remarks"></a>설명  

 `JITCompilationStarted`런타임이 클래스 생성자를 처리 하는 방식 때문에 각 함수에 대해 둘 이상의 및 [ICorProfilerCallback:: JITCompilationFinished](icorprofilercallback-jitcompilationfinished-method.md) 호출을 받을 수 있습니다. 예를 들어 런타임은 메서드 A를 JIT 컴파일하도록 시작 하지만 클래스 B에 대 한 클래스 생성자를 실행 해야 합니다. 따라서 런타임은 클래스 B에 대 한 생성자를 JIT로 컴파일하고 실행 합니다. 생성자는를 실행 하는 동안 메서드 a를 호출 하 여 메서드 A를 다시 JIT 컴파일합니다. 이 시나리오에서는 메서드 A의 첫 번째 JIT 컴파일이 중단 됩니다. 그러나 메서드 A를 JIT 컴파일하는 두 시도는 JIT 컴파일 이벤트로 보고 됩니다. 프로파일러가 [ICorProfilerInfo:: SetILFunctionBody](icorprofilerinfo-setilfunctionbody-method.md) 메서드를 호출 하 여 메서드 A의 MSIL (Microsoft 중간 언어) 코드를 바꾸려는 경우 두 이벤트 모두에 대해이 작업을 수행 해야 `JITCompilationStarted` 하지만 둘 다에 대해 동일한 msil 블록을 사용할 수 있습니다.  
  
 두 스레드가 동시에 콜백을 수행 하는 경우 프로파일러는 JIT 콜백의 시퀀스를 지원 해야 합니다. 예를 들어 스레드 A를 호출 `JITCompilationStarted` 합니다. 그러나 스레드 A가를 호출 하기 전에 스레드 `JITCompilationFinished` B는 스레드 a의 콜백에서 함수 ID를 사용 하 여 [ICorProfilerCallback:: ExceptionSearchFunctionEnter](icorprofilercallback-exceptionsearchfunctionenter-method.md) 를 호출 `JITCompilationStarted` 합니다. 에 대 한 호출이 `JITCompilationFinished` 프로파일러에서 아직 수신 되지 않았기 때문에 함수 ID가 아직 유효 하지 않은 것 처럼 보일 수 있습니다. 그러나 이와 같은 경우에는 함수 ID가 유효 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorProfilerCallback 인터페이스](icorprofilercallback-interface.md)
- [JITCompilationFinished 메서드](icorprofilercallback-jitcompilationfinished-method.md)
