---
title: IHostTaskManager::CreateTask 메서드
ms.date: 03/30/2017
api_name:
- IHostTaskManager.CreateTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::CreateTask
helpviewer_keywords:
- CreateTask method, IHostTaskManager interface [.NET Framework hosting]
- IHostTaskManager::CreateTask method [.NET Framework hosting]
ms.assetid: a6f8ad36-61e1-42b0-9db2-add575646d18
topic_type:
- apiref
ms.openlocfilehash: fef2f56fd000a8610a40661a30aa306ae5a7884e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177996"
---
# <a name="ihosttaskmanagercreatetask-method"></a>IHostTaskManager::CreateTask 메서드
호스트가 새 작업을 만들라는 요청입니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT CreateTask (  
    [in]  DWORD stacksize,
    [in]  LPTHREAD_START_ROUTINE pStartAddress,  
    [in]  PVOID pParameter,  
    [out] IHostTask **ppTask  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `stacksize`  
 【인】 요청된 크기(바이트)의 요청된 스택 또는 기본 크기의 경우 0(0)입니다.  
  
 `pStartAddress`  
 【인】 작업이 실행되는 함수에 대한 포인터입니다.  
  
 `pParameter`  
 【인】 함수에 전달할 사용자 데이터에 대한 포인터 또는 함수에 매개 변수가 없는 경우 null입니다.  
  
 `ppTask`  
 【아웃】 호스트에서 만든 [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) 인스턴스의 주소에 대한 포인터 또는 작업을 만들 수 없는 경우 null입니다. 작업은 [IHostTask ::Start에](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md)대한 호출에 의해 명시적으로 시작될 때까지 일시 중단된 상태로 유지됩니다.  
  
## <a name="return-value"></a>Return Value  
  
|HRESULT|Description|  
|-------------|-----------------|  
|S_OK|`CreateTask`성공적으로 반환됩니다.|  
|HOST_E_CLRNOTAVAILABLE|공통 언어 런타임(CLR)이 프로세스에 로드되지 않았거나 CLR이 관리 코드를 실행하거나 호출을 성공적으로 처리할 수 없는 상태입니다.|  
|HOST_E_TIMEOUT|통화 시간이 시간 미정으로 확인되었습니다.|  
|HOST_E_NOT_OWNER|호출자는 잠금을 소유하지 않습니다.|  
|HOST_E_ABANDONED|차단된 스레드 또는 파이버가 대기하는 동안 이벤트가 취소되었습니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생했습니다. 메서드가 E_FAIL 반환하면 프로세스 내에서 CLR을 더 이상 사용할 수 없습니다. 호스팅 메서드에 대한 후속 호출은 HOST_E_CLRNOTAVAILABLE 반환합니다.|  
|E_OUTOFMEMORY|요청된 작업을 만들 수 있는 메모리가 부족합니다.|  
  
## <a name="remarks"></a>설명  
 CLR은 `CreateTask` 호스트가 새 작업을 만들도록 요청하도록 호출합니다. 호스트는 인스턴스에 인터페이스 `IHostTask` 포인터를 반환합니다. 반환된 작업은 `IHostTask::Start`에 대한 호출에 의해 명시적으로 시작될 때까지 일시 중단된 상태로 유지되어야 합니다.  
  
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
