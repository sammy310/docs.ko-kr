---
description: '다음에 대 한 자세한 정보: 열거형 COR_GC_THREAD_STATS_TYPES'
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
ms.openlocfilehash: 04bc4e11c527b83cf5f1384b1092cc0d084008a3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799774"
---
# <a name="cor_gc_thread_stats_types-enumeration"></a><span data-ttu-id="c7617-103">COR_GC_THREAD_STATS_TYPES 열거형</span><span class="sxs-lookup"><span data-stu-id="c7617-103">COR_GC_THREAD_STATS_TYPES Enumeration</span></span>

<span data-ttu-id="c7617-104">스레드에 대 한 가비지 수집 통계를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c7617-104">Indicates the garbage collection statistics for a thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7617-105">구문</span><span class="sxs-lookup"><span data-stu-id="c7617-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_GC_THREAD_HAS_PROMOTED_BYTES  = 0x00000001  
} COR_GC_THREAD_STATS_TYPES;  
```  
  
## <a name="members"></a><span data-ttu-id="c7617-106">구성원</span><span class="sxs-lookup"><span data-stu-id="c7617-106">Members</span></span>  
  
|<span data-ttu-id="c7617-107">멤버</span><span class="sxs-lookup"><span data-stu-id="c7617-107">Member</span></span>|<span data-ttu-id="c7617-108">설명</span><span class="sxs-lookup"><span data-stu-id="c7617-108">Description</span></span>|  
|------------|-----------------|  
|`COR_GC_THREAD_HAS_PROMOTED_BYTES`|<span data-ttu-id="c7617-109">스레드의 바이트가 최신 가비지 수집에서 승격 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c7617-109">The thread has bytes that were promoted in the most recent garbage collection.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c7617-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c7617-110">Requirements</span></span>  

 <span data-ttu-id="c7617-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c7617-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7617-112">**헤더:** GCHost, GCHost</span><span class="sxs-lookup"><span data-stu-id="c7617-112">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="c7617-113">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7617-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7617-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c7617-114">See also</span></span>

- [<span data-ttu-id="c7617-115">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="c7617-115">Hosting Enumerations</span></span>](hosting-enumerations.md)
