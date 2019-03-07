---
title: ICLRSyncManager::CreateRWLockOwnerIterator 메서드
ms.date: 03/30/2017
api_name:
- ICLRSyncManager.CreateRWLockOwnerIterator
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRSyncManager::CreateRWLockOwnerIterator
helpviewer_keywords:
- ICLRSyncManager::CreateRWLockOwnerIterator method [.NET Framework hosting]
- CreateRWLockOwnerIterator method [.NET Framework hosting]
ms.assetid: b5535b87-9439-424e-b9b3-7d6fafb9819e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b2b9c2fb2a4ddcc39c7690d832a94d772e8b82a3
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57497082"
---
# <a name="iclrsyncmanagercreaterwlockowneriterator-method"></a>ICLRSyncManager::CreateRWLockOwnerIterator 메서드
CLR (공용 언어 런타임)에서 판독기-기록기 잠금을 대기 하는 태스크 집합을 결정 하는 데 호스트에 대 한 반복기를 만들도록 요청 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT CreateRWLockOwnerIterator (  
    [in]  SIZE_T    cookie,  
    [out] SIZE_T   *pIterator  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `cookie`  
 [in] 원하는 판독기-기록기 잠금과 사용 하 여 연결 된 쿠키입니다.  
  
 `pIterator`  
 [out] 에 전달 될 수 있는 반복기에 대 한 포인터를 [GetRWLockOwnerNext](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getrwlockownernext-method.md) 하 고 [DeleteRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md) 메서드.  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|`CreateRWLockOwnerIterator` 성공적으로 반환 합니다.|  
|HOST_E_CLRNOTAVAILABLE|CLR이 로드 된 프로세스에 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자가 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다. 메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.|  
|HOST_E_INVALIDOPERATION|`CreateRWLockOwnerIterator` 관리 되는 코드를 현재 실행 중인 스레드에서 호출 되었습니다.|  
  
## <a name="remarks"></a>설명  
 일반적으로 호스트를 호출 합니다 `CreateRWLockOwnerIterator`, `DeleteRWLockOwnerIterator`, 및 `GetRWLockOwnerNext` 교착 상태 감지 하는 동안 메서드. 호스트는 CLR에서는 판독기-기록기 잠금을 유지 하지 때문에 판독기 / 기록기 잠금이 여전히 유효한 지 확인 하는 일을 담당 합니다. 몇 가지 전략 호스트를 잠금의 유효성을 확인 하는 데 사용할 수 있습니다.  
  
-   호스트는 판독기 및 작성기 잠금 해제 호출이 차단할 수 있습니다 (예를 들어 [ihostsemaphore:: Releasesemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-releasesemaphore-method.md)) 하면서이 블록 교착 상태가 발생 하지 않습니다.  
  
-   호스트에 다시이 블록 교착 상태가 발생 하지 않습니다을 보장 판독기-기록기 잠금과 사용 하 여 연결 된 이벤트 개체에 대 한 대기 종료를 차단할 수 있습니다.  
  
> [!NOTE]
>  `CreateRWLockOwnerIterator` 스레드가 현재 실행 중인 관리 되지 않는 코드 에서만 호출 되어야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고자료
- [ICLRSyncManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [IHostSyncManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
