---
description: '자세히 알아보기: ICLRGCManager2 인터페이스'
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
ms.openlocfilehash: 455b3a99d10fa43bf325e9f7075d255dd55ae38b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789959"
---
# <a name="iclrgcmanager2-interface"></a><span data-ttu-id="36301-103">ICLRGCManager2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="36301-103">ICLRGCManager2 Interface</span></span>

<span data-ttu-id="36301-104">호스트가 공용 언어 런타임의 가비지 수집 시스템과 상호 작용할 수 있도록 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="36301-104">Provides methods that allow a host to interact with the common language runtime's garbage collection system.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="36301-105">메서드</span><span class="sxs-lookup"><span data-stu-id="36301-105">Methods</span></span>  
  
|<span data-ttu-id="36301-106">메서드</span><span class="sxs-lookup"><span data-stu-id="36301-106">Method</span></span>|<span data-ttu-id="36301-107">설명</span><span class="sxs-lookup"><span data-stu-id="36301-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="36301-108">SetGCStartupLimitsEx 메서드</span><span class="sxs-lookup"><span data-stu-id="36301-108">SetGCStartupLimitsEx Method</span></span>](iclrgcmanager2-setgcstartuplimitsex-method.md)|<span data-ttu-id="36301-109">가비지 수집 세그먼트의 크기와 가비지 수집 시스템의 최대 0 세대 크기를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="36301-109">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span> <span data-ttu-id="36301-110">0 세대 및 세그먼트 크기를 보다 크게 설정 `DWORD` 합니다.</span><span class="sxs-lookup"><span data-stu-id="36301-110">Enables generation 0 and segment sizes larger than `DWORD`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="36301-111">설명</span><span class="sxs-lookup"><span data-stu-id="36301-111">Remarks</span></span>  

 <span data-ttu-id="36301-112">이 인터페이스는 [ICLRGCManager 인터페이스](iclrgcmanager-interface.md)에서 상속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="36301-112">This interface inherits from the [ICLRGCManager Interface](iclrgcmanager-interface.md).</span></span>  
  
 <span data-ttu-id="36301-113">CLR (공용 언어 런타임)은 관리 되는 형식을 사용 하 여 가비지 수집 메커니즘을 구현 합니다 <xref:System.GC> .</span><span class="sxs-lookup"><span data-stu-id="36301-113">The common language runtime (CLR) implements its garbage collection mechanism with the managed <xref:System.GC> type.</span></span> <span data-ttu-id="36301-114">가비지 수집 시스템에 대 한 자세한 내용은 [가비지 수집](../../../standard/garbage-collection/index.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="36301-114">For more information about the garbage collection system, see [Garbage Collection](../../../standard/garbage-collection/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36301-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="36301-115">Requirements</span></span>  

 <span data-ttu-id="36301-116">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="36301-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36301-117">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="36301-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="36301-118">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="36301-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="36301-119">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36301-119">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36301-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="36301-120">See also</span></span>

- [<span data-ttu-id="36301-121">자동 메모리 관리</span><span class="sxs-lookup"><span data-stu-id="36301-121">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="36301-122">COR_GC_STATS 구조체</span><span class="sxs-lookup"><span data-stu-id="36301-122">COR_GC_STATS Structure</span></span>](cor-gc-stats-structure.md)
- [<span data-ttu-id="36301-123">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="36301-123">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="36301-124">.NET Framework 4 및 4.5에 추가된 CLR 호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="36301-124">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [<span data-ttu-id="36301-125">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="36301-125">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="36301-126">호스팅</span><span class="sxs-lookup"><span data-stu-id="36301-126">Hosting</span></span>](index.md)
