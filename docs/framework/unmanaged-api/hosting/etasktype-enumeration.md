---
title: ETaskType 열거형
ms.date: 03/30/2017
api_name:
- ETaskType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ETaskType
helpviewer_keywords:
- ETaskType enumeration [.NET Framework hosting]
ms.assetid: aa527b31-89d4-41f2-ad6f-63b76950b7df
topic_type:
- apiref
ms.openlocfilehash: 435d23d4a56d6ea98e3d368f0a5aa37c73e31d96
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616166"
---
# <a name="etasktype-enumeration"></a>ETaskType 열거형
[ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) 또는 [IHostTask](ihosttask-interface.md) 인터페이스로 표시 되는 작업의 유형을 나타내는 값을 포함 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef enum ETaskType {  
    TT_DEBUGGERHELPER           = 0x1,  
    TT_GC                       = 0x2,  
    TT_FINALIZER                = 0x4,  
    TT_THREADPOOL_TIMER         = 0x8,  
    TT_THREADPOOL_GATE          = 0x10,  
    TT_THREADPOOL_WORKER        = 0x20,  
    TT_THREADPOOL_IOCOMPLETION  = 0x40,  
    TT_ADUNLOAD                 = 0x80,  
    TT_USER                     = 0x100,  
    TT_THREADPOOL_WAIT          = 0x200,  
    TT_UNKNOWN                  = 0x80000000  
} ETaskType;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`TT_ADUNLOAD`|인터페이스는 응용 프로그램 도메인 언로드 태스크를 나타냅니다.|  
|`TT_DEBUGGERHELPER`|인터페이스는 디버거 도우미 태스크를 나타냅니다.|  
|`TT_FINALIZER`|인터페이스는 종료자 작업을 나타냅니다.|  
|`TT_GC`|인터페이스는 가비지 수집 작업을 나타냅니다.|  
|`TT_THREADPOOL_GATE`|인터페이스는 게이트 스레드 작업을 나타냅니다.|  
|`TT_THREADPOOL_IOCOMPLETION`|인터페이스는 i/o 스레드 작업 또는 완료 포트 스레드 작업을 나타냅니다.|  
|`TT_THREADPOOL_TIMER`|인터페이스는 타이머 스레드 작업을 나타냅니다.|  
|`TT_THREADPOOL_WAIT`|인터페이스는 대기 스레드 태스크를 나타냅니다.|  
|`TT_THREADPOOL_WORKER`|인터페이스는 작업자 스레드 태스크를 나타냅니다.|  
|`TT_UNKNOWN`|작업을 알 수 없습니다.|  
|`TT_USER`|인터페이스는 사용자 작업을 나타냅니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** Mscoree.dll  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [호스팅 열거형](hosting-enumerations.md)
