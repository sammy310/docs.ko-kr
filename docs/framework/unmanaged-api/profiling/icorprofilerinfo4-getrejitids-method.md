---
title: ICorProfilerInfo4::GetReJITIDs 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.GetReJITIDs
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::GetReJITIDs
helpviewer_keywords:
- GetReJITIDs method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::GetReJITIDs method [.NET Framework profiling]
ms.assetid: 634ac28c-a5b7-4fc3-af84-256c24ca8177
topic_type:
- apiref
ms.openlocfilehash: f6d26abba649b608858fde8beaac750600493869
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74442859"
---
# <a name="icorprofilerinfo4getrejitids-method"></a>ICorProfilerInfo4::GetReJITIDs 메서드
아직 할당 된 지정 된 함수의 JIT 다시 컴파일된 모든 버전을 식별 하는 Id 배열을 반환 합니다. 여기에는 나중에 되돌린 하지만 아직 해제 되지 않은 함수의 JIT 다시 컴파일된 버전 (예: 되돌린 함수를 포함 하는 응용 프로그램 도메인이 아직 사용 중인 경우)이 포함 됩니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT GetReJITIDs (  
     [in]  FunctionID          functionId,  
     [in]  ULONG               cReJitIds,  
     [out] ULONG *             pcReJitIds,  
     [out, size_is(cReJitIds), length_is(*pcReJitIds)]   ReJITID        reJitIds[]);  
```  
  
## <a name="parameters"></a>매개 변수  
 `functionId`  
 진행 버전을 열거할 함수 인스턴스의 `FunctionID`입니다.  
  
 `cReJitIds`  
 진행 `reJitIds` 배열에 할당 된 JIT 다시 컴파일된 Id 수입니다.  
  
 `pcReJitIds`  
 제한이 JIT 다시 컴파일된 Id의 실제 수입니다.  
  
 `reJitIds`  
 제한이 지정 된 함수의 JIT 다시 컴파일된 Id를 포함 하는 호출자가 할당 한 배열입니다.  
  
## <a name="remarks"></a>주의  
 `GetReJITIDs`는 지정 된 함수 인스턴스에 대해 활성 JIT 다시 컴파일된 Id를 열거 합니다. 호출자가 할당 한 버퍼를 허용 하는 다른 `ICorProfilerInfo` 함수와 동일한 사용 패턴을 따릅니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorProfilerInfo4 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
- [프로파일링 인터페이스](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [프로파일링](../../../../docs/framework/unmanaged-api/profiling/index.md)
