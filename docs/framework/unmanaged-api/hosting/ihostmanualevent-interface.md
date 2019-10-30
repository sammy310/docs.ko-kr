---
title: IHostManualEvent 인터페이스
ms.date: 03/30/2017
api_name:
- IHostManualEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostManualEvent
helpviewer_keywords:
- IHostManualEvent interface [.NET Framework hosting]
ms.assetid: 300c2661-b7d1-4c39-b080-9ebdef0fd523
topic_type:
- apiref
ms.openlocfilehash: 8eba189d6dfca3781c28631a72a9af3c037efeda
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136788"
---
# <a name="ihostmanualevent-interface"></a>IHostManualEvent 인터페이스
수동 다시 설정 이벤트 표현의 호스트 구현을 제공 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[Reset 메서드](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-reset-method.md)|현재 `IHostManualEvent` 인스턴스를 신호를 받지 않는 상태로 다시 설정 합니다.|  
|[Set 메서드](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-set-method.md)|현재 `IHostManualEvent` 인스턴스를 신호를 받은 상태로 설정 합니다.|  
|[Wait 메서드](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-wait-method.md)|현재 `IHostManualEvent` 인스턴스가 소유 될 때까지 기다리거나 지정 된 시간이 경과할 때까지 기다립니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICLRSyncManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [IHostAutoEvent 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [IHostSemaphore 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [IHostSyncManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- [호스팅 인터페이스](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
