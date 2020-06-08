---
title: IHostSyncManager 인터페이스
ms.date: 03/30/2017
api_name:
- IHostSyncManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager
helpviewer_keywords:
- IHostSyncManager interface [.NET Framework hosting]
ms.assetid: 2e081a37-6a28-4c93-b7ab-1c96a464637c
topic_type:
- apiref
ms.openlocfilehash: fd3c941d89fbd93f30fc1af235f6310b23758973
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501458"
---
# <a name="ihostsyncmanager-interface"></a>IHostSyncManager 인터페이스
Win32 동기화 함수를 사용 하는 대신 호스트를 호출 하 여 CLR (공용 언어 런타임)에서 동기화 기본 형식을 만들 수 있도록 하는 메서드를 제공 합니다.  
  
## <a name="methods"></a>메서드  
  
|방법|설명|  
|------------|-----------------|  
|[CreateAutoEvent 메서드](ihostsyncmanager-createautoevent-method.md)|자동 다시 설정 이벤트 개체를 만듭니다.|  
|[CreateCrst 메서드](ihostsyncmanager-createcrst-method.md)|동기화에 대 한 임계 영역 개체를 만듭니다.|  
|[CreateCrstWithSpinCount 메서드](ihostsyncmanager-createcrstwithspincount-method.md)|동기화에 대 한 회전 수를 사용 하 여 임계 영역 개체를 만듭니다.|  
|[CreateManualEvent 메서드](ihostsyncmanager-createmanualevent-method.md)|수동 다시 설정 이벤트 개체를 만듭니다.|  
|[CreateMonitorEvent 메서드](ihostsyncmanager-createmonitorevent-method.md)|모니터링 되는 자동 다시 설정 이벤트 개체를 만듭니다.|  
|[CreateRWLockReaderEvent 메서드](ihostsyncmanager-createrwlockreaderevent-method.md)|판독기 잠금 구현에 대 한 수동 다시 설정 이벤트 개체를 만듭니다.|  
|[CreateRWLockWriterEvent 메서드](ihostsyncmanager-createrwlockwriterevent-method.md)|작성기 잠금 구현에 대 한 자동 다시 설정 이벤트 개체를 만듭니다.|  
|[CreateSemaphore 메서드](ihostsyncmanager-createsemaphore-method.md)|대기 이벤트에 대 한 세마포에 사용할 CLR에 대 한 [IHostSemaphore](ihostsemaphore-interface.md) 개체를 만듭니다.|  
|[SetCLRSyncManager 메서드](ihostsyncmanager-setclrsyncmanager-method.md)|현재 인스턴스와 연결할 [ICLRSyncManager](iclrsyncmanager-interface.md) 인스턴스를 설정 합니다 `IHostSyncManager` .|  
  
## <a name="remarks"></a>설명  
 CLR은 IID_IHostSyncManager의를 사용 하 여 `IHostSyncManager` [IHostControl:: GetHostManager](ihostcontrol-gethostmanager-method.md) 메서드를 호출 하 여 호스트의 구현을 검색 합니다 `IID` .  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICLRSyncManager 인터페이스](iclrsyncmanager-interface.md)
- [호스팅 인터페이스](hosting-interfaces.md)
