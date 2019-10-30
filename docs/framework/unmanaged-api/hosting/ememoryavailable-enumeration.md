---
title: EMemoryAvailable 열거형
ms.date: 03/30/2017
api_name:
- EMemoryAvailable
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EMemoryAvailable
helpviewer_keywords:
- EMemoryAvailable enumeration [.NET Framework hosting]
ms.assetid: 38e72a06-dbed-473b-a59b-7e0b3ea4f2af
topic_type:
- apiref
ms.openlocfilehash: aec3c5f140df7eab10ea2bfa33634a4d853adcb0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134299"
---
# <a name="ememoryavailable-enumeration"></a>EMemoryAvailable 열거형
컴퓨터에서 사용 가능한 실제 메모리의 양을 나타내는 값을 포함 합니다. 이러한 값은 Windows API의 `CreateMemoryResourceNotification` 함수에서 반환 되는 높은 메모리와 낮은 메모리에 대 한 이벤트에 논리적으로 매핑됩니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef enum {  
    eMemoryAvailableLow     = 1,  
    eMemoryAvailableNeutral = 2,  
    eMemoryAvailableHigh    = 3   
} EMemoryAvailable;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`eMemoryAvailableHigh`|충분 한 실제 메모리를 사용할 수 있습니다.|  
|`eMemoryAvailableLow`|거의 실제 메모리를 사용할 수 없습니다.|  
|`eMemoryAvailableNeutral`|사용 가능한 실제 메모리가 중립입니다.|  
  
## <a name="remarks"></a>주의  
 이 값은 [ICLRMemoryNotificationCallback:: OnMemoryNotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md) 메서드를 호출 하 여 호스트에서 CLR (공용 언어 런타임)로 전달 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** Mscoree.dll  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [호스팅 열거형](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
