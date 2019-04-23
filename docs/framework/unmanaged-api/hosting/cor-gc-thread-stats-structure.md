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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59177738"
---
# <a name="corgcthreadstats-structure"></a><span data-ttu-id="acca8-102">COR_GC_THREAD_STATS 구조체</span><span class="sxs-lookup"><span data-stu-id="acca8-102">COR_GC_THREAD_STATS Structure</span></span>
<span data-ttu-id="acca8-103">가비지 수집과 관련 된 스레드 통계를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="acca8-103">Contains per-thread statistics pertaining to garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="acca8-104">구문</span><span class="sxs-lookup"><span data-stu-id="acca8-104">Syntax</span></span>  
  
```  
typedef struct _COR_GC_THREAD_STATS {  
    ULONGLONG  PerThreadAllocation;   
    ULONG      Flags;   
} COR_GC_THREAD_STATS;  
```  
  
## <a name="members"></a><span data-ttu-id="acca8-105">멤버</span><span class="sxs-lookup"><span data-stu-id="acca8-105">Members</span></span>  
  
|<span data-ttu-id="acca8-106">멤버</span><span class="sxs-lookup"><span data-stu-id="acca8-106">Member</span></span>|<span data-ttu-id="acca8-107">설명</span><span class="sxs-lookup"><span data-stu-id="acca8-107">Description</span></span>|  
|------------|-----------------|  
|`PerThreadAllocation`|<span data-ttu-id="acca8-108">연결 된 현재 스레드에 할당 된 메모리의 바이트 수가 `COR_GC_THREAD_STATS` 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="acca8-108">The number of bytes of memory allocated on the thread that is associated with the current `COR_GC_THREAD_STATS` instance.</span></span> <span data-ttu-id="acca8-109">이 번호는 0 세대 가비지 수집이 발생 될 때마다를 0으로 지워집니다.</span><span class="sxs-lookup"><span data-stu-id="acca8-109">This number is cleared to zero each time a generation-zero garbage collection occurs.</span></span>|  
|`Flags`|<span data-ttu-id="acca8-110">가장 최근의 가비지 컬렉션을 상위 세대로 승격 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="acca8-110">The number of bytes promoted to a higher generation at the most recent garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="acca8-111">설명</span><span class="sxs-lookup"><span data-stu-id="acca8-111">Remarks</span></span>  
 <span data-ttu-id="acca8-112">[Iclrtask:: Getmemstats](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md) 형식의 출력 매개 변수를 `COR_GC_THREAD_STATS`입니다.</span><span class="sxs-lookup"><span data-stu-id="acca8-112">[ICLRTask::GetMemStats](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md) takes an output parameter of type `COR_GC_THREAD_STATS`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="acca8-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="acca8-113">Requirements</span></span>  
 <span data-ttu-id="acca8-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="acca8-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="acca8-115">**헤더:** GCHost.idl</span><span class="sxs-lookup"><span data-stu-id="acca8-115">**Header:** GCHost.idl</span></span>  
  
 <span data-ttu-id="acca8-116">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="acca8-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="acca8-117">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="acca8-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acca8-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="acca8-118">See also</span></span>

- [<span data-ttu-id="acca8-119">호스팅 구조체</span><span class="sxs-lookup"><span data-stu-id="acca8-119">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [<span data-ttu-id="acca8-120">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="acca8-120">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
