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
ms.openlocfilehash: 2206499cad9be2a29f485ee66d468accbe00b5f5
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616686"
---
# <a name="cor_gc_thread_stats_types-enumeration"></a><span data-ttu-id="cf80f-102">COR_GC_THREAD_STATS_TYPES 열거형</span><span class="sxs-lookup"><span data-stu-id="cf80f-102">COR_GC_THREAD_STATS_TYPES Enumeration</span></span>
<span data-ttu-id="cf80f-103">스레드에 대 한 가비지 수집 통계를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cf80f-103">Indicates the garbage collection statistics for a thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf80f-104">구문</span><span class="sxs-lookup"><span data-stu-id="cf80f-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_GC_THREAD_HAS_PROMOTED_BYTES  = 0x00000001  
} COR_GC_THREAD_STATS_TYPES;  
```  
  
## <a name="members"></a><span data-ttu-id="cf80f-105">멤버</span><span class="sxs-lookup"><span data-stu-id="cf80f-105">Members</span></span>  
  
|<span data-ttu-id="cf80f-106">멤버</span><span class="sxs-lookup"><span data-stu-id="cf80f-106">Member</span></span>|<span data-ttu-id="cf80f-107">설명</span><span class="sxs-lookup"><span data-stu-id="cf80f-107">Description</span></span>|  
|------------|-----------------|  
|`COR_GC_THREAD_HAS_PROMOTED_BYTES`|<span data-ttu-id="cf80f-108">스레드의 바이트가 최신 가비지 수집에서 승격 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cf80f-108">The thread has bytes that were promoted in the most recent garbage collection.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cf80f-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cf80f-109">Requirements</span></span>  
 <span data-ttu-id="cf80f-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cf80f-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf80f-111">**헤더:** GCHost, GCHost</span><span class="sxs-lookup"><span data-stu-id="cf80f-111">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="cf80f-112">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf80f-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf80f-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cf80f-113">See also</span></span>

- [<span data-ttu-id="cf80f-114">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="cf80f-114">Hosting Enumerations</span></span>](hosting-enumerations.md)
