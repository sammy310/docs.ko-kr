---
title: IHostTaskManager::EndThreadAffinity 메서드
ms.date: 03/30/2017
api_name:
- IHostTaskManager.EndThreadAffinity
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::EndThreadAffinity
helpviewer_keywords:
- EndThreadAffinity method [.NET Framework hosting]
- IHostTaskManager::EndThreadAffinity method [.NET Framework hosting]
ms.assetid: 7738a904-0cd7-4fde-a3eb-2323a5533157
topic_type:
- apiref
ms.openlocfilehash: 2e857f951a837e1385d02dfc810fc12cfefd0d2b
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/26/2020
ms.locfileid: "83841960"
---
# <a name="ihosttaskmanagerendthreadaffinity-method"></a>IHostTaskManager::EndThreadAffinity 메서드
이전에 [IHostTaskManager:: BeginThreadAffinity](ihosttaskmanager-beginthreadaffinity-method.md)를 호출한 후에 관리 코드가 현재 작업을 다른 운영 체제 스레드로 이동 하지 않아야 하는 기간을 호스트에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT EndThreadAffinity ();  
```  
  
## <a name="return-value"></a>Return Value  
  
|HRESULT|Description|  
|-------------|-----------------|  
|S_OK|`EndThreadAffinity`성공적으로 반환 되었습니다.|  
|HOST_E_CLRNOTAVAILABLE|CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자가 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다. 호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.|  
|E_UNEXPECTED|`EndThreadAffinity`는에 대 한 이전 해당 호출 없이 호출 되었습니다 `BeginThreadAffinity` .|  
  
## <a name="remarks"></a>설명  
 CLR은를 `BeginThreadAffinity` 호출 하기 전에 현재 작업에 대해 해당 호출을 수행 `EndThreadAffinity` 합니다. 이러한 상응 하는 호출이 없으면 호스트의 [IHostTaskManager](ihosttaskmanager-interface.md) 구현에서 E_UNEXPECTED을 반환 하 고 아무 작업도 수행 하지 않아야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Threading>
- [ICLRTask 인터페이스](iclrtask-interface.md)
- [ICLRTaskManager 인터페이스](iclrtaskmanager-interface.md)
- [IHostTask 인터페이스](ihosttask-interface.md)
- [IHostTaskManager 인터페이스](ihosttaskmanager-interface.md)
