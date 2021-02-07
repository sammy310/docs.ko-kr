---
description: '다음에 대 한 자세한 정보: 열거형 WAIT_OPTION'
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
ms.openlocfilehash: 1d651909e0f62f2db7478a6e0b37139d1f953196
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99679136"
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
  
## <a name="members"></a>구성원  
  
|멤버|설명|  
|------------|-----------------|  
|`WAIT_ALERTABLE`|CLR이 [IHostTask:: Alert](ihosttask-alert-method.md) 메서드를 호출 하는 경우 작업을 활성화 해야 함을 호스트에 알립니다.|  
|`WAIT_MSGPUMP`|스레드가 차단 되는 경우 현재 OS 스레드에서 메시지를 펌프 해야 함을 호스트에 알립니다. 런타임은이 값을 스레드에서만 지정 합니다 <xref:System.Threading.ApartmentState.STA> .|  
|`WAIT_NOTINDEADLOCK`|호스트에서 지정 된 동기화 요청을 나눌 수 없음을 호스트에 알립니다. 즉, 호스트에서을 반환할 수 없습니다 `HOST_E_DEADLOCK` .|  
  
## <a name="remarks"></a>설명  

 [IHostTaskManager:: Sleep](ihosttaskmanager-sleep-method.md) 및 [IHostTaskManager:: switchtotask](ihosttaskmanager-switchtotask-method.md) 메서드는 모두이 형식의 매개 변수를 사용 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** MSCorEE.dll  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [호스팅 열거형](hosting-enumerations.md)
