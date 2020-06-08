---
title: COR_GC_STAT_TYPES 열거형
ms.date: 03/30/2017
api_name:
- COR_GC_STAT_TYPES
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_GC_STAT_TYPES
helpviewer_keywords:
- COR_GC_STAT_TYPES enumeration [.NET Framework hosting]
ms.assetid: fc51d6db-f7f8-408b-b93d-c166fc712c99
topic_type:
- apiref
ms.openlocfilehash: d7e78dfc4beba67cc376b221d0cd49f7200f5d23
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501705"
---
# <a name="cor_gc_stat_types-enumeration"></a><span data-ttu-id="91395-102">COR_GC_STAT_TYPES 열거형</span><span class="sxs-lookup"><span data-stu-id="91395-102">COR_GC_STAT_TYPES Enumeration</span></span>
<span data-ttu-id="91395-103">가비지 컬렉션에 대해 기록할 통계를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="91395-103">Specifies the statistics to be recorded for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91395-104">구문</span><span class="sxs-lookup"><span data-stu-id="91395-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_GC_COUNTS                 = 0x00000001  
    COR_GC_MEMORYUSAGE            = 0x00000002  
} COR_GC_STAT_TYPES;  
```  
  
## <a name="remarks"></a><span data-ttu-id="91395-105">설명</span><span class="sxs-lookup"><span data-stu-id="91395-105">Remarks</span></span>  
 <span data-ttu-id="91395-106">이 열거형은 [ICLRGCManager:: GetStats](iclrgcmanager-getstats-method.md) 메서드로 설정할 [COR_GC_STATS](cor-gc-stats-structure.md) 구조체의 통계를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="91395-106">This enumeration specifies which statistics in the [COR_GC_STATS](cor-gc-stats-structure.md) structure are to be set by [ICLRGCManager::GetStats](iclrgcmanager-getstats-method.md) method.</span></span>  
  
## <a name="members"></a><span data-ttu-id="91395-107">멤버</span><span class="sxs-lookup"><span data-stu-id="91395-107">Members</span></span>  
  
|<span data-ttu-id="91395-108">멤버</span><span class="sxs-lookup"><span data-stu-id="91395-108">Member</span></span>|<span data-ttu-id="91395-109">설명</span><span class="sxs-lookup"><span data-stu-id="91395-109">Description</span></span>|  
|------------|-----------------|  
|`COR_GC_COUNTS`|<span data-ttu-id="91395-110">각 세대에 대해 수행 된 가비지 컬렉션의 수를 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="91395-110">Records the number of garbage collections performed for each generation.</span></span>|  
|`COR_GC_MEMORYUSAGE`|<span data-ttu-id="91395-111">메모리 사용 및 가비지 컬렉션 크기 통계를 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="91395-111">Records memory usage and garbage collection size statistics.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="91395-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="91395-112">Requirements</span></span>  
 <span data-ttu-id="91395-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="91395-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91395-114">**헤더:** GCHost, GCHost</span><span class="sxs-lookup"><span data-stu-id="91395-114">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="91395-115">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91395-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91395-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="91395-116">See also</span></span>

- [<span data-ttu-id="91395-117">COR_GC_STATS 구조체</span><span class="sxs-lookup"><span data-stu-id="91395-117">COR_GC_STATS Structure</span></span>](cor-gc-stats-structure.md)
- [<span data-ttu-id="91395-118">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="91395-118">Hosting Enumerations</span></span>](hosting-enumerations.md)
