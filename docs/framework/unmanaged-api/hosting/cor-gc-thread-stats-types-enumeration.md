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
ms.openlocfilehash: a984e8645bec0f58d8a31965b762e0a3a190ba59
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67768024"
---
# <a name="corgcthreadstatstypes-enumeration"></a><span data-ttu-id="5bd1d-102">COR_GC_THREAD_STATS_TYPES 열거형</span><span class="sxs-lookup"><span data-stu-id="5bd1d-102">COR_GC_THREAD_STATS_TYPES Enumeration</span></span>
<span data-ttu-id="5bd1d-103">스레드에 대 한 가비지 수집 통계를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5bd1d-103">Indicates the garbage collection statistics for a thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5bd1d-104">구문</span><span class="sxs-lookup"><span data-stu-id="5bd1d-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_GC_THREAD_HAS_PROMOTED_BYTES  = 0x00000001  
} COR_GC_THREAD_STATS_TYPES;  
```  
  
## <a name="members"></a><span data-ttu-id="5bd1d-105">멤버</span><span class="sxs-lookup"><span data-stu-id="5bd1d-105">Members</span></span>  
  
|<span data-ttu-id="5bd1d-106">멤버</span><span class="sxs-lookup"><span data-stu-id="5bd1d-106">Member</span></span>|<span data-ttu-id="5bd1d-107">Description</span><span class="sxs-lookup"><span data-stu-id="5bd1d-107">Description</span></span>|  
|------------|-----------------|  
|`COR_GC_THREAD_HAS_PROMOTED_BYTES`|<span data-ttu-id="5bd1d-108">스레드가 가장 최근의 가비지 수집에서 승격 된 바이트입니다.</span><span class="sxs-lookup"><span data-stu-id="5bd1d-108">The thread has bytes that were promoted in the most recent garbage collection.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5bd1d-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5bd1d-109">Requirements</span></span>  
 <span data-ttu-id="5bd1d-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5bd1d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5bd1d-111">**헤더:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="5bd1d-111">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="5bd1d-112">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5bd1d-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bd1d-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="5bd1d-113">See also</span></span>

- [<span data-ttu-id="5bd1d-114">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="5bd1d-114">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
