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
ms.openlocfilehash: f71c3b738d8e1f1670ac870d5e8c23ea9182d924
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703975"
---
# <a name="iclrgcmanager2setgcstartuplimitsex-method"></a><span data-ttu-id="2c881-102">ICLRGCManager2::SetGCStartupLimitsEx 메서드</span><span class="sxs-lookup"><span data-stu-id="2c881-102">ICLRGCManager2::SetGCStartupLimitsEx Method</span></span>
<span data-ttu-id="2c881-103">가비지 수집 세그먼트의 크기와 가비지 수집 시스템의 최대 0 세대 크기를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c881-103">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c881-104">구문</span><span class="sxs-lookup"><span data-stu-id="2c881-104">Syntax</span></span>  
  
```cpp  
HRESULT SetGCStartupLimitsEx (  
    [in] SIZE_T SegmentSize,
    [in] SIZE_T MaxGen0Size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2c881-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2c881-105">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="2c881-106">진행 지정 된 가비지 수집 세그먼트 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="2c881-106">[in] The specified size of a garbage collection segment.</span></span>  
  
 <span data-ttu-id="2c881-107">최소 세그먼트 크기는 4mb입니다.</span><span class="sxs-lookup"><span data-stu-id="2c881-107">The minimum segment size is 4 MB.</span></span> <span data-ttu-id="2c881-108">세그먼트는 1mb 씩 늘릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c881-108">Segments can be increased in increments of 1 MB or larger.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="2c881-109">진행 0 세대의 지정 된 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="2c881-109">[in] The specified maximum size for generation 0.</span></span>  
  
 <span data-ttu-id="2c881-110">최소 0 세대 크기는 64 KB입니다.</span><span class="sxs-lookup"><span data-stu-id="2c881-110">The minimum generation 0 size is 64 KB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2c881-111">Return Value</span><span class="sxs-lookup"><span data-stu-id="2c881-111">Return Value</span></span>  
  
|<span data-ttu-id="2c881-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2c881-112">HRESULT</span></span>|<span data-ttu-id="2c881-113">설명</span><span class="sxs-lookup"><span data-stu-id="2c881-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2c881-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="2c881-114">S_OK</span></span>|<span data-ttu-id="2c881-115">`SetGCStartupLimitsEx`성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2c881-115">`SetGCStartupLimitsEx` returned successfully.</span></span>|  
|<span data-ttu-id="2c881-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2c881-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2c881-117">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c881-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2c881-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2c881-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2c881-119">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2c881-119">The call timed out.</span></span>|  
|<span data-ttu-id="2c881-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2c881-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2c881-121">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2c881-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2c881-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2c881-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2c881-123">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="2c881-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2c881-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2c881-124">E_FAIL</span></span>|<span data-ttu-id="2c881-125">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="2c881-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2c881-126">메서드가 E_FAIL 반환 된 후에는 프로세스 내에서 CLR을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2c881-126">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2c881-127">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c881-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2c881-128">설명</span><span class="sxs-lookup"><span data-stu-id="2c881-128">Remarks</span></span>  
 <span data-ttu-id="2c881-129">를 설정 하는 값은 `SetGCStartupLimitsEx` 호스트를 시작 하기 전에만 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c881-129">The values that `SetGCStartupLimitsEx` sets can be specified only before the host is started.</span></span> <span data-ttu-id="2c881-130">에 대 한 이후 호출은 `SetGCStartupLimitsEx` 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c881-130">Later calls to `SetGCStartupLimitsEx` are ignored.</span></span>  
  
 <span data-ttu-id="2c881-131">다른 매개 변수에 영향을 주지 않고 두 매개 변수를 설정 하려면 변경 하지 않으려는 매개 변수에 0을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c881-131">To set either parameter without affecting the other, specify 0 (zero) for the parameter you don't want to change.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c881-132">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2c881-132">Requirements</span></span>  
 <span data-ttu-id="2c881-133">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2c881-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c881-134">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="2c881-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2c881-135">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c881-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2c881-136">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c881-136">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c881-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2c881-137">See also</span></span>

- [<span data-ttu-id="2c881-138">자동 메모리 관리</span><span class="sxs-lookup"><span data-stu-id="2c881-138">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="2c881-139">가비지 수집</span><span class="sxs-lookup"><span data-stu-id="2c881-139">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
- [<span data-ttu-id="2c881-140">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2c881-140">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="2c881-141">ICLRGCManager2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2c881-141">ICLRGCManager2 Interface</span></span>](iclrgcmanager2-interface.md)
