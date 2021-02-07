---
description: '자세히 알아보기: IHostCrst 인터페이스'
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
ms.openlocfilehash: 7945f0087667c1d610a1a2370528b055af74d579
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99708881"
---
# <a name="ihostcrst-interface"></a>IHostCrst 인터페이스

스레딩에 대 한 중요 한 섹션의 호스트 표현으로 사용 됩니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[Enter 메서드](ihostcrst-enter-method.md)|임계 영역을 입력 합니다.|  
|[Leave 메서드](ihostcrst-leave-method.md)|임계 영역을 남겨 둡니다.|  
|[SetSpinCount 메서드](ihostcrst-setspincount-method.md)|임계 영역에 대 한 회전 수를 설정 합니다.|  
|[TryEnter 메서드](ihostcrst-tryenter-method.md)|임계 영역에 대 한 시작을 시도 하 고 성공 또는 실패를 즉시 보고 합니다.|  
  
## <a name="remarks"></a>설명  

 `IHostCrst` CLR (공용 언어 런타임)이 또는와 같은 Win32 함수를 사용 하지 않고 중요 한 섹션의 호스트 표현과 직접 통신할 수 있도록 합니다 `EnterCriticalSection` `LeaveCriticalSection` .  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICLRSyncManager 인터페이스](iclrsyncmanager-interface.md)
- [IHostSyncManager 인터페이스](ihostsyncmanager-interface.md)
- [호스팅 인터페이스](hosting-interfaces.md)
