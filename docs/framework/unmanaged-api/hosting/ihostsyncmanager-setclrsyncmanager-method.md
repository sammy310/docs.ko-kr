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
ms.openlocfilehash: 9c08a790d4dad748e5d09271bd870add22255b4a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132616"
---
# <a name="ihostsyncmanagersetclrsyncmanager-method"></a><span data-ttu-id="5bb99-102">IHostSyncManager::SetCLRSyncManager 메서드</span><span class="sxs-lookup"><span data-stu-id="5bb99-102">IHostSyncManager::SetCLRSyncManager Method</span></span>
<span data-ttu-id="5bb99-103">현재 [IHostSyncManager](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md) 인스턴스와 연결할 [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) 인스턴스를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bb99-103">Sets the [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) instance to associate with the current [IHostSyncManager](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5bb99-104">구문</span><span class="sxs-lookup"><span data-stu-id="5bb99-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCLRSyncManager (  
    [in] ICLRSyncManager *pManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5bb99-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5bb99-105">Parameters</span></span>  
 `pManager`  
 <span data-ttu-id="5bb99-106">진행 CLR (공용 언어 런타임)에서 제공 하는 `ICLRSyncManager` 인스턴스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5bb99-106">[in] A pointer to an `ICLRSyncManager` instance supplied by the common language runtime (CLR).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5bb99-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="5bb99-107">Return Value</span></span>  
  
|<span data-ttu-id="5bb99-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5bb99-108">HRESULT</span></span>|<span data-ttu-id="5bb99-109">설명</span><span class="sxs-lookup"><span data-stu-id="5bb99-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5bb99-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="5bb99-110">S_OK</span></span>|<span data-ttu-id="5bb99-111">`SetCLRSyncManager` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5bb99-111">`SetCLRSyncManager` returned successfully.</span></span>|  
|<span data-ttu-id="5bb99-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5bb99-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5bb99-113">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bb99-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5bb99-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5bb99-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5bb99-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5bb99-115">The call timed out.</span></span>|  
|<span data-ttu-id="5bb99-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5bb99-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5bb99-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5bb99-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5bb99-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5bb99-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5bb99-119">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="5bb99-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5bb99-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5bb99-120">E_FAIL</span></span>|<span data-ttu-id="5bb99-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="5bb99-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5bb99-122">메서드가 E_FAIL을 반환 하는 경우 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5bb99-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5bb99-123">호스팅 메서드에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bb99-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5bb99-124">주의</span><span class="sxs-lookup"><span data-stu-id="5bb99-124">Remarks</span></span>  
 <span data-ttu-id="5bb99-125">호스트와 CLR 간의 통신을 용이 하 게 하기 위해 호스팅 인터페이스는 일반적으로 쌍으로 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5bb99-125">To facilitate communication between the host and the CLR, hosting interfaces generally come in pairs.</span></span> <span data-ttu-id="5bb99-126">이 쌍의 멤버 중 하나는 호스트에 의해 구현 되 고 다른 멤버는 CLR에 의해 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5bb99-126">One member of the pair is implemented by the host, and the other member is implemented by the CLR.</span></span> <span data-ttu-id="5bb99-127">호스트 쪽 구현에서는 `IHostSyncManager` 인터페이스가 CLR에서 구현 하는 `ICLRSyncManager` 인터페이스에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bb99-127">As a host-side implementation, the `IHostSyncManager` interface corresponds to the `ICLRSyncManager` interface implemented by the CLR.</span></span> <span data-ttu-id="5bb99-128">CLR은 `SetCLRSyncManager`를 호출 하 여 현재 `IHostSyncManager` 인스턴스와 연결할 호스트의 `ICLRSyncManager` 인스턴스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bb99-128">The CLR calls `SetCLRSyncManager` to supply an `ICLRSyncManager` instance for the host to associate with the current `IHostSyncManager` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5bb99-129">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5bb99-129">Requirements</span></span>  
 <span data-ttu-id="5bb99-130">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5bb99-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5bb99-131">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="5bb99-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5bb99-132">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5bb99-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5bb99-133">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5bb99-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bb99-134">참조</span><span class="sxs-lookup"><span data-stu-id="5bb99-134">See also</span></span>

- [<span data-ttu-id="5bb99-135">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5bb99-135">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="5bb99-136">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5bb99-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
