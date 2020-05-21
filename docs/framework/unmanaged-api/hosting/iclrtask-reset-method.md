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
ms.openlocfilehash: 15004238ee296e44ae77cd8739b7f62ea2a7a100
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762970"
---
# <a name="iclrtaskreset-method"></a>ICLRTask::Reset 메서드
호스트가 작업을 완료 했음을 CLR (공용 언어 런타임)에 알리고 CLR에서 현재 [ICLRTask](iclrtask-interface.md) 인스턴스를 다시 사용 하 여 다른 작업을 나타낼 수 있도록 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT Reset (  
    [in] BOOL fFull  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `fFull`  
 [in] `true` 런타임에 현재 인스턴스와 관련 된 보안 및 로캘 정보와 함께 모든 스레드 관련 정적 값을 다시 설정 해야 하면 `ICLRTask` 이 고, 그렇지 않으면 `false` 입니다.  
  
 값이 이면 `true` 런타임은 또는를 사용 하 여 저장 된 데이터를 다시 설정 합니다 <xref:System.Threading.Thread.AllocateDataSlot%2A> <xref:System.Threading.Thread.AllocateNamedDataSlot%2A> .  
  
## <a name="return-value"></a>Return Value  
  
|HRESULT|Description|  
|-------------|-----------------|  
|S_OK|`Reset`성공적으로 반환 되었습니다.|  
|HOST_E_CLRNOTAVAILABLE|CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 처리할 수 없는 상태에 있습니다. 성공할|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자가 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다. 호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.|  
  
## <a name="remarks"></a>설명  
 CLR은 이전에 만든 `ICLRTask` 인스턴스를 재활용 하 여 새 작업을 필요할 때마다 반복 해 서 새 인스턴스를 만들 때의 오버 헤드를 방지할 수 있습니다. 호스트에서는 `ICLRTask::Reset` 작업을 완료 했을 때 [ICLRTask:: exittask](iclrtask-exittask-method.md) 대신를 호출 하 여이 기능을 사용 하도록 설정 합니다. 다음 목록에서는 인스턴스의 일반적인 수명 주기를 요약 합니다 `ICLRTask` .  
  
1. 런타임이 새 인스턴스를 만듭니다 `ICLRTask` .  
  
2. 런타임은 [IHostTaskManager:: GetCurrentTask](ihosttaskmanager-getcurrenttask-method.md) 를 호출 하 여 현재 호스트 태스크에 대 한 참조를 가져옵니다.  
  
3. 런타임은 [IHostTask:: SetCLRTask](ihosttask-setclrtask-method.md) 를 호출 하 여 새 인스턴스를 호스트 태스크에 연결 합니다.  
  
4. 태스크가 실행 되 고 완료 됩니다.  
  
5. 호스트는를 호출 하 여 작업을 소멸 시킵니다 `ICLRTask::ExitTask` .  
  
 `Reset`에서는 두 가지 방법으로이 시나리오를 변경 합니다. 위의 5 단계에서 호스트는를 호출 `Reset` 하 여 작업을 정리 상태로 다시 설정 하 고 `ICLRTask` 해당 인스턴스를 연결 된 [IHostTask](ihosttask-interface.md) 인스턴스에서 분리 합니다. 원하는 경우 호스트는 다시 사용할 인스턴스를 캐시할 수도 있습니다 `IHostTask` . 위의 1 단계에서 런타임은 `ICLRTask` 새 인스턴스를 만드는 대신 캐시에서 재활용을 가져옵니다.  
  
 이 방법은 호스트에 재사용 가능한 작업자 태스크의 풀도 있는 경우에 효과적입니다. 호스트는 인스턴스 중 하나를 소멸 시키는 경우를 `IHostTask` 호출 하 여 해당 하는를 소멸 시킵니다 `ICLRTask` `ExitTask` .  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICLRTask 인터페이스](iclrtask-interface.md)
- [ICLRTaskManager 인터페이스](iclrtaskmanager-interface.md)
- [IHostTask 인터페이스](ihosttask-interface.md)
- [IHostTaskManager 인터페이스](ihosttaskmanager-interface.md)
