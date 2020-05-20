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
ms.openlocfilehash: 0dce86a12ed3e93983ee62620fa0ddf7dfbc48f5
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616946"
---
# <a name="iclrgcmanagersetgcstartuplimits-method"></a><span data-ttu-id="3bcc9-102">ICLRGCManager::SetGCStartupLimits 메서드</span><span class="sxs-lookup"><span data-stu-id="3bcc9-102">ICLRGCManager::SetGCStartupLimits Method</span></span>
<span data-ttu-id="3bcc9-103">가비지 수집 세그먼트의 크기와 가비지 수집 시스템의 최대 0 세대 크기를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3bcc9-103">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="3bcc9-104">.NET Framework 4.5 부터는 `DWORD` [ICLRGCManager2:: SetGCStartupLimitsEx](iclrgcmanager2-setgcstartuplimitsex-method.md) 메서드를 사용 하 여 세그먼트 크기와 최대 0 세대 크기를 보다 큰 값으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3bcc9-104">Starting with the .NET Framework 4.5, you can set segment size and maximum generation 0 size to values greater than `DWORD` by using the [ICLRGCManager2::SetGCStartupLimitsEx](iclrgcmanager2-setgcstartuplimitsex-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3bcc9-105">구문</span><span class="sxs-lookup"><span data-stu-id="3bcc9-105">Syntax</span></span>  
  
```cpp  
HRESULT SetGCStartupLimits (  
    [in] DWORD SegmentSize,
    [in] DWORD MaxGen0Size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3bcc9-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3bcc9-106">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="3bcc9-107">진행 지정 된 가비지 수집 세그먼트 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="3bcc9-107">[in] The specified size of a garbage collection segment.</span></span>  
  
 <span data-ttu-id="3bcc9-108">최소 세그먼트 크기는 4mb입니다.</span><span class="sxs-lookup"><span data-stu-id="3bcc9-108">The minimum segment size is 4 MB.</span></span> <span data-ttu-id="3bcc9-109">세그먼트는 1mb 씩 늘릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3bcc9-109">Segments can be increased in increments of 1 MB or larger.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="3bcc9-110">진행 0 세대의 지정 된 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="3bcc9-110">[in] The specified maximum size for generation 0.</span></span>  
  
 <span data-ttu-id="3bcc9-111">최소 0 세대 크기는 64 KB입니다.</span><span class="sxs-lookup"><span data-stu-id="3bcc9-111">The minimum generation 0 size is 64 KB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3bcc9-112">Return Value</span><span class="sxs-lookup"><span data-stu-id="3bcc9-112">Return Value</span></span>  
  
|<span data-ttu-id="3bcc9-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3bcc9-113">HRESULT</span></span>|<span data-ttu-id="3bcc9-114">설명</span><span class="sxs-lookup"><span data-stu-id="3bcc9-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3bcc9-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="3bcc9-115">S_OK</span></span>|<span data-ttu-id="3bcc9-116">`SetGCStartupLimits`성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3bcc9-116">`SetGCStartupLimits` returned successfully.</span></span>|  
|<span data-ttu-id="3bcc9-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3bcc9-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3bcc9-118">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3bcc9-118">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3bcc9-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3bcc9-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3bcc9-120">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3bcc9-120">The call timed out.</span></span>|  
|<span data-ttu-id="3bcc9-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3bcc9-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3bcc9-122">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3bcc9-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3bcc9-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3bcc9-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3bcc9-124">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="3bcc9-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3bcc9-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3bcc9-125">E_FAIL</span></span>|<span data-ttu-id="3bcc9-126">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="3bcc9-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3bcc9-127">메서드가 E_FAIL 반환 된 후에는 프로세스 내에서 CLR을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3bcc9-127">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3bcc9-128">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3bcc9-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3bcc9-129">설명</span><span class="sxs-lookup"><span data-stu-id="3bcc9-129">Remarks</span></span>  
 <span data-ttu-id="3bcc9-130">을 설정 하는 값은 `SetGCStartupLimits` 한 번만 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3bcc9-130">The values that `SetGCStartupLimits` sets can be specified only once.</span></span> <span data-ttu-id="3bcc9-131">에 대 한 이후 호출은 `SetGCStartupLimits` 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3bcc9-131">Later calls to `SetGCStartupLimits` are ignored.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3bcc9-132">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3bcc9-132">Requirements</span></span>  
 <span data-ttu-id="3bcc9-133">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3bcc9-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3bcc9-134">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="3bcc9-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3bcc9-135">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3bcc9-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3bcc9-136">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3bcc9-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bcc9-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3bcc9-137">See also</span></span>

- [<span data-ttu-id="3bcc9-138">자동 메모리 관리</span><span class="sxs-lookup"><span data-stu-id="3bcc9-138">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="3bcc9-139">가비지 수집</span><span class="sxs-lookup"><span data-stu-id="3bcc9-139">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
- [<span data-ttu-id="3bcc9-140">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3bcc9-140">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="3bcc9-141">ICLRGCManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3bcc9-141">ICLRGCManager Interface</span></span>](iclrgcmanager-interface.md)
