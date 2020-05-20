---
title: ICLRPolicyManager::SetTimeoutAndAction 메서드
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetTimeoutAndAction
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetTimeoutAndAction
helpviewer_keywords:
- ICLRPolicyManager::SetTimeoutAndAction method [.NET Framework hosting]
- SetTimeoutAndAction method [.NET Framework hosting]
ms.assetid: 60454f91-d855-4ddf-bb6d-60a02f5eabab
topic_type:
- apiref
ms.openlocfilehash: efd30ef04c148d5e098110efcb37e50f143884e4
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703430"
---
# <a name="iclrpolicymanagersettimeoutandaction-method"></a>ICLRPolicyManager::SetTimeoutAndAction 메서드
지정 된 작업에 대 한 시간 제한 값을 설정 하 고, 작업이 발생할 때 CLR (공용 언어 런타임)이 수행 해야 하는 정책 동작을 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetTimeoutAndAction (  
    [in] EClrOperation operation,  
    [in] DWORD dwMilliseconds,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `operation`  
 진행 제한 시간 및 `action` 정책을 설정할 작업을 나타내는 [EClrOperation](eclroperation-enumeration.md) 값 중 하나입니다. 다음 값이 지원 됩니다.  
  
- OPR_AppDomainUnload  
  
- OPR_ProcessExit  
  
- OPR_ThreadRudeAbortInCriticalRegion  
  
- OPR_ThreadRudeAbortInNonCriticalRegion  
  
 `dwMilliseconds`  
 진행 새 시간 제한 값 (밀리초)입니다. 값이 INFINITE 이면 `operation` 시간 제한이 없습니다.  
  
 `action`  
 진행 [EPolicyAction](epolicyaction-enumeration.md) 값 중 하나로, CLR이 발생할 때 수행 해야 하는 정책 작업을 나타냅니다 `operation` .  
  
## <a name="return-value"></a>Return Value  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|`SetTimeoutAndAction`성공적으로 반환 되었습니다.|  
|HOST_E_CLRNOTAVAILABLE|CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자가 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드가 E_FAIL 반환 된 후에는 프로세스 내에서 CLR을 더 이상 사용할 수 없습니다. 호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.|  
|E_INVALIDARG|지정 된에 대 한 제한 시간을 설정할 수 `operation` 없거나에 잘못 된 값이 제공 `action` 된 경우|  
  
## <a name="remarks"></a>설명  
 `SetTimeoutAndAction`는 [ICLRPolicyManager:: SetTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md) 및 [ICLRPolicyManager:: SetActionOnTimeout](iclrpolicymanager-setactionontimeout-method.md) 메서드의 기능을 캡슐화 하며 이러한 두 메서드에 대 한 순차적 호출 대신 호출 될 수 있습니다.  
  
> [!IMPORTANT]
> 모든 정책 동작 값을 CLR 작업의 시간 제한 동작으로 지정할 수 있는 것은 아닙니다. 유효한 값은 이러한 두 메서드에 대 한 항목의 설명 섹션을 참조 하세요.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [EClrOperation 열거형](eclroperation-enumeration.md)
- [EPolicyAction 열거형](epolicyaction-enumeration.md)
- [ICLRPolicyManager 인터페이스](iclrpolicymanager-interface.md)
- [SetActionOnTimeout 메서드](iclrpolicymanager-setactionontimeout-method.md)
- [ICLRPolicyManager::SetTimeoutAndAction](iclrpolicymanager-settimeoutandaction-method.md)
