---
title: ICorProfilerInfo4::EnumJITedFunctions2 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.EnumJITedFunctions2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::EnumJITedFunctions2
helpviewer_keywords:
- EnumJITedFunctions2 method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::EnumJITedFunctions2 method [.NET Framework profiling]
ms.assetid: 40e9a1be-9bd2-4fad-9921-34a84b61c1e3
topic_type:
- apiref
ms.openlocfilehash: 2c4a89d5f96ef572518f25bf58a0005454f8e3f0
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84496131"
---
# <a name="icorprofilerinfo4enumjitedfunctions2-method"></a>ICorProfilerInfo4::EnumJITedFunctions2 메서드
이전에 JIT 컴파일된 후 JIT 다시 컴파일된 모든 함수에 대 한 열거자를 반환 합니다. 이 메서드는 JIT 다시 컴파일된 Id를 열거 하지 않는 [ICorProfilerInfo3:: EnumJITedFunctions](icorprofilerinfo3-enumjitedfunctions-method.md) 메서드를 대체 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT EnumJITedFunctions([out] ICorProfilerFunctionEnum** ppEnum);  
```  
  
## <a name="parameters"></a>매개 변수  
 `ppEnum`  
 제한이 [ICorProfilerFunctionEnum](icorprofilerfunctionenum-interface.md) 열거자에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 이 메서드 `JITCompilation` 는 [ICorProfilerCallback:: JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md) 메서드와 같은 콜백과 겹칠 수 있습니다. 반환 된 열거형에는 필드에 대 한 값이 포함 됩니다 `COR_PRF_FUNCTION::reJitId` . 이 메서드가 대체 하는 [ICorProfilerInfo3:: EnumJITedFunctions](icorprofilerinfo3-enumjitedfunctions-method.md) 메서드는 `COR_PRF_FUNCTION::reJitId` 필드가 항상 0으로 설정 되므로 JIT 다시 컴파일된 id를 열거 하지 않습니다. `ICorProfilerInfo4::EnumJITedFunctions`이 메서드는 `COR_PRF_FUNCTION::reJitId` 필드가 올바르게 설정 되어 있으므로 JIT 다시 컴파일된 id를 열거 합니다. [ICorProfilerInfo4:: EnumJITedFunctions2](icorprofilerinfo4-enumjitedfunctions2-method.md) 메서드는 가비지 수집을 트리거할 수 있지만 [ICorProfilerInfo3:: EnumJITedFunctions 메서드](icorprofilerinfo3-enumjitedfunctions-method.md) 는 그렇지 않습니다.  자세한 내용은 [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](corprof-e-unsupported-call-sequence-hresult.md)를 참조 하세요.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [EnumJITedFunctions 메서드](icorprofilerinfo3-enumjitedfunctions-method.md)
- [ICorProfilerInfo4 인터페이스](icorprofilerinfo4-interface.md)
- [프로파일링 인터페이스](profiling-interfaces.md)
- [프로파일링](index.md)
