---
title: ICorProfilerCallback::Initialize 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.Initialize
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::Initialize
helpviewer_keywords:
- Initialize method, ICorProfilerCallback interface [.NET Framework profiling]
- ICorProfilerCallback::Initialize method [.NET Framework profiling]
ms.assetid: dc5fab2a-4b45-4b12-8727-b89c9915f23e
topic_type:
- apiref
ms.openlocfilehash: 64df6a81eb23c20537238c702fd0c204d64d14bc
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74434558"
---
# <a name="icorprofilercallbackinitialize-method"></a>ICorProfilerCallback::Initialize 메서드
새 CLR (공용 언어 런타임) 응용 프로그램이 시작 될 때마다 코드 프로파일러를 초기화 하기 위해 호출 됩니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT Initialize(  
    [in] IUnknown     *pICorProfilerInfoUnk);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pICorProfilerInfoUnk`  
 인터페이스 [에서](/cpp/atl/iunknown) 프로파일러가 [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) 인터페이스 포인터를 쿼리해야 합니다.  
  
## <a name="remarks"></a>주의  
 `Initialize` 호출은 변경할 수 없는 콜백을 사용 하거나 사용 하지 않도록 설정 하는 유일한 기회입니다. `Initialize` 호출로 콜백을 사용 하도록 설정한 후에는 나중에 [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md)를 사용 하 여 콜백을 사용 하지 않도록 설정할 수 없습니다. [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) 열거형의 COR_PRF_MONITOR_IMMUTABLE 값은 변경할 수 없는 이벤트를 나타냅니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorProfilerCallback 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [Shutdown 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-shutdown-method.md)
