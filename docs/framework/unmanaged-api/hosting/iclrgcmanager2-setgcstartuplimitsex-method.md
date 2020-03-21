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
ms.openlocfilehash: 9885149a71147db6eef13958b8ef825caa1d6ec6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176385"
---
# <a name="iclrgcmanager2setgcstartuplimitsex-method"></a><span data-ttu-id="6c75d-102">ICLRGCManager2::SetGCStartupLimitsEx 메서드</span><span class="sxs-lookup"><span data-stu-id="6c75d-102">ICLRGCManager2::SetGCStartupLimitsEx Method</span></span>
<span data-ttu-id="6c75d-103">가비지 수집 세그먼트의 크기와 가비지 수집 시스템의 생성 0의 최대 크기를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6c75d-103">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c75d-104">구문</span><span class="sxs-lookup"><span data-stu-id="6c75d-104">Syntax</span></span>  
  
```cpp  
HRESULT SetGCStartupLimitsEx (  
    [in] SIZE_T SegmentSize,
    [in] SIZE_T MaxGen0Size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6c75d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6c75d-105">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="6c75d-106">【인】 가비지 수집 세그먼트의 지정된 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="6c75d-106">[in] The specified size of a garbage collection segment.</span></span>  
  
 <span data-ttu-id="6c75d-107">최소 세그먼트 크기는 4MB입니다.</span><span class="sxs-lookup"><span data-stu-id="6c75d-107">The minimum segment size is 4 MB.</span></span> <span data-ttu-id="6c75d-108">세그먼트는 1MB 이상 단위로 늘릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c75d-108">Segments can be increased in increments of 1 MB or larger.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="6c75d-109">【인】 0세대에 대해 지정된 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="6c75d-109">[in] The specified maximum size for generation 0.</span></span>  
  
 <span data-ttu-id="6c75d-110">최소 세대 0 크기는 64KB입니다.</span><span class="sxs-lookup"><span data-stu-id="6c75d-110">The minimum generation 0 size is 64 KB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6c75d-111">Return Value</span><span class="sxs-lookup"><span data-stu-id="6c75d-111">Return Value</span></span>  
  
|<span data-ttu-id="6c75d-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6c75d-112">HRESULT</span></span>|<span data-ttu-id="6c75d-113">Description</span><span class="sxs-lookup"><span data-stu-id="6c75d-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6c75d-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="6c75d-114">S_OK</span></span>|<span data-ttu-id="6c75d-115">`SetGCStartupLimitsEx`성공적으로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c75d-115">`SetGCStartupLimitsEx` returned successfully.</span></span>|  
|<span data-ttu-id="6c75d-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6c75d-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6c75d-117">공통 언어 런타임(CLR)이 프로세스에 로드되지 않았거나 CLR이 관리 코드를 실행하거나 호출을 성공적으로 처리할 수 없는 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="6c75d-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6c75d-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6c75d-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6c75d-119">통화 시간이 시간 미정으로 확인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6c75d-119">The call timed out.</span></span>|  
|<span data-ttu-id="6c75d-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6c75d-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6c75d-121">호출자는 잠금을 소유하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6c75d-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6c75d-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6c75d-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6c75d-123">차단된 스레드 또는 파이버가 대기하는 동안 이벤트가 취소되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6c75d-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6c75d-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6c75d-124">E_FAIL</span></span>|<span data-ttu-id="6c75d-125">알 수 없는 치명적인 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="6c75d-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6c75d-126">메서드가 E_FAIL 반환하면 프로세스 내에서 CLR을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6c75d-126">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6c75d-127">호스팅 메서드에 대한 후속 호출은 HOST_E_CLRNOTAVAILABLE 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6c75d-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6c75d-128">설명</span><span class="sxs-lookup"><span data-stu-id="6c75d-128">Remarks</span></span>  
 <span data-ttu-id="6c75d-129">설정하는 `SetGCStartupLimitsEx` 값은 호스트가 시작되기 전에만 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c75d-129">The values that `SetGCStartupLimitsEx` sets can be specified only before the host is started.</span></span> <span data-ttu-id="6c75d-130">나중에 `SetGCStartupLimitsEx` 호출은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c75d-130">Later calls to `SetGCStartupLimitsEx` are ignored.</span></span>  
  
 <span data-ttu-id="6c75d-131">다른 매개 변수에 영향을 주지 않고 두 매개 변수를 설정하려면 변경하지 않으려는 매개 변수에 대해 0(0)을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6c75d-131">To set either parameter without affecting the other, specify 0 (zero) for the parameter you don't want to change.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c75d-132">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6c75d-132">Requirements</span></span>  
 <span data-ttu-id="6c75d-133">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6c75d-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c75d-134">**헤더:** MSCorE.h</span><span class="sxs-lookup"><span data-stu-id="6c75d-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6c75d-135">**라이브러리:** MSCorEE.dll의 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="6c75d-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6c75d-136">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c75d-136">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c75d-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6c75d-137">See also</span></span>

- [<span data-ttu-id="6c75d-138">자동 메모리 관리</span><span class="sxs-lookup"><span data-stu-id="6c75d-138">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="6c75d-139">가비지 수집</span><span class="sxs-lookup"><span data-stu-id="6c75d-139">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
- [<span data-ttu-id="6c75d-140">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6c75d-140">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="6c75d-141">ICLRGCManager2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6c75d-141">ICLRGCManager2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md)
