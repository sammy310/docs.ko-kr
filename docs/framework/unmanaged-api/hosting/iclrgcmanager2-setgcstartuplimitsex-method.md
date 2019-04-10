---
title: ICLRGCManager2::SetGCStartupLimitsEx 메서드
ms.date: 03/30/2017
api_name:
- ICLRGCManager2.SetGCStartupLimitsEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager2::SetCLRGCStartupLimitsEx
helpviewer_keywords:
- ICLRGCManager2::SetGCStartupLimitsEx method [.NET Framework hosting]
- SetGCStartupLimitsEx method, ICLRGCManager2 interface [.NET Framework hosting]
ms.assetid: 6c3a08a9-5d65-48d4-8bbf-2a86ed7d356a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6cba7b4a34835eb2f394aa71be8b907973cb1cd6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59204720"
---
# <a name="iclrgcmanager2setgcstartuplimitsex-method"></a><span data-ttu-id="39be7-102">ICLRGCManager2::SetGCStartupLimitsEx 메서드</span><span class="sxs-lookup"><span data-stu-id="39be7-102">ICLRGCManager2::SetGCStartupLimitsEx Method</span></span>
<span data-ttu-id="39be7-103">가비지 수집 세그먼트의 크기 및 가비지 컬렉션 시스템의 0 세대의 최대 크기를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="39be7-103">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39be7-104">구문</span><span class="sxs-lookup"><span data-stu-id="39be7-104">Syntax</span></span>  
  
```  
HRESULT SetGCStartupLimitsEx (  
    [in] SIZE_T SegmentSize,   
    [in] SIZE_T MaxGen0Size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="39be7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="39be7-105">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="39be7-106">[in] 가비지 수집 세그먼트의 지정 된 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="39be7-106">[in] The specified size of a garbage collection segment.</span></span>  
  
 <span data-ttu-id="39be7-107">최소 세그먼트 크기는 4MB입니다.</span><span class="sxs-lookup"><span data-stu-id="39be7-107">The minimum segment size is 4 MB.</span></span> <span data-ttu-id="39be7-108">1MB 단위로 증가 하거나 더 큰 세그먼트 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39be7-108">Segments can be increased in increments of 1 MB or larger.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="39be7-109">[in] 0 세대에 대 한 지정 된 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="39be7-109">[in] The specified maximum size for generation 0.</span></span>  
  
 <span data-ttu-id="39be7-110">0 세대의 최소 크기는 64KB입니다.</span><span class="sxs-lookup"><span data-stu-id="39be7-110">The minimum generation 0 size is 64 KB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="39be7-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="39be7-111">Return Value</span></span>  
  
|<span data-ttu-id="39be7-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="39be7-112">HRESULT</span></span>|<span data-ttu-id="39be7-113">설명</span><span class="sxs-lookup"><span data-stu-id="39be7-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="39be7-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="39be7-114">S_OK</span></span>|`SetGCStartupLimitsEx` <span data-ttu-id="39be7-115">성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="39be7-115">returned successfully.</span></span>|  
|<span data-ttu-id="39be7-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="39be7-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="39be7-117">프로세스에는 CLR (공용 언어 런타임)에 로드 되지 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="39be7-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="39be7-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="39be7-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="39be7-119">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="39be7-119">The call timed out.</span></span>|  
|<span data-ttu-id="39be7-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="39be7-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="39be7-121">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="39be7-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="39be7-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="39be7-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="39be7-123">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39be7-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="39be7-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="39be7-124">E_FAIL</span></span>|<span data-ttu-id="39be7-125">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="39be7-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="39be7-126">E_FAIL을 반환 하는 메서드를 CLR 더 이상 프로세스 내에서 사용 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="39be7-126">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="39be7-127">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="39be7-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="39be7-128">설명</span><span class="sxs-lookup"><span data-stu-id="39be7-128">Remarks</span></span>  
 <span data-ttu-id="39be7-129">값을 `SetGCStartupLimitsEx` 집합 호스트 시작 되기 전에만 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39be7-129">The values that `SetGCStartupLimitsEx` sets can be specified only before the host is started.</span></span> <span data-ttu-id="39be7-130">나중에 호출 `SetGCStartupLimitsEx` 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="39be7-130">Later calls to `SetGCStartupLimitsEx` are ignored.</span></span>  
  
 <span data-ttu-id="39be7-131">매개 변수 중 하나가 다른 영향을 주지 않고을 설정 하려면 0 (영)을 변경 하지 않으려는 매개 변수에 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="39be7-131">To set either parameter without affecting the other, specify 0 (zero) for the parameter you don't want to change.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39be7-132">요구 사항</span><span class="sxs-lookup"><span data-stu-id="39be7-132">Requirements</span></span>  
 <span data-ttu-id="39be7-133">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="39be7-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39be7-134">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="39be7-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="39be7-135">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="39be7-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="39be7-136">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="39be7-136">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="39be7-137">참고자료</span><span class="sxs-lookup"><span data-stu-id="39be7-137">See also</span></span>

- [<span data-ttu-id="39be7-138">Automatic Memory Management</span><span class="sxs-lookup"><span data-stu-id="39be7-138">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)
- [<span data-ttu-id="39be7-139">가비지 컬렉션</span><span class="sxs-lookup"><span data-stu-id="39be7-139">Garbage Collection</span></span>](../../../../docs/standard/garbage-collection/index.md)
- [<span data-ttu-id="39be7-140">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="39be7-140">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="39be7-141">ICLRGCManager2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="39be7-141">ICLRGCManager2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md)
