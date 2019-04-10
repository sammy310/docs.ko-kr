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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c631a0a3abb3cb2a342dfd44fdffb147b742ae3c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59212468"
---
# <a name="corgcthreadstatstypes-enumeration"></a><span data-ttu-id="59043-102">COR_GC_THREAD_STATS_TYPES 열거형</span><span class="sxs-lookup"><span data-stu-id="59043-102">COR_GC_THREAD_STATS_TYPES Enumeration</span></span>
<span data-ttu-id="59043-103">스레드에 대 한 가비지 수집 통계를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="59043-103">Indicates the garbage collection statistics for a thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59043-104">구문</span><span class="sxs-lookup"><span data-stu-id="59043-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_GC_THREAD_HAS_PROMOTED_BYTES  = 0x00000001  
} COR_GC_THREAD_STATS_TYPES;  
```  
  
## <a name="members"></a><span data-ttu-id="59043-105">멤버</span><span class="sxs-lookup"><span data-stu-id="59043-105">Members</span></span>  
  
|<span data-ttu-id="59043-106">멤버</span><span class="sxs-lookup"><span data-stu-id="59043-106">Member</span></span>|<span data-ttu-id="59043-107">설명</span><span class="sxs-lookup"><span data-stu-id="59043-107">Description</span></span>|  
|------------|-----------------|  
|`COR_GC_THREAD_HAS_PROMOTED_BYTES`|<span data-ttu-id="59043-108">스레드가 가장 최근의 가비지 수집에서 승격 된 바이트입니다.</span><span class="sxs-lookup"><span data-stu-id="59043-108">The thread has bytes that were promoted in the most recent garbage collection.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="59043-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="59043-109">Requirements</span></span>  
 <span data-ttu-id="59043-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="59043-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59043-111">**헤더:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="59043-111">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 **<span data-ttu-id="59043-112">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="59043-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="59043-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="59043-113">See also</span></span>

- [<span data-ttu-id="59043-114">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="59043-114">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
