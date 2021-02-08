---
description: '자세히 알아보기: ICLRSyncManager:: GetRWLockOwnerNext 메서드'
title: ICLRSyncManager::GetRWLockOwnerNext 메서드
ms.date: 03/30/2017
api_name:
- ICLRSyncManager.GetRWLockOwnerNext
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRSyncManager::GetRWLockOwnerNext
helpviewer_keywords:
- ICLRSyncManager::GetRWLockOwnerNext method [.NET Framework hosting]
- GetRWLockOwnerNext method [.NET Framework hosting]
ms.assetid: 0e025b6a-280e-40a2-a2d0-b15f58777b81
topic_type:
- apiref
ms.openlocfilehash: f49bdd5065ac896147967c0a013347ab39ce1eff
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784998"
---
# <a name="iclrsyncmanagergetrwlockownernext-method"></a>ICLRSyncManager::GetRWLockOwnerNext 메서드

현재 판독기-작성기 잠금에서 차단 된 다음 [IHostTask](ihosttask-interface.md) 인스턴스를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT GetRWLockOwnerNext (  
    [in] SIZE_T       Iterator,  
    [out] IHostTask  *ppOwnerHostTask  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `Iterator`  
 진행 [CreateRWLockOwnerIterator](iclrsyncmanager-createrwlockowneriterator-method.md)에 대 한 호출을 사용 하 여 만든 반복기입니다.  
  
 `ppOwnerHostTask`  
 제한이 잠금을 기다리는 다음에 대 한 포인터 `IHostTask` 이거나, 대기 중인 태스크가 없는 경우 null입니다.  
  
## <a name="return-value"></a>Return Value  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|`GetRWLockOwnerNext` 성공적으로 반환 되었습니다.|  
|HOST_E_CLRNOTAVAILABLE|CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자가 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다. 호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.|  
  
## <a name="remarks"></a>설명  

 `ppOwnerHostTask`가 null로 설정 되 면 반복이 종료 되 고 호스트에서 [DeleteRWLockOwnerIterator](iclrsyncmanager-deleterwlockowneriterator-method.md) 메서드를 호출 해야 합니다.  
  
> [!NOTE]
> CLR은에 `AddRef` 대해를 호출 하 여 `IHostTask` `ppOwnerHostTask` 호스트가 포인터를 보유 하는 동안이 작업을 종료 하지 못하도록 합니다. `Release`완료 되 면 호스트는를 호출 하 여 참조 횟수를 감소 시켜야 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICLRSyncManager 인터페이스](iclrsyncmanager-interface.md)
- [IHostSyncManager 인터페이스](ihostsyncmanager-interface.md)
