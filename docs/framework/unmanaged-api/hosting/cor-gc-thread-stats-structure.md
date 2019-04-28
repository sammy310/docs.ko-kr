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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f60a4b56270318a05d0e5a480fdb56eb45593d5e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61696712"
---
# <a name="corgcthreadstats-structure"></a>COR_GC_THREAD_STATS 구조체
가비지 수집과 관련 된 스레드 통계를 포함 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef struct _COR_GC_THREAD_STATS {  
    ULONGLONG  PerThreadAllocation;   
    ULONG      Flags;   
} COR_GC_THREAD_STATS;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`PerThreadAllocation`|연결 된 현재 스레드에 할당 된 메모리의 바이트 수가 `COR_GC_THREAD_STATS` 인스턴스. 이 번호는 0 세대 가비지 수집이 발생 될 때마다를 0으로 지워집니다.|  
|`Flags`|가장 최근의 가비지 컬렉션을 상위 세대로 승격 바이트 수입니다.|  
  
## <a name="remarks"></a>설명  
 [Iclrtask:: Getmemstats](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md) 형식의 출력 매개 변수를 `COR_GC_THREAD_STATS`입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** GCHost.idl  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [호스팅 구조체](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [IHostTask 인터페이스](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
