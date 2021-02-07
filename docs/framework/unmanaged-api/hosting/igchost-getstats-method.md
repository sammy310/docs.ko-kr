---
description: '자세히 알아보기: IGCHost:: GetStats 메서드'
title: IGCHost::GetStats 메서드
ms.date: 03/30/2017
api_name:
- IGCHost.GetStats
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetStats
helpviewer_keywords:
- GetStats method, IGCHost interface [.NET Framework hosting]
- IGCHost::GetStats method [.NET Framework hosting]
ms.assetid: c4ae022c-46ac-4f19-9ddd-09b955f19412
topic_type:
- apiref
ms.openlocfilehash: 564224d01e23c8ac1fe81025ee87dabc41ed5166
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99709694"
---
# <a name="igchostgetstats-method"></a><span data-ttu-id="f85e2-103">IGCHost::GetStats 메서드</span><span class="sxs-lookup"><span data-stu-id="f85e2-103">IGCHost::GetStats Method</span></span>

<span data-ttu-id="f85e2-104">가비지 수집 시스템의 현재 상태에 대 한 통계를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f85e2-104">Gets the statistics for the current state of the garbage collection system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f85e2-105">구문</span><span class="sxs-lookup"><span data-stu-id="f85e2-105">Syntax</span></span>  
  
```cpp  
HRESULT GetStats (  
    [in, out] COR_GC_STATS *pStats  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f85e2-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f85e2-106">Parameters</span></span>  

 `pStats`  
 <span data-ttu-id="f85e2-107">[in, out] 가비지 수집 시스템의 현재 상태에 대 한 통계를 포함 하는 [COR_GC_STATS](cor-gc-stats-structure.md) 구조체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f85e2-107">[in, out] A pointer to a [COR_GC_STATS](cor-gc-stats-structure.md) structure that contains the statistics for the current state of the garbage collection system.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f85e2-108">설명</span><span class="sxs-lookup"><span data-stu-id="f85e2-108">Remarks</span></span>  

 <span data-ttu-id="f85e2-109">통계는 가비지 수집 시스템이 작동 하는 데 도움이 되는 스마트 할당 시스템에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f85e2-109">The statistics can be used by a smart allocation system to help the garbage collection system operate.</span></span> <span data-ttu-id="f85e2-110">예를 들어 할당 시스템에서 통계를 검토 한 후 메모리를 더 추가 하거나 컬렉션을 강제 적용 해야 하는지 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f85e2-110">For example, the allocation system may determine, after reviewing the statistics, that it needs to add more memory or force a collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f85e2-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f85e2-111">Requirements</span></span>  

 <span data-ttu-id="f85e2-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f85e2-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f85e2-113">**헤더:** GCHost, GCHost</span><span class="sxs-lookup"><span data-stu-id="f85e2-113">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="f85e2-114">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f85e2-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f85e2-115">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f85e2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f85e2-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f85e2-116">See also</span></span>

- [<span data-ttu-id="f85e2-117">IGCHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f85e2-117">IGCHost Interface</span></span>](igchost-interface.md)
