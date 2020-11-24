---
title: IHostTaskManager 인터페이스
ms.date: 03/30/2017
api_name:
- IHostTaskManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager
helpviewer_keywords:
- IHostTaskManager interface [.NET Framework hosting]
ms.assetid: 4a0b05b9-3ef1-4607-b7c8-bd4dd43647a0
topic_type:
- apiref
ms.openlocfilehash: deb14d291bfd511e8f3534f3c5e32787c259c5e8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673113"
---
# <a name="ihosttaskmanager-interface"></a>IHostTaskManager 인터페이스

표준 운영 체제 스레딩 또는 파이버 함수를 사용 하는 대신 CLR (공용 언어 런타임)이 호스트를 통해 작업을 수행할 수 있도록 하는 메서드를 제공 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[BeginDelayAbort 메서드](ihosttaskmanager-begindelayabort-method.md)|관리 코드가 현재 작업을 중단 하지 않아야 하는 기간을 입력 했음을 호스트에 알립니다.|  
|[BeginThreadAffinity 메서드](ihosttaskmanager-beginthreadaffinity-method.md)|관리 코드에서 현재 작업을 다른 운영 체제 스레드로 이동 하지 않아야 하는 기간이 입력 되었음을 호스트에 알립니다.|  
|[CallNeedsHostHook 메서드](ihosttaskmanager-callneedshosthook-method.md)|호스트에서 공용 언어 런타임이 관리 되지 않는 함수에 대 한 지정 된 호출을 인라인 할 수 있는지 여부를 지정할 수 있도록 합니다.|  
|[CreateTask 메서드](ihosttaskmanager-createtask-method.md)|호스트에서 새 작업을 만들도록 요청 합니다.|  
|[EndDelayAbort 메서드](ihosttaskmanager-enddelayabort-method.md)|에 대 한 이전 호출에 따라 관리 코드가 현재 작업을 중단 하지 않아야 하는 기간을 종료 하 고 있음을 호스트에 알립니다 `BeginDelayAbort` .|  
|[EndThreadAffinity 메서드](ihosttaskmanager-endthreadaffinity-method.md)|이전에를 호출 하 여 관리 코드가 현재 작업을 다른 운영 체제 스레드로 이동 하지 않아야 하는 기간을 호스트에 알립니다 `BeginThreadAffinity` .|  
|[EnterRuntime 메서드](ihosttaskmanager-enterruntime-method.md)|플랫폼 호출 메서드와 같은 관리 되지 않는 메서드에 대 한 호출이 CLR에 실행 제어를 반환 한다는 것을 호스트에 알립니다.|  
|[GetCurrentTask 메서드](ihosttaskmanager-getcurrenttask-method.md)|이 호출이 수행 되는 운영 체제 스레드에서 현재 실행 중인 작업에 대 한 인터페이스 포인터를 가져옵니다.|  
|[GetStackGuarantee 메서드](ihosttaskmanager-getstackguarantee-method.md)|스택 작업이 완료 된 후 프로세스가 종료 되기 전에 사용할 수 있도록 보장 되는 스택 공간의 크기를 가져옵니다.|  
|[LeaveRuntime 메서드](ihosttaskmanager-leaveruntime-method.md)|관리 코드에서 관리 되지 않는 함수에 대 한 호출을 수행 하려고 했음을 호스트에 알립니다.|  
|[ReverseEnterRuntime 메서드](ihosttaskmanager-reverseenterruntime-method.md)|비관리 코드에서 CLR (공용 언어 런타임)에 대 한 호출이 수행 되 고 있음을 호스트에 알립니다.|  
|[ReverseLeaveRuntime 메서드](ihosttaskmanager-reverseleaveruntime-method.md)|관리 코드에서 호출 된 관리 되지 않는 함수를 제어 하 고 있음을 호스트에 알립니다.|  
|[SetCLRTaskManager 메서드](ihosttaskmanager-setclrtaskmanager-method.md)|호스트에 CLR에서 구현 하는 [ICLRTaskManager](iclrtaskmanager-interface.md) 인스턴스에 대 한 인터페이스 포인터를 제공 합니다.|  
|[SetLocale 메서드](ihosttaskmanager-setlocale-method.md)|CLR이 현재 작업에 대 한 로캘을 변경 했음을 호스트에 알립니다.|  
|[SetStackGuarantee 메서드](ihosttaskmanager-setstackguarantee-method.md)|이 속성은 내부 전용으로 예약되어 있으므로|  
|[SetUILocale 메서드](ihosttaskmanager-setuilocale-method.md)|현재 작업에서 사용자 인터페이스 로캘이 변경 되었음을 호스트에 알립니다.|  
|[Sleep 메서드](ihosttaskmanager-sleep-method.md)|현재 태스크가 절전 모드로 전환 되었음을 호스트에 알립니다.|  
|[SwitchToTask 메서드](ihosttaskmanager-switchtotask-method.md)|현재 작업을 전환 해야 함을 호스트에 알립니다.|  
  
## <a name="remarks"></a>설명  

 `IHostTaskManager` CLR에서 작업을 생성 및 관리 하 고, 관리 코드에서 비관리 코드로의 제어가 전송 될 때 호스트에 대 한 후크를 제공 하 고, 해당 호스트에서 코드 실행 중에 수행할 수 있는 특정 작업을 지정할 수 있도록 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICLRTask 인터페이스](iclrtask-interface.md)
- [ICLRTaskManager 인터페이스](iclrtaskmanager-interface.md)
- [IHostTask 인터페이스](ihosttask-interface.md)
- [호스팅 인터페이스](hosting-interfaces.md)
