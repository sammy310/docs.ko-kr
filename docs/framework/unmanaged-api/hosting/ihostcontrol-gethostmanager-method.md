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
ms.openlocfilehash: c23773dce448c8c98d4926dff3fa51100e683fd0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73192046"
---
# <a name="ihostcontrolgethostmanager-method"></a><span data-ttu-id="37b6f-102">IHostControl::GetHostManager 메서드</span><span class="sxs-lookup"><span data-stu-id="37b6f-102">IHostControl::GetHostManager Method</span></span>
<span data-ttu-id="37b6f-103">지정 된 `IID`를 사용 하 여 호스트의 인터페이스 구현에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="37b6f-103">Gets an interface pointer to the host's implementation of the interface with the specified `IID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37b6f-104">구문</span><span class="sxs-lookup"><span data-stu-id="37b6f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHostManager (  
    [in] REFIID riid,  
    [out, iid_is(riid)] void** ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="37b6f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="37b6f-105">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="37b6f-106">진행 CLR (공용 언어 런타임)에서 쿼리 하는 인터페이스의 `IID`입니다.</span><span class="sxs-lookup"><span data-stu-id="37b6f-106">[in] The `IID` of the interface that the common language runtime (CLR) is querying for.</span></span>  
  
 `ppObject`  
 <span data-ttu-id="37b6f-107">제한이 호스트에서 구현 하는 인터페이스에 대 한 포인터 이거나, 호스트가이 인터페이스를 지원 하지 않는 경우 null입니다.</span><span class="sxs-lookup"><span data-stu-id="37b6f-107">[out] A pointer to the host-implemented interface, or null if the host does not support this interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="37b6f-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="37b6f-108">Return Value</span></span>  
  
|<span data-ttu-id="37b6f-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="37b6f-109">HRESULT</span></span>|<span data-ttu-id="37b6f-110">설명</span><span class="sxs-lookup"><span data-stu-id="37b6f-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="37b6f-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="37b6f-111">S_OK</span></span>|<span data-ttu-id="37b6f-112">`GetHostManager` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="37b6f-112">`GetHostManager` returned successfully.</span></span>|  
|<span data-ttu-id="37b6f-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="37b6f-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="37b6f-114">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37b6f-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="37b6f-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="37b6f-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="37b6f-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="37b6f-116">The call timed out.</span></span>|  
|<span data-ttu-id="37b6f-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="37b6f-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="37b6f-118">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="37b6f-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="37b6f-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="37b6f-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="37b6f-120">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="37b6f-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="37b6f-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="37b6f-121">E_FAIL</span></span>|<span data-ttu-id="37b6f-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="37b6f-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="37b6f-123">메서드가 E_FAIL을 반환 하는 경우 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="37b6f-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="37b6f-124">호스팅 메서드에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="37b6f-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="37b6f-125">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="37b6f-125">E_INVALIDARG</span></span>|<span data-ttu-id="37b6f-126">요청 된 `IID` 잘못 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="37b6f-126">The requested `IID` is not valid.</span></span>|  
|<span data-ttu-id="37b6f-127">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="37b6f-127">E_NOINTERFACE</span></span>|<span data-ttu-id="37b6f-128">요청 된 인터페이스가 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="37b6f-128">The requested interface is not supported.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="37b6f-129">주의</span><span class="sxs-lookup"><span data-stu-id="37b6f-129">Remarks</span></span>  
 <span data-ttu-id="37b6f-130">CLR은 호스트를 쿼리하여 다음 인터페이스 중 하나 이상을 지원 하는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="37b6f-130">The CLR queries the host to determine whether it supports one or more of the following interfaces:</span></span>  
  
- [<span data-ttu-id="37b6f-131">IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="37b6f-131">IHostMemoryManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
  
- [<span data-ttu-id="37b6f-132">IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="37b6f-132">IHostTaskManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
  
- [<span data-ttu-id="37b6f-133">IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="37b6f-133">IHostThreadPoolManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)  
  
- [<span data-ttu-id="37b6f-134">IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="37b6f-134">IHostIoCompletionManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)  
  
- [<span data-ttu-id="37b6f-135">IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="37b6f-135">IHostSyncManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
  
- [<span data-ttu-id="37b6f-136">IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="37b6f-136">IHostAssemblyManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
  
- [<span data-ttu-id="37b6f-137">IHostGCManager</span><span class="sxs-lookup"><span data-stu-id="37b6f-137">IHostGCManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)  
  
- [<span data-ttu-id="37b6f-138">IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="37b6f-138">IHostPolicyManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)  
  
- [<span data-ttu-id="37b6f-139">IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="37b6f-139">IHostSecurityManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
  
 <span data-ttu-id="37b6f-140">호스트에서 지정 된 인터페이스를 지 원하는 경우 `ppObject`를 해당 인터페이스의 구현으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="37b6f-140">If the host supports the specified interface, it sets `ppObject` to its implementation of that interface.</span></span> <span data-ttu-id="37b6f-141">그렇지 않으면 `ppObject`를 null로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="37b6f-141">Otherwise, it sets `ppObject` to null.</span></span>  
  
 <span data-ttu-id="37b6f-142">CLR은 호스트 관리자의 `Release`를 종료 하는 경우에도 호출 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="37b6f-142">The CLR does not call `Release` on host managers, even when you shut it down.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="37b6f-143">요구 사항</span><span class="sxs-lookup"><span data-stu-id="37b6f-143">Requirements</span></span>  
 <span data-ttu-id="37b6f-144">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="37b6f-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="37b6f-145">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="37b6f-145">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="37b6f-146">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="37b6f-146">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="37b6f-147">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="37b6f-147">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37b6f-148">참조</span><span class="sxs-lookup"><span data-stu-id="37b6f-148">See also</span></span>

- [<span data-ttu-id="37b6f-149">IHostControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="37b6f-149">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
