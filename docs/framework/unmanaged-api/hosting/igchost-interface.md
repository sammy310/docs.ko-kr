---
title: IGCHost 인터페이스
ms.date: 03/30/2017
api_name:
- IGCHost
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IGCHost
helpviewer_keywords:
- IGCHost interface [.NET Framework hosting]
ms.assetid: 9ad70ffd-6963-4ab2-8c84-3d86c3fb8deb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3202aa25261863dae953e3edac36f3406fa001d8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61699753"
---
# <a name="igchost-interface"></a><span data-ttu-id="8b831-102">IGCHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8b831-102">IGCHost Interface</span></span>
<span data-ttu-id="8b831-103">가비지 컬렉션 시스템에 대 한 정보를 얻기 위한 고 가비지 컬렉션의 일부 측면을 제어 하기 위한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b831-103">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8b831-104">부터 [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)]를 사용할 수는 [IGCHost2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) 가비지 수집 세그먼트의 크기 및 가비지 컬렉션 시스템의 0 세대의 최대 크기 값 보다 큰으로 설정 하는 방법의 `DWORD` 에 의해 적용 되는 제한 된 [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/igchost-setgcstartuplimits-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="8b831-104">Starting with the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], you can use the [IGCHost2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) method to set the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0 to values greater than the `DWORD` limit that is imposed by the [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/igchost-setgcstartuplimits-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8b831-105">이 인터페이스는 전문가 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="8b831-105">This interface is for expert usage only.</span></span> <span data-ttu-id="8b831-106">부적절 하 게 사용 하는 경우에 응용 프로그램의 성능 영향을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b831-106">It can affect the performance of an application if used improperly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8b831-107">메서드</span><span class="sxs-lookup"><span data-stu-id="8b831-107">Methods</span></span>  
  
|<span data-ttu-id="8b831-108">메서드</span><span class="sxs-lookup"><span data-stu-id="8b831-108">Method</span></span>|<span data-ttu-id="8b831-109">설명</span><span class="sxs-lookup"><span data-stu-id="8b831-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8b831-110">Collect 메서드</span><span class="sxs-lookup"><span data-stu-id="8b831-110">Collect Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-collect-method.md)|<span data-ttu-id="8b831-111">현재 가비지 컬렉션의 상태에 관계 없이 지정된 된 세대에 발생 하는 수집을 강제로 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b831-111">Forces a collection to occur for the given generation, regardless of the state of the current garbage collection.</span></span>|  
|[<span data-ttu-id="8b831-112">GetStats 메서드</span><span class="sxs-lookup"><span data-stu-id="8b831-112">GetStats Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-getstats-method.md)|<span data-ttu-id="8b831-113">가비지 컬렉션 시스템의 현재 상태에 대 한 통계를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8b831-113">Gets the statistics for the current state of the garbage collection system.</span></span>|  
|[<span data-ttu-id="8b831-114">GetThreadStats 메서드</span><span class="sxs-lookup"><span data-stu-id="8b831-114">GetThreadStats Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-getthreadstats-method.md)|<span data-ttu-id="8b831-115">가비지 컬렉션에 대 한 스레드당 통계를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8b831-115">Gets the per-thread statistics for garbage collection.</span></span>|  
|[<span data-ttu-id="8b831-116">SetGCStartupLimits 메서드</span><span class="sxs-lookup"><span data-stu-id="8b831-116">SetGCStartupLimits Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-setgcstartuplimits-method.md)|<span data-ttu-id="8b831-117">0 세대에 대 한 세그먼트 크기 및 최대 크기를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8b831-117">Sets the segment size and the maximum size for generation 0.</span></span>|  
|[<span data-ttu-id="8b831-118">SetVirtualMemLimit 메서드</span><span class="sxs-lookup"><span data-stu-id="8b831-118">SetVirtualMemLimit Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-setvirtualmemlimit-method.md)|<span data-ttu-id="8b831-119">런타임의 가상 메모리의 최대 크기를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8b831-119">Sets the maximum size of the runtime's virtual memory.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8b831-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8b831-120">Requirements</span></span>  
 <span data-ttu-id="8b831-121">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="8b831-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b831-122">**헤더:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="8b831-122">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="8b831-123">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="8b831-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8b831-124">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b831-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b831-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="8b831-125">See also</span></span>

- [<span data-ttu-id="8b831-126">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8b831-126">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="8b831-127">CorRuntimeHost Coclass</span><span class="sxs-lookup"><span data-stu-id="8b831-127">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
