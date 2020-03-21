---
title: ICorProfilerCallback8::DynamicMethodJIT 편집 완료 방법
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8.DynamicMethodJITCompilationFinished
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: c2e9489654a0fe5fa65ec638ed0f991a6c01415a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175111"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationfinished-method"></a>ICorProfilerCallback8::DynamicMethodJIT 편집 완료 방법
[.NET 프레임워크 4.7 이후 버전에서 지원]  
  
동적 메서드의 JIT 컴파일이 완료될 때마다 프로파일러에 이를 고지합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT DynamicMethodJITCompilationFinished(  
     [in]  FunctionID  functionId,
     [in]  BOOL        hrStatus,
     [in]  BOOL        fIsSafeToBlock
);  
```  
  
## <a name="parameters"></a>매개 변수  
[in] `functionId`  
JIT 컴파일이 시작되는 메모리 내 함수의 식별자입니다.

【인】 `hrStatus` JIT 컴파일이 성공했는지 여부를 나타내는 값입니다.

【인】 `fIsSafeToBlock` 차단으로 인해 런타임이 호출 스레드가 이 콜백에서 반환될 때까지 기다릴 수 있음을 
 `true` 나타냅니다. `false` 을 사용하여 차단이 런타임 작업에 영향을 미치지 않음을 나타냅니다.  

## <a name="remarks"></a>설명  

이 콜백은 동적 메서드의 JIT 컴파일이 완료될 때마다 트리거됩니다. 여기에는 다양한 IL 스텁 및 LCG 방법이 포함됩니다. 그 목표는 프로파일러 작성기에 컴파일된 메서드를 사용자에게 식별할 수 있는 충분한 정보를 제공하는 것입니다.

> [!NOTE]
> `functionId`동적 메서드에는 메타데이터가 없기 때문에 메타데이터 토큰으로 해결하는 데 값을 사용할 수 없습니다.

## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  
  
## <a name="see-also"></a>참고 항목

- [DynamicMethodJITCompilationStarted 메서드](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [ICorProfilerCallback8 인터페이스](icorprofilercallback8-interface.md)
