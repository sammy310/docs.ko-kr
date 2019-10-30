---
title: IGCHost::GetThreadStats 메서드
ms.date: 03/30/2017
api_name:
- IGCHost.GetThreadStats
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetThreadStats
helpviewer_keywords:
- IGCHost::GetThreadStats method [.NET Framework hosting]
- GetThreadStats method [.NET Framework hosting]
ms.assetid: 826baa9b-9218-4736-a509-7ab193b125a0
topic_type:
- apiref
ms.openlocfilehash: 36eeb7ed4f80979ef2edb930e65963a1db0c894f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134899"
---
# <a name="igchostgetthreadstats-method"></a><span data-ttu-id="c972a-102">IGCHost::GetThreadStats 메서드</span><span class="sxs-lookup"><span data-stu-id="c972a-102">IGCHost::GetThreadStats Method</span></span>
<span data-ttu-id="c972a-103">가비지 수집에 대 한 스레드별 통계를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c972a-103">Gets the per-thread statistics for garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c972a-104">구문</span><span class="sxs-lookup"><span data-stu-id="c972a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadStats (  
    [in] DWORD *pFiberCookie,  
    [in, out] COR_GC_THREAD_STATS *pStats  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c972a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c972a-105">Parameters</span></span>  
 `pFiberCookie`  
 <span data-ttu-id="c972a-106">진행 통계를 검색할 스레드를 지정 하는 파이버 쿠키에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c972a-106">[in] A pointer to a fiber cookie that specifies the thread for which to retrieve the statistics.</span></span>  
  
 `pStats`  
 <span data-ttu-id="c972a-107">[in, out] 지정 된 스레드에 대 한 가비지 수집 통계를 포함 하는 [COR_GC_THREAD_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md) 구조체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c972a-107">[in, out] A pointer to a [COR_GC_THREAD_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md) structure that contains the garbage collection statistics for the specified thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c972a-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c972a-108">Requirements</span></span>  
 <span data-ttu-id="c972a-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c972a-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c972a-110">**헤더:** GCHost, GCHost</span><span class="sxs-lookup"><span data-stu-id="c972a-110">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="c972a-111">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c972a-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c972a-112">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c972a-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c972a-113">참조</span><span class="sxs-lookup"><span data-stu-id="c972a-113">See also</span></span>

- [<span data-ttu-id="c972a-114">IGCHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c972a-114">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
