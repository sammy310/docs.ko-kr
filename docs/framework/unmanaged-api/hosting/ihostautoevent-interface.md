---
title: IHostAutoEvent 인터페이스
ms.date: 03/30/2017
api_name:
- IHostAutoEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAutoEvent
helpviewer_keywords:
- IHostAutoEvent interface [.NET Framework hosting]
ms.assetid: 6c1d15c1-a80a-4ee9-b1e4-6e859db6575a
topic_type:
- apiref
ms.openlocfilehash: 6893b019c7e86d3f359cf64752d30f7896203786
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95680869"
---
# <a name="ihostautoevent-interface"></a>IHostAutoEvent 인터페이스

자동 재설정 이벤트의 호스트 구현에 대 한 표현을 제공 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[Set 메서드](ihostautoevent-set-method.md)|현재 인스턴스를 `IHostAutoEvent` 신호를 받은 상태로 설정 합니다.|  
|[Wait 메서드](ihostautoevent-wait-method.md)|`IHostAutoEvent`이벤트가 소유 될 때까지 또는 지정 된 시간이 경과할 때까지 현재 인스턴스가 대기 하도록 합니다.|  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICLRSyncManager 인터페이스](iclrsyncmanager-interface.md)
- [IHostManualEvent 인터페이스](ihostmanualevent-interface.md)
- [IHostSyncManager 인터페이스](ihostsyncmanager-interface.md)
- [호스팅 인터페이스](hosting-interfaces.md)
