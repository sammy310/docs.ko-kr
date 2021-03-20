---
description: '자세히 알아보기: ICorProfilerCallback:: JITCompilationFinished 메서드'
title: ICorProfilerCallback::JITCompilationFinished 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITCompilationFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITCompilationFinished
helpviewer_keywords:
- JITCompilationFinished method [.NET Framework profiling]
- ICorProfilerCallback::JITCompilationFinished method [.NET Framework profiling]
ms.assetid: 8dcd7537-d0c6-498c-8a56-2c060310ef65
topic_type:
- apiref
ms.openlocfilehash: 32a47860ae2e973d32ef12b2bd9002bb1de45ee9
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/20/2021
ms.locfileid: "104760329"
---
# <a name="icorprofilercallbackjitcompilationfinished-method"></a>ICorProfilerCallback::JITCompilationFinished 메서드

JIT (just-in-time) 컴파일러가 함수 컴파일을 완료 했음을 프로파일러에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT JITCompilationFinished(  
    [in] FunctionID functionId,  
    [in] HRESULT    hrStatus,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a>매개 변수

`functionId` 진행 컴파일된 함수의 ID입니다.

`hrStatus` 진행 컴파일이 성공 했는지 여부를 나타내는 값입니다.

`fIsSafeToBlock` 진행 차단이 런타임 작업에 영향을 주는지 여부를 프로파일러에 나타내는 값입니다. `true`차단 하면 호출 스레드가이 콜백에서 반환 될 때까지 런타임이 대기 하 게 될 수 있으면 값이이 고, 그렇지 않으면 `false` 입니다.

값은 `true` 런타임에 영향을 주지 않지만 프로 파일링 결과를 기울일 수 있습니다.

## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorProfilerCallback 인터페이스](icorprofilercallback-interface.md)
- [JITCompilationStarted 메서드](icorprofilercallback-jitcompilationstarted-method.md)
