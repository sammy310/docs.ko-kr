---
title: ICLRSyncManager::GetMonitorOwner 메서드
ms.date: 03/30/2017
api_name:
- ICLRSyncManager.GetMonitorOwner
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRSyncManager::GetMonitorOwner
helpviewer_keywords:
- ICLRSyncManager::GetMonitorOwner method [.NET Framework hosting]
- GetMonitorOwner method [.NET Framework hosting]
ms.assetid: 840983a4-396d-47b4-86a0-d35f9b437cdb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4b14421bbe71b68ca677cf712512a7f10aa30583
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763628"
---
# <a name="iclrsyncmanagergetmonitorowner-method"></a>ICLRSyncManager::GetMonitorOwner 메서드
가져옵니다 합니다 [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) 지정한 쿠키로 식별 되는 모니터를 소유 하는 인스턴스.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetMonitorOwner (  
    [in]  SIZE_T     cookie,  
    [out] IHostTask *ppOwnerHostTask  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `cookie`  
 [in] 모니터와 관련 된 쿠키입니다.  
  
 `ppOwnerHostTask`  
 [out] 에 대 한 포인터를 `IHostTask` 현재 소유 하는 모니터 또는 null 소유권이 없는 작업 하는 경우.  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|`GetMonitorOwner` 성공적으로 반환 합니다.|  
|HOST_E_CLRNOTAVAILABLE|CLR이 로드 된 프로세스에 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자가 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다. 메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.|  
  
## <a name="remarks"></a>설명  
 호스트는 일반적으로 호출 `GetMonitorOwner` 교착 상태 감지 메커니즘의 일부분으로 합니다. 쿠키와 관련이 모니터에 대 한 호출을 사용 하 여 만들어지면 [ihostsyncmanager:: Createmonitorevent](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmonitorevent-method.md)합니다.  
  
> [!NOTE]
>  모니터를 내부 이벤트를 해제 하는 호출 되지 않을-교착 상태가 되지 않고-이 메서드에 대 한 호출에서 실행 되는 모니터와 관련 된 쿠키에 하는 경우. 이 모니터를 획득 하려고 할 경우에 다른 작업 차단할 수도 있습니다.  
  
 `GetMonitorOwner` 항상 즉시 반환 하 고 호출 후 언제 든 지 호출할 수 있습니다 `CreateMonitorEvent`합니다. 호스트는 태스크가 대기 하는 이벤트에 대 한 때까지 대기 하지 않아도 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [ICLRSyncManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [IHostSyncManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
