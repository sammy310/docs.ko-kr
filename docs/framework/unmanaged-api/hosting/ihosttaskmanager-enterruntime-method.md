---
title: IHostTaskManager::EnterRuntime 메서드
ms.date: 03/30/2017
api_name:
- IHostTaskManager.EnterRuntime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::EnterRuntime
helpviewer_keywords:
- IHostTaskManager::EnterRuntime method [.NET Framework hosting]
- EnterRuntime method [.NET Framework hosting]
ms.assetid: 1aa7a4b1-636a-4f5e-b834-b406d72f7120
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e4ef2971d9835070e9db72a5e5d370ff35c8edfe
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59106441"
---
# <a name="ihosttaskmanagerenterruntime-method"></a>IHostTaskManager::EnterRuntime 메서드
관리 되지 않는 메서드를 호출 메서드를 호출 하는 플랫폼와 같은 실행 결과 제어가 반환 되는 CLR (공용 언어 런타임) 호스트에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT EnterRuntime ();  
```  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|`EnterRuntime` 성공적으로 반환 합니다.|  
|HOST_E_CLRNOTAVAILABLE|CLR이 로드 된 프로세스에 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자가 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다. 메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.|  
|E_OUTOFMEMORY|요청된 된 할당을 완료 하려면 사용할 수 있는 메모리가 충분 하지 않습니다.|  
  
## <a name="remarks"></a>설명  
 `EnterRuntime` 호스트에 알리기 위해 호출 됩니다는는 관리 되지 않는 함수를 호출 하 여 이전를 [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md) 메서드 만들어진가 실행을 완료 하 고 런타임에 실행 제어를 반환 합니다.  
  
> [!NOTE]
>  [ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md) 호스트에 알리기 위해 호출 됩니다는는 관리 되지 않는 함수를 호출 하 여 이전 `LeaveRuntime` 만들어진, 관리 되는 코드로 호출을 수행 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [고급 수준의 COM 상호 운용성](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bd9cdfyx)
- [방법: PInvoke를 사용 하 여 관리 되는 코드에서 네이티브 Dll 호출](/cpp/dotnet/how-to-call-native-dlls-from-managed-code-using-pinvoke)
- [ICLRTask 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [ICLRTaskManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [IHostTask 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [IHostTaskManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [LeaveRuntime 메서드](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md)
