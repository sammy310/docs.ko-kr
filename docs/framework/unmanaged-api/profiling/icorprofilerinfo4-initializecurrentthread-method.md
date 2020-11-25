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
ms.openlocfilehash: 51f16523c00cc3dd95b786f1586ccfd75ce8d5f1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733830"
---
# <a name="icorprofilerinfo4initializecurrentthread-method"></a>ICorProfilerInfo4::InitializeCurrentThread 메서드

교착 상태를 방지할 수 있도록 동일한 스레드에서 후속 프로파일러 API 호출을 앞서 현재 스레드를 초기화 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT InitializeCurrentThread ();  
```  
  
## <a name="remarks"></a>설명  

 `InitializeCurrentThread`일시 중단 된 스레드가 있는 동안 프로파일러 API를 호출 하는 모든 스레드에서를 호출 하는 것이 좋습니다. 이 메서드는 일반적으로 [ICorProfilerInfo2::D ostacksnapshot](icorprofilerinfo2-dostacksnapshot-method.md) 메서드를 호출 하 여 대상 스레드가 일시 중단 된 동안 스택 워크를 수행 하는 자체 스레드를 만드는 샘플링 프로파일러에 사용 됩니다. `InitializeCurrentThread`프로파일러가 먼저 샘플링 스레드를 만들 때를 한 번 호출 하 여 프로파일러는 `DoStackSnapshot` 다른 스레드가 일시 중단 되지 않은 경우에 대 한 첫 번째 호출을 수행 하는 동안 CLR에서 수행 하는 지연 스레드 단위 초기화를 수행할 수 있도록 합니다.  
  
> [!NOTE]
> `InitializeCurrentThread` 는 잠금을 수행 하는 작업을 완료 하도록 미리 초기화를 수행 하 고 교착 상태를 발생 시킬 수 있습니다. `InitializeCurrentThread`일시 중단 된 스레드가 없는 경우에만를 호출 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorProfilerInfo4 인터페이스](icorprofilerinfo4-interface.md)
- [프로파일링 인터페이스](profiling-interfaces.md)
- [프로파일링](index.md)
