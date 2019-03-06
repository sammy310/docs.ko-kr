---
title: IHostTaskManager::LeaveRuntime 메서드
ms.date: 03/30/2017
api_name:
- IHostTaskManager.LeaveRuntime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::LeaveRuntime
helpviewer_keywords:
- IHostTaskManager::LeaveRuntime method [.NET Framework hosting]
- LeaveRuntime method [.NET Framework hosting]
ms.assetid: 43689cc4-e48e-46e5-a22d-bafd768b8759
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2059657a6f4543ee29d795ecae7b93b72876fdf4
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57474633"
---
# <a name="ihosttaskmanagerleaveruntime-method"></a>IHostTaskManager::LeaveRuntime 메서드
현재 실행 중인 작업의 CLR (공용 언어 런타임)을 유지 하 고 비관리 코드는 호스트에 알립니다.  
  
> [!IMPORTANT]
>  해당 호출 [ihosttaskmanager:: Enterruntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md) 현재 실행 중인 작업 관리 코드를 다시 입력은 호스트에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT LeaveRuntime (  
    [in] SIZE_T target  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `target`  
 [in] 관리 되지 않는 함수를 호출할 수의 매핑된 이식 가능한 실행 파일 내 주소입니다.  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|`LeaveRuntime` 성공적으로 반환 합니다.|  
|HOST_E_CLRNOTAVAILABLE|CLR이 로드 된 프로세스에 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자가 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다. 메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.|  
|E_OUTOFMEMORY|메모리가 부족 하 여 요청 된 할당을 완료할 수 없습니다.|  
  
## <a name="remarks"></a>설명  
 비관리 코드 간의 호출 시퀀스를 중첩할 수 있습니다. 아래 목록에는 있는 가상의 상황을 설명 하는 예를 들어,에 대 한 호출의 시퀀스 `LeaveRuntime`하십시오 [ihosttaskmanager:: Reverseenterruntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md), [ihosttaskmanager:: Reverseleaveruntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md), 및 `IHostTaskManager::EnterRuntime` 중첩 된 레이어를 식별 하는 호스트 수 있습니다.  
  
|작업|해당 메서드 호출|  
|------------|-------------------------------|  
|관리 되는 Visual Basic 실행 호출 플랫폼을 사용 하 여 C로 작성 된 관리 되지 않는 함수를 호출 합니다.|`IHostTaskManager::LeaveRuntime`|  
|관리 되지 않는 C 함수를 작성 하는 관리 되는 DLL의 메서드를 호출 합니다. C#입니다.|`IHostTaskManager::ReverseEnterRuntime`|  
|관리 되는 C# 함수에서 C로 작성 된 다른 관리 되지 않는 함수 호출, 또한 플랫폼을 사용 하 여 호출 합니다.|`IHostTaskManager::LeaveRuntime`|  
|두 번째 관리 되지 않는 함수 실행을 반환 합니다 C# 함수입니다.|`IHostTaskManager::EnterRuntime`|  
|C# 함수는 첫 번째 관리 되지 않는 함수에 실행을 반환 합니다.|`IHostTaskManager::ReverseLeaveRuntime`|  
|첫 번째 관리 되지 않는 함수는 Visual Basic 프로그램 실행을 반환합니다.|`IHostTaskManager::EnterRuntime`|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고자료
- [ICLRTask 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [ICLRTaskManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [IHostTask 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [IHostTaskManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
