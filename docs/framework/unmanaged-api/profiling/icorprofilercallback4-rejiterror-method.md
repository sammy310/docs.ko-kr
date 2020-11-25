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
ms.openlocfilehash: 46312aaf530e69f0e6a90e35515f1373d01b4340
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730242"
---
# <a name="icorprofilercallback4rejiterror-method"></a>ICorProfilerCallback4::ReJITError 메서드

JIT (just-in-time) 컴파일러에서 재컴파일을 처리할 때 오류가 발생 했음을 프로파일러에 알립니다.  
  
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
 진행 `ModuleID` 실패 한 재컴파일을 시도한입니다.  
  
 `methodId`  
 진행 `MethodDef` 실패 한 재컴파일을 시도한 메서드의입니다.  
  
 `functionId`  
 진행 다시 컴파일하거나 다시 컴파일하도록 표시 되는 함수 인스턴스입니다. 이 값 `NULL` 은 오류가 발생 하는 경우 (예: 프로파일러에서 다시 컴파일할 메서드에 대해 잘못 된 메타 데이터 토큰을 지정 하는 경우)와 같은 방법으로 오류가 발생 한 경우에 해당 합니다.  
  
 `hrStatus`  
 진행 오류의 특성을 나타내는 HRESULT입니다. 값 목록은 상태 HRESULT 섹션을 참조 하세요.  
  
## <a name="return-value"></a>반환 값  

 이 콜백의 반환 값은 무시됩니다.  
  
## <a name="status-hresults"></a>상태 HRESULTS  
  
|상태 배열 HRESULT|설명|  
|--------------------------|-----------------|  
|E_INVALIDARG|`moduleID`또는 `methodDef` 토큰이 인 `NULL` 경우|  
|CORPROF_E_DATAINCOMPLETE|모듈은 아직 완전히 로드되지 않았거나 언로드되는 중입니다.|  
|CORPROF_E_MODULE_IS_DYNAMIC|지정 된 모듈이 동적으로 생성 된 경우 (예: `Reflection.Emit` )이 메서드에서 지원 되지 않습니다.|  
|CORPROF_E_FUNCTION_IS_COLLECTIBLE|메서드는 수집 가능한 어셈블리로 인스턴스화되기 때문에 다시 컴파일할 수 없습니다. 비 리플렉션 컨텍스트 (예:)에 정의 된 형식 및 함수를 수집 가능한 `List<MyCollectibleStruct>` 어셈블리로 인스턴스화할 수 있습니다.|  
|E_OUTOFMEMORY|지정 된 메서드를 JIT 다시 컴파일하도록 표시 하는 동안 CLR에 메모리가 부족 합니다.|  
|기타|운영 체제가 CLR의 제어 범위를 벗어난 오류를 반환했습니다. 예를 들어 메모리 페이지의 액세스 보호를 변경 하는 시스템 호출이 실패 하면 운영 체제 오류가 표시 됩니다.|  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorProfilerCallback 인터페이스](icorprofilercallback-interface.md)
- [ICorProfilerCallback4 인터페이스](icorprofilercallback4-interface.md)
