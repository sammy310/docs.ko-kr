---
title: ICorProfilerCallback4::ReJITError 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4.ReJITError
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::ReJITError
helpviewer_keywords:
- ReJITError method, ICorProfilerCallback4 interface [.NET Framework profiling]
- ICorProfilerCallback4::ReJITError method [.NET Framework profiling]
ms.assetid: d7888aa9-dfaa-420f-9f99-e06ab35ca482
topic_type:
- apiref
ms.openlocfilehash: 6ea9dee6e83870d1f2e0fdccffa53f16e6f18dba
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74430101"
---
# <a name="icorprofilercallback4rejiterror-method"></a>ICorProfilerCallback4::ReJITError 메서드
Notifies the profiler that the just-in-time (JIT) compiler encountered an error in the recompilation process.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT ReJITError(  
    [in] ModuleID    moduleId,  
    [in] mdMethodDef methodId,  
    [in] FunctionID  functionId,  
    [in] HRESULT     hrStatus);  
```  
  
## <a name="parameters"></a>매개 변수  
 `moduleID`  
 [in] The `ModuleID` in which the failed recompilation attempt was made.  
  
 `methodId`  
 [in] The `MethodDef` of the method on which the failed recompilation attempt was made.  
  
 `functionId`  
 [in] The function instance that is being recompiled or marked for recompilation. This value may be `NULL` if the failure occurred on a per-method basis instead of a per-instantiation basis (for example, if the profiler specified an invalid metadata token for the method to be recompiled).  
  
 `hrStatus`  
 [in] An HRESULT that indicates the nature of the failure. See the Status HRESULTS section for a list of values.  
  
## <a name="return-value"></a>반환 값  
 이 콜백의 반환 값은 무시됩니다.  
  
## <a name="status-hresults"></a>상태 HRESULTS  
  
|상태 배열 HRESULT|설명|  
|--------------------------|-----------------|  
|E_INVALIDARG|The `moduleID` or `methodDef` token is `NULL`.|  
|CORPROF_E_DATAINCOMPLETE|모듈은 아직 완전히 로드되지 않았거나 언로드되는 중입니다.|  
|CORPROF_E_MODULE_IS_DYNAMIC|The specified module was dynamically generated (for example, by `Reflection.Emit`), and is thus not supported by this method.|  
|CORPROF_E_FUNCTION_IS_COLLECTIBLE|The method is instantiated into a collectible assembly, and is therefore not able to be recompiled. Note that types and functions defined in a non-reflection context (for example, `List<MyCollectibleStruct>`) can be instantiated into a collectible assembly.|  
|E_OUTOFMEMORY|The CLR ran out of memory while trying to mark the specified method for JIT recompilation.|  
|기타|운영 체제가 CLR의 제어 범위를 벗어난 오류를 반환했습니다. For example, if a system call to change the access protection of a page of memory fails, the operating system error is displayed.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorProfilerCallback 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [ICorProfilerCallback4 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
