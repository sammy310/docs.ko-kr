---
title: ICLRGCManager::SetGCStartupLimits 메서드
ms.date: 03/30/2017
api_name:
- ICLRGCManager.SetGCStartupLimits
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager::SetGCStartupLimits
helpviewer_keywords:
- SetGCStartupLimits method, ICLRGCManager interface [.NET Framework hosting]
- ICLRGCManager::SetGCStartupLimits method [.NET Framework hosting]
ms.assetid: 1c8d9959-95b5-4131-be4a-556d97774014
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1ffbe29db96cbb6162adc3b4cc77b45dcef27a46
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59117289"
---
# <a name="iclrgcmanagersetgcstartuplimits-method"></a><span data-ttu-id="f7142-102">ICLRGCManager::SetGCStartupLimits 메서드</span><span class="sxs-lookup"><span data-stu-id="f7142-102">ICLRGCManager::SetGCStartupLimits Method</span></span>
<span data-ttu-id="f7142-103">가비지 수집 세그먼트의 크기 및 가비지 컬렉션 시스템의 0 세대의 최대 크기를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f7142-103">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f7142-104">로 시작 합니다 [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], 세그먼트 크기를 설정할 수 있습니다 및 0 세대의 최대 크기 보다 큰 값 `DWORD` 사용 하 여를 [ICLRGCManager2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="f7142-104">Starting with the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], you can set segment size and maximum generation 0 size to values greater than `DWORD` by using the [ICLRGCManager2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7142-105">구문</span><span class="sxs-lookup"><span data-stu-id="f7142-105">Syntax</span></span>  
  
```  
HRESULT SetGCStartupLimits (  
    [in] DWORD SegmentSize,   
    [in] DWORD MaxGen0Size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f7142-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f7142-106">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="f7142-107">[in] 가비지 수집 세그먼트의 지정 된 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="f7142-107">[in] The specified size of a garbage collection segment.</span></span>  
  
 <span data-ttu-id="f7142-108">최소 세그먼트 크기는 4MB입니다.</span><span class="sxs-lookup"><span data-stu-id="f7142-108">The minimum segment size is 4 MB.</span></span> <span data-ttu-id="f7142-109">1MB 단위로 증가 하거나 더 큰 세그먼트 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7142-109">Segments can be increased in increments of 1 MB or larger.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="f7142-110">[in] 0 세대에 대 한 지정 된 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="f7142-110">[in] The specified maximum size for generation 0.</span></span>  
  
 <span data-ttu-id="f7142-111">0 세대의 최소 크기는 64KB입니다.</span><span class="sxs-lookup"><span data-stu-id="f7142-111">The minimum generation 0 size is 64 KB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f7142-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="f7142-112">Return Value</span></span>  
  
|<span data-ttu-id="f7142-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f7142-113">HRESULT</span></span>|<span data-ttu-id="f7142-114">설명</span><span class="sxs-lookup"><span data-stu-id="f7142-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f7142-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="f7142-115">S_OK</span></span>|<span data-ttu-id="f7142-116">`SetGCStartupLimits` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7142-116">`SetGCStartupLimits` returned successfully.</span></span>|  
|<span data-ttu-id="f7142-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f7142-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f7142-118">프로세스에는 CLR (공용 언어 런타임)에 로드 되지 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f7142-118">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f7142-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f7142-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f7142-120">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f7142-120">The call timed out.</span></span>|  
|<span data-ttu-id="f7142-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f7142-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f7142-122">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f7142-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f7142-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f7142-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f7142-124">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7142-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f7142-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f7142-125">E_FAIL</span></span>|<span data-ttu-id="f7142-126">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="f7142-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f7142-127">E_FAIL을 반환 하는 메서드를 CLR 더 이상 프로세스 내에서 사용 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7142-127">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f7142-128">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7142-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f7142-129">설명</span><span class="sxs-lookup"><span data-stu-id="f7142-129">Remarks</span></span>  
 <span data-ttu-id="f7142-130">값을 `SetGCStartupLimits` 집합을 한 번만 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7142-130">The values that `SetGCStartupLimits` sets can be specified only once.</span></span> <span data-ttu-id="f7142-131">나중에 호출 `SetGCStartupLimits` 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7142-131">Later calls to `SetGCStartupLimits` are ignored.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7142-132">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f7142-132">Requirements</span></span>  
 <span data-ttu-id="f7142-133">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f7142-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7142-134">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f7142-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f7142-135">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="f7142-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f7142-136">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7142-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7142-137">참고자료</span><span class="sxs-lookup"><span data-stu-id="f7142-137">See also</span></span>

- [<span data-ttu-id="f7142-138">자동 메모리 관리</span><span class="sxs-lookup"><span data-stu-id="f7142-138">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)
- [<span data-ttu-id="f7142-139">가비지 수집</span><span class="sxs-lookup"><span data-stu-id="f7142-139">Garbage Collection</span></span>](../../../../docs/standard/garbage-collection/index.md)
- [<span data-ttu-id="f7142-140">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f7142-140">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="f7142-141">ICLRGCManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f7142-141">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)
