---
title: COR_GC_THREAD_STATS_TYPES 열거형
ms.date: 03/30/2017
api_name:
- COR_GC_THREAD_STATS_TYPES
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_GC_THREAD_STATS_TYPES
helpviewer_keywords:
- COR_GC_THREAD_STATS_TYPES enumeration [.NET Framework hosting]
ms.assetid: aa227704-0ab1-4b08-aee2-1f439762162e
topic_type:
- apiref
ms.openlocfilehash: 63275aaa7ed1f63c4f100845d2cbe9e93fcd0bcd
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131250"
---
# <a name="cor_gc_thread_stats_types-enumeration"></a><span data-ttu-id="6ecbd-102">COR_GC_THREAD_STATS_TYPES 열거형</span><span class="sxs-lookup"><span data-stu-id="6ecbd-102">COR_GC_THREAD_STATS_TYPES Enumeration</span></span>
<span data-ttu-id="6ecbd-103">스레드에 대 한 가비지 수집 통계를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6ecbd-103">Indicates the garbage collection statistics for a thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ecbd-104">구문</span><span class="sxs-lookup"><span data-stu-id="6ecbd-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_GC_THREAD_HAS_PROMOTED_BYTES  = 0x00000001  
} COR_GC_THREAD_STATS_TYPES;  
```  
  
## <a name="members"></a><span data-ttu-id="6ecbd-105">멤버</span><span class="sxs-lookup"><span data-stu-id="6ecbd-105">Members</span></span>  
  
|<span data-ttu-id="6ecbd-106">멤버</span><span class="sxs-lookup"><span data-stu-id="6ecbd-106">Member</span></span>|<span data-ttu-id="6ecbd-107">설명</span><span class="sxs-lookup"><span data-stu-id="6ecbd-107">Description</span></span>|  
|------------|-----------------|  
|`COR_GC_THREAD_HAS_PROMOTED_BYTES`|<span data-ttu-id="6ecbd-108">스레드의 바이트가 최신 가비지 수집에서 승격 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6ecbd-108">The thread has bytes that were promoted in the most recent garbage collection.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6ecbd-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6ecbd-109">Requirements</span></span>  
 <span data-ttu-id="6ecbd-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6ecbd-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ecbd-111">**헤더:** GCHost, GCHost</span><span class="sxs-lookup"><span data-stu-id="6ecbd-111">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="6ecbd-112">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ecbd-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ecbd-113">참조</span><span class="sxs-lookup"><span data-stu-id="6ecbd-113">See also</span></span>

- [<span data-ttu-id="6ecbd-114">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="6ecbd-114">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
