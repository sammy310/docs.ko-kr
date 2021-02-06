---
description: '자세히 알아보기: ICorProfilerCallback:: Shutdown 메서드'
title: ICorProfilerCallback::Shutdown 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.Shutdown
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::Shutdown
helpviewer_keywords:
- ICorProfilerCallback::Shutdown method [.NET Framework profiling]
- Shutdown method [.NET Framework profiling]
ms.assetid: 1ea194f0-a331-4855-a2ce-37393b8e5f84
topic_type:
- apiref
ms.openlocfilehash: 7afc274579f248ee190e379160f2709b5cb9881a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99657322"
---
# <a name="icorprofilercallbackshutdown-method"></a>ICorProfilerCallback::Shutdown 메서드

응용 프로그램이 종료 되었음을 프로파일러에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT Shutdown();  
```  
  
## <a name="remarks"></a>설명  

 메서드를 호출한 후에는 프로파일러 코드가 [ICorProfilerInfo](icorprofilerinfo-interface.md) 인터페이스의 메서드를 안전 하 게 호출할 수 없습니다 `Shutdown` . 메서드를 호출 `ICorProfilerInfo` 하면 메서드가 반환 된 후에 정의 되지 않은 동작이 발생 `Shutdown` 합니다. 종료 후에는 변경할 수 없는 특정 이벤트가 계속 발생할 수 있습니다. 이 문제가 발생 하면 프로파일러가 즉시 반환 되도록 주의 해야 합니다.  
  
 메서드는 프로 파일링 되는 관리 되는 `Shutdown` 응용 프로그램이 관리 코드 (즉, 프로세스 스택의 초기 프레임)로 시작 된 경우에만 호출 됩니다. 응용 프로그램이 비관리 코드로 시작 되었지만 나중에 관리 코드로 점프 하 여 CLR (공용 언어 런타임)의 인스턴스를 만든 경우에 `Shutdown` 는가 호출 되지 않습니다. 이러한 경우 프로파일러는 DLL_PROCESS_DETACH 값을 사용 하 여 리소스를 `DllMain` 해제 하 고 디스크에 추적을 플러시하는 등의 데이터의 정리 처리를 수행 하는 루틴을 라이브러리에 포함 해야 합니다.  
  
 일반적으로 프로파일러는 예기치 않은 종료로 대처 해야 합니다. 예를 들어 Win32's `TerminateProcess` 메서드 (Winbase. h에 선언 됨)에 의해 프로세스가 중단 될 수 있습니다. 다른 경우에는 CLR에서 특정 관리 되는 스레드 (백그라운드 스레드)에 대 한 순차적 소멸 메시지를 제공 하지 않고 중단 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorProfilerCallback 인터페이스](icorprofilercallback-interface.md)
- [Initialize 메서드](icorprofilercallback-initialize-method.md)
