---
description: '자세히 알아보기: ICorProfilerCallback7:: Moduleinmemory기호 향상 날짜 메서드'
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
ms.openlocfilehash: fa6056beb5685ca9ce9545efea567ca0df6029ce
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/20/2021
ms.locfileid: "104759861"
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

 `moduleId`  
 진행 기호 스트림이 업데이트 되는 메모리 내 모듈의 식별자입니다.  
  
## <a name="remarks"></a>설명  

 이 콜백은 [ICorProfilerCallback5:: SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) 메서드를 호출할 때 [COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED](cor-prf-high-monitor-enumeration.md) 이벤트 마스크 플래그를 설정 하 여 제어 됩니다.  
  
> [!NOTE]
> 이 이벤트는 현재 api를 통해 암시적으로 만들어지거나 수정 된 기호에 대해 발생 하지 않습니다 <xref:System.Reflection.Emit> .  
  
 어셈블리에 대 한 기호를 지정 하기 위해 인수를 포함 하는 관리 되는 메서드의 오버 로드 중 하나를 호출 하는 즉시 기호가 제공 되는 경우에도 <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> `rawSymbolStore` 런타임은 [moduleloadfinished](icorprofilercallback-moduleloadfinished-method.md) 콜백이 발생 했을 때까지 기호 데이터를 모듈에 실제로 연결 하지 않을 수 있습니다. 이 이벤트는 나중에 이러한 모듈의 기호를 수집할 수 있는 기회를 제공 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ModuleLoadFinished 메서드](icorprofilercallback-moduleloadfinished-method.md)
- [SetEventMask2 메서드](icorprofilerinfo5-seteventmask2-method.md)
- [ICorProfilerCallback7 인터페이스](icorprofilercallback7-interface.md)
