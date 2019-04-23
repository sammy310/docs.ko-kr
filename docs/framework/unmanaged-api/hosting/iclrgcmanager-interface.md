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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b9519f7c2df5cf078bac6be038275527d7741edb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59152167"
---
# <a name="iclrgcmanager-interface"></a><span data-ttu-id="9cb86-102">ICLRGCManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9cb86-102">ICLRGCManager Interface</span></span>
<span data-ttu-id="9cb86-103">공용 언어 런타임의 가비지 컬렉션 시스템과 상호 작용 하는 데 사용 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cb86-103">Provides methods that allow a host to interact with the common language runtime's garbage collection system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9cb86-104">부터 합니다 [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)]를 사용할 수는 [ICLRGCManager2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) 가비지 수집 세그먼트의 크기 및 가비지 컬렉션 시스템의 0 세대의 최대 크기 값에 큰 설정 하는 방법 보다는 `DWORD` 에 의해 적용 되는 제한 된 [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-setgcstartuplimits-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="9cb86-104">Starting with the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], you can use the [ICLRGCManager2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) method to set the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0 to values greater than the `DWORD` limit that is imposed by the [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-setgcstartuplimits-method.md) method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9cb86-105">메서드</span><span class="sxs-lookup"><span data-stu-id="9cb86-105">Methods</span></span>  
  
|<span data-ttu-id="9cb86-106">메서드</span><span class="sxs-lookup"><span data-stu-id="9cb86-106">Method</span></span>|<span data-ttu-id="9cb86-107">설명</span><span class="sxs-lookup"><span data-stu-id="9cb86-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9cb86-108">Collect 메서드</span><span class="sxs-lookup"><span data-stu-id="9cb86-108">Collect Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-collect-method.md)|<span data-ttu-id="9cb86-109">지정된 된 세대의 가비지 수집을 강제로 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cb86-109">Forces a garbage collection for the specified generation.</span></span>|  
|[<span data-ttu-id="9cb86-110">GetStats 메서드</span><span class="sxs-lookup"><span data-stu-id="9cb86-110">GetStats Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md)|<span data-ttu-id="9cb86-111">가비지 컬렉션 시스템에 대 한 현재 통계의 집합을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9cb86-111">Gets a set of current statistics about the garbage collection system.</span></span>|  
|[<span data-ttu-id="9cb86-112">SetGCStartupLimits 메서드</span><span class="sxs-lookup"><span data-stu-id="9cb86-112">SetGCStartupLimits Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-setgcstartuplimits-method.md)|<span data-ttu-id="9cb86-113">가비지 수집 세그먼트의 크기 및 가비지 컬렉션 시스템의 0 세대의 최대 크기를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9cb86-113">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9cb86-114">설명</span><span class="sxs-lookup"><span data-stu-id="9cb86-114">Remarks</span></span>  
 <span data-ttu-id="9cb86-115">관리 되는 가비지 수집 메커니즘을 구현 하는 CLR (공용 언어 런타임) <xref:System.GC> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="9cb86-115">The common language runtime (CLR) implements its garbage collection mechanism with the managed <xref:System.GC> type.</span></span> <span data-ttu-id="9cb86-116">가비지 컬렉션 시스템에 대 한 자세한 내용은 참조 하세요. [가비지 수집](../../../../docs/standard/garbage-collection/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9cb86-116">For more information about the garbage collection system, see [Garbage Collection](../../../../docs/standard/garbage-collection/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9cb86-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9cb86-117">Requirements</span></span>  
 <span data-ttu-id="9cb86-118">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9cb86-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9cb86-119">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9cb86-119">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9cb86-120">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="9cb86-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9cb86-121">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9cb86-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cb86-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="9cb86-122">See also</span></span>

- [<span data-ttu-id="9cb86-123">자동 메모리 관리</span><span class="sxs-lookup"><span data-stu-id="9cb86-123">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)
- [<span data-ttu-id="9cb86-124">COR_GC_STATS 구조체</span><span class="sxs-lookup"><span data-stu-id="9cb86-124">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)
- [<span data-ttu-id="9cb86-125">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9cb86-125">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="9cb86-126">CLR 호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9cb86-126">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)
- [<span data-ttu-id="9cb86-127">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9cb86-127">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="9cb86-128">호스팅</span><span class="sxs-lookup"><span data-stu-id="9cb86-128">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
