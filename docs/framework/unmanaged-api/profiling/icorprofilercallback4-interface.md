---
title: ICorProfilerCallback4 인터페이스
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4
helpviewer_keywords:
- ICorProfilerCallback4 interface [.NET Framework profiling]
ms.assetid: 665f3cfc-cd6f-4880-906c-ea65ad384783
topic_type:
- apiref
ms.openlocfilehash: 942ee8234b79c6579acc009960f4571801fc3185
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730294"
---
# <a name="icorprofilercallback4-interface"></a>ICorProfilerCallback4 인터페이스

CLR (공용 언어 런타임)이 프로파일러에 정보를 전달 하는 데 사용 하는 콜백 메서드를 제공 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[GetReJITParameters 메서드](icorprofilercallback4-getrejitparameters-method.md)|코드 프로파일러가 다시 컴파일된 새 메서드 본문에 대 한 대체 코드 생성 플래그를 설정할 수 있습니다.|  
|[MovedReferences2 메서드](icorprofilercallback4-movedreferences2-method.md)|압축 가비지 수집의 결과로 힙에 있는 개체의 새 레이아웃을 보고 합니다.|  
|[ReJITCompilationFinished 메서드](icorprofilercallback4-rejitcompilationfinished-method.md)|JIT (just-in-time) 컴파일러가 함수를 다시 컴파일 했음을 프로파일러에 알립니다.|  
|[ReJITCompilationStarted 메서드](icorprofilercallback4-rejitcompilationstarted-method.md)|JIT (just-in-time) 컴파일러가 함수를 다시 컴파일하기 시작 했음을 프로파일러에 알립니다.|  
|[ReJITError 메서드](icorprofilercallback4-rejiterror-method.md)|Recompile 요청을 처리 하는 동안 발생 한 오류를 보고 합니다.|  
|[SurvivingReferences2 메서드](icorprofilercallback4-survivingreferences2-method.md)|비압축 가비지 수집의 결과로 힙에 있는 개체의 레이아웃을 보고합니다.|  
  
## <a name="remarks"></a>설명  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorProfilerCallback2 인터페이스](icorprofilercallback2-interface.md)
- [프로파일링 인터페이스](profiling-interfaces.md)
- [ICorProfilerInfo 인터페이스](icorprofilerinfo-interface.md)
