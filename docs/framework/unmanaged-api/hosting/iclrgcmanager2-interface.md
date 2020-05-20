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
ms.openlocfilehash: 0f3ecc0d497eaee937647df47ba0956335a2fe41
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703950"
---
# <a name="iclrgcmanager2-interface"></a><span data-ttu-id="72674-102">ICLRGCManager2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="72674-102">ICLRGCManager2 Interface</span></span>
<span data-ttu-id="72674-103">호스트가 공용 언어 런타임의 가비지 수집 시스템과 상호 작용할 수 있도록 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="72674-103">Provides methods that allow a host to interact with the common language runtime's garbage collection system.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="72674-104">메서드</span><span class="sxs-lookup"><span data-stu-id="72674-104">Methods</span></span>  
  
|<span data-ttu-id="72674-105">메서드</span><span class="sxs-lookup"><span data-stu-id="72674-105">Method</span></span>|<span data-ttu-id="72674-106">설명</span><span class="sxs-lookup"><span data-stu-id="72674-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="72674-107">SetGCStartupLimitsEx 메서드</span><span class="sxs-lookup"><span data-stu-id="72674-107">SetGCStartupLimitsEx Method</span></span>](iclrgcmanager2-setgcstartuplimitsex-method.md)|<span data-ttu-id="72674-108">가비지 수집 세그먼트의 크기와 가비지 수집 시스템의 최대 0 세대 크기를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="72674-108">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span> <span data-ttu-id="72674-109">0 세대 및 세그먼트 크기를 보다 크게 설정 `DWORD` 합니다.</span><span class="sxs-lookup"><span data-stu-id="72674-109">Enables generation 0 and segment sizes larger than `DWORD`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="72674-110">설명</span><span class="sxs-lookup"><span data-stu-id="72674-110">Remarks</span></span>  
 <span data-ttu-id="72674-111">이 인터페이스는 [ICLRGCManager 인터페이스](iclrgcmanager-interface.md)에서 상속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="72674-111">This interface inherits from the [ICLRGCManager Interface](iclrgcmanager-interface.md).</span></span>  
  
 <span data-ttu-id="72674-112">CLR (공용 언어 런타임)은 관리 되는 형식을 사용 하 여 가비지 수집 메커니즘을 구현 합니다 <xref:System.GC> .</span><span class="sxs-lookup"><span data-stu-id="72674-112">The common language runtime (CLR) implements its garbage collection mechanism with the managed <xref:System.GC> type.</span></span> <span data-ttu-id="72674-113">가비지 수집 시스템에 대 한 자세한 내용은 [가비지 수집](../../../standard/garbage-collection/index.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="72674-113">For more information about the garbage collection system, see [Garbage Collection](../../../standard/garbage-collection/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72674-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="72674-114">Requirements</span></span>  
 <span data-ttu-id="72674-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="72674-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72674-116">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="72674-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="72674-117">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="72674-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="72674-118">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72674-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72674-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="72674-119">See also</span></span>

- [<span data-ttu-id="72674-120">자동 메모리 관리</span><span class="sxs-lookup"><span data-stu-id="72674-120">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="72674-121">COR_GC_STATS 구조체</span><span class="sxs-lookup"><span data-stu-id="72674-121">COR_GC_STATS Structure</span></span>](cor-gc-stats-structure.md)
- [<span data-ttu-id="72674-122">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="72674-122">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="72674-123">.NET Framework 4 및 4.5에 추가된 CLR 호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="72674-123">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [<span data-ttu-id="72674-124">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="72674-124">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="72674-125">호스팅</span><span class="sxs-lookup"><span data-stu-id="72674-125">Hosting</span></span>](index.md)
