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
ms.openlocfilehash: f8fde4905c41dffde90c6361b5a8cdffa15deb4a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503967"
---
# <a name="iclrsyncmanagercreaterwlockowneriterator-method"></a>ICLRSyncManager::CreateRWLockOwnerIterator 메서드
CLR (공용 언어 런타임)이 판독기-작성기 잠금을 기다리는 작업 집합을 결정 하는 데 사용할 반복기를 호스트에 만들도록 요청 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT CreateRWLockOwnerIterator (  
    [in]  SIZE_T    cookie,  
    [out] SIZE_T   *pIterator  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `cookie`  
 진행 원하는 판독기-작성기 잠금과 연결 된 쿠키입니다.  
  
 `pIterator`  
 제한이 [GetRWLockOwnerNext](iclrsyncmanager-getrwlockownernext-method.md) 및 [DeleteRWLockOwnerIterator](iclrsyncmanager-deleterwlockowneriterator-method.md) 메서드에 전달할 수 있는 반복기에 대 한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|`CreateRWLockOwnerIterator`성공적으로 반환 되었습니다.|  
|HOST_E_CLRNOTAVAILABLE|CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자가 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다. 호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.|  
|HOST_E_INVALIDOPERATION|`CreateRWLockOwnerIterator`현재 관리 코드를 실행 하 고 있는 스레드에서를 호출 했습니다.|  
  
## <a name="remarks"></a>설명  
 호스트는 일반적으로 `CreateRWLockOwnerIterator` `DeleteRWLockOwnerIterator` 교착 상태를 검색 하는 동안, 및 메서드를 호출 합니다 `GetRWLockOwnerNext` . 이 경우에는 CLR에서 판독기-작성기 잠금을 활성 상태로 유지할 필요가 없기 때문에 호스트에서 판독기-작성기 잠금이 여전히 유효한 지 확인 해야 합니다. 호스트에서 잠금의 유효성을 확인 하는 데 사용할 수 있는 몇 가지 전략이 있습니다.  
  
- 이 블록이 교착 상태를 발생 시 키 지 않도록 하는 동시에 호스트는 판독기-작성기 잠금 (예 [: IHostSemaphore:: ReleaseSemaphore](ihostsemaphore-releasesemaphore-method.md))에서 릴리스 호출을 차단할 수 있습니다.  
  
- 호스트는 판독기-작성기 잠금과 연결 된 이벤트 개체를 대기 하는 것을 차단 하 여이 블록이 교착 상태를 발생 시 키 지 않도록 합니다.  
  
> [!NOTE]
> `CreateRWLockOwnerIterator`는 현재 비관리 코드를 실행 하는 스레드에서만 호출 해야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICLRSyncManager 인터페이스](iclrsyncmanager-interface.md)
- [IHostSyncManager 인터페이스](ihostsyncmanager-interface.md)
