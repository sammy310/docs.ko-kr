---
description: '자세히 알아보기: ICorProfilerCallback:: JITCachedFunctionSearchStarted 메서드'
title: ICorProfilerCallback::JITCachedFunctionSearchStarted 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITCachedFunctionSearchStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITCachedFunctionSearchStarted
helpviewer_keywords:
- JITCachedFunctionSearchStarted method [.NET Framework profiling]
- ICorProfilerCallback::JITCachedFunctionSearchStarted method [.NET Framework profiling]
ms.assetid: 5cba642c-0d80-48ee-889d-198c5044d821
topic_type:
- apiref
ms.openlocfilehash: 1faaf8fbc1e0fee9ce76850cfedcd4e8cf934371
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99705774"
---
# <a name="icorprofilercallbackjitcachedfunctionsearchstarted-method"></a>ICorProfilerCallback::JITCachedFunctionSearchStarted 메서드

NGen.exe (네이티브 이미지 생성기)를 사용 하 여 이전에 컴파일된 함수에 대해 검색이 시작 되었음을 프로파일러에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT JITCachedFunctionSearchStarted(  
    [in]  FunctionID functionId,  
    [out] BOOL *pbUseCachedFunction);  
```  
  
## <a name="parameters"></a>매개 변수

- `functionId`

  \[in] 검색을 수행할 함수의 ID입니다.

- `pbUseCachedFunction`

  \[out] `true` 실행 엔진이 캐시 된 버전의 함수 (있는 경우)를 사용 해야 하면이 고, 그렇지 않으면 `false` 입니다. 값이 이면 `false` 실행 엔진이 jit 컴파일되지 않는 버전을 사용 하는 대신 함수를 jit 컴파일합니다.

## <a name="remarks"></a>설명  

 .NET Framework 버전 2.0에서는 `JITCachedFunctionSearchStarted` 일반 NGen 이미지의 모든 함수에 대해 및 [ICorProfilerCallback:: JITCachedFunctionSearchFinished 메서드](icorprofilercallback-jitcachedfunctionsearchfinished-method.md) 콜백이 생성 되지 않습니다. 프로필에 대해 최적화 된 NGen 이미지만이 이미지의 모든 함수에 대해 콜백을 생성 합니다. 그러나 추가 오버 헤드로 인해 프로파일러는 이러한 콜백을 사용 하 여 함수를 JIT (just-in-time)로 강제 컴파일하는 경우에만 프로파일러 최적화 NGen 이미지를 요청 해야 합니다. 그렇지 않으면 프로파일러는 함수 정보를 수집 하기 위해 지연 전략을 사용 해야 합니다.  
  
 프로파일러는 프로 파일링 된 응용 프로그램의 여러 스레드가 동일한 메서드를 동시에 호출 하는 경우를 지원 해야 합니다. 예를 들어 스레드 A가를 호출 하 `JITCachedFunctionSearchStarted` 고 프로파일러는 *PBUSECACHEDFUNCTION* 을 FALSE로 설정 하 여 강제로 JIT 컴파일을 수행 합니다. 그런 다음 스레드 A는 [ICorProfilerCallback:: JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md) 및 [ICorProfilerCallback:: JITCompilationFinished](icorprofilercallback-jitcompilationfinished-method.md)를 호출 합니다.  
  
 이제 스레드 B `JITCachedFunctionSearchStarted` 는 동일한 함수를 호출 합니다. 프로파일러에서 함수를 JIT 컴파일하는 의도를 언급 했더라도 프로파일러는 프로파일러가 스레드 A의 호출에 응답 하기 전에 콜백을 보내기 때문에 두 번째 콜백을 수신 합니다 `JITCachedFunctionSearchStarted` . 스레드가 호출 하는 순서는 스레드를 예약 하는 방법에 따라 달라 집니다.  
  
 프로파일러에서 중복 콜백을 받으면에서 참조 하는 값을 `pbUseCachedFunction` 모든 중복 콜백에 대 한 동일한 값으로 설정 해야 합니다. 즉, `JITCachedFunctionSearchStarted` 동일한 값을 사용 하 여를 여러 번 호출 하면 `functionId` 프로파일러가 매번 동일한 응답을 해야 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorProfilerCallback 인터페이스](icorprofilercallback-interface.md)
