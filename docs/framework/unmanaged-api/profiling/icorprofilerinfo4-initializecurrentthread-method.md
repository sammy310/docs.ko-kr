---
title: ICorProfilerInfo4::InitializeCurrentThread 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4::InitializeCurrentThread
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::InitializeCurrentThread
helpviewer_keywords:
- ICorProfilerInfo4::InitializeCurrentThread method [.NET Framework profiling]
- InitializeCurrentThread method, ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: 18a3335c-8c75-476c-b6de-72c0bfedae5d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9fd0900e61c57d105439d83430284dc8634d2a1e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62000508"
---
# <a name="icorprofilerinfo4initializecurrentthread-method"></a>ICorProfilerInfo4::InitializeCurrentThread 메서드
후속 프로파일러 해당 교착 상태를 방지할 수 있도록 동일한 스레드에서 API 호출 하기 전에 현재 스레드를 초기화 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT InitializeCurrentThread ();  
```  
  
## <a name="remarks"></a>설명  
 호출 하는 것이 좋습니다 `InitializeCurrentThread` 있기는 API는 프로파일러를 호출 하는 모든 스레드에서 스레드를 일시 중단 합니다. 이 메서드는 일반적으로 샘플링 프로파일러는 자체 스레드를 호출 하 여 사용 합니다 [ICorProfilerInfo2::DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) 대상 스레드가 일시 중단 된 동안 스택 수행 하는 방법에 설명 합니다. 호출 하 여 `InitializeCurrentThread` 프로파일러 CLR 그렇지 않은 경우 첫 번째 호출 하는 동안 수행 하는 해당 스레드 단위 지연 초기화 확실히 경우 프로파일러는 샘플링 스레드를 먼저 만듭니다, 면 `DoStackSnapshot` 다른 스레드가 없을 때 안전 하 게 발생 이제 수 일시 중지 됩니다.  
  
> [!NOTE]
>  `InitializeCurrentThread` 잠금을 하 고 교착 상태가 발생할 수 있는 작업을 완료 하기 전에 초기화를 수행 합니다. 호출 `InitializeCurrentThread` 일시 중단 된 스레드가 없는 경우에 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [ICorProfilerInfo4 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
- [프로파일링 인터페이스](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [프로파일링](../../../../docs/framework/unmanaged-api/profiling/index.md)
