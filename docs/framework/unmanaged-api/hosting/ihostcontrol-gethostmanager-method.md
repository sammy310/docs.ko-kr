---
title: IHostControl::GetHostManager 메서드
ms.date: 03/30/2017
api_name:
- IHostControl.GetHostManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostControl::GetHostManager
helpviewer_keywords:
- GetHostManager method [.NET Framework hosting]
- IHostControl::GetHostManager method [.NET Framework hosting]
ms.assetid: 0fa34bca-ed18-4626-9e78-d33684d18edb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cad7b319a20bce09779821af6f50aea086880c26
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59187345"
---
# <a name="ihostcontrolgethostmanager-method"></a><span data-ttu-id="cddea-102">IHostControl::GetHostManager 메서드</span><span class="sxs-lookup"><span data-stu-id="cddea-102">IHostControl::GetHostManager Method</span></span>
<span data-ttu-id="cddea-103">지정 된 인터페이스의 호스트의 구현에 대 한 인터페이스 포인터를 가져옵니다 `IID`합니다.</span><span class="sxs-lookup"><span data-stu-id="cddea-103">Gets an interface pointer to the host's implementation of the interface with the specified `IID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cddea-104">구문</span><span class="sxs-lookup"><span data-stu-id="cddea-104">Syntax</span></span>  
  
```  
HRESULT GetHostManager (  
    [in] REFIID riid,  
    [out, iid_is(riid)] void** ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cddea-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cddea-105">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="cddea-106">[in] `IID` 는 CLR (공용 언어 런타임)에 대 한 쿼리 하는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="cddea-106">[in] The `IID` of the interface that the common language runtime (CLR) is querying for.</span></span>  
  
 `ppObject`  
 <span data-ttu-id="cddea-107">[out] 호스트가 구현한 인터페이스 또는 호스트는이 인터페이스를 지원 하지 않는 경우 null 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="cddea-107">[out] A pointer to the host-implemented interface, or null if the host does not support this interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cddea-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="cddea-108">Return Value</span></span>  
  
|<span data-ttu-id="cddea-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="cddea-109">HRESULT</span></span>|<span data-ttu-id="cddea-110">설명</span><span class="sxs-lookup"><span data-stu-id="cddea-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cddea-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="cddea-111">S_OK</span></span>|<span data-ttu-id="cddea-112">`GetHostManager` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cddea-112">`GetHostManager` returned successfully.</span></span>|  
|<span data-ttu-id="cddea-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="cddea-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="cddea-114">CLR이 로드 된 프로세스에 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cddea-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="cddea-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="cddea-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="cddea-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cddea-116">The call timed out.</span></span>|  
|<span data-ttu-id="cddea-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="cddea-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="cddea-118">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cddea-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="cddea-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="cddea-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="cddea-120">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cddea-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="cddea-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="cddea-121">E_FAIL</span></span>|<span data-ttu-id="cddea-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="cddea-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="cddea-123">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cddea-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="cddea-124">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cddea-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="cddea-125">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="cddea-125">E_INVALIDARG</span></span>|<span data-ttu-id="cddea-126">요청 된 `IID` 올바르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cddea-126">The requested `IID` is not valid.</span></span>|  
|<span data-ttu-id="cddea-127">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="cddea-127">E_NOINTERFACE</span></span>|<span data-ttu-id="cddea-128">요청한 인터페이스가 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cddea-128">The requested interface is not supported.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cddea-129">설명</span><span class="sxs-lookup"><span data-stu-id="cddea-129">Remarks</span></span>  
 <span data-ttu-id="cddea-130">CLR 다음 인터페이스 중 하나 이상을 지원 하는지 여부를 확인 하려면 호스트를 쿼리 합니다.</span><span class="sxs-lookup"><span data-stu-id="cddea-130">The CLR queries the host to determine whether it supports one or more of the following interfaces:</span></span>  
  
-   [<span data-ttu-id="cddea-131">IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="cddea-131">IHostMemoryManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
  
-   [<span data-ttu-id="cddea-132">IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="cddea-132">IHostTaskManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
  
-   [<span data-ttu-id="cddea-133">IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="cddea-133">IHostThreadPoolManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)  
  
-   [<span data-ttu-id="cddea-134">IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="cddea-134">IHostIoCompletionManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)  
  
-   [<span data-ttu-id="cddea-135">IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="cddea-135">IHostSyncManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
  
-   [<span data-ttu-id="cddea-136">IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="cddea-136">IHostAssemblyManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
  
-   [<span data-ttu-id="cddea-137">IHostGCManager</span><span class="sxs-lookup"><span data-stu-id="cddea-137">IHostGCManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)  
  
-   [<span data-ttu-id="cddea-138">IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="cddea-138">IHostPolicyManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)  
  
-   [<span data-ttu-id="cddea-139">IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="cddea-139">IHostSecurityManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
  
 <span data-ttu-id="cddea-140">호스트에서 지정된 된 인터페이스를 지 원하는 경우 설정 `ppObject` 를 해당 인터페이스의 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="cddea-140">If the host supports the specified interface, it sets `ppObject` to its implementation of that interface.</span></span> <span data-ttu-id="cddea-141">그렇지 않은 경우 설정 `ppObject` null로 합니다.</span><span class="sxs-lookup"><span data-stu-id="cddea-141">Otherwise, it sets `ppObject` to null.</span></span>  
  
 <span data-ttu-id="cddea-142">CLR에서 호출 하지 않습니다 `Release` 를 종료 하는 경우에 호스트 관리자에서.</span><span class="sxs-lookup"><span data-stu-id="cddea-142">The CLR does not call `Release` on host managers, even when you shut it down.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cddea-143">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cddea-143">Requirements</span></span>  
 <span data-ttu-id="cddea-144">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="cddea-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cddea-145">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="cddea-145">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cddea-146">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="cddea-146">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cddea-147">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cddea-147">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cddea-148">참고자료</span><span class="sxs-lookup"><span data-stu-id="cddea-148">See also</span></span>

- [<span data-ttu-id="cddea-149">IHostControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cddea-149">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
