---
title: ICLRPolicyManager::SetActionOnFailure 메서드
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetActionOnFailure
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetActionOnFailure
helpviewer_keywords:
- SetActionOnFailure method [.NET Framework hosting]
- ICLRPolicyManager::SetActionOnFailure method [.NET Framework hosting]
ms.assetid: 4664033f-db97-4388-b988-2ec470796e58
topic_type:
- apiref
ms.openlocfilehash: 8f44247ca7904a40f5ebc092d95c2e08b6048438
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725575"
---
# <a name="iclrpolicymanagersetactiononfailure-method"></a>ICLRPolicyManager::SetActionOnFailure 메서드

지정 된 오류가 발생할 때 CLR (공용 언어 런타임)이 수행 해야 하는 정책 동작을 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetActionOnFailure (  
    [in] EClrFailure   failure,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `failure`  
 진행 작업을 수행할 실패 유형을 나타내는 [EClrFailure](eclrfailure-enumeration.md) 값 중 하나입니다.  
  
 `action`  
 진행 오류가 발생할 때 수행할 작업을 나타내는 [EPolicyAction](epolicyaction-enumeration.md) 값 중 하나입니다. 지원 되는 값의 목록은 설명 섹션을 참조 하세요.  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|`SetActionOnFailure` 성공적으로 반환 되었습니다.|  
|HOST_E_CLRNOTAVAILABLE|CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자가 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드가 E_FAIL 반환 된 후에는 프로세스 내에서 CLR을 더 이상 사용할 수 없습니다. 호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.|  
|E_INVALIDARG|지정 된 작업에 대해 정책 작업을 설정할 수 없거나 작업에 대해 잘못 된 정책 동작을 지정한 경우|  
  
## <a name="remarks"></a>설명  

 기본적으로 CLR은 메모리와 같은 리소스를 할당 하지 못한 경우 예외를 throw 합니다. `SetActionOnFailure` 오류가 발생할 때 수행할 정책 작업을 지정 하 여 호스트가이 동작을 재정의할 수 있도록 합니다. 다음 표에서는 지원 되는 [EClrFailure](eclrfailure-enumeration.md) 및 [EPolicyAction](epolicyaction-enumeration.md) 값의 조합을 보여 줍니다. FAIL_ 접두사는 [EClrFailure](eclrfailure-enumeration.md) 값에서 생략 됩니다.  
  
||NonCriticalResource|CriticalResource|FatalRuntime|OrphanedLock|StackOverflow|AccessViolation|CodeContract|  
|-|-------------------------|----------------------|------------------|------------------|-------------------|---------------------|------------------|  
|`eNoAction`|X|X||||해당 없음||  
|eThrowException|X|X||||해당 없음||  
|`eAbortThread`|X|X||||해당 없음|X|  
|`eRudeAbortThread`|X|X||||해당 없음|X|  
|`eUnloadAppDomain`|X|X||X||해당 없음|X|  
|`eRudeUnloadAppDomain`|X|X||X|X|해당 없음|X|  
|`eExitProcess`|X|X||X|X|해당 없음|X|  
|eFastExitProcess|X|X||X|X|해당 없음||  
|`eRudeExitProcess`|X|X|X|X|X|해당 없음||  
|`eDisableRuntime`|X|X|X|X|X|해당 없음||  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [EClrFailure 열거형](eclrfailure-enumeration.md)
- [EPolicyAction 열거형](epolicyaction-enumeration.md)
- [ICLRControl 인터페이스](iclrcontrol-interface.md)
- [ICLRPolicyManager 인터페이스](iclrpolicymanager-interface.md)
