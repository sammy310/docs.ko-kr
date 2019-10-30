---
title: 'ICorProfilerCallback7:: Moduleinmemory기호 및 날짜 메서드'
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback7.ModuleInMemorySymbolsUpdated
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.assetid: f362a896-3247-4894-9727-e48dbbcd2c78
ms.openlocfilehash: f6dd10d196ffd3a653584e1bc8d1a5643850bc33
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136606"
---
# <a name="icorprofilercallback7moduleinmemorysymbolsupdated-method"></a>ICorProfilerCallback7:: Moduleinmemory기호 및 날짜 메서드
[.NET Framework 4.6.1 이상 버전에서 지원됨]  
  
 메모리 내 모듈과 연관 된 기호 스트림이 업데이트 될 때마다 프로파일러에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT ModuleInMemorySymbolsUpdated(  
     ModuleID moduleId  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 [in] `moduleId`  
 기호 스트림이 업데이트 되는 메모리 내 모듈의 식별자입니다.  
  
## <a name="remarks"></a>주의  
 이 콜백은 [ICorProfilerCallback5:: SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) 메서드를 호출할 때 [COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) 이벤트 마스크 플래그를 설정 하 여 제어 됩니다.  
  
> [!NOTE]
> 이 이벤트는 <xref:System.Reflection.Emit> Api를 통해 암시적으로 만들어지거나 수정 된 기호에 대해 현재 발생 하지 않습니다.  
  
 어셈블리의 기호를 지정 하기 위해 `rawSymbolStore` 인수를 포함 하는 관리 되는 <xref:System.Reflection.Assembly.Load*?displayProperty=nameWithType> 메서드의 오버 로드 중 하나를 호출 하는 즉시 기호가 제공 되는 경우에도 런타임에서는 기호 데이터를 모듈에 연결 하지 않을 수 있습니다 [Moduleloadfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) 콜백이 발생 했습니다. 이 이벤트는 나중에 이러한 모듈의 기호를 수집할 수 있는 기회를 제공 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ModuleLoadFinished 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)
- [SetEventMask2 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)
- [ICorProfilerCallback7 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-interface.md)
