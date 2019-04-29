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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774545"
---
# <a name="corgcstats-structure"></a><span data-ttu-id="4a8e9-102">COR_GC_STATS 구조체</span><span class="sxs-lookup"><span data-stu-id="4a8e9-102">COR_GC_STATS Structure</span></span>
<span data-ttu-id="4a8e9-103">CLR (공용 언어 런타임)의 가비지 수집 메커니즘에 대 한 통계를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4a8e9-103">Provides statistics about the garbage collection mechanism of the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a8e9-104">구문</span><span class="sxs-lookup"><span data-stu-id="4a8e9-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="4a8e9-105">멤버</span><span class="sxs-lookup"><span data-stu-id="4a8e9-105">Members</span></span>  
  
|<span data-ttu-id="4a8e9-106">멤버</span><span class="sxs-lookup"><span data-stu-id="4a8e9-106">Member</span></span>|<span data-ttu-id="4a8e9-107">설명</span><span class="sxs-lookup"><span data-stu-id="4a8e9-107">Description</span></span>|  
|------------|-----------------|  
|`Flags`|<span data-ttu-id="4a8e9-108">계산 고 반환 하는 필드 값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4a8e9-108">Indicates which field values should be calculated and returned.</span></span>|  
|`ExplicitGCCount`|<span data-ttu-id="4a8e9-109">외부 요청에서 강제 된 가비지 수집 횟수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4a8e9-109">Indicates the number of garbage collections that were forced by external request.</span></span>|  
|`GenCollectionsTaken`|<span data-ttu-id="4a8e9-110">각 세대에 대해 수행 하는 가비지 수집 횟수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4a8e9-110">Indicates the number of garbage collections performed for each generation.</span></span>|  
|`CommittedKBytes`|<span data-ttu-id="4a8e9-111">모든 힙에서 커밋 (킬로바이트)의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="4a8e9-111">The total number of kilobytes committed in all heaps.</span></span>|  
|`ReservedKBytes`|<span data-ttu-id="4a8e9-112">(킬로바이트) 모든 힙의 예약의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="4a8e9-112">The total number of kilobytes reserved in all heaps.</span></span>|  
|`Gen0HeapSizeKBytes`|<span data-ttu-id="4a8e9-113">(킬로바이트) 0 세대 힙의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="4a8e9-113">The size, in kilobytes, of the generation-zero heap.</span></span>|  
|`Gen1HeapSizeKBytes`|<span data-ttu-id="4a8e9-114">(킬로바이트)의 1 세대 힙의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="4a8e9-114">The size, in kilobytes, of the generation-one heap.</span></span>|  
|`Gen2HeapSizeKBytes`|<span data-ttu-id="4a8e9-115">(킬로바이트)의 2 세대 힙의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="4a8e9-115">The size, in kilobytes, of the generation-two heap.</span></span>|  
|`LargeObjectHeapSizeKBytes`|<span data-ttu-id="4a8e9-116">(킬로바이트)의 대형 개체 힙의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="4a8e9-116">The size, in kilobytes, of the large object heap.</span></span>|  
|`KBytesPromotedFromGen0`|<span data-ttu-id="4a8e9-117">(킬로바이트) 0 세대에서 1 세대로 승격 된 개체의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="4a8e9-117">The size, in kilobytes, of the objects promoted from generation zero to generation one.</span></span>|  
|`KBytesPromotedFromGen1`|<span data-ttu-id="4a8e9-118">(킬로바이트) 1 세대에서 2 세대로 승격 된 개체의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="4a8e9-118">The size, in kilobytes, of the objects promoted from generation one to generation two.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4a8e9-119">설명</span><span class="sxs-lookup"><span data-stu-id="4a8e9-119">Remarks</span></span>  
 <span data-ttu-id="4a8e9-120">[iclrgcmanager:: Getstats](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md) 메서드를 사용 하려면 합니다 `Flags` 필드를 `COR_GC_STATS` 구조체의 하나 이상의 값으로 설정 됩니다는 [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) 를 지정 하는 열거형 통계가 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a8e9-120">The [ICLRGCManager::GetStats](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md) method requires the `Flags` field of the `COR_GC_STATS` structure to be set to one or more values of the [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) enumeration to specify which statistics are to be set.</span></span>  
  
 <span data-ttu-id="4a8e9-121">다음 표에서이 구조를 두 개의 제공 하는 통계 [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) 열거형 값 `COR_GC_COUNTS` 고 `COR_GC_MEMORYUSAGE`입니다.</span><span class="sxs-lookup"><span data-stu-id="4a8e9-121">The following table maps the statistics provided by this structure to the two [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) enumeration values, `COR_GC_COUNTS` and `COR_GC_MEMORYUSAGE`.</span></span>  
  
|<span data-ttu-id="4a8e9-122">지정 된 COR_GC_COUNTS</span><span class="sxs-lookup"><span data-stu-id="4a8e9-122">Specified by COR_GC_COUNTS</span></span>|<span data-ttu-id="4a8e9-123">지정 된 COR_GC_MEMORYUSAGE</span><span class="sxs-lookup"><span data-stu-id="4a8e9-123">Specified by COR_GC_MEMORYUSAGE</span></span>|  
|----------------------------------|---------------------------------------|  
|`ExplicitGCCount`<br /><br /> `GenCollectionsTaken`|`CommittedKBytes`<br /><br /> `ReservedKBytes`<br /><br /> `Gen0HeapSizeKBytes`<br /><br /> `Gen1HeapSizeKBytes`<br /><br /> `Gen2HeapSizeKBytes`<br /><br /> `LargeObjectHeapSizeKBytes`<br /><br /> `KBytesPromotedFromGen0`<br /><br /> `KBytesPromotedFromGen1`|  
  
 <span data-ttu-id="4a8e9-124">사용 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4a8e9-124">An example of the usage is as follows:</span></span>  
  
```  
COR_GC_STATS GCStats;  
GCStats.Flags = COR_GC_COUNTS | COR_GC_MEMORYUSAGE;  
pCLRGCManager->GetStats(&GCStats);  
```  
  
## <a name="requirements"></a><span data-ttu-id="4a8e9-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4a8e9-125">Requirements</span></span>  
 <span data-ttu-id="4a8e9-126">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="4a8e9-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a8e9-127">**헤더:** GCHost.idl</span><span class="sxs-lookup"><span data-stu-id="4a8e9-127">**Header:** GCHost.idl</span></span>  
  
 <span data-ttu-id="4a8e9-128">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="4a8e9-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4a8e9-129">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a8e9-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a8e9-130">참고자료</span><span class="sxs-lookup"><span data-stu-id="4a8e9-130">See also</span></span>

- [<span data-ttu-id="4a8e9-131">호스팅 구조체</span><span class="sxs-lookup"><span data-stu-id="4a8e9-131">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [<span data-ttu-id="4a8e9-132">자동 메모리 관리</span><span class="sxs-lookup"><span data-stu-id="4a8e9-132">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)
- [<span data-ttu-id="4a8e9-133">가비지 수집</span><span class="sxs-lookup"><span data-stu-id="4a8e9-133">Garbage Collection</span></span>](../../../../docs/standard/garbage-collection/index.md)
