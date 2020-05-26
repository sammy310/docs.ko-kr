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
ms.openlocfilehash: 4a7a2da58e197749d492f24c7a12134508efef57
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805227"
---
# <a name="igchostgetthreadstats-method"></a><span data-ttu-id="6f1db-102">IGCHost::GetThreadStats 메서드</span><span class="sxs-lookup"><span data-stu-id="6f1db-102">IGCHost::GetThreadStats Method</span></span>
<span data-ttu-id="6f1db-103">가비지 수집에 대 한 스레드별 통계를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6f1db-103">Gets the per-thread statistics for garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f1db-104">구문</span><span class="sxs-lookup"><span data-stu-id="6f1db-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadStats (  
    [in] DWORD *pFiberCookie,  
    [in, out] COR_GC_THREAD_STATS *pStats  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6f1db-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6f1db-105">Parameters</span></span>  
 `pFiberCookie`  
 <span data-ttu-id="6f1db-106">진행 통계를 검색할 스레드를 지정 하는 파이버 쿠키에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6f1db-106">[in] A pointer to a fiber cookie that specifies the thread for which to retrieve the statistics.</span></span>  
  
 `pStats`  
 <span data-ttu-id="6f1db-107">[in, out] 지정 된 스레드에 대 한 가비지 수집 통계를 포함 하는 [COR_GC_THREAD_STATS](cor-gc-thread-stats-structure.md) 구조체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6f1db-107">[in, out] A pointer to a [COR_GC_THREAD_STATS](cor-gc-thread-stats-structure.md) structure that contains the garbage collection statistics for the specified thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f1db-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6f1db-108">Requirements</span></span>  
 <span data-ttu-id="6f1db-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6f1db-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f1db-110">**헤더:** GCHost, GCHost</span><span class="sxs-lookup"><span data-stu-id="6f1db-110">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="6f1db-111">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f1db-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6f1db-112">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f1db-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f1db-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6f1db-113">See also</span></span>

- [<span data-ttu-id="6f1db-114">IGCHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6f1db-114">IGCHost Interface</span></span>](igchost-interface.md)
