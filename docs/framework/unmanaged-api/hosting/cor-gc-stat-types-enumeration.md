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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6fdfe33c5b488d8f464001a86233124d4e7df0ed
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779072"
---
# <a name="corgcstattypes-enumeration"></a><span data-ttu-id="eadc2-102">COR_GC_STAT_TYPES 열거형</span><span class="sxs-lookup"><span data-stu-id="eadc2-102">COR_GC_STAT_TYPES Enumeration</span></span>
<span data-ttu-id="eadc2-103">가비지 컬렉션에 대 한 기록 통계를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="eadc2-103">Specifies the statistics to be recorded for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eadc2-104">구문</span><span class="sxs-lookup"><span data-stu-id="eadc2-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_GC_COUNTS                 = 0x00000001  
    COR_GC_MEMORYUSAGE            = 0x00000002  
} COR_GC_STAT_TYPES;  
```  
  
## <a name="remarks"></a><span data-ttu-id="eadc2-105">설명</span><span class="sxs-lookup"><span data-stu-id="eadc2-105">Remarks</span></span>  
 <span data-ttu-id="eadc2-106">이 열거형에는 통계를 지정 합니다 [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) 구조는 설정할 [iclrgcmanager:: Getstats](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="eadc2-106">This enumeration specifies which statistics in the [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) structure are to be set by [ICLRGCManager::GetStats](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md) method.</span></span>  
  
## <a name="members"></a><span data-ttu-id="eadc2-107">멤버</span><span class="sxs-lookup"><span data-stu-id="eadc2-107">Members</span></span>  
  
|<span data-ttu-id="eadc2-108">멤버</span><span class="sxs-lookup"><span data-stu-id="eadc2-108">Member</span></span>|<span data-ttu-id="eadc2-109">설명</span><span class="sxs-lookup"><span data-stu-id="eadc2-109">Description</span></span>|  
|------------|-----------------|  
|`COR_GC_COUNTS`|<span data-ttu-id="eadc2-110">레코드 가비지 수집 횟수 각 세대에 대해 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="eadc2-110">Records the number of garbage collections performed for each generation.</span></span>|  
|`COR_GC_MEMORYUSAGE`|<span data-ttu-id="eadc2-111">레코드 메모리 사용 및 가비지 컬렉션 크기 통계입니다.</span><span class="sxs-lookup"><span data-stu-id="eadc2-111">Records memory usage and garbage collection size statistics.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="eadc2-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="eadc2-112">Requirements</span></span>  
 <span data-ttu-id="eadc2-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="eadc2-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eadc2-114">**헤더:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="eadc2-114">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="eadc2-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eadc2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eadc2-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="eadc2-116">See also</span></span>

- [<span data-ttu-id="eadc2-117">COR_GC_STATS 구조체</span><span class="sxs-lookup"><span data-stu-id="eadc2-117">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)
- [<span data-ttu-id="eadc2-118">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="eadc2-118">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
