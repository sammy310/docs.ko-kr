---
title: ICLRTask 인터페이스
ms.date: 03/30/2017
api_name:
- ICLRTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask
helpviewer_keywords:
- ICLRTask interface [.NET Framework hosting]
ms.assetid: b3a44df3-578a-4451-b55e-70c8e7695f5e
topic_type:
- apiref
ms.openlocfilehash: 5ecc42950775a620796a1c775e5f088f461a12c3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690826"
---
# <a name="iclrtask-interface"></a>ICLRTask 인터페이스

호스트가 CLR (공용 언어 런타임)에 대 한 요청을 수행 하거나 CLR에 연결 된 작업에 대 한 알림을 제공할 수 있도록 하는 메서드를 제공 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[Abort 메서드](iclrtask-abort-method.md)|현재 인스턴스가 나타내는 작업을 CLR에서 중단 하도록 요청 `ICLRTask` 합니다.|  
|[ExitTask 메서드](iclrtask-exittask-method.md)|현재 인스턴스와 연결 된 태스크가 종료 되 고 있음을 CLR에 알리고 `ICLRTask` 작업을 정상적으로 종료 하려고 시도 합니다.|  
|[GetMemStats 메서드](iclrtask-getmemstats-method.md)|현재 인스턴스에서 나타내는 작업의 메모리 리소스 사용에 대 한 통계 정보를 가져옵니다 `ICLRTask` .|  
|[LocksHeld 메서드](iclrtask-locksheld-method.md)|작업에 대해 현재 보유 하 고 있는 잠금 수를 가져옵니다.|  
|[NeedsPriorityScheduling 메서드](iclrtask-needspriorityscheduling-method.md)|현재 인스턴스가 나타내는 작업을 다시 예약 하기 위해 호스트에서 높은 우선 순위를 할당 해야 하는지 여부를 나타내는 값을 가져옵니다 `ICLRTask` .|  
|[Reset 메서드](iclrtask-reset-method.md)|호스트가 작업을 완료 했음을 CLR에 알리고 CLR에서 현재 인스턴스를 다시 사용 하 여 다른 작업을 나타낼 수 있도록 합니다 `ICLRTask` .|  
|[RudeAbort 메서드](iclrtask-rudeabort-method.md)|`ICLRTask`종료 자가 실행 되는 것을 보장 하지 않고 CLR이 현재 인스턴스로 표시 된 작업을 즉시 중단 하도록 합니다.|  
|[SetTaskIdentifier 메서드](iclrtask-settaskidentifier-method.md)|디버깅에 사용 하기 위해 현재 인스턴스가 나타내는 작업의 고유 식별자를 설정 합니다 `ICLRTask` .|  
|[SwitchIn 메서드](iclrtask-switchin-method.md)|현재 인스턴스가 나타내는 작업이 작동할 수 있는 상태임을 CLR에 알립니다 `ICLRTask` .|  
|[SwitchOut 메서드](iclrtask-switchout-method.md)|현재 인스턴스가 나타내는 작업이 더 이상 작동 하지 않는 상태임을 CLR에 알립니다 `ICLRTask` .|  
|[YieldTask 메서드](iclrtask-yieldtask-method.md)|CLR에서 프로세서 시간을 다른 작업에 사용할 수 있도록 요청 합니다. CLR은 태스크가 처리 시간을 얻을 수 있는 상태로 전환 되는 것을 보장 하지 않습니다.|  
  
## <a name="remarks"></a>설명  

 는 `ICLRTask` CLR의 작업 표현입니다. 코드를 실행 하는 동안 언제 든 지 실행 중이거나 실행 대기 중으로 작업을 설명할 수 있습니다. 호스트는 메서드를 호출 `ICLRTask::SwitchIn` 하 여 현재 인스턴스를 나타내는 작업이 현재 작동 가능한 상태 임을 CLR에 알립니다 `ICLRTask` . 를 호출한 후 `ICLRTask::SwitchIn` 호스트는 [IHostTaskManager:: beginthreadaffinity](ihosttaskmanager-beginthreadaffinity-method.md) 및 [IHostTaskManager:: endthreadaffinity](ihosttaskmanager-endthreadaffinity-method.md) 메서드 호출에 지정 된 대로 런타임에 스레드 선호도가 필요한 경우를 제외 하 고 모든 운영 체제 스레드에서 작업을 예약할 수 있습니다. 잠시 후 운영 체제에서 작업을 스레드에서 제거 하 고 실행 되지 않는 상태로 둘 수 있습니다. 예를 들어 작업이 동기화 기본 형식에서 차단 될 때마다 또는 i/o 작업이 완료 될 때까지 기다릴 수 있습니다. 호스트는 [Switchout](iclrtask-switchout-method.md) 을 호출 하 여 현재 인스턴스가 나타내는 작업이 더 이상 작동 하지 않는 상태임을 CLR에 알립니다 `ICLRTask` .  
  
 일반적으로 작업은 코드 실행이 끝날 때 종료 됩니다. 이때 호스트는를 호출 하 여 `ICLRTask::ExitTask` 연결 된를 제거 합니다 `ICLRTask` . 그러나에 대 한 호출을 사용 하 여 작업을 재활용할 수도 있습니다 .이를 통해 `ICLRTask::Reset` `ICLRTask` 인스턴스를 다시 사용할 수 있습니다. 이 방법은 인스턴스를 반복적으로 만들고 삭제 하는 오버 헤드를 방지 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICLRTaskManager 인터페이스](iclrtaskmanager-interface.md)
- [IHostTask 인터페이스](ihosttask-interface.md)
- [IHostTaskManager 인터페이스](ihosttaskmanager-interface.md)
- [호스팅 인터페이스](hosting-interfaces.md)
- [ICLRTask2 인터페이스](iclrtask2-interface.md)
