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
ms.openlocfilehash: 8b8b8521a09fa54a105e8263a471ab0467fb6ccc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176294"
---
# <a name="ihosttaskmanagercallneedshosthook-method"></a>IHostTaskManager::CallNeedsHostHook 메서드
호스트가 공통 언어 런타임(CLR)이 지정된 호출을 관리되지 않는 함수에 인라인할 수 있는지 여부를 지정할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT CallNeedsHostHook (  
    [in]  SIZE_T target,
    [out] BOOL   *pbCallNeedsHostHook  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `target`  
 【인】 호출할 관리되지 않는 함수의 매핑된 이식형 실행 파일(PE) 내의 주소입니다.  
  
 `pbCallNeedsHostHook`  
 【아웃】 호스트에 연결해야 하는 호출을 사용할지 여부를 나타내는 부울 값에 대한 포인터입니다.  
  
## <a name="return-value"></a>Return Value  
  
|HRESULT|Description|  
|-------------|-----------------|  
|S_OK|`CallNeedsHostHook`성공적으로 반환됩니다.|  
|HOST_E_CLRNOTAVAILABLE|CLR이 프로세스에 로드되지 않았거나 CLR이 관리 코드를 실행하거나 호출을 성공적으로 처리할 수 없는 상태입니다.|  
|HOST_E_TIMEOUT|통화 시간이 시간 미정으로 확인되었습니다.|  
|HOST_E_NOT_OWNER|호출자는 잠금을 소유하지 않습니다.|  
|HOST_E_ABANDONED|차단된 스레드 또는 파이버가 대기하는 동안 이벤트가 취소되었습니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생했습니다. 메서드가 E_FAIL 반환하면 프로세스 내에서 CLR을 더 이상 사용할 수 없습니다. 호스팅 메서드에 대한 후속 호출은 HOST_E_CLRNOTAVAILABLE 반환합니다.|  
  
## <a name="remarks"></a>설명  
 코드 실행을 최적화하기 위해 CLR은 컴파일 중에 호출을 호출하는 각 플랫폼에 대한 분석을 수행하여 호출을 인라인할 수 있는지 여부를 결정합니다. `CallNeedsHostHook`호스트가 관리되지 않는 함수에 대한 호출을 연결하도록 요구하여 해당 결정을 재정의할 수 있습니다. 호스트에 후크가 필요한 경우 런타임이 호출에 인라인되지 않습니다.  
  
 호스트는 일반적으로 부동 지점 상태를 조정해야 하는 후크가 필요하거나 호출이 런타임의 메모리 요청 또는 잠금 을 추적할 수 없는 상태가 된다는 알림을 받을 때 필요합니다. 호스트가 호출을 연결해야 하는 경우 런타임은 [EnterRuntime,](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md) [LeaveRuntime,](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md) [ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md)및 [ReverseLeaveRunTime에](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md)대한 호출을 사용하여 관리 코드로 전환 호스트를 통보합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** MSCorE.h  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICLRTask 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [ICLRTaskManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [IHostTask 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [IHostTaskManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
