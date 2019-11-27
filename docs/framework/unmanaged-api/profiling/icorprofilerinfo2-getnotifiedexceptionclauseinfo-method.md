---
title: ICorProfilerInfo2::GetNotifiedExceptionClauseInfo 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetNotifiedExceptionClauseInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetNotifiedExceptionClauseInfo
helpviewer_keywords:
- ICorProfilerInfo2::GetNotifiedExceptionCaluseInfo method [.NET Framework profiling]
- GetNotifiedExceptionCaluseInfo method [.NET Framework profiling]
ms.assetid: f9594a7e-cb0c-4c48-accb-29f762aa0c21
topic_type:
- apiref
ms.openlocfilehash: 52ad124638a1c1ec7d39fa41b9163f3ab50ffe70
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74433073"
---
# <a name="icorprofilerinfo2getnotifiedexceptionclauseinfo-method"></a>ICorProfilerInfo2::GetNotifiedExceptionClauseInfo 메서드
실행 되거나 방금 실행 된 예외 절 (`catch`/`finally`/`filter`)에 대 한 기본 주소 및 프레임 정보를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetNotifiedExceptionClauseInfo(  
    [out] COR_PRF_EX_CLAUSE_INFO *pinfo);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pinfo`  
 제한이 현재 예외 절 인스턴스와 관련 프레임을 설명 하는 [COR_PRF_EX_CLAUSE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-ex-clause-info-structure.md) 구조체에 대 한 포인터입니다.  
  
## <a name="remarks"></a>주의  
 예외 알림이 `GetNotifiedExceptionClauseInfo` 수신 되 면 실행 될 예외 절 /`finally`/`catch`([ICorProfilerCallback:: ExceptionCatcherEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherenter-method.md), [ICorProfilerCallback:: ExceptionUnwindFinallyEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyenter-method.md)또는 [ICorProfilerCallback:: exceptionsearchfilterenter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterenter-method.md) callback이 수신 됨)에 대 한 기본 주소와 프레임 정보를 가져오는 데 사용할 수 있습니다. 또는 방금 실행 ([ICorProfilerCallback:: ExceptionCatcherLeave ](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherleave-method.md), [ICorProfilerCallback:: ExceptionUnwindFinallyLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyleave-method.md)또는 [ICorProfilerCallback:: exceptionsearchfilterleave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterleave-method.md) 콜백은 프로파일러에서 수신 합니다.`filter`  
  
 이 호출은 일치 하는 Leave 콜백이 수신 되거나 현재 절에서 중첩 된 예외가 throw 될 때까지 위의 Enter 콜백 중 하나를 실행 한 후 언제 든 지 수행할 수 있습니다 .이 경우에는 해당 절에 대 한 Leave 알림이 없습니다. Throw 된 예외가 `filter` exception 절을 이스케이프 하는 것은 불가능 하므로이 경우 항상 Leave 알림이 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorProfilerInfo 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [ICorProfilerInfo2 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
