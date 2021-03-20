---
description: '자세히 알아보기: ICorProfilerCallback:: JITCachedFunctionSearchFinished 메서드'
title: ICorProfilerCallback::JITCachedFunctionSearchFinished 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITCachedFunctionSearchFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITCachedFunctionSearchFinished
helpviewer_keywords:
- JITCachedFunctionSearchFinished method [.NET Framework profiling]
- ICorProfilerCallback::JITCachedFunctionSearchFinished method [.NET Framework profiling]
ms.assetid: 3c325c82-cddd-4b00-b3da-e450c36abf62
topic_type:
- apiref
ms.openlocfilehash: 3dc655c2a049a2cac08f6e4856aab98ee690b9df
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/20/2021
ms.locfileid: "104759962"
---
# <a name="icorprofilercallbackjitcachedfunctionsearchfinished-method"></a>ICorProfilerCallback::JITCachedFunctionSearchFinished 메서드

NGen.exe (네이티브 이미지 생성기)를 사용 하 여 이전에 컴파일된 함수에 대해 검색이 완료 되었음을 프로파일러에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT JITCachedFunctionSearchFinished(  
    [in] FunctionID        functionId,  
    [in] COR_PRF_JIT_CACHE result);  
```  
  
## <a name="parameters"></a>매개 변수

`functionId` 진행 검색이 수행 된 함수의 ID입니다.

`result` 진행 검색 결과를 나타내는 [COR_PRF_JIT_CACHE](cor-prf-jit-cache-enumeration.md) 열거형의 값입니다.

## <a name="remarks"></a>설명  

 .NET Framework 버전 2.0에서는 일반 NGen 이미지의 모든 함수에 대해 [ICorProfilerCallback:: JITCachedFunctionSearchStarted](icorprofilercallback-jitcachedfunctionsearchstarted-method.md) 및 `JITCachedFunctionSearchFinished` 콜백이 생성 되지 않습니다. 프로파일러에 대해 최적화 된 NGen 이미지만이 이미지의 모든 함수에 대해 콜백을 생성 합니다. 그러나 추가 오버 헤드로 인해 프로파일러는 이러한 콜백을 사용 하 여 함수를 JIT (just-in-time)로 강제 컴파일하는 경우에만 프로파일러 최적화 NGen 이미지를 요청 해야 합니다. 그렇지 않으면 프로파일러는 함수 정보를 수집 하기 위해 지연 전략을 사용 해야 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorProfilerCallback 인터페이스](icorprofilercallback-interface.md)
