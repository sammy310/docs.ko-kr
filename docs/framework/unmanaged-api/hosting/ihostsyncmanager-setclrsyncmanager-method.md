---
title: IHostSyncManager::SetCLRSyncManager 메서드
ms.date: 03/30/2017
api_name:
- IHostSyncManager.SetCLRSyncManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::SetCLRSyncManager
helpviewer_keywords:
- IHostSyncManager::SetCLRSyncManager method [.NET Framework hosting]
- SetCLRSyncManager method [.NET Framework hosting]
ms.assetid: 2b8bbe76-a45d-4989-bacb-11df42f8798c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b27cf1ab377a3bb51700b287024d801e75107c8c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57464923"
---
# <a name="ihostsyncmanagersetclrsyncmanager-method"></a><span data-ttu-id="daada-102">IHostSyncManager::SetCLRSyncManager 메서드</span><span class="sxs-lookup"><span data-stu-id="daada-102">IHostSyncManager::SetCLRSyncManager Method</span></span>
<span data-ttu-id="daada-103">집합의 [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) 현재 연결할 인스턴스 [IHostSyncManager](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md) 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="daada-103">Sets the [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) instance to associate with the current [IHostSyncManager](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="daada-104">구문</span><span class="sxs-lookup"><span data-stu-id="daada-104">Syntax</span></span>  
  
```  
HRESULT SetCLRSyncManager (  
    [in] ICLRSyncManager *pManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="daada-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="daada-105">Parameters</span></span>  
 `pManager`  
 <span data-ttu-id="daada-106">[in] 에 대 한 포인터는 `ICLRSyncManager` 인스턴스는 CLR (공용 언어 런타임)에서 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="daada-106">[in] A pointer to an `ICLRSyncManager` instance supplied by the common language runtime (CLR).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="daada-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="daada-107">Return Value</span></span>  
  
|<span data-ttu-id="daada-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="daada-108">HRESULT</span></span>|<span data-ttu-id="daada-109">설명</span><span class="sxs-lookup"><span data-stu-id="daada-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="daada-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="daada-110">S_OK</span></span>|<span data-ttu-id="daada-111">`SetCLRSyncManager` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="daada-111">`SetCLRSyncManager` returned successfully.</span></span>|  
|<span data-ttu-id="daada-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="daada-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="daada-113">CLR이 로드 된 프로세스에 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="daada-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="daada-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="daada-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="daada-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="daada-115">The call timed out.</span></span>|  
|<span data-ttu-id="daada-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="daada-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="daada-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="daada-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="daada-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="daada-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="daada-119">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="daada-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="daada-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="daada-120">E_FAIL</span></span>|<span data-ttu-id="daada-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="daada-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="daada-122">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="daada-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="daada-123">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="daada-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="daada-124">설명</span><span class="sxs-lookup"><span data-stu-id="daada-124">Remarks</span></span>  
 <span data-ttu-id="daada-125">호스트와 CLR 간의 통신을 위해 일반적으로 호스팅 인터페이스는 쌍으로 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="daada-125">To facilitate communication between the host and the CLR, hosting interfaces generally come in pairs.</span></span> <span data-ttu-id="daada-126">쌍의 한 구성원 호스트에 의해 구현 됩니다 하 고 다른 멤버가 CLR에 의해 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="daada-126">One member of the pair is implemented by the host, and the other member is implemented by the CLR.</span></span> <span data-ttu-id="daada-127">호스트 쪽 구현으로는 `IHostSyncManager` 에 해당 하는 인터페이스를 `ICLRSyncManager` CLR에 의해 구현 되는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="daada-127">As a host-side implementation, the `IHostSyncManager` interface corresponds to the `ICLRSyncManager` interface implemented by the CLR.</span></span> <span data-ttu-id="daada-128">CLR 호출 `SetCLRSyncManager` 제공 하는 `ICLRSyncManager` 호스트에 현재 연결에 대 한 인스턴스 `IHostSyncManager` 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="daada-128">The CLR calls `SetCLRSyncManager` to supply an `ICLRSyncManager` instance for the host to associate with the current `IHostSyncManager` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="daada-129">요구 사항</span><span class="sxs-lookup"><span data-stu-id="daada-129">Requirements</span></span>  
 <span data-ttu-id="daada-130">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="daada-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="daada-131">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="daada-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="daada-132">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="daada-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="daada-133">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="daada-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="daada-134">참고자료</span><span class="sxs-lookup"><span data-stu-id="daada-134">See also</span></span>
- [<span data-ttu-id="daada-135">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="daada-135">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="daada-136">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="daada-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
