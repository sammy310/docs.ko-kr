---
title: WAIT_OPTION 열거형
ms.date: 03/30/2017
api_name:
- WAIT_OPTION
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- WAIT_OPTION
helpviewer_keywords:
- WAIT_OPTION enumeration [.NET Framework hosting]
ms.assetid: 962fc293-8ded-4b3b-90ce-2c21a4f1b244
topic_type:
- apiref
ms.openlocfilehash: 9ecfb551b55551e5f6cc7e7e9ffb55e5a96259ee
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141508"
---
# <a name="wait_option-enumeration"></a>WAIT_OPTION 열거형
CLR (공용 언어 런타임) 블록에서 요청 된 작업을 수행할 때 호스트가 수행할 동작을 나타내는 값을 포함 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef enum {  
    WAIT_MSGPUMP       = 0x1,  
    WAIT_ALERTABLE     = 0x2,  
    WAIT_NOTINDEADLOCK = 0x4,  
} WAIT_OPTION;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`WAIT_ALERTABLE`|CLR이 [IHostTask:: Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) 메서드를 호출 하는 경우 작업을 활성화 해야 함을 호스트에 알립니다.|  
|`WAIT_MSGPUMP`|스레드가 차단 되는 경우 현재 OS 스레드에서 메시지를 펌프 해야 함을 호스트에 알립니다. 런타임은 <xref:System.Threading.ApartmentState.STA> 스레드에서만이 값을 지정 합니다.|  
|`WAIT_NOTINDEADLOCK`|호스트에서 지정 된 동기화 요청을 나눌 수 없음을 호스트에 알립니다. 즉, 호스트는 `HOST_E_DEADLOCK`을 반환할 수 없습니다.|  
  
## <a name="remarks"></a>주의  
 [IHostTaskManager:: Sleep](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-sleep-method.md) 및 [IHostTaskManager:: switchtotask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-switchtotask-method.md) 메서드는 모두이 형식의 매개 변수를 사용 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** Mscoree.dll  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [호스팅 열거형](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
