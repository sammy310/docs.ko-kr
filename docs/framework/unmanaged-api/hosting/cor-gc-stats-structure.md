---
title: COR_GC_STATS 구조체
ms.date: 03/30/2017
api_name:
- COR_GC_STATS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_GC_STATS
helpviewer_keywords:
- COR_GC_STATS structure [.NET Framework hosting]
ms.assetid: 8d4ff73e-739b-40f6-9349-359fbc99c2f9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d335a62545f06a66d4044b59aa9499d3f7ede515
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59208477"
---
# <a name="corgcstats-structure"></a>COR_GC_STATS 구조체
CLR (공용 언어 런타임)의 가비지 수집 메커니즘에 대 한 통계를 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef struct _COR_GC_STATS {  
    ULONG   Flags;   
    SIZE_T  ExplicitGCCount;  
    SIZE_T  GenCollectionsTaken[3];  
    SIZE_T  CommittedKBytes;   
    SIZE_T  ReservedKBytes;  
    SIZE_T  Gen0HeapSizeKBytes;  
    SIZE_T  Gen1HeapSizeKBytes;  
    SIZE_T  Gen2HeapSizeKBytes;  
    SIZE_T  LargeObjectHeapSizeKBytes;  
    SIZE_T  KBytesPromotedFromGen0;  
    SIZE_T  KBytesPromotedFromGen1;  
} COR_GC_STATS;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`Flags`|계산 고 반환 하는 필드 값을 나타냅니다.|  
|`ExplicitGCCount`|외부 요청에서 강제 된 가비지 수집 횟수를 나타냅니다.|  
|`GenCollectionsTaken`|각 세대에 대해 수행 하는 가비지 수집 횟수를 나타냅니다.|  
|`CommittedKBytes`|모든 힙에서 커밋 (킬로바이트)의 총 수입니다.|  
|`ReservedKBytes`|(킬로바이트) 모든 힙의 예약의 총 수입니다.|  
|`Gen0HeapSizeKBytes`|(킬로바이트) 0 세대 힙의 크기입니다.|  
|`Gen1HeapSizeKBytes`|(킬로바이트)의 1 세대 힙의 크기입니다.|  
|`Gen2HeapSizeKBytes`|(킬로바이트)의 2 세대 힙의 크기입니다.|  
|`LargeObjectHeapSizeKBytes`|(킬로바이트)의 대형 개체 힙의 크기입니다.|  
|`KBytesPromotedFromGen0`|(킬로바이트) 0 세대에서 1 세대로 승격 된 개체의 크기입니다.|  
|`KBytesPromotedFromGen1`|(킬로바이트) 1 세대에서 2 세대로 승격 된 개체의 크기입니다.|  
  
## <a name="remarks"></a>설명  
 [iclrgcmanager:: Getstats](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md) 메서드를 사용 하려면 합니다 `Flags` 필드를 `COR_GC_STATS` 구조체의 하나 이상의 값으로 설정 됩니다는 [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) 를 지정 하는 열거형 통계가 설정 해야 합니다.  
  
 다음 표에서이 구조를 두 개의 제공 하는 통계 [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) 열거형 값 `COR_GC_COUNTS` 고 `COR_GC_MEMORYUSAGE`입니다.  
  
|지정 된 COR_GC_COUNTS|지정 된 COR_GC_MEMORYUSAGE|  
|----------------------------------|---------------------------------------|  
|`ExplicitGCCount`<br /><br /> `GenCollectionsTaken`|`CommittedKBytes`<br /><br /> `ReservedKBytes`<br /><br /> `Gen0HeapSizeKBytes`<br /><br /> `Gen1HeapSizeKBytes`<br /><br /> `Gen2HeapSizeKBytes`<br /><br /> `LargeObjectHeapSizeKBytes`<br /><br /> `KBytesPromotedFromGen0`<br /><br /> `KBytesPromotedFromGen1`|  
  
 사용 예는 다음과 같습니다.  
  
```  
COR_GC_STATS GCStats;  
GCStats.Flags = COR_GC_COUNTS | COR_GC_MEMORYUSAGE;  
pCLRGCManager->GetStats(&GCStats);  
```  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** GCHost.idl  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [호스팅 구조체](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [Automatic Memory Management](../../../../docs/standard/automatic-memory-management.md)
- [가비지 컬렉션](../../../../docs/standard/garbage-collection/index.md)
