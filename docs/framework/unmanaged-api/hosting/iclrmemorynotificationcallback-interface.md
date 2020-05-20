---
title: ICLRMemoryNotificationCallback 인터페이스
ms.date: 03/30/2017
api_name:
- ICLRMemoryNotificationCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMemoryNotificationCallback
helpviewer_keywords:
- ICLRMemoryNotificationCallback interface [.NET Framework hosting]
ms.assetid: 873639e2-4837-4568-83b3-4493e67e4174
topic_type:
- apiref
ms.openlocfilehash: 52fc21044d345998ad72c045cdf5e80a8a03a38e
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703808"
---
# <a name="iclrmemorynotificationcallback-interface"></a>ICLRMemoryNotificationCallback 인터페이스
호스트에서 Win32 함수와 유사한 방법을 사용 하 여 메모리 압력 상태를 보고할 수 있습니다 `CreateMemoryResourceNotification` .  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[OnMemoryNotification 메서드](iclrmemorynotificationcallback-onmemorynotification-method.md)|컴퓨터의 메모리 로드를 CLR (공용 언어 런타임)에 알립니다.|  
  
## <a name="remarks"></a>설명  
 호스트는 인터페이스를 사용 하 여 `ICLRMemoryNotificationCallback` CLR의 사용 가능한 메모리 리소스를 요청 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IHostMemoryManager 인터페이스](ihostmemorymanager-interface.md)
- [호스팅 인터페이스](hosting-interfaces.md)
