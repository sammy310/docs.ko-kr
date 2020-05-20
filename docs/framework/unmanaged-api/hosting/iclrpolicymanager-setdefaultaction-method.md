---
title: ICLRPolicyManager::SetDefaultAction 메서드
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetDefaultAction
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetDefaultAction
helpviewer_keywords:
- SetDefaultAction method [.NET Framework hosting]
- ICLRPolicyManager::SetDefaultAction method [.NET Framework hosting]
ms.assetid: f9411e7a-27df-451f-9f6c-d643d6a7a7ce
topic_type:
- apiref
ms.openlocfilehash: c0d8b66c8b85710b0365bfc410188c81431720ff
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703441"
---
# <a name="iclrpolicymanagersetdefaultaction-method"></a>ICLRPolicyManager::SetDefaultAction 메서드
지정 된 작업이 수행 될 때 CLR (공용 언어 런타임)이 수행 해야 하는 정책 동작을 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetDefaultAction (  
    [in] EClrOperation operation,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `operation`  
 진행 CLR 동작을 사용자 지정 해야 하는 동작을 나타내는 [EClrOperation](eclroperation-enumeration.md) 값 중 하나입니다.  
  
 `action`  
 진행 [EPolicyAction](epolicyaction-enumeration.md) 값 중 하나로, 발생할 때 CLR이 수행 해야 하는 정책 작업을 나타냅니다 `operation` .  
  
## <a name="return-value"></a>Return Value  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|`SetDefaultAction`성공적으로 반환 되었습니다.|  
|HOST_E_CLRNOTAVAILABLE|CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자가 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드가 E_FAIL 반환 된 후에는 프로세스 내에서 CLR을 더 이상 사용할 수 없습니다. 호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.|  
|E_INVALIDARG|에 대해 잘못 된가 `action` 지정 되었거나 `operation` 에 잘못 된 값이 제공 된 `operation` 경우|  
  
## <a name="remarks"></a>설명  
 모든 정책 동작 값을 CLR 작업의 기본 동작으로 지정할 수 있는 것은 아닙니다. `SetDefaultAction`일반적으로 동작을 에스컬레이션 하는 데만 사용할 수 있습니다. 예를 들어 호스트는 스레드 중단이 강제 스레드 중단으로 전환 되도록 지정할 수 있지만 반대의 경우에는 지정할 수 없습니다. 다음 표에서는 `action` 가능한 각 값에 대 한 유효한 값을 설명 합니다 `operation` .  
  
|값`operation`|유효한 값`action`|  
|---------------------------|-------------------------------|  
|OPR_ThreadAbort|- eAbortThread<br />- eRudeAbortThread<br />- eUnloadAppDomain<br />- eRudeUnloadAppDomain<br />-eExitProcess<br />-eFastExitProcess<br />-eRudeExitProcess<br />- eDisableRuntime|  
|OPR_ThreadRudeAbortInNonCriticalRegion<br /><br /> OPR_ThreadRudeAbortInCriticalRegion|- eRudeAbortThread<br />- eUnloadAppDomain<br />- eRudeUnloadAppDomain<br />-eExitProcess<br />-eFastExitProcess<br />-eRudeExitProcess<br />- eDisableRuntime|  
|OPR_AppDomainUnload|- eUnloadAppDomain<br />- eRudeUnloadAppDomain<br />-eExitProcess<br />-eFastExitProcess<br />-eRudeExitProcess<br />- eDisableRuntime|  
|OPR_AppDomainRudeUnload|- eRudeUnloadAppDomain<br />-eExitProcess<br />-eFastExitProcess<br />-eRudeExitProcess<br />- eDisableRuntime|  
|OPR_ProcessExit|-eExitProcess<br />-eFastExitProcess<br />-eRudeExitProcess<br />- eDisableRuntime|  
|OPR_FinalizerRun|- eNoAction<br />- eAbortThread<br />- eRudeAbortThread<br />- eUnloadAppDomain<br />- eRudeUnloadAppDomain<br />-eExitProcess<br />-eFastExitProcess<br />-eRudeExitProcess<br />- eDisableRuntime|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [EClrOperation 열거형](eclroperation-enumeration.md)
- [EPolicyAction 열거형](epolicyaction-enumeration.md)
- [ICLRPolicyManager 인터페이스](iclrpolicymanager-interface.md)
