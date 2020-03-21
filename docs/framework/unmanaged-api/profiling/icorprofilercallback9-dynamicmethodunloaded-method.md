---
title: ICorProfilerCallback9::DynamicMethod언로드 방법
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback9.DynamicMethodUnloaded
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 0eb38c83e9ab706c96bdef971f0bf17cc096822b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177035"
---
# <a name="icorprofilercallback9dynamicmethodunloaded-method"></a>ICorProfilerCallback9::DynamicMethod언로드 방법
[.NET 프레임워크 4.7.2 이상 버전에서 지원]  
  
동적 메서드가 가비지 수집되고 이후에 언로드될 때마다 프로파일러에 대해 인지합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT DynamicMethodUnloaded(  
     [in]  FunctionID  functionId
);  
```  
  
## <a name="parameters"></a>매개 변수  
[in] `functionId`  
가비지 수집 및 언로드된 메모리 내 함수의 식별자입니다.

## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorProfilerCallback8.DynamicMethodJIT 컴파일 시작 방법](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [ICorProfilerCallback8.DynamicMethodJIT 컴파일 완성 방법](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
- [ICorProfilerCallback9 인터페이스](icorprofilercallback9-interface.md)
- [COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS](cor-prf-high-monitor-enumeration.md)
