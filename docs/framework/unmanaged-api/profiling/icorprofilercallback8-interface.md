---
title: ICorProfilerCallback8 인터페이스
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 617b27923e96d9abc62ccbf158b076c6e45b20a8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175098"
---
# <a name="icorprofilercallback8-interface"></a>ICorProfilerCallback8 인터페이스
[.NET 프레임워크 4.7 이후 버전에서 지원]  

 동적 메서드의 JIT 컴파일이 시작되고 완료되었음을 프로파일러에게 알리기 위해 공통 언어 런타임에서 사용하는 콜백 메서드를 제공하는 [ICorProfilerCallback7의](icorprofilercallback7-interface.md) 하위 클래스입니다.
  
## <a name="methods"></a>메서드  
  
|방법|Description|  
|------------|-----------------|  
|[DynamicMethodJITCompilationStarted 메서드](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)|동적 메서드의 JIT 컴파일이 시작되었음을 프로파일러에 보오시면 됩니다.|  
|[DynamicMethodJITCompilationFinished 메서드](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)|동적 메서드의 JIT 컴파일이 완료되었음을 프로파일러에 보오시면 됩니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
**.NET Framework 버전:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>참고 항목

- [프로파일링 인터페이스](profiling-interfaces.md)
- [ICorProfilerCallback9 인터페이스](icorprofilercallback9-interface.md)
