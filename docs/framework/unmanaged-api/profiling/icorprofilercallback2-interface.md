---
title: ICorProfilerCallback2 인터페이스
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2
helpviewer_keywords:
- ICorProfilerCallback2 interface [.NET Framework profiling]
ms.assetid: 4a261dba-450d-4f1f-8d98-865b58bfc992
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 83c72704ccb01baf68a3cacb6252367e07909fa8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59178999"
---
# <a name="icorprofilercallback2-interface"></a>ICorProfilerCallback2 인터페이스
코드 프로파일러는 프로파일러가 구독 한 이벤트가 발생할 때 알릴는 CLR (공용 언어 런타임)에서 사용 되는 메서드를 제공 합니다. 합니다 `ICorProfilerCallback2` 인터페이스의 확장은 합니다 [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) 인터페이스입니다. 즉,.NET Framework 버전 2.0에에서 도입 된 새 콜백을 제공 합니다.  
  
> [!NOTE]
>  각 메서드 구현 값을 가진 s_ok E_FAIL이 성공 또는 실패 HRESULT를 반환 해야 합니다. CLR에서 제외 하 고 각 콜백에 의해 반환 되는 HRESULT를 무시 하는 현재 [icorprofilercallback:: Objectreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md)합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[FinalizeableObjectQueued 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-finalizeableobjectqueued-method.md)|실행에 대 한 종료자 스레드에 개체 종료자를 사용 하 여 큐에 대기 되었습니다는 코드 프로파일러에 알립니다. 해당 `Finalize` 메서드.|  
|[GarbageCollectionFinished 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md)|가비지 수집을 완료 하 고에 대 한 모든 가비지 컬렉션 콜백이 실행 된 프로파일러에 알립니다.|  
|[GarbageCollectionStarted 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md)|가비지 수집을 시작한 코드 프로파일러에 알립니다.|  
|[HandleCreated 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-handlecreated-method.md)|가비지 컬렉션 핸들 만들어졌는지 코드 프로파일러에 알립니다.|  
|[HandleDestroyed 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-handledestroyed-method.md)|가비지 컬렉션 핸들을 소멸 된 코드 프로파일러에 알립니다.|  
|[RootReferences2 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md)|가비지 수집이 발생 한 후 루트 참조에 대 한 프로파일러를 알립니다. 이 메서드는 확장 합니다 [icorprofilercallback:: Rootreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) 메서드.|  
|[SurvivingReferences 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-survivingreferences-method.md)|에서는 가비지 수집에서 남은 개체 참조에 대 한 프로파일러를 알립니다.|  
|[ThreadNameChanged 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-threadnamechanged-method.md)|스레드의 이름 변경 된 코드 프로파일러에 알립니다.|  
  
## <a name="remarks"></a>설명  
 CLR에서 메서드를 호출 합니다 `ICorProfilerCallback` (또는 `ICorProfilerCallback2`) 프로파일러가 구독 하는, 이벤트를 프로파일러에 알리는 인터페이스를 발생 합니다. CLR 코드 프로파일러를 사용 하 여 통신 하는 기본 콜백 인터페이스입니다.  
  
 코드 프로파일러가의 메서드를 구현 해야 합니다는 `ICorProfilerCallback` 인터페이스입니다. .NET Framework 2.0 및 이후 버전에서는 프로파일러도 구현 해야 합니다 `ICorProfilerCallback2` 메서드. 각 메서드 구현 값을 가진 s_ok E_FAIL이 성공 또는 실패 HRESULT를 반환 해야 합니다. CLR에서 제외 하 고 각 콜백에 의해 반환 되는 HRESULT를 무시 하는 현재 [icorprofilercallback:: Objectreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md)합니다.  
  
 코드 프로파일러는 Microsoft Windows 레지스트리를 구현 하는 COM 개체에 등록 해야 합니다 `ICorProfilerCallback` 및 `ICorProfilerCallback2` 인터페이스입니다. 코드 프로파일러는 호출 하 여 알림을 수신 하려는 이벤트를 구독할 [icorprofilerinfo:: Seteventmask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md)합니다. 프로파일러의 구현에서는 일반적으로 이렇게 [icorprofilercallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md)합니다. 프로파일러는 이벤트 수행 되려고 하거나 실행 중인 런타임 프로세스에서 발생 한 직후 때 런타임에서 알림을 수신 합니다.  
  
> [!NOTE]
>  프로파일러는 단일 COM 개체를 등록합니다. COM 개체의 메서드를 구현만 필요한 프로파일러를.NET Framework 버전 1.0 또는 1.1을 대상으로 하는 경우 `ICorProfilerCallback`합니다. .NET Framework 버전 2.0 대상으로 하 고 COM 개체의 메서드를 구현도 해야 나중 `ICorProfilerCallback2`합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [프로파일링 인터페이스](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [ICorProfilerCallback 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [ICorProfilerCallback3 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-interface.md)
- [ICorProfilerCallback4 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
