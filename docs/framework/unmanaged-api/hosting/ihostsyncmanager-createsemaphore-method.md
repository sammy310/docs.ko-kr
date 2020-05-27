---
title: IHostSyncManager::CreateSemaphore 메서드
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateSemaphore
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateSemaphore
helpviewer_keywords:
- CreateSemaphore method [.NET Framework hosting]
- IHostSyncManager::CreateSemaphore method [.NET Framework hosting]
ms.assetid: 37679e94-5ff9-4173-8fa5-457febeb89bf
topic_type:
- apiref
ms.openlocfilehash: 680280e959d523356b95a5a4d9390c80720c0330
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/22/2020
ms.locfileid: "83803133"
---
# <a name="ihostsyncmanagercreatesemaphore-method"></a>IHostSyncManager::CreateSemaphore 메서드
대기 이벤트에 대 한 세마포에 사용할 CLR (공용 언어 런타임)에 대 한 [IHostSemaphore](ihostsemaphore-interface.md) 개체를 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT CreateSemaphore (  
    [in]  DWORD dwInitial,  
    [in]  DWORD dwMax,  
    [out] IHostSemaphore **ppSemaphore  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `dwInitial`  
 진행 의 초기 개수 `ppSemaphore` 입니다.  
  
 `dwMax`  
 진행 의 최대 개수 `ppSemaphore` 입니다.  
  
 `ppSemaphore`  
 제한이 인스턴스의 주소에 대 한 포인터 `IHostSemaphore` 이거나, 세마포를 만들 수 없는 경우 null입니다.  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|Description|  
|-------------|-----------------|  
|S_OK|`CreateSemaphore`성공적으로 반환 되었습니다.|  
|HOST_E_CLRNOTAVAILABLE|CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자가 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다. 호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.|  
|E_OUTOFMEMORY|메모리가 부족 하 여 요청한 이벤트 개체를 만들 수 없습니다.|  
  
## <a name="remarks"></a>설명  
 `CreateSemaphore`이름이 같은 Win32 함수를 미러링합니다. `dwInitial`및 `dwMax` 매개 변수는 `lInitialCount` 각각 Win32 및 매개 변수와 동일한 세마포 수의 의미 체계를 사용 합니다 `lMaximumCount` . `dwInitial`0과 (포함) 사이 여야 합니다 `dwMax` . `dwMax`0 보다 커야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICLRSyncManager 인터페이스](iclrsyncmanager-interface.md)
- [IHostSemaphore 인터페이스](ihostsemaphore-interface.md)
- [IHostSyncManager 인터페이스](ihostsyncmanager-interface.md)
