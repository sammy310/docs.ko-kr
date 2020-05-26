---
title: IHostSemaphore 인터페이스
ms.date: 03/30/2017
api_name:
- IHostSemaphore
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSemaphore
helpviewer_keywords:
- IHostSemaphore interface [.NET Framework hosting]
ms.assetid: c0765321-656c-441e-bab5-58176292be1e
topic_type:
- apiref
ms.openlocfilehash: 8345d85502087568cb05dd262cccf181e3ca07ac
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/22/2020
ms.locfileid: "83803698"
---
# <a name="ihostsemaphore-interface"></a>IHostSemaphore 인터페이스
스레딩을 위한 호스트의 세마포 구현을 나타냅니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|Description|  
|------------|-----------------|  
|[ReleaseSemaphore 메서드](ihostsemaphore-releasesemaphore-method.md)|현재 인스턴스의 개수를 지정 된 `IHostSemaphore` 양만큼 늘립니다.|  
|[Wait 메서드](ihostsemaphore-wait-method.md)|현재 `IHostSemaphore` 인스턴스가 소유 될 때까지 또는 지정 된 시간이 경과할 때까지 대기 하도록 합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICLRSyncManager 인터페이스](iclrsyncmanager-interface.md)
- [IHostAutoEvent 인터페이스](ihostautoevent-interface.md)
- [IHostManualEvent 인터페이스](ihostmanualevent-interface.md)
- [IHostSyncManager 인터페이스](ihostsyncmanager-interface.md)
- [호스팅 인터페이스](hosting-interfaces.md)
