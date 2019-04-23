---
title: ICLRTask::LocksHeld 메서드
ms.date: 03/30/2017
api_name:
- ICLRTask.LocksHeld
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::LocksHeld
helpviewer_keywords:
- LocksHeld method [.NET Framework hosting]
- ICLRTask::LocksHeld method [.NET Framework hosting]
ms.assetid: e88a4dc3-02cc-4703-a474-292b71c40657
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3f548d8b19a76aaccbae276dd63f091e4488690b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59106810"
---
# <a name="iclrtasklocksheld-method"></a><span data-ttu-id="03d78-102">ICLRTask::LocksHeld 메서드</span><span class="sxs-lookup"><span data-stu-id="03d78-102">ICLRTask::LocksHeld Method</span></span>
<span data-ttu-id="03d78-103">작업에서 현재 보유 중인 잠금 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="03d78-103">Gets the number of locks currently held on the task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03d78-104">구문</span><span class="sxs-lookup"><span data-stu-id="03d78-104">Syntax</span></span>  
  
```  
HRESULT LocksHeld (  
    [out] SIZE_T *pLockCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="03d78-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="03d78-105">Parameters</span></span>  
 `pLockCount`  
 <span data-ttu-id="03d78-106">[out] 메서드 호출 시 태스크에 보유 한 잠금 횟수입니다.</span><span class="sxs-lookup"><span data-stu-id="03d78-106">[out] The number of locks held on the task at the time of the method call.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="03d78-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="03d78-107">Return Value</span></span>  
  
|<span data-ttu-id="03d78-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="03d78-108">HRESULT</span></span>|<span data-ttu-id="03d78-109">설명</span><span class="sxs-lookup"><span data-stu-id="03d78-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="03d78-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="03d78-110">S_OK</span></span>|<span data-ttu-id="03d78-111">`LocksHeld` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="03d78-111">`LocksHeld` returned successfully.</span></span>|  
|<span data-ttu-id="03d78-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="03d78-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="03d78-113">프로세스에는 CLR (공용 언어 런타임)에 로드 되지 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="03d78-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="03d78-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="03d78-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="03d78-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="03d78-115">The call timed out.</span></span>|  
|<span data-ttu-id="03d78-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="03d78-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="03d78-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="03d78-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="03d78-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="03d78-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="03d78-119">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03d78-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="03d78-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="03d78-120">E_FAIL</span></span>|<span data-ttu-id="03d78-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="03d78-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="03d78-122">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="03d78-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="03d78-123">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="03d78-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="03d78-124">요구 사항</span><span class="sxs-lookup"><span data-stu-id="03d78-124">Requirements</span></span>  
 <span data-ttu-id="03d78-125">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="03d78-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="03d78-126">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="03d78-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="03d78-127">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="03d78-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="03d78-128">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="03d78-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03d78-129">참고자료</span><span class="sxs-lookup"><span data-stu-id="03d78-129">See also</span></span>

- [<span data-ttu-id="03d78-130">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="03d78-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="03d78-131">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="03d78-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="03d78-132">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="03d78-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="03d78-133">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="03d78-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
