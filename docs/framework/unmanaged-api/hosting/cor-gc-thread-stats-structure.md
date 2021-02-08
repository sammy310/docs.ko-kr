---
description: '다음에 대 한 자세한 정보: COR_GC_THREAD_STATS 구조체'
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
ms.openlocfilehash: 179eb335e9f8c118ee98d4b777c347f3758ee0c6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799787"
---
# <a name="cor_gc_thread_stats-structure"></a><span data-ttu-id="e4021-103">COR_GC_THREAD_STATS 구조체</span><span class="sxs-lookup"><span data-stu-id="e4021-103">COR_GC_THREAD_STATS Structure</span></span>

<span data-ttu-id="e4021-104">가비지 수집과 관련 된 스레드별 통계를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4021-104">Contains per-thread statistics pertaining to garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4021-105">구문</span><span class="sxs-lookup"><span data-stu-id="e4021-105">Syntax</span></span>  
  
```cpp  
typedef struct _COR_GC_THREAD_STATS {  
    ULONGLONG  PerThreadAllocation;
    ULONG      Flags;
} COR_GC_THREAD_STATS;  
```  
  
## <a name="members"></a><span data-ttu-id="e4021-106">구성원</span><span class="sxs-lookup"><span data-stu-id="e4021-106">Members</span></span>  
  
|<span data-ttu-id="e4021-107">멤버</span><span class="sxs-lookup"><span data-stu-id="e4021-107">Member</span></span>|<span data-ttu-id="e4021-108">설명</span><span class="sxs-lookup"><span data-stu-id="e4021-108">Description</span></span>|  
|------------|-----------------|  
|`PerThreadAllocation`|<span data-ttu-id="e4021-109">현재 인스턴스와 연결 된 스레드에 할당 된 메모리의 바이트 수입니다 `COR_GC_THREAD_STATS` .</span><span class="sxs-lookup"><span data-stu-id="e4021-109">The number of bytes of memory allocated on the thread that is associated with the current `COR_GC_THREAD_STATS` instance.</span></span> <span data-ttu-id="e4021-110">0 세대 가비지 수집이 발생 될 때마다이 숫자는 0으로 지워집니다.</span><span class="sxs-lookup"><span data-stu-id="e4021-110">This number is cleared to zero each time a generation-zero garbage collection occurs.</span></span>|  
|`Flags`|<span data-ttu-id="e4021-111">최신 가비지 수집에서 더 높은 세대로 승격 된 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="e4021-111">The number of bytes promoted to a higher generation at the most recent garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e4021-112">설명</span><span class="sxs-lookup"><span data-stu-id="e4021-112">Remarks</span></span>  

 <span data-ttu-id="e4021-113">[ICLRTask:: GetMemStats](iclrtask-getmemstats-method.md) 는 형식의 출력 매개 변수를 사용 `COR_GC_THREAD_STATS` 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4021-113">[ICLRTask::GetMemStats](iclrtask-getmemstats-method.md) takes an output parameter of type `COR_GC_THREAD_STATS`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4021-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e4021-114">Requirements</span></span>  

 <span data-ttu-id="e4021-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e4021-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4021-116">**헤더:** GCHost</span><span class="sxs-lookup"><span data-stu-id="e4021-116">**Header:** GCHost.idl</span></span>  
  
 <span data-ttu-id="e4021-117">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4021-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e4021-118">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e4021-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4021-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e4021-119">See also</span></span>

- [<span data-ttu-id="e4021-120">호스팅 구조체</span><span class="sxs-lookup"><span data-stu-id="e4021-120">Hosting Structures</span></span>](hosting-structures.md)
- [<span data-ttu-id="e4021-121">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e4021-121">IHostTask Interface</span></span>](ihosttask-interface.md)
