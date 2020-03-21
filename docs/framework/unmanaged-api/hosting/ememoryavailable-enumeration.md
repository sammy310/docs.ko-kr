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
ms.openlocfilehash: 0073a532f680d8764ec9e76ea22326a630457043
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176437"
---
# <a name="ememoryavailable-enumeration"></a>EMemoryAvailable 열거형
컴퓨터에서 사용 가능한 실제 메모리의 양을 나타내는 값을 포함합니다. 이러한 값은 Windows API의 함수에서 반환되는 `CreateMemoryResourceNotification` 높고 낮은 메모리에 대한 이벤트에 논리적으로 매핑됩니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef enum {  
    eMemoryAvailableLow     = 1,  
    eMemoryAvailableNeutral = 2,  
    eMemoryAvailableHigh    = 3
} EMemoryAvailable;  
```  
  
## <a name="members"></a>구성원  
  
|멤버|Description|  
|------------|-----------------|  
|`eMemoryAvailableHigh`|실제 메모리를 많이 사용할 수 있습니다.|  
|`eMemoryAvailableLow`|실제 메모리를 사용할 수 있는 것은 거의 없습니다.|  
|`eMemoryAvailableNeutral`|사용 가능한 실제 메모리는 중립적입니다.|  
  
## <a name="remarks"></a>설명  
 이 값은 [ICLRMemoryNotificationCallback::OnMemoryNotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md) 메서드에 대 한 호출을 사용 하 여 공통 언어 런타임 (CLR)에 호스트에 의해 전달 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** MSCorE.h  
  
 **라이브러리:** Mscoree.dll  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [호스팅 열거형](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
