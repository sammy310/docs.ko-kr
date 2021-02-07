---
description: '자세히 알아보기: IHostControl:: GetHostManager 메서드'
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
ms.openlocfilehash: 7cc118808c8788504da2cc07a8c61c419d3c588f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99708909"
---
# <a name="ihostcontrolgethostmanager-method"></a><span data-ttu-id="4f1e3-103">IHostControl::GetHostManager 메서드</span><span class="sxs-lookup"><span data-stu-id="4f1e3-103">IHostControl::GetHostManager Method</span></span>

<span data-ttu-id="4f1e3-104">지정 된을 사용 하 여 호스트의 인터페이스 구현에 대 한 인터페이스 포인터를 가져옵니다 `IID` .</span><span class="sxs-lookup"><span data-stu-id="4f1e3-104">Gets an interface pointer to the host's implementation of the interface with the specified `IID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f1e3-105">구문</span><span class="sxs-lookup"><span data-stu-id="4f1e3-105">Syntax</span></span>  
  
```cpp  
HRESULT GetHostManager (  
    [in] REFIID riid,  
    [out, iid_is(riid)] void** ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4f1e3-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4f1e3-106">Parameters</span></span>  

 `riid`  
 <span data-ttu-id="4f1e3-107">진행 `IID` CLR (공용 언어 런타임)에서 쿼리 하는 인터페이스의입니다.</span><span class="sxs-lookup"><span data-stu-id="4f1e3-107">[in] The `IID` of the interface that the common language runtime (CLR) is querying for.</span></span>  
  
 `ppObject`  
 <span data-ttu-id="4f1e3-108">제한이 호스트에서 구현 하는 인터페이스에 대 한 포인터 이거나, 호스트가이 인터페이스를 지원 하지 않는 경우 null입니다.</span><span class="sxs-lookup"><span data-stu-id="4f1e3-108">[out] A pointer to the host-implemented interface, or null if the host does not support this interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4f1e3-109">Return Value</span><span class="sxs-lookup"><span data-stu-id="4f1e3-109">Return Value</span></span>  
  
|<span data-ttu-id="4f1e3-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4f1e3-110">HRESULT</span></span>|<span data-ttu-id="4f1e3-111">설명</span><span class="sxs-lookup"><span data-stu-id="4f1e3-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4f1e3-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="4f1e3-112">S_OK</span></span>|<span data-ttu-id="4f1e3-113">`GetHostManager` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4f1e3-113">`GetHostManager` returned successfully.</span></span>|  
|<span data-ttu-id="4f1e3-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4f1e3-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4f1e3-115">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f1e3-115">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4f1e3-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4f1e3-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4f1e3-117">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4f1e3-117">The call timed out.</span></span>|  
|<span data-ttu-id="4f1e3-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4f1e3-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4f1e3-119">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4f1e3-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4f1e3-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4f1e3-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4f1e3-121">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="4f1e3-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4f1e3-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4f1e3-122">E_FAIL</span></span>|<span data-ttu-id="4f1e3-123">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="4f1e3-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4f1e3-124">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4f1e3-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4f1e3-125">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f1e3-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="4f1e3-126">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="4f1e3-126">E_INVALIDARG</span></span>|<span data-ttu-id="4f1e3-127">요청 된 `IID` 이 잘못 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4f1e3-127">The requested `IID` is not valid.</span></span>|  
|<span data-ttu-id="4f1e3-128">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="4f1e3-128">E_NOINTERFACE</span></span>|<span data-ttu-id="4f1e3-129">요청 된 인터페이스가 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4f1e3-129">The requested interface is not supported.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4f1e3-130">설명</span><span class="sxs-lookup"><span data-stu-id="4f1e3-130">Remarks</span></span>  

 <span data-ttu-id="4f1e3-131">CLR은 호스트를 쿼리하여 다음 인터페이스 중 하나 이상을 지원 하는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f1e3-131">The CLR queries the host to determine whether it supports one or more of the following interfaces:</span></span>  
  
- [<span data-ttu-id="4f1e3-132">IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="4f1e3-132">IHostMemoryManager</span></span>](ihostmemorymanager-interface.md)  
  
- [<span data-ttu-id="4f1e3-133">IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="4f1e3-133">IHostTaskManager</span></span>](ihosttaskmanager-interface.md)  
  
- [<span data-ttu-id="4f1e3-134">IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="4f1e3-134">IHostThreadPoolManager</span></span>](ihostthreadpoolmanager-interface.md)  
  
- [<span data-ttu-id="4f1e3-135">IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="4f1e3-135">IHostIoCompletionManager</span></span>](ihostiocompletionmanager-interface.md)  
  
- [<span data-ttu-id="4f1e3-136">IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="4f1e3-136">IHostSyncManager</span></span>](ihostsyncmanager-interface.md)  
  
- [<span data-ttu-id="4f1e3-137">IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="4f1e3-137">IHostAssemblyManager</span></span>](ihostassemblymanager-interface.md)  
  
- [<span data-ttu-id="4f1e3-138">IHostGCManager</span><span class="sxs-lookup"><span data-stu-id="4f1e3-138">IHostGCManager</span></span>](ihostgcmanager-interface.md)  
  
- [<span data-ttu-id="4f1e3-139">IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="4f1e3-139">IHostPolicyManager</span></span>](ihostpolicymanager-interface.md)  
  
- [<span data-ttu-id="4f1e3-140">IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="4f1e3-140">IHostSecurityManager</span></span>](ihostsecuritymanager-interface.md)  
  
 <span data-ttu-id="4f1e3-141">호스트에서 지정 된 인터페이스를 지 원하는 경우 해당 인터페이스 `ppObject` 의 구현으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f1e3-141">If the host supports the specified interface, it sets `ppObject` to its implementation of that interface.</span></span> <span data-ttu-id="4f1e3-142">그렇지 않으면 `ppObject` null로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f1e3-142">Otherwise, it sets `ppObject` to null.</span></span>  
  
 <span data-ttu-id="4f1e3-143">CLR은 `Release` 종료 하는 경우에도 호스트 관리자에서를 호출 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4f1e3-143">The CLR does not call `Release` on host managers, even when you shut it down.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f1e3-144">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4f1e3-144">Requirements</span></span>  

 <span data-ttu-id="4f1e3-145">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4f1e3-145">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f1e3-146">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="4f1e3-146">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4f1e3-147">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f1e3-147">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4f1e3-148">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f1e3-148">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f1e3-149">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4f1e3-149">See also</span></span>

- [<span data-ttu-id="4f1e3-150">IHostControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4f1e3-150">IHostControl Interface</span></span>](ihostcontrol-interface.md)
