---
title: ICLRDebugManager::SetConnectionTasks 메서드
ms.date: 03/30/2017
api_name:
- ICLRDebugManager.SetConnectionTasks
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager::SetConnectionTasks
helpviewer_keywords:
- SetConnectionTasks method [.NET Framework hosting]
- ICLRDebugManager::SetConnectionTasks method [.NET Framework hosting]
ms.assetid: b38bbc9a-872c-41a9-b8c3-ca011d25456a
topic_type:
- apiref
ms.openlocfilehash: 5df01ac929874d00a5fddda83f532927dc46d67b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719842"
---
# <a name="iclrdebugmanagersetconnectiontasks-method"></a>ICLRDebugManager::SetConnectionTasks 메서드

[ICLRTask](iclrtask-interface.md) 인스턴스 목록을 식별자 및 이름과 연결 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetConnectionTasks (  
    [in] CONNID id,  
    [in] DWORD dwCount,  
    [in, size_is(dwCount)] ICLRTask **ppCLRTask  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `id`  
 진행 배열과 연결할 연결의 호스트 관련 식별자 `ppCLRTask` 입니다.  
  
 `dwCount`  
 진행 의 멤버 수입니다 `ppCLRTask` . 이 숫자는 0 보다 커야 합니다.  
  
 `ppCLRTask`  
 진행 `ICLRTask` 로 식별 되는 연결과 연결할 포인터의 배열입니다 `id` . 이 배열은 멤버를 하나 이상 포함 해야 합니다.  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|`SetConnectionTasks` 성공적으로 반환 되었습니다.|  
|HOST_E_CLRNOTAVAILABLE|CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자가 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드가 E_FAIL 반환 된 후에는 프로세스 내에서 CLR을 더 이상 사용할 수 없습니다. 호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.|  
|E_INVALIDARG|[Beginconnection](iclrdebugmanager-beginconnection-method.md) 이이 값을 사용 하 여 호출 되지 않았거나 `id` `dwCount` 또는 `id` 가 0 이거나의 요소 중 하나가 `ppCLRTask` null입니다.|  
  
## <a name="remarks"></a>설명  

 [ICLRDebugManager](iclrdebugmanager-interface.md) 는 작업 목록과 식별자를 연결 하는 데 사용 되는 세 가지 메서드,, `BeginConnection` `SetConnectionTasks` 및 [endconnection](iclrdebugmanager-endconnection-method.md)을 제공 합니다.  
  
> [!IMPORTANT]
> 이러한 세 메서드는 각 작업 집합에 대해 특정 순서로 호출 되어야 합니다. `BeginConnection` 새 연결을 설정 하기 위해가 먼저 호출 됩니다. `SetConnectionTasks` 는 해당 연결과 관련 된 태스크 집합을 제공 하기 위해 다음에 호출 됩니다. `EndConnection` 작업 목록과 식별자와 이름 간의 연결을 제거 하기 위해 마지막으로 호출 됩니다. 그러나 다른 연결에 대 한 호출은 중첩할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICLRControl 인터페이스](iclrcontrol-interface.md)
- [ICLRDebugManager 인터페이스](iclrdebugmanager-interface.md)
- [BeginConnection 메서드](iclrdebugmanager-beginconnection-method.md)
- [EndConnection 메서드](iclrdebugmanager-endconnection-method.md)
- [IHostControl 인터페이스](ihostcontrol-interface.md)
