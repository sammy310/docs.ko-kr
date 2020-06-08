---
title: ICorProfilerCallback5 인터페이스
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback5
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback5
helpviewer_keywords:
- ICorProfilerCallback5 interface [.NET Framework profiling]
ms.assetid: 61d2e9ef-5f1f-4771-8847-239616e35d84
topic_type:
- apiref
ms.openlocfilehash: 02a690503d7b6323f19dcb66247d8a552b760b1c
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499209"
---
# <a name="icorprofilercallback5-interface"></a>ICorProfilerCallback5 인터페이스
[ICorProfilerCallback:: RootReferences](icorprofilercallback-rootreferences-method.md) 또는 [ICorProfilerCallback2:: RootReferences2](icorprofilercallback2-rootreferences2-method.md) 메서드와 함께 [ICorProfilerCallback:: ObjectReferences](icorprofilercallback-objectreferences-method.md) 및 [ConditionalWeakTableElementReferences](icorprofilercallback5-conditionalweaktableelementreferences-method.md) 메서드와 함께 사용 되는 경우 프로파일러가 라이브 개체의 전체 클로저를 식별 하는 데 도움이 되는 정보를 보완 합니다.  
  
 관리되는 메모리 프로파일러가 `ICorProfilerCallback5`를 구현하여 종속 핸들과 관련된 알림을 구독해야 합니다.  
  
## <a name="remarks"></a>설명  
  
## <a name="methods"></a>메서드  
  
|방법|설명|  
|------------|-----------------|  
|[ConditionalWeakTableElementReferences 메서드](icorprofilercallback5-conditionalweaktableelementreferences-method.md)|직접 멤버 필드 참조와 `ConditionalWeakTable` 종속성을 모두 사용하여 루트를 통해 참조되는 개체의 전이적 Closure를 식별합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [프로파일링 인터페이스](profiling-interfaces.md)
- [ICorProfilerCallback2 인터페이스](icorprofilercallback2-interface.md)
