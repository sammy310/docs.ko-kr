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
ms.openlocfilehash: 645b64c8b536029663c350bdcde9a716a715aab3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178091"
---
# <a name="iclrgcmanagersetgcstartuplimits-method"></a><span data-ttu-id="19319-102">ICLRGCManager::SetGCStartupLimits 메서드</span><span class="sxs-lookup"><span data-stu-id="19319-102">ICLRGCManager::SetGCStartupLimits Method</span></span>
<span data-ttu-id="19319-103">가비지 수집 세그먼트의 크기와 가비지 수집 시스템의 생성 0의 최대 크기를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="19319-103">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="19319-104">.NET Framework 4.5부터 는 [ICLRGCManager2:SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) `DWORD` 메서드를 사용하는 것보다 큰 값으로 세그먼트 크기와 최대 생성 0 크기를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19319-104">Starting with the .NET Framework 4.5, you can set segment size and maximum generation 0 size to values greater than `DWORD` by using the [ICLRGCManager2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19319-105">구문</span><span class="sxs-lookup"><span data-stu-id="19319-105">Syntax</span></span>  
  
```cpp  
HRESULT SetGCStartupLimits (  
    [in] DWORD SegmentSize,
    [in] DWORD MaxGen0Size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="19319-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="19319-106">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="19319-107">【인】 가비지 수집 세그먼트의 지정된 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="19319-107">[in] The specified size of a garbage collection segment.</span></span>  
  
 <span data-ttu-id="19319-108">최소 세그먼트 크기는 4MB입니다.</span><span class="sxs-lookup"><span data-stu-id="19319-108">The minimum segment size is 4 MB.</span></span> <span data-ttu-id="19319-109">세그먼트는 1MB 이상 단위로 늘릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19319-109">Segments can be increased in increments of 1 MB or larger.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="19319-110">【인】 0세대에 대해 지정된 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="19319-110">[in] The specified maximum size for generation 0.</span></span>  
  
 <span data-ttu-id="19319-111">최소 세대 0 크기는 64KB입니다.</span><span class="sxs-lookup"><span data-stu-id="19319-111">The minimum generation 0 size is 64 KB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="19319-112">Return Value</span><span class="sxs-lookup"><span data-stu-id="19319-112">Return Value</span></span>  
  
|<span data-ttu-id="19319-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="19319-113">HRESULT</span></span>|<span data-ttu-id="19319-114">Description</span><span class="sxs-lookup"><span data-stu-id="19319-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="19319-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="19319-115">S_OK</span></span>|<span data-ttu-id="19319-116">`SetGCStartupLimits`성공적으로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="19319-116">`SetGCStartupLimits` returned successfully.</span></span>|  
|<span data-ttu-id="19319-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="19319-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="19319-118">공통 언어 런타임(CLR)이 프로세스에 로드되지 않았거나 CLR이 관리 코드를 실행하거나 호출을 성공적으로 처리할 수 없는 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="19319-118">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="19319-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="19319-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="19319-120">통화 시간이 시간 미정으로 확인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="19319-120">The call timed out.</span></span>|  
|<span data-ttu-id="19319-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="19319-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="19319-122">호출자는 잠금을 소유하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="19319-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="19319-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="19319-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="19319-124">차단된 스레드 또는 파이버가 대기하는 동안 이벤트가 취소되었습니다.</span><span class="sxs-lookup"><span data-stu-id="19319-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="19319-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="19319-125">E_FAIL</span></span>|<span data-ttu-id="19319-126">알 수 없는 치명적인 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="19319-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="19319-127">메서드가 E_FAIL 반환하면 프로세스 내에서 CLR을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="19319-127">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="19319-128">호스팅 메서드에 대한 후속 호출은 HOST_E_CLRNOTAVAILABLE 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="19319-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="19319-129">설명</span><span class="sxs-lookup"><span data-stu-id="19319-129">Remarks</span></span>  
 <span data-ttu-id="19319-130">`SetGCStartupLimits` 설정하는 값은 한 번만 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19319-130">The values that `SetGCStartupLimits` sets can be specified only once.</span></span> <span data-ttu-id="19319-131">나중에 `SetGCStartupLimits` 호출은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="19319-131">Later calls to `SetGCStartupLimits` are ignored.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19319-132">요구 사항</span><span class="sxs-lookup"><span data-stu-id="19319-132">Requirements</span></span>  
 <span data-ttu-id="19319-133">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="19319-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19319-134">**헤더:** MSCorE.h</span><span class="sxs-lookup"><span data-stu-id="19319-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="19319-135">**라이브러리:** MSCorEE.dll의 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="19319-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="19319-136">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19319-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19319-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="19319-137">See also</span></span>

- [<span data-ttu-id="19319-138">자동 메모리 관리</span><span class="sxs-lookup"><span data-stu-id="19319-138">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="19319-139">가비지 수집</span><span class="sxs-lookup"><span data-stu-id="19319-139">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
- [<span data-ttu-id="19319-140">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="19319-140">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="19319-141">ICLRGCManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="19319-141">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)
