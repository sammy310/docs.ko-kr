---
title: ICorProfilerFunctionControl 인터페이스
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionControl
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionControl
helpviewer_keywords:
- ICorProfilerFunctionControl interface [.NET Framework profiling]
ms.assetid: 4e3d3141-4662-4166-8f05-bc857c1b4216
topic_type:
- apiref
ms.openlocfilehash: 1286ce953c96eb3e3164ba5b209031dd1ec5c453
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76864702"
---
# <a name="icorprofilerfunctioncontrol-interface"></a>ICorProfilerFunctionControl 인터페이스
코드 프로파일러가 CLR(공용 언어 런타임)과 통신하여 특정 메서드를 다시 컴파일할 때 JIT 컴파일러가 코드를 생성하는 방법을 제어할 수 있도록 하는 메서드를 제공합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[SetCodegenFlags 메서드](icorprofilerfunctioncontrol-setcodegenflags-method.md)|JIT (just in time) 컴파일 함수의 코드 생성을 제어 하기 위해 [COR_PRF_CODEGEN_FLAGS](cor-prf-codegen-flags-enumeration.md) 열거형에서 하나 이상의 플래그를 설정 합니다.|  
|[SetILFunctionBody 메서드](icorprofilerfunctioncontrol-setilfunctionbody-method.md)|메서드의 공용 중간 언어(CIL) 본문을 바꿉니다.|  
|[SetILInstrumentedCodeMap 메서드](icorprofilerfunctioncontrol-setilinstrumentedcodemap-method.md)|지정한 CIL(공용 중간 언어) 맵 엔트리를 사용하여 지정된 함수에 대한 코드 맵을 설정합니다.|  
  
## <a name="remarks"></a>주의  
 `ICorProfilerFunctionControl` 인터페이스는 다시 컴파일된 단일 함수에 대한 코드 생성을 제어하는 메서드를 제공합니다. 프로파일러는 [ICorProfilerCallback4:: GetReJITParameters](icorprofilercallback4-getrejitparameters-method.md) 콜백을 통해이 인터페이스의 인스턴스를 가져옵니다. `ICorProfilerFunctionControl`의 각 인스턴스가 단일 함수의 모든 인스턴스를 제어합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorProfilerInfo4 인터페이스](icorprofilerinfo4-interface.md)
- [프로파일링 인터페이스](profiling-interfaces.md)
- [EnumJITedFunctions2 메서드](icorprofilerinfo4-enumjitedfunctions2-method.md)
