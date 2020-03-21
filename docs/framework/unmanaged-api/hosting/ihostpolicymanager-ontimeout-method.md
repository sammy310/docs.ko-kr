---
title: IHostPolicyManager::OnTimeout 메서드
ms.date: 03/30/2017
api_name:
- IHostPolicyManager.OnTimeout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostPolicyManager::OnTimeout
helpviewer_keywords:
- IHostPolicyManager::OnTimeout method [.NET Framework hosting]
- OnTimeout method [.NET Framework hosting]
ms.assetid: 0a313b51-5e4d-4714-a86b-af75cf3902e6
topic_type:
- apiref
ms.openlocfilehash: d5b5fa5198ae2c0bba30ae0f8d6d3834f2891672
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178013"
---
# <a name="ihostpolicymanagerontimeout-method"></a>IHostPolicyManager::OnTimeout 메서드
호스트에 공통 언어 런타임(CLR)이 [ICLRPolicyPolicy::SetActionOnTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) 메서드에 대한 호출에서 지정한 작업을 수행하려고 한다는 것을 호스트에 시간 지정에 대한 응답으로 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT OnTimeout (  
    [in] EClrOperation  operation,
    [in] EPolicyAction  action  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `operation`  
 【인】 시간 중지된 작업 종류를 나타내는 [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) 값 중 하나입니다.  
  
 `action`  
 【인】 [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) 값 중 하나로, CLR이 시간 시간에 대한 응답으로 수행하는 작업을 나타냅니다.  
  
## <a name="return-value"></a>Return Value  
  
|HRESULT|Description|  
|-------------|-----------------|  
|S_OK|`OnTimeout`성공적으로 반환됩니다.|  
|HOST_E_CLRNOTAVAILABLE|CLR이 프로세스에 로드되지 않았거나 CLR이 관리 코드를 실행하거나 호출을 성공적으로 처리할 수 없는 상태입니다.|  
|HOST_E_TIMEOUT|통화 시간이 시간 미정으로 확인되었습니다.|  
|HOST_E_NOT_OWNER|호출자는 잠금을 소유하지 않습니다.|  
|HOST_E_ABANDONED|차단된 스레드 또는 파이버가 대기하는 동안 이벤트가 취소되었습니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생했습니다. 메서드가 E_FAIL 반환하면 프로세스 내에서 CLR을 더 이상 사용할 수 없습니다. 호스팅 메서드에 대한 후속 호출은 HOST_E_CLRNOTAVAILABLE 반환합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** MSCorE.h  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [EClrOperation 열거형](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [EPolicyAction 열거형](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [ICLRPolicyManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [IHostPolicyManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
