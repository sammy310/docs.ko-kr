---
description: '자세히 알아보기: IHostTaskManager:: ReverseLeaveRuntime 메서드'
title: IHostTaskManager::ReverseLeaveRuntime 메서드
ms.date: 03/30/2017
api_name:
- IHostTaskManager.ReverseLeaveRuntime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::ReverseLeaveRuntime
helpviewer_keywords:
- IHostTaskManager::ReverseLeaveRuntime method [.NET Framework hosting]
- ReverseLeaveRuntime method [.NET Framework hosting]
ms.assetid: 4837d398-16a1-4e32-902c-022cd1aad3ca
topic_type:
- apiref
ms.openlocfilehash: 2fed157f6ea05243270b957cacdb00ba5a47a88f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99680867"
---
# <a name="ihosttaskmanagerreverseleaveruntime-method"></a>IHostTaskManager::ReverseLeaveRuntime 메서드

컨트롤이 CLR (공용 언어 런타임)을 유지 하 고 관리 코드에서 호출 된 관리 되지 않는 함수를 시작 했음을 호스트에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT ReverseLeaveRuntime ();  
```  
  
## <a name="return-value"></a>Return Value  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|`ReverseLeaveRuntime` 성공적으로 반환 되었습니다.|  
|HOST_E_CLRNOTAVAILABLE|CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자가 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다. 호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.|  
|E_OUTOFMEMORY|메모리가 부족 하 여 요청 된 리소스 할당을 완료할 수 없습니다.|  
  
## <a name="remarks"></a>설명  

 CLR은 `ReverseLeaveRuntime` 현재 실행 중인 작업이 플랫폼 호출을 통해 관리 코드에서 호출 된 관리 되지 않는 함수로 제어를 반환 함을 호스트에 알리기 위해를 호출 합니다. 에 대 한 각 호출은 `ReverseLeaveRuntime` [ReverseEnterRuntime](ihosttaskmanager-reverseenterruntime-method.md)에 대 한 해당 호출과 일치 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [CallNeedsHostHook 메서드](ihosttaskmanager-callneedshosthook-method.md)
- [EnterRuntime 메서드](ihosttaskmanager-enterruntime-method.md)
- [ICLRTask 인터페이스](iclrtask-interface.md)
- [ICLRTaskManager 인터페이스](iclrtaskmanager-interface.md)
- [IHostTask 인터페이스](ihosttask-interface.md)
- [IHostTaskManager 인터페이스](ihosttaskmanager-interface.md)
- [LeaveRuntime 메서드](ihosttaskmanager-leaveruntime-method.md)
- [플랫폼 호출 자세히 보기](/previous-versions/dotnet/netframework-4.0/0h9e9t7d(v=vs.100))
