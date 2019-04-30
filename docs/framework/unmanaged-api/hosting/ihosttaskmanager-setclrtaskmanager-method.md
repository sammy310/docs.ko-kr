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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 283e390b024fd1d0d6a51659b67eff82477fc64d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62043604"
---
# <a name="ihosttaskmanagersetclrtaskmanager-method"></a><span data-ttu-id="8a480-102">IHostTaskManager::SetCLRTaskManager 메서드</span><span class="sxs-lookup"><span data-stu-id="8a480-102">IHostTaskManager::SetCLRTaskManager Method</span></span>
<span data-ttu-id="8a480-103">호스트에 대 한 인터페이스 포인터를 제공는 [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md) 인스턴스는 CLR (공용 언어 런타임)에 의해 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a480-103">Provides the host with an interface pointer to an [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md) instance implemented by the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a480-104">구문</span><span class="sxs-lookup"><span data-stu-id="8a480-104">Syntax</span></span>  
  
```  
HRESULT SetCLRTaskManager (  
    [in] ICLRTaskManager *pManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8a480-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8a480-105">Parameters</span></span>  
 `pManager`  
 <span data-ttu-id="8a480-106">[in] 에 대 한 포인터는 `ICLRTaskManager` 공용 언어 런타임에서 구현 되는 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="8a480-106">[in] A pointer to an `ICLRTaskManager` instance implemented by the common language runtime.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8a480-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="8a480-107">Return Value</span></span>  
  
|<span data-ttu-id="8a480-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8a480-108">HRESULT</span></span>|<span data-ttu-id="8a480-109">설명</span><span class="sxs-lookup"><span data-stu-id="8a480-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8a480-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="8a480-110">S_OK</span></span>|<span data-ttu-id="8a480-111">`SetCLRTaskManager` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a480-111">`SetCLRTaskManager` returned successfully.</span></span>|  
|<span data-ttu-id="8a480-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8a480-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8a480-113">CLR이 로드 된 프로세스에 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8a480-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8a480-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8a480-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8a480-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8a480-115">The call timed out.</span></span>|  
|<span data-ttu-id="8a480-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8a480-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8a480-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8a480-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8a480-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8a480-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8a480-119">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a480-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8a480-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8a480-120">E_FAIL</span></span>|<span data-ttu-id="8a480-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="8a480-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8a480-122">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8a480-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8a480-123">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a480-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8a480-124">설명</span><span class="sxs-lookup"><span data-stu-id="8a480-124">Remarks</span></span>  
 <span data-ttu-id="8a480-125">런타임 호출 `SetCLRTaskManager` 에 대 한 인터페이스 포인터를 사용 하 여 호스트를 제공 하는 `ICLRTaskManager` 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="8a480-125">The runtime calls `SetCLRTaskManager` to provide the host with an interface pointer to an `ICLRTaskManager` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a480-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8a480-126">Requirements</span></span>  
 <span data-ttu-id="8a480-127">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="8a480-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a480-128">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8a480-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8a480-129">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="8a480-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8a480-130">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a480-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a480-131">참고자료</span><span class="sxs-lookup"><span data-stu-id="8a480-131">See also</span></span>

- [<span data-ttu-id="8a480-132">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8a480-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="8a480-133">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8a480-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="8a480-134">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8a480-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="8a480-135">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8a480-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
