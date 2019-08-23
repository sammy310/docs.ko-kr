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
ms.openlocfilehash: 0d881c71d4725e1a73d743aa098aecc053182947
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918603"
---
# <a name="iclrgcmanager2setgcstartuplimitsex-method"></a><span data-ttu-id="00256-102">ICLRGCManager2::SetGCStartupLimitsEx 메서드</span><span class="sxs-lookup"><span data-stu-id="00256-102">ICLRGCManager2::SetGCStartupLimitsEx Method</span></span>
<span data-ttu-id="00256-103">가비지 수집 세그먼트의 크기와 가비지 수집 시스템의 최대 0 세대 크기를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="00256-103">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00256-104">구문</span><span class="sxs-lookup"><span data-stu-id="00256-104">Syntax</span></span>  
  
```cpp  
HRESULT SetGCStartupLimitsEx (  
    [in] SIZE_T SegmentSize,   
    [in] SIZE_T MaxGen0Size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="00256-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="00256-105">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="00256-106">진행 지정 된 가비지 수집 세그먼트 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="00256-106">[in] The specified size of a garbage collection segment.</span></span>  
  
 <span data-ttu-id="00256-107">최소 세그먼트 크기는 4mb입니다.</span><span class="sxs-lookup"><span data-stu-id="00256-107">The minimum segment size is 4 MB.</span></span> <span data-ttu-id="00256-108">세그먼트는 1mb 씩 늘릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00256-108">Segments can be increased in increments of 1 MB or larger.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="00256-109">진행 0 세대의 지정 된 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="00256-109">[in] The specified maximum size for generation 0.</span></span>  
  
 <span data-ttu-id="00256-110">최소 0 세대 크기는 64 KB입니다.</span><span class="sxs-lookup"><span data-stu-id="00256-110">The minimum generation 0 size is 64 KB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="00256-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="00256-111">Return Value</span></span>  
  
|<span data-ttu-id="00256-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="00256-112">HRESULT</span></span>|<span data-ttu-id="00256-113">Description</span><span class="sxs-lookup"><span data-stu-id="00256-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="00256-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="00256-114">S_OK</span></span>|<span data-ttu-id="00256-115">`SetGCStartupLimitsEx`성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="00256-115">`SetGCStartupLimitsEx` returned successfully.</span></span>|  
|<span data-ttu-id="00256-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="00256-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="00256-117">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00256-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="00256-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="00256-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="00256-119">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="00256-119">The call timed out.</span></span>|  
|<span data-ttu-id="00256-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="00256-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="00256-121">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="00256-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="00256-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="00256-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="00256-123">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="00256-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="00256-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="00256-124">E_FAIL</span></span>|<span data-ttu-id="00256-125">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="00256-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="00256-126">메서드가 E_FAIL을 반환한 후에는 프로세스 내에서 CLR을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="00256-126">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="00256-127">호스팅 메서드에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="00256-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="00256-128">설명</span><span class="sxs-lookup"><span data-stu-id="00256-128">Remarks</span></span>  
 <span data-ttu-id="00256-129">를 설정 하 `SetGCStartupLimitsEx` 는 값은 호스트를 시작 하기 전에만 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00256-129">The values that `SetGCStartupLimitsEx` sets can be specified only before the host is started.</span></span> <span data-ttu-id="00256-130">에 대 한 `SetGCStartupLimitsEx` 이후 호출은 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="00256-130">Later calls to `SetGCStartupLimitsEx` are ignored.</span></span>  
  
 <span data-ttu-id="00256-131">다른 매개 변수에 영향을 주지 않고 두 매개 변수를 설정 하려면 변경 하지 않으려는 매개 변수에 0을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="00256-131">To set either parameter without affecting the other, specify 0 (zero) for the parameter you don't want to change.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00256-132">요구 사항</span><span class="sxs-lookup"><span data-stu-id="00256-132">Requirements</span></span>  
 <span data-ttu-id="00256-133">**플랫폼** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="00256-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00256-134">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="00256-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="00256-135">**라이브러리** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="00256-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="00256-136">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00256-136">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00256-137">참고자료</span><span class="sxs-lookup"><span data-stu-id="00256-137">See also</span></span>

- [<span data-ttu-id="00256-138">자동 메모리 관리</span><span class="sxs-lookup"><span data-stu-id="00256-138">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="00256-139">가비지 수집</span><span class="sxs-lookup"><span data-stu-id="00256-139">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
- [<span data-ttu-id="00256-140">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="00256-140">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="00256-141">ICLRGCManager2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="00256-141">ICLRGCManager2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md)
