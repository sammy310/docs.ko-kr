---
description: '자세히 알아보기: ICLRGCManager 인터페이스'
title: ICLRGCManager 인터페이스
ms.date: 03/30/2017
api_name:
- ICLRGCManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager
helpviewer_keywords:
- ICLRGCManager interface [.NET Framework hosting]
ms.assetid: fb511c9b-3fe4-41b0-822a-6ba4a079d1f5
topic_type:
- apiref
ms.openlocfilehash: 648b2b131e28da8aabc7028b6d745351cae772fe
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789998"
---
# <a name="iclrgcmanager-interface"></a><span data-ttu-id="0648f-103">ICLRGCManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0648f-103">ICLRGCManager Interface</span></span>

<span data-ttu-id="0648f-104">호스트가 공용 언어 런타임의 가비지 수집 시스템과 상호 작용할 수 있도록 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0648f-104">Provides methods that allow a host to interact with the common language runtime's garbage collection system.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0648f-105">4.5 .NET Framework부터 [ICLRGCManager2:: SetGCStartupLimitsEx](iclrgcmanager2-setgcstartuplimitsex-method.md) 메서드를 사용 하 여 가비지 수집 세그먼트의 크기와 가비지 수집 시스템의 최대 크기를 `DWORD` [SetGCStartupLimits](iclrgcmanager-setgcstartuplimits-method.md) 메서드에서 적용 되는 제한 보다 큰 값으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0648f-105">Starting with the .NET Framework 4.5, you can use the [ICLRGCManager2::SetGCStartupLimitsEx](iclrgcmanager2-setgcstartuplimitsex-method.md) method to set the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0 to values greater than the `DWORD` limit that is imposed by the [SetGCStartupLimits](iclrgcmanager-setgcstartuplimits-method.md) method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0648f-106">메서드</span><span class="sxs-lookup"><span data-stu-id="0648f-106">Methods</span></span>  
  
|<span data-ttu-id="0648f-107">메서드</span><span class="sxs-lookup"><span data-stu-id="0648f-107">Method</span></span>|<span data-ttu-id="0648f-108">설명</span><span class="sxs-lookup"><span data-stu-id="0648f-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0648f-109">Collect 메서드</span><span class="sxs-lookup"><span data-stu-id="0648f-109">Collect Method</span></span>](iclrgcmanager-collect-method.md)|<span data-ttu-id="0648f-110">지정 된 세대에 대 한 가비지 수집을 강제로 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="0648f-110">Forces a garbage collection for the specified generation.</span></span>|  
|[<span data-ttu-id="0648f-111">GetStats 메서드</span><span class="sxs-lookup"><span data-stu-id="0648f-111">GetStats Method</span></span>](iclrgcmanager-getstats-method.md)|<span data-ttu-id="0648f-112">가비지 컬렉션 시스템에 대 한 현재 통계 집합을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0648f-112">Gets a set of current statistics about the garbage collection system.</span></span>|  
|[<span data-ttu-id="0648f-113">SetGCStartupLimits 메서드</span><span class="sxs-lookup"><span data-stu-id="0648f-113">SetGCStartupLimits Method</span></span>](iclrgcmanager-setgcstartuplimits-method.md)|<span data-ttu-id="0648f-114">가비지 수집 세그먼트의 크기와 가비지 수집 시스템의 최대 0 세대 크기를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0648f-114">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0648f-115">설명</span><span class="sxs-lookup"><span data-stu-id="0648f-115">Remarks</span></span>  

 <span data-ttu-id="0648f-116">CLR (공용 언어 런타임)은 관리 되는 형식을 사용 하 여 가비지 수집 메커니즘을 구현 합니다 <xref:System.GC> .</span><span class="sxs-lookup"><span data-stu-id="0648f-116">The common language runtime (CLR) implements its garbage collection mechanism with the managed <xref:System.GC> type.</span></span> <span data-ttu-id="0648f-117">가비지 수집 시스템에 대 한 자세한 내용은 [가비지 수집](../../../standard/garbage-collection/index.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0648f-117">For more information about the garbage collection system, see [Garbage Collection](../../../standard/garbage-collection/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0648f-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0648f-118">Requirements</span></span>  

 <span data-ttu-id="0648f-119">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0648f-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0648f-120">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="0648f-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0648f-121">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0648f-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0648f-122">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0648f-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0648f-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0648f-123">See also</span></span>

- [<span data-ttu-id="0648f-124">자동 메모리 관리</span><span class="sxs-lookup"><span data-stu-id="0648f-124">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="0648f-125">COR_GC_STATS 구조체</span><span class="sxs-lookup"><span data-stu-id="0648f-125">COR_GC_STATS Structure</span></span>](cor-gc-stats-structure.md)
- [<span data-ttu-id="0648f-126">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0648f-126">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="0648f-127">CLR 호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0648f-127">CLR Hosting Interfaces</span></span>](clr-hosting-interfaces.md)
- [<span data-ttu-id="0648f-128">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0648f-128">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="0648f-129">호스팅</span><span class="sxs-lookup"><span data-stu-id="0648f-129">Hosting</span></span>](index.md)
