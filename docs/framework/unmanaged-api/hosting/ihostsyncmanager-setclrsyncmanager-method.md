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
ms.openlocfilehash: bbeae2561d2d340c1a7dfed38e740dcc6838e4da
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/22/2020
ms.locfileid: "83803102"
---
# <a name="ihostsyncmanagersetclrsyncmanager-method"></a><span data-ttu-id="87343-102">IHostSyncManager::SetCLRSyncManager 메서드</span><span class="sxs-lookup"><span data-stu-id="87343-102">IHostSyncManager::SetCLRSyncManager Method</span></span>
<span data-ttu-id="87343-103">현재 [IHostSyncManager](ihostsyncmanager-interface.md) 인스턴스와 연결할 [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) 인스턴스를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="87343-103">Sets the [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) instance to associate with the current [IHostSyncManager](ihostsyncmanager-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87343-104">구문</span><span class="sxs-lookup"><span data-stu-id="87343-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCLRSyncManager (  
    [in] ICLRSyncManager *pManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="87343-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="87343-105">Parameters</span></span>  
 `pManager`  
 <span data-ttu-id="87343-106">진행 `ICLRSyncManager`CLR (공용 언어 런타임)에서 제공 하는 인스턴스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="87343-106">[in] A pointer to an `ICLRSyncManager` instance supplied by the common language runtime (CLR).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="87343-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="87343-107">Return Value</span></span>  
  
|<span data-ttu-id="87343-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="87343-108">HRESULT</span></span>|<span data-ttu-id="87343-109">Description</span><span class="sxs-lookup"><span data-stu-id="87343-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="87343-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="87343-110">S_OK</span></span>|<span data-ttu-id="87343-111">`SetCLRSyncManager`성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="87343-111">`SetCLRSyncManager` returned successfully.</span></span>|  
|<span data-ttu-id="87343-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="87343-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="87343-113">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87343-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="87343-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="87343-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="87343-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="87343-115">The call timed out.</span></span>|  
|<span data-ttu-id="87343-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="87343-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="87343-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="87343-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="87343-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="87343-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="87343-119">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="87343-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="87343-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="87343-120">E_FAIL</span></span>|<span data-ttu-id="87343-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="87343-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="87343-122">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="87343-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="87343-123">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87343-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="87343-124">설명</span><span class="sxs-lookup"><span data-stu-id="87343-124">Remarks</span></span>  
 <span data-ttu-id="87343-125">호스트와 CLR 간의 통신을 용이 하 게 하기 위해 호스팅 인터페이스는 일반적으로 쌍으로 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87343-125">To facilitate communication between the host and the CLR, hosting interfaces generally come in pairs.</span></span> <span data-ttu-id="87343-126">이 쌍의 멤버 중 하나는 호스트에 의해 구현 되 고 다른 멤버는 CLR에 의해 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87343-126">One member of the pair is implemented by the host, and the other member is implemented by the CLR.</span></span> <span data-ttu-id="87343-127">호스트 쪽 구현에서는 `IHostSyncManager` 인터페이스가 `ICLRSyncManager` CLR에서 구현 하는 인터페이스에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="87343-127">As a host-side implementation, the `IHostSyncManager` interface corresponds to the `ICLRSyncManager` interface implemented by the CLR.</span></span> <span data-ttu-id="87343-128">CLR은 `SetCLRSyncManager` 를 호출 하 여 `ICLRSyncManager` 현재 인스턴스와 연결할 호스트에 대 한 인스턴스를 제공 합니다 `IHostSyncManager` .</span><span class="sxs-lookup"><span data-stu-id="87343-128">The CLR calls `SetCLRSyncManager` to supply an `ICLRSyncManager` instance for the host to associate with the current `IHostSyncManager` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87343-129">요구 사항</span><span class="sxs-lookup"><span data-stu-id="87343-129">Requirements</span></span>  
 <span data-ttu-id="87343-130">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="87343-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87343-131">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="87343-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="87343-132">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87343-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="87343-133">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87343-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87343-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="87343-134">See also</span></span>

- [<span data-ttu-id="87343-135">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="87343-135">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="87343-136">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="87343-136">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
