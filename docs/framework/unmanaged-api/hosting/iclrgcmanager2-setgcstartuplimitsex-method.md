---
description: '자세히 알아보기: ICLRGCManager2:: SetGCStartupLimitsEx 메서드'
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
ms.openlocfilehash: 2a4801d2f6255f5f84e0a4bae7a1886689ee8dc5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99689240"
---
# <a name="iclrgcmanager2setgcstartuplimitsex-method"></a><span data-ttu-id="b97fc-103">ICLRGCManager2::SetGCStartupLimitsEx 메서드</span><span class="sxs-lookup"><span data-stu-id="b97fc-103">ICLRGCManager2::SetGCStartupLimitsEx Method</span></span>

<span data-ttu-id="b97fc-104">가비지 수집 세그먼트의 크기와 가비지 수집 시스템의 최대 0 세대 크기를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b97fc-104">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b97fc-105">구문</span><span class="sxs-lookup"><span data-stu-id="b97fc-105">Syntax</span></span>  
  
```cpp  
HRESULT SetGCStartupLimitsEx (  
    [in] SIZE_T SegmentSize,
    [in] SIZE_T MaxGen0Size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b97fc-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b97fc-106">Parameters</span></span>  

 `SegmentSize`  
 <span data-ttu-id="b97fc-107">진행 지정 된 가비지 수집 세그먼트 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="b97fc-107">[in] The specified size of a garbage collection segment.</span></span>  
  
 <span data-ttu-id="b97fc-108">최소 세그먼트 크기는 4mb입니다.</span><span class="sxs-lookup"><span data-stu-id="b97fc-108">The minimum segment size is 4 MB.</span></span> <span data-ttu-id="b97fc-109">세그먼트는 1mb 씩 늘릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b97fc-109">Segments can be increased in increments of 1 MB or larger.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="b97fc-110">진행 0 세대의 지정 된 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="b97fc-110">[in] The specified maximum size for generation 0.</span></span>  
  
 <span data-ttu-id="b97fc-111">최소 0 세대 크기는 64 KB입니다.</span><span class="sxs-lookup"><span data-stu-id="b97fc-111">The minimum generation 0 size is 64 KB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b97fc-112">Return Value</span><span class="sxs-lookup"><span data-stu-id="b97fc-112">Return Value</span></span>  
  
|<span data-ttu-id="b97fc-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b97fc-113">HRESULT</span></span>|<span data-ttu-id="b97fc-114">설명</span><span class="sxs-lookup"><span data-stu-id="b97fc-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b97fc-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="b97fc-115">S_OK</span></span>|<span data-ttu-id="b97fc-116">`SetGCStartupLimitsEx` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b97fc-116">`SetGCStartupLimitsEx` returned successfully.</span></span>|  
|<span data-ttu-id="b97fc-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b97fc-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b97fc-118">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b97fc-118">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b97fc-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b97fc-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b97fc-120">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b97fc-120">The call timed out.</span></span>|  
|<span data-ttu-id="b97fc-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b97fc-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b97fc-122">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b97fc-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b97fc-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b97fc-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b97fc-124">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="b97fc-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b97fc-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b97fc-125">E_FAIL</span></span>|<span data-ttu-id="b97fc-126">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="b97fc-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b97fc-127">메서드가 E_FAIL 반환 된 후에는 프로세스 내에서 CLR을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b97fc-127">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b97fc-128">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b97fc-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b97fc-129">설명</span><span class="sxs-lookup"><span data-stu-id="b97fc-129">Remarks</span></span>  

 <span data-ttu-id="b97fc-130">를 설정 하는 값은 `SetGCStartupLimitsEx` 호스트를 시작 하기 전에만 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b97fc-130">The values that `SetGCStartupLimitsEx` sets can be specified only before the host is started.</span></span> <span data-ttu-id="b97fc-131">에 대 한 이후 호출은 `SetGCStartupLimitsEx` 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b97fc-131">Later calls to `SetGCStartupLimitsEx` are ignored.</span></span>  
  
 <span data-ttu-id="b97fc-132">다른 매개 변수에 영향을 주지 않고 두 매개 변수를 설정 하려면 변경 하지 않으려는 매개 변수에 0을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b97fc-132">To set either parameter without affecting the other, specify 0 (zero) for the parameter you don't want to change.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b97fc-133">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b97fc-133">Requirements</span></span>  

 <span data-ttu-id="b97fc-134">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b97fc-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b97fc-135">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="b97fc-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b97fc-136">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b97fc-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b97fc-137">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b97fc-137">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b97fc-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b97fc-138">See also</span></span>

- [<span data-ttu-id="b97fc-139">자동 메모리 관리</span><span class="sxs-lookup"><span data-stu-id="b97fc-139">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="b97fc-140">가비지 수집</span><span class="sxs-lookup"><span data-stu-id="b97fc-140">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
- [<span data-ttu-id="b97fc-141">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b97fc-141">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="b97fc-142">ICLRGCManager2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b97fc-142">ICLRGCManager2 Interface</span></span>](iclrgcmanager2-interface.md)
