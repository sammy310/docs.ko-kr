---
title: IHostTaskManager::SetCLRTaskManager 메서드
ms.date: 03/30/2017
api_name:
- IHostTaskManager.SetCLRTaskManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::SetCLRTaskManager
helpviewer_keywords:
- IHostTaskManager::SetCLRTaskManager method [.NET Framework hosting]
- SetCLRTaskManager method [.NET Framework hosting]
ms.assetid: ec90ee83-bd4b-408b-9274-62a923ab86a1
topic_type:
- apiref
ms.openlocfilehash: c674cc43065bf8ea102bec1c5134757380454913
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141233"
---
# <a name="ihosttaskmanagersetclrtaskmanager-method"></a><span data-ttu-id="eeffc-102">IHostTaskManager::SetCLRTaskManager 메서드</span><span class="sxs-lookup"><span data-stu-id="eeffc-102">IHostTaskManager::SetCLRTaskManager Method</span></span>
<span data-ttu-id="eeffc-103">호스트에 CLR (공용 언어 런타임)에 의해 구현 된 [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md) 인스턴스에 대 한 인터페이스 포인터를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="eeffc-103">Provides the host with an interface pointer to an [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md) instance implemented by the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eeffc-104">구문</span><span class="sxs-lookup"><span data-stu-id="eeffc-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCLRTaskManager (  
    [in] ICLRTaskManager *pManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eeffc-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="eeffc-105">Parameters</span></span>  
 `pManager`  
 <span data-ttu-id="eeffc-106">진행 공용 언어 런타임에서 구현 하는 `ICLRTaskManager` 인스턴스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="eeffc-106">[in] A pointer to an `ICLRTaskManager` instance implemented by the common language runtime.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="eeffc-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="eeffc-107">Return Value</span></span>  
  
|<span data-ttu-id="eeffc-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="eeffc-108">HRESULT</span></span>|<span data-ttu-id="eeffc-109">설명</span><span class="sxs-lookup"><span data-stu-id="eeffc-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="eeffc-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="eeffc-110">S_OK</span></span>|<span data-ttu-id="eeffc-111">`SetCLRTaskManager` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="eeffc-111">`SetCLRTaskManager` returned successfully.</span></span>|  
|<span data-ttu-id="eeffc-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="eeffc-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="eeffc-113">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eeffc-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="eeffc-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="eeffc-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="eeffc-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="eeffc-115">The call timed out.</span></span>|  
|<span data-ttu-id="eeffc-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="eeffc-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="eeffc-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="eeffc-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="eeffc-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="eeffc-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="eeffc-119">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="eeffc-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="eeffc-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="eeffc-120">E_FAIL</span></span>|<span data-ttu-id="eeffc-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="eeffc-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="eeffc-122">메서드가 E_FAIL을 반환 하는 경우 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="eeffc-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="eeffc-123">호스팅 메서드에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="eeffc-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eeffc-124">주의</span><span class="sxs-lookup"><span data-stu-id="eeffc-124">Remarks</span></span>  
 <span data-ttu-id="eeffc-125">런타임은 `SetCLRTaskManager`를 호출 하 여 호스트에 `ICLRTaskManager` 인스턴스에 대 한 인터페이스 포인터를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="eeffc-125">The runtime calls `SetCLRTaskManager` to provide the host with an interface pointer to an `ICLRTaskManager` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eeffc-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="eeffc-126">Requirements</span></span>  
 <span data-ttu-id="eeffc-127">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="eeffc-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eeffc-128">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="eeffc-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="eeffc-129">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eeffc-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="eeffc-130">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eeffc-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eeffc-131">참조</span><span class="sxs-lookup"><span data-stu-id="eeffc-131">See also</span></span>

- [<span data-ttu-id="eeffc-132">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="eeffc-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="eeffc-133">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="eeffc-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="eeffc-134">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="eeffc-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="eeffc-135">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="eeffc-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
