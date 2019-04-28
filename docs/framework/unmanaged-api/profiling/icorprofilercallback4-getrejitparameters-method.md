---
title: ICorProfilerCallback4::GetReJITParameters 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4.GetReJITParameters
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::GetReJITParameters
helpviewer_keywords:
- ICorProfilerCallback4::GetReJITParameters method [.NET Framework profiling]
- GetReJITParameters method, ICorProfilerCallback4 interface [.NET Framework profiling]
ms.assetid: 0e9bfe07-9f20-498c-b568-9017c8f6056c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ca176be93b92e44228d9b4063e87a62263e83e04
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61782508"
---
# <a name="icorprofilercallback4getrejitparameters-method"></a>ICorProfilerCallback4::GetReJITParameters 메서드
코드 프로파일러를 새 다시 컴파일된 메서드 본문에 대 한 대체 코드 생성 플래그를 설정할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetReJITParameters(     [in] ModuleID moduleId,     [in] mdMethodDef methodId,     [in] ICorProfilerFunctionControl *pFunctionControl);  
```  
  
## <a name="parameters"></a>매개 변수  
 `moduleID`  
 [in] CLR 필요 JIT 다시 컴파일을 매개 변수는 메서드가 포함 된 모듈입니다.  
  
 `methodId`  
 [in] `MethodDef` 메서드의 CLR JIT 다시 컴파일을 매개 변수는 필요 합니다.  
  
 `pFunctionControl`  
 [in] 에 대 한 포인터를 [ICorProfilerFunctionControl](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md) 프로파일러 컴파일되는 메서드에 대 한 JIT 다시 컴파일을 정보를 제공 하는 데 사용할 수 있는 인터페이스입니다.  
  
## <a name="remarks"></a>설명  
 CLR 문제는 `GetReJITParameters` 콜백 프로파일러는 지정 된 메서드를 다시 컴파일할 매개 변수를 지정할 수 있도록 합니다. `GetReJITParameters` 콜백 함수 당 한 번만 발생; 프로파일러에서 제공 하는 매개 변수를 해당 함수의 모든 인스턴스에 적용 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [ICorProfilerCallback 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [ICorProfilerCallback4 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
- [JITCompilationStarted 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md)
- [ReJITCompilationStarted 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationstarted-method.md)
