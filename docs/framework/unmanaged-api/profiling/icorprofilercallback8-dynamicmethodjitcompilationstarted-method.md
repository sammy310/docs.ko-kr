---
title: ICorProfilerCallback8::D ynamicMethodJITCompilationStarted 메서드
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8.DynamicMethodJITCompilationStarted
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 1eaf29e1c93f352facde4af2ee57910783d82e5d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136460"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationstarted-method"></a>ICorProfilerCallback8::D ynamicMethodJITCompilationStarted 메서드
[.NET Framework 4.7 이상 버전에서 지원 됨]  
  
동적 메서드의 JIT 컴파일이 시작 될 때마다 프로파일러에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT DynamicMethodJITCompilationStarted(  
     [in]  FunctionID  functionId,   
     [in]  BOOL        fIsSafeToBlock,   
     [in]  LPCBYTE     pILHeader,   
     [in]  LONG        cbILHeader   
);  
```  
  
## <a name="parameters"></a>매개 변수  
[in] `functionId`  
JIT 컴파일이 시작 되는 메모리 내 함수의 식별자입니다.   

[in] `fIsSafeToBlock`   
차단으로 인해 런타임에서 호출 스레드가이 콜백에서 반환 될 때까지 기다릴 수 있음을 나타내려면 `true` 합니다. 블로킹이 런타임 작업에 영향을 주지 않음을 나타내려면 `false` 합니다.  

[in] `pILHeader`    
메서드의 IL 헤더에 대 한 첫 번째 바이트에 대 한 포인터입니다.   

[in] `cbILHeader`    
IL 헤더의 바이트 수입니다. 

## <a name="remarks"></a>주의  

이 콜백은 동적 메서드가 JIT 컴파일될 때마다 트리거됩니다. 여기에는 다양 한 IL 스텁 및 LCG 메서드가 포함 됩니다. 이는 사용자에 게 컴파일된 메서드를 식별 하는 데 충분 한 정보를 제공 하는 프로파일러 작성기를 제공 하는 것입니다.

> [!NOTE]
> 동적 메서드에 메타 데이터가 없으므로 `functionId` 값을 사용 하 여 메타 데이터 토큰을 확인할 수 없습니다.

`pILHeader` 포인터는 콜백 중에만 유효 합니다.

## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  
  
## <a name="see-also"></a>참고 항목

- [DynamicMethodJITCompilationFinished 메서드](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
- [ICorProfilerCallback8 인터페이스](icorprofilercallback8-interface.md)
