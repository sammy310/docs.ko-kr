---
title: COR_PRF_SUSPEND_REASON 열거형
ms.date: 03/30/2017
api_name:
- COR_PRF_SUSPEND_REASON
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_SUSPEND_REASON
helpviewer_keywords:
- COR_PRF_SUSPEND_REASON enumeration [.NET Framework profiling]
ms.assetid: 75594833-bed3-47b2-a426-b75c5fe6fbcf
topic_type:
- apiref
ms.openlocfilehash: 1036ecbdb735b95c0ad6897c1545e3bd8cb6c3a9
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76867076"
---
# <a name="cor_prf_suspend_reason-enumeration"></a>COR_PRF_SUSPEND_REASON 열거형
런타임이 일시 중단 된 이유를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef enum {  
    COR_PRF_SUSPEND_OTHER                   = 0x00,  
    COR_PRF_SUSPEND_FOR_GC                  = 0x01,  
    COR_PRF_SUSPEND_FOR_APPDOMAIN_SHUTDOWN  = 0x02,  
    COR_PRF_SUSPEND_FOR_CODE_PITCHING       = 0x03,  
    COR_PRF_SUSPEND_FOR_SHUTDOWN            = 0x04,  
    COR_PRF_SUSPEND_FOR_INPROC_DEBUGGER     = 0x06,  
    COR_PRF_SUSPEND_FOR_GC_PREP             = 0x07,    COR_PRF_SUSPEND_FOR_REJIT               = 8  
} COR_PRF_SUSPEND_REASON;  
```  
  
## <a name="members"></a>Members  
  
|Member|설명|  
|------------|-----------------|  
|`COR_PRF_FIELD_SUSPEND_OTHER`|지정 되지 않은 이유로 런타임이 일시 중단 됩니다.|  
|`COR_PRF_FIELD_SUSPEND_FOR_GC`|런타임은 가비지 수집 요청을 처리 하기 위해 일시 중단 됩니다.<br /><br /> 가비지 컬렉션 관련 콜백은 [ICorProfilerCallback:: RuntimeSuspendFinished](icorprofilercallback-runtimesuspendfinished-method.md) 및 [ICorProfilerCallback:: Run Esumestarted](icorprofilercallback-runtimeresumestarted-method.md) 콜백 사이에서 발생 합니다.|  
|`COR_PRF_FIELD_SUSPEND_FOR_APPDOMAIN_SHUTDOWN`|`AppDomain`를 종료할 수 있도록 런타임이 일시 중단 됩니다.<br /><br /> 런타임이 일시 중단 된 동안 런타임에서는 종료 되는 `AppDomain`에 있는 스레드를 확인 하 고 다시 시작할 때 abort로 설정 합니다. 이 일시 중단 중에 `AppDomain`특정 콜백이 없습니다.|  
|`COR_PRF_FIELD_SUSPEND_FOR_CODE_PITCHING`|코드 피칭 발생할 수 있도록 런타임이 일시 중단 됩니다.<br /><br /> Code 피칭 ensues는 JIT (just-in-time) 컴파일러가 활성화 된 코드 피칭 사용 하는 경우에만 사용 됩니다. 코드 피칭 콜백은 `ICorProfilerCallback::RuntimeSuspendFinished`와 `ICorProfilerCallback::RuntimeResumeStarted` 콜백 사이에서 발생 합니다. **참고:**  CLR JIT는 .NET Framework 버전 2.0에서 함수를 피치 하지 않으므로 2.0에서는이 값이 사용 되지 않습니다.|  
|`COR_PRF_FIELD_SUSPEND_FOR_SHUTDOWN`|런타임이 종료 될 수 있도록 일시 중단 됩니다. 작업을 완료 하려면 모든 스레드를 일시 중단 해야 합니다.|  
|`COR_PRF_FIELD_SUSPEND_FOR_INPROC_DEBUGGER`|In-process 디버깅에 대해 런타임이 일시 중단 됩니다.|  
|`COR_PRF_FIELD_SUSPEND_FOR_GC_PREP`|가비지 수집을 준비 하기 위해 런타임이 일시 중단 됩니다.|  
|`COR_PRF_SUSPEND_FOR_REJIT`|JIT 재컴파일에 대해 런타임이 일시 중단 됩니다.|  
  
## <a name="remarks"></a>주의  
 비관리 코드에 있는 모든 런타임 스레드는 런타임을 다시 시작할 때까지 계속 실행 되도록 허용 되며, 런타임이 다시 시작 될 때까지 일시 중단 됩니다. 이는 런타임에 입력 하는 새 스레드에도 적용 됩니다. 런타임 내의 모든 스레드는 중단 될 수 있는 코드에 있는 경우 즉시 일시 중단 되 고, 인터럽트 가능 코드에 도달 하면 일시 중단을 요청 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조

- [프로파일링 열거형](profiling-enumerations.md)
