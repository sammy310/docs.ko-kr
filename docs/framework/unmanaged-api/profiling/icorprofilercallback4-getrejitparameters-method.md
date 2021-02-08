---
description: '자세히 알아보기: ICorProfilerCallback4:: GetReJITParameters 메서드'
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
ms.openlocfilehash: f8dbf2c6ae80e41b8427fdaf0ef617a83138bb14
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99788763"
---
# <a name="icorprofilercallback4getrejitparameters-method"></a>ICorProfilerCallback4::GetReJITParameters 메서드

코드 프로파일러가 다시 컴파일된 새 메서드 본문에 대 한 대체 코드 생성 플래그를 설정할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetReJITParameters(     [in] ModuleID moduleId,     [in] mdMethodDef methodId,     [in] ICorProfilerFunctionControl *pFunctionControl);  
```  
  
## <a name="parameters"></a>매개 변수  

 `moduleID`  
 진행 CLR에서 JIT 재컴파일 매개 변수를 필요로 하는 메서드가 포함 된 모듈입니다.  
  
 `methodId`  
 진행 `MethodDef` CLR에서 JIT 재컴파일 매개 변수를 필요로 하는 메서드의입니다.  
  
 `pFunctionControl`  
 진행 프로파일러가 다시 컴파일하는 메서드에 대 한 JIT 재컴파일 정보를 제공 하는 데 사용할 수 있는 [ICorProfilerFunctionControl](icorprofilerfunctioncontrol-interface.md) 인터페이스에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  

 `GetReJITParameters`프로파일러가 지정 된 메서드를 다시 컴파일하는 매개 변수를 지정할 수 있도록 CLR은 콜백을 실행 합니다. `GetReJITParameters`콜백은 함수 마다 한 번만 실행 됩니다. 프로파일러에서 제공 하는 매개 변수는 해당 함수의 모든 인스턴스에 적용 됩니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorProfilerCallback 인터페이스](icorprofilercallback-interface.md)
- [ICorProfilerCallback4 인터페이스](icorprofilercallback4-interface.md)
- [JITCompilationStarted 메서드](icorprofilercallback-jitcompilationstarted-method.md)
- [ReJITCompilationStarted 메서드](icorprofilercallback4-rejitcompilationstarted-method.md)
