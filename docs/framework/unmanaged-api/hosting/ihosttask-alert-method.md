---
title: IHostTask::Alert 메서드
ms.date: 03/30/2017
api_name:
- IHostTask.Alert
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::Alert
helpviewer_keywords:
- IHostTask::Alert method [.NET Framework hosting]
- Alert method, IHostTask interface [.NET Framework hosting]
ms.assetid: 5245d4b5-b6c3-48df-9cb9-8caf059f43fb
topic_type:
- apiref
ms.openlocfilehash: 5a4870a4472081a78cd1fade51f441c22aa5eb48
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720479"
---
# <a name="ihosttaskalert-method"></a>IHostTask::Alert 메서드

호스트가 현재 [IHostTask](ihosttask-interface.md) 인스턴스로 표시 되는 작업의 절전 모드를 해제 하도록 요청 하므로 작업이 중단 될 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT Alert ();  
```  
  
## <a name="return-value"></a>Return Value  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|메서드가 성공적으로 반환했습니다.|  
|HOST_E_CLRNOTAVAILABLE|CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자가 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다. 호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.|  
  
## <a name="remarks"></a>설명  

 CLR은 `Alert` <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> 사용자 코드에서가 호출 될 때 또는 현재와 연결 된가 종료 될 때 메서드를 호출 합니다 <xref:System.AppDomain> <xref:System.Threading.Thread> . 호출이 비동기적으로 수행 되므로 호스트는를 즉시 반환 해야 합니다. 호스트가 작업을 즉시 경고할 수 없는 경우 다음에 경고가 표시 될 수 있는 상태로 전환 될 때 절전 모드를 해제 해야 합니다.  
  
> [!NOTE]
> `Alert` 런타임이 WAIT_ALERTABLE의 [WAIT_OPTION](wait-option-enumeration.md) 값을 [Join](ihosttask-join-method.md)과 같은 메서드에 전달 하는 작업에만 영향을 줍니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICLRTask 인터페이스](iclrtask-interface.md)
- [ICLRTaskManager 인터페이스](iclrtaskmanager-interface.md)
- [IHostTask 인터페이스](ihosttask-interface.md)
- [IHostTaskManager 인터페이스](ihosttaskmanager-interface.md)
