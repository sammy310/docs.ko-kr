---
title: IHostCrst 인터페이스
ms.date: 03/30/2017
api_name:
- IHostCrst
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostCrst
helpviewer_keywords:
- IHostCrst interface [.NET Framework hosting]
ms.assetid: ac298ebd-0815-47e4-a823-30b31baab903
topic_type:
- apiref
ms.openlocfilehash: 108492ba298e9f8429b2acd890ab3404365bc602
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130520"
---
# <a name="ihostcrst-interface"></a>IHostCrst 인터페이스
스레딩에 대 한 중요 한 섹션의 호스트 표현으로 사용 됩니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[Enter 메서드](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-enter-method.md)|임계 영역을 입력 합니다.|  
|[Leave 메서드](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-leave-method.md)|임계 영역을 남겨 둡니다.|  
|[SetSpinCount 메서드](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-setspincount-method.md)|임계 영역에 대 한 회전 수를 설정 합니다.|  
|[TryEnter 메서드](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-tryenter-method.md)|임계 영역에 대 한 시작을 시도 하 고 성공 또는 실패를 즉시 보고 합니다.|  
  
## <a name="remarks"></a>주의  
 `IHostCrst`를 사용 하면 CLR (공용 언어 런타임)이 `EnterCriticalSection` 또는 `LeaveCriticalSection`같은 Win32 함수를 사용 하는 대신 CLR (공용 언어 런타임)에서 중요 한 섹션의 호스트 표현과 직접 통신할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICLRSyncManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [IHostSyncManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- [호스팅 인터페이스](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
