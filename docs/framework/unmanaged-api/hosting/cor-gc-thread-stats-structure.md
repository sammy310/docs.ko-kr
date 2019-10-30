---
title: COR_GC_THREAD_STATS 구조체
ms.date: 03/30/2017
api_name:
- COR_GC_THREAD_STATS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_GC_THREAD_STATS
helpviewer_keywords:
- COR_GC_THREAD_STATS structure [.NET Framework hosting]
ms.assetid: 01f9a59b-7679-4d42-9ced-4a8981625c3d
topic_type:
- apiref
ms.openlocfilehash: 37da471aaa8e9f802a8430d7b3289b375ff1b40a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136978"
---
# <a name="cor_gc_thread_stats-structure"></a>COR_GC_THREAD_STATS 구조체
가비지 수집과 관련 된 스레드별 통계를 포함 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef struct _COR_GC_THREAD_STATS {  
    ULONGLONG  PerThreadAllocation;   
    ULONG      Flags;   
} COR_GC_THREAD_STATS;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`PerThreadAllocation`|현재 `COR_GC_THREAD_STATS` 인스턴스와 연결 된 스레드에 할당 된 메모리의 바이트 수입니다. 0 세대 가비지 수집이 발생 될 때마다이 숫자는 0으로 지워집니다.|  
|`Flags`|최신 가비지 수집에서 더 높은 세대로 승격 된 바이트 수입니다.|  
  
## <a name="remarks"></a>주의  
 [ICLRTask:: GetMemStats](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md) 는 `COR_GC_THREAD_STATS`형식의 출력 매개 변수를 사용 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** GCHost  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조

- [호스팅 구조체](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [IHostTask 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
