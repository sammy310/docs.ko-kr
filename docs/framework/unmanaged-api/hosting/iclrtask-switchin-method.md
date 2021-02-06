---
description: '자세한 정보: ICLRTask:: SwitchIn 메서드'
title: ICLRTask::SwitchIn 메서드
ms.date: 03/30/2017
api_name:
- ICLRTask.SwitchIn
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::SwitchIn
helpviewer_keywords:
- ICLRTask::SwitchIn method [.NET Framework hosting]
- SwitchIn method [.NET Framework hosting]
ms.assetid: 3d37ce20-aa65-4043-8f13-7c728b5d8a52
topic_type:
- apiref
ms.openlocfilehash: 0bbcd2b9594a8ce465a1dcd7b5ae3f8a0799826d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99636834"
---
# <a name="iclrtaskswitchin-method"></a>ICLRTask::SwitchIn 메서드

현재 [ICLRTask](iclrtask-interface.md) 인스턴스가 나타내는 작업이 현재 작동 가능한 상태 임을 CLR (공용 언어 런타임)에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SwitchIn (  
    [in] HANDLE threadHandle  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `threadHandle`  
 진행 현재 인스턴스가 나타내는 작업이 실행 중인 실제 스레드에 대 한 핸들입니다 `ICLRTask` .  
  
## <a name="return-value"></a>Return Value  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|`SwitchIn` 성공적으로 반환 되었습니다.|  
|HOST_E_CLRNOTAVAILABLE|CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.|  
|HOST_E_TIMEOUT|호출 시간이 초과 되었습니다.|  
|HOST_E_NOT_OWNER|호출자가 잠금을 소유 하지 않습니다.|  
|HOST_E_ABANDONED|차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.|  
|E_FAIL|알 수 없는 치명적인 오류가 발생 했습니다. 메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다. 호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.|  
|HOST_E_INVALIDOPERATION|`SwitchIn` 는 [Switchout 메서드](iclrtask-switchout-method.md)를 이전에 호출 하지 않고 호출 되었습니다.|  
  
## <a name="remarks"></a>설명  

 `threadHandle`매개 변수는 현재 인스턴스가 나타내는 작업이 예약 된 운영 체제 스레드에 대 한 핸들을 나타냅니다 `ICLRTask` . 이 스레드에서 가장이 발생 한 경우 작업에서 전환 하기 전에 [IHostSecurityManager:: RevertToSelf](ihostsecuritymanager-reverttoself-method.md) 를 호출 해야 합니다.  
  
> [!NOTE]
> `SwitchIn`를 이전에 호출 하지 않고를 호출 하면 `SwitchOut` HRESULT 값 HOST_E_INVALIDOPERATION가 발생 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICLRTask 인터페이스](iclrtask-interface.md)
- [ICLRTaskManager 인터페이스](iclrtaskmanager-interface.md)
- [IHostTask 인터페이스](ihosttask-interface.md)
- [IHostTaskManager 인터페이스](ihosttaskmanager-interface.md)
