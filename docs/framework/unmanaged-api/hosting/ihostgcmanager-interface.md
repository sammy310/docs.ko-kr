---
title: IHostGCManager 인터페이스
ms.date: 03/30/2017
api_name:
- IHostGCManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostGCManager
helpviewer_keywords:
- IHostGCManager interface [.NET Framework hosting]
ms.assetid: 820330a4-244c-4f67-ab5e-f24b0b3c2080
topic_type:
- apiref
ms.openlocfilehash: eb7e52b5237d4341c27b8c167249dc2614168679
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729532"
---
# <a name="ihostgcmanager-interface"></a>IHostGCManager 인터페이스

CLR (공용 언어 런타임)에서 구현 하는 가비지 수집 메커니즘에서 이벤트의 호스트에 알리는 메서드를 제공 합니다.  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|[SuspensionEnding 메서드](ihostgcmanager-suspensionending-method.md)|CLR이 가비지 컬렉션에 대해 일시 중단 된 스레드의 작업 실행을 다시 시작 하 고 있음을 호스트에 알립니다.|  
|[SuspensionStarting 메서드](ihostgcmanager-suspensionstarting-method.md)|가비지 수집을 수행 하기 위해 CLR이 태스크의 실행을 일시 중단 했음을 호스트에 알립니다.|  
|[ThreadIsBlockingForSuspension 메서드](ihostgcmanager-threadisblockingforsuspension-method.md)|메서드 호출이 수행 된 스레드가 가비지 컬렉션에 대해 차단 하려고 함을 호스트에 알립니다.|  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICLRTask 인터페이스](iclrtask-interface.md)
- [ICLRTaskManager 인터페이스](iclrtaskmanager-interface.md)
- [IHostTask 인터페이스](ihosttask-interface.md)
- [IHostTaskManager 인터페이스](ihosttaskmanager-interface.md)
- [호스팅 인터페이스](hosting-interfaces.md)
