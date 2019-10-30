---
title: ICLRTask::Reset 메서드
ms.date: 03/30/2017
api_name:
- ICLRTask.Reset
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::Reset
helpviewer_keywords:
- ICLRTask::Reset method [.NET Framework hosting]
- Reset method, ICLRTask interface [.NET Framework hosting]
ms.assetid: 1bfb5d3a-0ffd-4bb4-9bf6-aec00cb675b7
topic_type:
- apiref
ms.openlocfilehash: 17fca3e5a2d763277d3a5f9f72e2d35be6fc350c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124638"
---
# <a name="iclrtaskreset-method"></a>ICLRTask::Reset 메서드
호스트가 작업을 완료 했음을 CLR (공용 언어 런타임)에 알리고 CLR에서 현재 [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) 인스턴스를 다시 사용 하 여 다른 작업을 나타낼 수 있도록 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT Reset (  
    [in] BOOL fFull  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `fFull`  
 [in] `true`런타임에서 현재 `ICLRTask` 인스턴스와 관련 된 보안 및 로캘 정보 외에도 모든 스레드 관련 정적 값을 다시 설정 해야 하는 경우 그렇지 않으면 `false`합니다.  
  
 값이 `true`이면 런타임은 <xref:System.Threading.Thread.AllocateDataSlot%2A> 또는 <xref:System.Threading.Thread.AllocateNamedDataSlot%2A>를 사용 하 여 저장 된 데이터를 다시 설정 합니다.  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|`Reset` 성공적으로 반환 되었습니다.|  
|HOST_E_CLRNOTAVAILABLE|CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 처리할 수 없는 상태에 있습니다. 성공할|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자가 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드가 E_FAIL을 반환 하는 경우 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다. 호스팅 메서드에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.|  
  
## <a name="remarks"></a>주의  
 CLR은 이전에 만든 `ICLRTask` 인스턴스를 재활용 하 여 새 작업이 필요할 때마다 반복 해 서 새 인스턴스를 만들 때의 오버 헤드를 방지할 수 있습니다. 호스트에서는 작업을 완료 했을 때 [ICLRTask:: ExitTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-exittask-method.md) 대신 `ICLRTask::Reset`를 호출 하 여이 기능을 사용 하도록 설정 합니다. 다음 목록에서는 `ICLRTask` 인스턴스의 일반적인 수명 주기를 요약 합니다.  
  
1. 런타임이 새 `ICLRTask` 인스턴스를 만듭니다.  
  
2. 런타임은 [IHostTaskManager:: GetCurrentTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-getcurrenttask-method.md) 를 호출 하 여 현재 호스트 태스크에 대 한 참조를 가져옵니다.  
  
3. 런타임은 [IHostTask:: SetCLRTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setclrtask-method.md) 를 호출 하 여 새 인스턴스를 호스트 태스크에 연결 합니다.  
  
4. 태스크가 실행 되 고 완료 됩니다.  
  
5. 호스트는 `ICLRTask::ExitTask`를 호출 하 여 작업을 소멸 시킵니다.  
  
 `Reset`는 두 가지 방법으로이 시나리오를 변경 합니다. 위의 5 단계에서 호스트는 `Reset`를 호출 하 여 작업을 정리 된 상태로 다시 설정 하 고 연결 된 [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) 인스턴스에서 `ICLRTask` 인스턴스를 분리 합니다. 원하는 경우 호스트는 다시 사용 하기 위해 `IHostTask` 인스턴스를 캐시할 수도 있습니다. 위의 1 단계에서 런타임은 새 인스턴스를 만드는 대신 캐시에서 재활용 된 `ICLRTask`를 가져옵니다.  
  
 이 방법은 호스트에 재사용 가능한 작업자 태스크의 풀도 있는 경우에 효과적입니다. 호스트는 `IHostTask` 인스턴스 중 하나를 소멸 시킨 경우 `ExitTask`를 호출 하 여 해당 `ICLRTask`를 소멸 시킵니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICLRTask 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [ICLRTaskManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [IHostTask 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [IHostTaskManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
