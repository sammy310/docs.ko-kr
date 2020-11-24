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
ms.openlocfilehash: c48b580e632d67db5a9826c210415adab1bdba96
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95670071"
---
# <a name="igchostgetthreadstats-method"></a><span data-ttu-id="2ffe3-102">IGCHost::GetThreadStats 메서드</span><span class="sxs-lookup"><span data-stu-id="2ffe3-102">IGCHost::GetThreadStats Method</span></span>

<span data-ttu-id="2ffe3-103">가비지 수집에 대 한 스레드별 통계를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2ffe3-103">Gets the per-thread statistics for garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ffe3-104">구문</span><span class="sxs-lookup"><span data-stu-id="2ffe3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadStats (  
    [in] DWORD *pFiberCookie,  
    [in, out] COR_GC_THREAD_STATS *pStats  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2ffe3-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2ffe3-105">Parameters</span></span>  

 `pFiberCookie`  
 <span data-ttu-id="2ffe3-106">진행 통계를 검색할 스레드를 지정 하는 파이버 쿠키에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="2ffe3-106">[in] A pointer to a fiber cookie that specifies the thread for which to retrieve the statistics.</span></span>  
  
 `pStats`  
 <span data-ttu-id="2ffe3-107">[in, out] 지정 된 스레드에 대 한 가비지 수집 통계를 포함 하는 [COR_GC_THREAD_STATS](cor-gc-thread-stats-structure.md) 구조체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="2ffe3-107">[in, out] A pointer to a [COR_GC_THREAD_STATS](cor-gc-thread-stats-structure.md) structure that contains the garbage collection statistics for the specified thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ffe3-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2ffe3-108">Requirements</span></span>  

 <span data-ttu-id="2ffe3-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2ffe3-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ffe3-110">**헤더:** GCHost, GCHost</span><span class="sxs-lookup"><span data-stu-id="2ffe3-110">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="2ffe3-111">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ffe3-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2ffe3-112">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ffe3-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ffe3-113">참조</span><span class="sxs-lookup"><span data-stu-id="2ffe3-113">See also</span></span>

- [<span data-ttu-id="2ffe3-114">IGCHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2ffe3-114">IGCHost Interface</span></span>](igchost-interface.md)
