---
title: IHostCrst::SetSpinCount 메서드
ms.date: 03/30/2017
api_name:
- IHostCrst.SetSpinCount
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostCrst::SetSpinCount
helpviewer_keywords:
- IHostCrst::SetSpinCount method [.NET Framework hosting]
- SetSpinCount method [.NET Framework hosting]
ms.assetid: 863fc8ce-9b8a-477e-8dd8-75c8544bb43a
topic_type:
- apiref
ms.openlocfilehash: 22274759f931da614a234efe0a6f6eb3aade027c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729566"
---
# <a name="ihostcrstsetspincount-method"></a>IHostCrst::SetSpinCount 메서드

현재 [IHostCrst](ihostcrst-interface.md) 인스턴스의 회전 수를 설정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetSpinCount (  
    [in] DWORD dwSpinCount  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `dwSpinCount`  
 진행 현재 인스턴스의 새 스핀 개수 `IHostCrst` 입니다.  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|`SetSpinCount` 성공적으로 반환 되었습니다.|  
|HOST_E_CLRNOTAVAILABLE|CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자가 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다. 호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.|  
  
## <a name="remarks"></a>설명  

 다중 프로세서 시스템에서 현재 인스턴스로 표시 되는 임계 영역을 `IHostCrst` 사용할 수 없는 경우 호출 스레드는 `dwSpinCount` 임계 영역에 연결 된 세마포에 대해 [IHostSemaphore:: Wait](ihostsemaphore-wait-method.md) 를 호출 하기 전에 시간을 회전 합니다. Spin 작업 중에 임계 영역을 사용할 수 없게 되 면 호출 스레드가 대기 작업을 방지 합니다.  
  
 를 사용 `dwSpinCount` 하는 것은 Win32 함수에서 동일한 이름의 매개 변수를 사용 하는 것과 동일 합니다 `InitializeCriticalSectionAndSpinCount` .  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICLRSyncManager 인터페이스](iclrsyncmanager-interface.md)
- [IHostCrst 인터페이스](ihostcrst-interface.md)
- [IHostSyncManager 인터페이스](ihostsyncmanager-interface.md)
