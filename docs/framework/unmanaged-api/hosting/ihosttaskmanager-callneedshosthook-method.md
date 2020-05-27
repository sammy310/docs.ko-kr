---
title: IHostTaskManager::CallNeedsHostHook 메서드
ms.date: 03/30/2017
api_name:
- IHostTaskManager.CallNeedsHostHook
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::CallNeedsHostHook
helpviewer_keywords:
- CallNeedsHostHook method [.NET Framework hosting]
- IHostTaskManager::CallNeedsHostHook method [.NET Framework hosting]
ms.assetid: b60f1f59-9825-4b57-961f-d2979518e6a7
topic_type:
- apiref
ms.openlocfilehash: 5bc5752d4d2b772b1d18f438c4daaa1b8938da9e
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842350"
---
# <a name="ihosttaskmanagercallneedshosthook-method"></a>IHostTaskManager::CallNeedsHostHook 메서드
호스트에서 CLR (공용 언어 런타임)이 관리 되지 않는 함수에 대 한 지정 된 호출을 인라인 할 수 있는지 여부를 지정할 수 있도록 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT CallNeedsHostHook (  
    [in]  SIZE_T target,
    [out] BOOL   *pbCallNeedsHostHook  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `target`  
 진행 호출 될 관리 되지 않는 함수의 매핑된 PE (이식 가능한 실행) 파일 내 주소입니다.  
  
 `pbCallNeedsHostHook`  
 제한이 호스트에서 후크를 호출 해야 하는지 여부를 나타내는 부울 값에 대 한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|Description|  
|-------------|-----------------|  
|S_OK|`CallNeedsHostHook`성공적으로 반환 되었습니다.|  
|HOST_E_CLRNOTAVAILABLE|CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자가 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다. 호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.|  
  
## <a name="remarks"></a>설명  
 CLR은 코드 실행을 최적화 하는 데 도움이 되도록 컴파일하는 동안 각 플랫폼 호출에 대 한 분석을 수행 하 여 호출이 인라인 될 수 있는지 여부를 확인 합니다. `CallNeedsHostHook`관리 되지 않는 함수에 대 한 호출이 후크 되도록 요구 하 여 호스트가 해당 결정을 재정의할 수 있도록 합니다. 호스트에 후크가 필요 하면 런타임에서 호출을 인라인 하지 않습니다.  
  
 호스트에는 일반적으로 부동 소수점 상태를 조정 해야 하는 후크가 필요 합니다. 또는 호출이 호스트에서 메모리 또는 사용 된 모든 잠금에 대 한 런타임 요청을 추적할 수 없는 상태를 호출 한다는 알림이 필요 합니다. 호스트에서 호출이 후크 되어야 하는 경우 런타임은 [EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md), [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md), [ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md)및 [ReverseLeaveRuntime](ihosttaskmanager-reverseleaveruntime-method.md)에 대 한 호출을 사용 하 여 관리 코드와의 전환을 호스트에 알립니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICLRTask 인터페이스](iclrtask-interface.md)
- [ICLRTaskManager 인터페이스](iclrtaskmanager-interface.md)
- [IHostTask 인터페이스](ihosttask-interface.md)
- [IHostTaskManager 인터페이스](ihosttaskmanager-interface.md)
