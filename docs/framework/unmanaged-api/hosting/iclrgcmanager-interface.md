---
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
ms.openlocfilehash: dbe3df6bb20e5ad8f9eb534a366405eb9c33984f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95678248"
---
# <a name="iclrgcmanager-interface"></a><span data-ttu-id="555bb-102">ICLRGCManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="555bb-102">ICLRGCManager Interface</span></span>

<span data-ttu-id="555bb-103">호스트가 공용 언어 런타임의 가비지 수집 시스템과 상호 작용할 수 있도록 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="555bb-103">Provides methods that allow a host to interact with the common language runtime's garbage collection system.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="555bb-104">4.5 .NET Framework부터 [ICLRGCManager2:: SetGCStartupLimitsEx](iclrgcmanager2-setgcstartuplimitsex-method.md) 메서드를 사용 하 여 가비지 수집 세그먼트의 크기와 가비지 수집 시스템의 최대 크기를 `DWORD` [SetGCStartupLimits](iclrgcmanager-setgcstartuplimits-method.md) 메서드에서 적용 되는 제한 보다 큰 값으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="555bb-104">Starting with the .NET Framework 4.5, you can use the [ICLRGCManager2::SetGCStartupLimitsEx](iclrgcmanager2-setgcstartuplimitsex-method.md) method to set the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0 to values greater than the `DWORD` limit that is imposed by the [SetGCStartupLimits](iclrgcmanager-setgcstartuplimits-method.md) method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="555bb-105">메서드</span><span class="sxs-lookup"><span data-stu-id="555bb-105">Methods</span></span>  
  
|<span data-ttu-id="555bb-106">메서드</span><span class="sxs-lookup"><span data-stu-id="555bb-106">Method</span></span>|<span data-ttu-id="555bb-107">설명</span><span class="sxs-lookup"><span data-stu-id="555bb-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="555bb-108">Collect 메서드</span><span class="sxs-lookup"><span data-stu-id="555bb-108">Collect Method</span></span>](iclrgcmanager-collect-method.md)|<span data-ttu-id="555bb-109">지정 된 세대에 대 한 가비지 수집을 강제로 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="555bb-109">Forces a garbage collection for the specified generation.</span></span>|  
|[<span data-ttu-id="555bb-110">GetStats 메서드</span><span class="sxs-lookup"><span data-stu-id="555bb-110">GetStats Method</span></span>](iclrgcmanager-getstats-method.md)|<span data-ttu-id="555bb-111">가비지 컬렉션 시스템에 대 한 현재 통계 집합을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="555bb-111">Gets a set of current statistics about the garbage collection system.</span></span>|  
|[<span data-ttu-id="555bb-112">SetGCStartupLimits 메서드</span><span class="sxs-lookup"><span data-stu-id="555bb-112">SetGCStartupLimits Method</span></span>](iclrgcmanager-setgcstartuplimits-method.md)|<span data-ttu-id="555bb-113">가비지 수집 세그먼트의 크기와 가비지 수집 시스템의 최대 0 세대 크기를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="555bb-113">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="555bb-114">설명</span><span class="sxs-lookup"><span data-stu-id="555bb-114">Remarks</span></span>  

 <span data-ttu-id="555bb-115">CLR (공용 언어 런타임)은 관리 되는 형식을 사용 하 여 가비지 수집 메커니즘을 구현 합니다 <xref:System.GC> .</span><span class="sxs-lookup"><span data-stu-id="555bb-115">The common language runtime (CLR) implements its garbage collection mechanism with the managed <xref:System.GC> type.</span></span> <span data-ttu-id="555bb-116">가비지 수집 시스템에 대 한 자세한 내용은 [가비지 수집](../../../standard/garbage-collection/index.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="555bb-116">For more information about the garbage collection system, see [Garbage Collection](../../../standard/garbage-collection/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="555bb-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="555bb-117">Requirements</span></span>  

 <span data-ttu-id="555bb-118">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="555bb-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="555bb-119">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="555bb-119">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="555bb-120">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="555bb-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="555bb-121">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="555bb-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="555bb-122">참조</span><span class="sxs-lookup"><span data-stu-id="555bb-122">See also</span></span>

- [<span data-ttu-id="555bb-123">자동 메모리 관리</span><span class="sxs-lookup"><span data-stu-id="555bb-123">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="555bb-124">COR_GC_STATS 구조체</span><span class="sxs-lookup"><span data-stu-id="555bb-124">COR_GC_STATS Structure</span></span>](cor-gc-stats-structure.md)
- [<span data-ttu-id="555bb-125">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="555bb-125">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="555bb-126">CLR 호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="555bb-126">CLR Hosting Interfaces</span></span>](clr-hosting-interfaces.md)
- [<span data-ttu-id="555bb-127">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="555bb-127">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="555bb-128">호스팅</span><span class="sxs-lookup"><span data-stu-id="555bb-128">Hosting</span></span>](index.md)
