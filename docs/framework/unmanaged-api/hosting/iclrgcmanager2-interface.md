---
title: ICLRGCManager2 인터페이스
ms.date: 03/30/2017
api_name:
- ICLRGCManager2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager2
helpviewer_keywords:
- ICLRGCManager2 interface [.NET Framework hosting]
ms.assetid: 4b5ffd7b-9ad7-41cd-9bba-34030ae3da7e
topic_type:
- apiref
ms.openlocfilehash: 72ffd7b47795ee8e46f8fbff07559133843793e6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141151"
---
# <a name="iclrgcmanager2-interface"></a><span data-ttu-id="b7deb-102">ICLRGCManager2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b7deb-102">ICLRGCManager2 Interface</span></span>
<span data-ttu-id="b7deb-103">호스트가 공용 언어 런타임의 가비지 수집 시스템과 상호 작용할 수 있도록 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7deb-103">Provides methods that allow a host to interact with the common language runtime's garbage collection system.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b7deb-104">메서드</span><span class="sxs-lookup"><span data-stu-id="b7deb-104">Methods</span></span>  
  
|<span data-ttu-id="b7deb-105">메서드</span><span class="sxs-lookup"><span data-stu-id="b7deb-105">Method</span></span>|<span data-ttu-id="b7deb-106">설명</span><span class="sxs-lookup"><span data-stu-id="b7deb-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b7deb-107">SetGCStartupLimitsEx 메서드</span><span class="sxs-lookup"><span data-stu-id="b7deb-107">SetGCStartupLimitsEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md)|<span data-ttu-id="b7deb-108">가비지 수집 세그먼트의 크기와 가비지 수집 시스템의 최대 0 세대 크기를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7deb-108">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span> <span data-ttu-id="b7deb-109">0 세대 및 세그먼트 크기를 `DWORD`보다 크게 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7deb-109">Enables generation 0 and segment sizes larger than `DWORD`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b7deb-110">주의</span><span class="sxs-lookup"><span data-stu-id="b7deb-110">Remarks</span></span>  
 <span data-ttu-id="b7deb-111">이 인터페이스는 [ICLRGCManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)에서 상속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7deb-111">This interface inherits from the [ICLRGCManager Interface](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md).</span></span>  
  
 <span data-ttu-id="b7deb-112">CLR (공용 언어 런타임)은 관리 되는 <xref:System.GC> 형식으로 가비지 수집 메커니즘을 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7deb-112">The common language runtime (CLR) implements its garbage collection mechanism with the managed <xref:System.GC> type.</span></span> <span data-ttu-id="b7deb-113">가비지 수집 시스템에 대 한 자세한 내용은 [가비지 수집](../../../standard/garbage-collection/index.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b7deb-113">For more information about the garbage collection system, see [Garbage Collection](../../../standard/garbage-collection/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7deb-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b7deb-114">Requirements</span></span>  
 <span data-ttu-id="b7deb-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b7deb-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7deb-116">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="b7deb-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b7deb-117">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7deb-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b7deb-118">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7deb-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7deb-119">참조</span><span class="sxs-lookup"><span data-stu-id="b7deb-119">See also</span></span>

- [<span data-ttu-id="b7deb-120">자동 메모리 관리</span><span class="sxs-lookup"><span data-stu-id="b7deb-120">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="b7deb-121">COR_GC_STATS 구조체</span><span class="sxs-lookup"><span data-stu-id="b7deb-121">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)
- [<span data-ttu-id="b7deb-122">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b7deb-122">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="b7deb-123">.NET Framework 4 및 4.5에 추가된 CLR 호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b7deb-123">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [<span data-ttu-id="b7deb-124">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b7deb-124">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="b7deb-125">호스팅</span><span class="sxs-lookup"><span data-stu-id="b7deb-125">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
