---
title: ICLRTaskManager::GetCurrentTask 메서드
ms.date: 03/30/2017
api_name:
- ICLRTaskManager.GetCurrentTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager::GetCurrentTask
helpviewer_keywords:
- GetCurrentTask method, ICLRTaskManager interface [.NET Framework hosting]
- ICLRTaskManager::GetCurrentTask method [.NET Framework hosting]
ms.assetid: c0b82a9f-edc6-4878-9c81-48de53c02142
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7db333cd97963ca8ef26673c0ba5cbf352fa331b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59165310"
---
# <a name="iclrtaskmanagergetcurrenttask-method"></a><span data-ttu-id="b4166-102">ICLRTaskManager::GetCurrentTask 메서드</span><span class="sxs-lookup"><span data-stu-id="b4166-102">ICLRTaskManager::GetCurrentTask Method</span></span>
<span data-ttu-id="b4166-103">가져옵니다 합니다 [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) 메서드 호출을 시작 하는 운영 체제 스레드에서 현재 실행 중인 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="b4166-103">Gets the [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance that is currently running on the operating system thread from which the method call originated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4166-104">구문</span><span class="sxs-lookup"><span data-stu-id="b4166-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentTask (  
    [out] ICLRTask **ppTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b4166-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b4166-105">Parameters</span></span>  
 `ppTask`  
 <span data-ttu-id="b4166-106">[out] 주소에 대 한 포인터는 `ICLRTask` , 호출을 시작 하는 운영 체제 스레드에서 현재 실행 중인 인스턴스 또는 작업이 아닙니다는 현재이 스레드에서 실행 중인 경우 null입니다.</span><span class="sxs-lookup"><span data-stu-id="b4166-106">[out] A pointer to the address of an `ICLRTask` instance that is currently executing on the operating system thread from which the call originated, or null if no task is currently executing on this thread.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b4166-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="b4166-107">Return Value</span></span>  
  
|<span data-ttu-id="b4166-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b4166-108">HRESULT</span></span>|<span data-ttu-id="b4166-109">설명</span><span class="sxs-lookup"><span data-stu-id="b4166-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b4166-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="b4166-110">S_OK</span></span>|<span data-ttu-id="b4166-111">메서드가 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4166-111">The method returned successfully.</span></span>|  
|<span data-ttu-id="b4166-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b4166-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b4166-113">프로세스에는 CLR (공용 언어 런타임)에 로드 되지 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b4166-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b4166-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b4166-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b4166-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b4166-115">The call timed out.</span></span>|  
|<span data-ttu-id="b4166-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b4166-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b4166-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b4166-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b4166-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b4166-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b4166-119">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4166-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b4166-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b4166-120">E_FAIL</span></span>|<span data-ttu-id="b4166-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="b4166-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b4166-122">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b4166-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b4166-123">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4166-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b4166-124">설명</span><span class="sxs-lookup"><span data-stu-id="b4166-124">Remarks</span></span>  
 <span data-ttu-id="b4166-125">합니다 `ICLRTask` 인스턴스는 `ppTask` 매개 변수가 가리키는 나타내는 현재 실행 중인 작업 CLR에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4166-125">The `ICLRTask` instance that the `ppTask` parameter points to represents the currently executing task for the CLR.</span></span> <span data-ttu-id="b4166-126">합니다 `ICLRTask` 인스턴스가 해당 연관 [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) 호스트에 대 한 작업을 나타내는 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="b4166-126">The `ICLRTask` instance is associated with a corresponding [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance that represents the task for the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4166-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b4166-127">Requirements</span></span>  
 <span data-ttu-id="b4166-128">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b4166-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4166-129">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b4166-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b4166-130">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="b4166-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b4166-131">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4166-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4166-132">참고자료</span><span class="sxs-lookup"><span data-stu-id="b4166-132">See also</span></span>

- [<span data-ttu-id="b4166-133">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b4166-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="b4166-134">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b4166-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="b4166-135">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b4166-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="b4166-136">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b4166-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
