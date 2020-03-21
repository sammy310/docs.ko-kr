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
ms.openlocfilehash: 2ab0c38645a8e5fbd9e71b3c1787e88bfe2c0604
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176528"
---
# <a name="cor_gc_stats-structure"></a>COR_GC_STATS 구조체
공통 언어 런타임(CLR)의 가비지 수집 메커니즘에 대한 통계를 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
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
  
## <a name="members"></a>구성원  
  
|멤버|Description|  
|------------|-----------------|  
|`Flags`|계산하고 반환해야 하는 필드 값을 나타냅니다.|  
|`ExplicitGCCount`|외부 요청에 의해 강제로 적용된 가비지 콜렉션 수를 나타냅니다.|  
|`GenCollectionsTaken`|각 세대에 대해 수행된 가비지 콜렉션 수를 나타냅니다.|  
|`CommittedKBytes`|모든 힙에서 커밋된 총 킬로바이트 수입니다.|  
|`ReservedKBytes`|모든 힙에 예약된 총 킬로바이트 수입니다.|  
|`Gen0HeapSizeKBytes`|생성 제로 힙의 크기(킬로바이트)입니다.|  
|`Gen1HeapSizeKBytes`|1세대 힙의 크기(킬로바이트)입니다.|  
|`Gen2HeapSizeKBytes`|2세대 힙의 크기(킬로바이트)입니다.|  
|`LargeObjectHeapSizeKBytes`|큰 개체 힙의 크기(킬로바이트)입니다.|  
|`KBytesPromotedFromGen0`|0세대에서 1세대로 승격된 개체의 크기(킬로바이트)입니다.|  
|`KBytesPromotedFromGen1`|1세대에서 2세대로 승격된 개체의 크기(킬로바이트)입니다.|  
  
## <a name="remarks"></a>설명  
 [ICLRGCManager:GetStats](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md) 메서드는 `COR_GC_STATS` 설정할 `Flags` 통계를 지정하려면 [구조의](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) 필드를 COR_GC_STAT_TYPES 열거형의 하나 이상의 값으로 설정해야 합니다.  
  
 다음 표는 이 구조에서 제공하는 통계를 두 [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) 열거값 `COR_GC_COUNTS` 및 `COR_GC_MEMORYUSAGE`에 매핑합니다.  
  
|COR_GC_COUNTS 지정|COR_GC_MEMORYUSAGE 지정|  
|----------------------------------|---------------------------------------|  
|`ExplicitGCCount`<br /><br /> `GenCollectionsTaken`|`CommittedKBytes`<br /><br /> `ReservedKBytes`<br /><br /> `Gen0HeapSizeKBytes`<br /><br /> `Gen1HeapSizeKBytes`<br /><br /> `Gen2HeapSizeKBytes`<br /><br /> `LargeObjectHeapSizeKBytes`<br /><br /> `KBytesPromotedFromGen0`<br /><br /> `KBytesPromotedFromGen1`|  
  
 사용의 예는 다음과 같습니다.  
  
```cpp  
COR_GC_STATS GCStats;  
GCStats.Flags = COR_GC_COUNTS | COR_GC_MEMORYUSAGE;  
pCLRGCManager->GetStats(&GCStats);  
```  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** GCHost.idl  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [호스팅 구조체](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [자동 메모리 관리](../../../standard/automatic-memory-management.md)
- [가비지 수집](../../../standard/garbage-collection/index.md)
