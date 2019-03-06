---
title: ICorProfilerCallback7::ModuleInMemorySymbolsUpdated Method
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback7.ModuleInMemorySymbolsUpdated
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.assetid: f362a896-3247-4894-9727-e48dbbcd2c78
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f33eef5c405b98b9dbf88973a8b7cafad06308b6
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57466455"
---
# <a name="icorprofilercallback7moduleinmemorysymbolsupdated-method"></a>ICorProfilerCallback7::ModuleInMemorySymbolsUpdated Method
[.NET Framework 4.6.1 이상 버전에서 지원됨]  
  
 메모리 내 모듈과 연관 된 기호 스트림이 업데이트 될 때마다 프로파일러를 알립니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT ModuleInMemorySymbolsUpdated(  
     ModuleID moduleId  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 [in] `moduleId`  
 해당 기호 스트림이 업데이트는 메모리 내 모듈의 식별자입니다.  
  
## <a name="remarks"></a>설명  
 이 콜백을 설정 하 여 제어 합니다 [COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) 이벤트 마스크 플래그를 호출할 때 합니다 [ICorProfilerCallback5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) 메서드.  
  
> [!NOTE]
>  이 이벤트는 암시적으로 생성 되거나를 통해 수정 기호에 대 한 현재 발생 하지 <xref:System.Reflection.Emit> Api.  
  
 도 때 기호에에서 제공 된 사전 관리 되는 오버 로드 중 하나를 호출 하 <xref:System.Reflection.Assembly.Load*?displayProperty=nameWithType> 포함 하는 메서드를 `rawSymbolStore` 런타임 어셈블리에 대 한 기호를 지정 하는 인수 기호 데이터 모듈을 사용 하 여 실제로 연결 하지 않을 수 있습니다 될 때까지 후 합니다 [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) 콜백 발생 했습니다. 이 이벤트는 이러한 모듈에 대 한 기호를 수집 하는 이후 기회를 제공 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>참고자료
- [ModuleLoadFinished 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)
- [SetEventMask2 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)
- [ICorProfilerCallback7 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-interface.md)
