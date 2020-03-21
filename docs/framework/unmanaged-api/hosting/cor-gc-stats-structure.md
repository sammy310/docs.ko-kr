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
# <a name="cor_gc_stats-structure"></a><span data-ttu-id="05e59-102">COR_GC_STATS 구조체</span><span class="sxs-lookup"><span data-stu-id="05e59-102">COR_GC_STATS Structure</span></span>
<span data-ttu-id="05e59-103">공통 언어 런타임(CLR)의 가비지 수집 메커니즘에 대한 통계를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="05e59-103">Provides statistics about the garbage collection mechanism of the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05e59-104">구문</span><span class="sxs-lookup"><span data-stu-id="05e59-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="05e59-105">구성원</span><span class="sxs-lookup"><span data-stu-id="05e59-105">Members</span></span>  
  
|<span data-ttu-id="05e59-106">멤버</span><span class="sxs-lookup"><span data-stu-id="05e59-106">Member</span></span>|<span data-ttu-id="05e59-107">Description</span><span class="sxs-lookup"><span data-stu-id="05e59-107">Description</span></span>|  
|------------|-----------------|  
|`Flags`|<span data-ttu-id="05e59-108">계산하고 반환해야 하는 필드 값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="05e59-108">Indicates which field values should be calculated and returned.</span></span>|  
|`ExplicitGCCount`|<span data-ttu-id="05e59-109">외부 요청에 의해 강제로 적용된 가비지 콜렉션 수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="05e59-109">Indicates the number of garbage collections that were forced by external request.</span></span>|  
|`GenCollectionsTaken`|<span data-ttu-id="05e59-110">각 세대에 대해 수행된 가비지 콜렉션 수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="05e59-110">Indicates the number of garbage collections performed for each generation.</span></span>|  
|`CommittedKBytes`|<span data-ttu-id="05e59-111">모든 힙에서 커밋된 총 킬로바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="05e59-111">The total number of kilobytes committed in all heaps.</span></span>|  
|`ReservedKBytes`|<span data-ttu-id="05e59-112">모든 힙에 예약된 총 킬로바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="05e59-112">The total number of kilobytes reserved in all heaps.</span></span>|  
|`Gen0HeapSizeKBytes`|<span data-ttu-id="05e59-113">생성 제로 힙의 크기(킬로바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="05e59-113">The size, in kilobytes, of the generation-zero heap.</span></span>|  
|`Gen1HeapSizeKBytes`|<span data-ttu-id="05e59-114">1세대 힙의 크기(킬로바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="05e59-114">The size, in kilobytes, of the generation-one heap.</span></span>|  
|`Gen2HeapSizeKBytes`|<span data-ttu-id="05e59-115">2세대 힙의 크기(킬로바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="05e59-115">The size, in kilobytes, of the generation-two heap.</span></span>|  
|`LargeObjectHeapSizeKBytes`|<span data-ttu-id="05e59-116">큰 개체 힙의 크기(킬로바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="05e59-116">The size, in kilobytes, of the large object heap.</span></span>|  
|`KBytesPromotedFromGen0`|<span data-ttu-id="05e59-117">0세대에서 1세대로 승격된 개체의 크기(킬로바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="05e59-117">The size, in kilobytes, of the objects promoted from generation zero to generation one.</span></span>|  
|`KBytesPromotedFromGen1`|<span data-ttu-id="05e59-118">1세대에서 2세대로 승격된 개체의 크기(킬로바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="05e59-118">The size, in kilobytes, of the objects promoted from generation one to generation two.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="05e59-119">설명</span><span class="sxs-lookup"><span data-stu-id="05e59-119">Remarks</span></span>  
 <span data-ttu-id="05e59-120">[ICLRGCManager:GetStats](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md) 메서드는 `COR_GC_STATS` 설정할 `Flags` 통계를 지정하려면 [구조의](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) 필드를 COR_GC_STAT_TYPES 열거형의 하나 이상의 값으로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05e59-120">The [ICLRGCManager::GetStats](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md) method requires the `Flags` field of the `COR_GC_STATS` structure to be set to one or more values of the [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) enumeration to specify which statistics are to be set.</span></span>  
  
 <span data-ttu-id="05e59-121">다음 표는 이 구조에서 제공하는 통계를 두 [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) 열거값 `COR_GC_COUNTS` 및 `COR_GC_MEMORYUSAGE`에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="05e59-121">The following table maps the statistics provided by this structure to the two [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) enumeration values, `COR_GC_COUNTS` and `COR_GC_MEMORYUSAGE`.</span></span>  
  
|<span data-ttu-id="05e59-122">COR_GC_COUNTS 지정</span><span class="sxs-lookup"><span data-stu-id="05e59-122">Specified by COR_GC_COUNTS</span></span>|<span data-ttu-id="05e59-123">COR_GC_MEMORYUSAGE 지정</span><span class="sxs-lookup"><span data-stu-id="05e59-123">Specified by COR_GC_MEMORYUSAGE</span></span>|  
|----------------------------------|---------------------------------------|  
|`ExplicitGCCount`<br /><br /> `GenCollectionsTaken`|`CommittedKBytes`<br /><br /> `ReservedKBytes`<br /><br /> `Gen0HeapSizeKBytes`<br /><br /> `Gen1HeapSizeKBytes`<br /><br /> `Gen2HeapSizeKBytes`<br /><br /> `LargeObjectHeapSizeKBytes`<br /><br /> `KBytesPromotedFromGen0`<br /><br /> `KBytesPromotedFromGen1`|  
  
 <span data-ttu-id="05e59-124">사용의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="05e59-124">An example of the usage is as follows:</span></span>  
  
```cpp  
COR_GC_STATS GCStats;  
GCStats.Flags = COR_GC_COUNTS | COR_GC_MEMORYUSAGE;  
pCLRGCManager->GetStats(&GCStats);  
```  
  
## <a name="requirements"></a><span data-ttu-id="05e59-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="05e59-125">Requirements</span></span>  
 <span data-ttu-id="05e59-126">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="05e59-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05e59-127">**헤더:** GCHost.idl</span><span class="sxs-lookup"><span data-stu-id="05e59-127">**Header:** GCHost.idl</span></span>  
  
 <span data-ttu-id="05e59-128">**라이브러리:** MSCorEE.dll의 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="05e59-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="05e59-129">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05e59-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05e59-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="05e59-130">See also</span></span>

- [<span data-ttu-id="05e59-131">호스팅 구조체</span><span class="sxs-lookup"><span data-stu-id="05e59-131">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [<span data-ttu-id="05e59-132">자동 메모리 관리</span><span class="sxs-lookup"><span data-stu-id="05e59-132">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="05e59-133">가비지 수집</span><span class="sxs-lookup"><span data-stu-id="05e59-133">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
