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
ms.openlocfilehash: a57610d1b41d80d54a245b9744aafd78a1e88177
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73195902"
---
# <a name="iclrtaskmanagergetcurrenttask-method"></a><span data-ttu-id="c332b-102">ICLRTaskManager::GetCurrentTask 메서드</span><span class="sxs-lookup"><span data-stu-id="c332b-102">ICLRTaskManager::GetCurrentTask Method</span></span>
<span data-ttu-id="c332b-103">메서드 호출이 시작 된 운영 체제 스레드에서 현재 실행 중인 [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c332b-103">Gets the [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance that is currently running on the operating system thread from which the method call originated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c332b-104">구문</span><span class="sxs-lookup"><span data-stu-id="c332b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentTask (  
    [out] ICLRTask **ppTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c332b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c332b-105">Parameters</span></span>  
 `ppTask`  
 <span data-ttu-id="c332b-106">제한이 호출이 시작 된 운영 체제 스레드에서 현재 실행 중인 `ICLRTask` 인스턴스의 주소에 대 한 포인터 이거나,이 스레드에서 현재 실행 중인 작업이 없는 경우 null입니다.</span><span class="sxs-lookup"><span data-stu-id="c332b-106">[out] A pointer to the address of an `ICLRTask` instance that is currently executing on the operating system thread from which the call originated, or null if no task is currently executing on this thread.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c332b-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="c332b-107">Return Value</span></span>  
  
|<span data-ttu-id="c332b-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c332b-108">HRESULT</span></span>|<span data-ttu-id="c332b-109">설명</span><span class="sxs-lookup"><span data-stu-id="c332b-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c332b-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="c332b-110">S_OK</span></span>|<span data-ttu-id="c332b-111">메서드가 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c332b-111">The method returned successfully.</span></span>|  
|<span data-ttu-id="c332b-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c332b-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c332b-113">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c332b-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c332b-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c332b-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c332b-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c332b-115">The call timed out.</span></span>|  
|<span data-ttu-id="c332b-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c332b-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c332b-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c332b-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c332b-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c332b-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c332b-119">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c332b-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c332b-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c332b-120">E_FAIL</span></span>|<span data-ttu-id="c332b-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c332b-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c332b-122">메서드가 E_FAIL을 반환 하는 경우 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c332b-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c332b-123">호스팅 메서드에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c332b-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c332b-124">주의</span><span class="sxs-lookup"><span data-stu-id="c332b-124">Remarks</span></span>  
 <span data-ttu-id="c332b-125">`ppTask` 매개 변수가 가리키는 `ICLRTask` 인스턴스는 CLR에 대해 현재 실행 중인 작업을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c332b-125">The `ICLRTask` instance that the `ppTask` parameter points to represents the currently executing task for the CLR.</span></span> <span data-ttu-id="c332b-126">`ICLRTask` 인스턴스는 호스트의 작업을 나타내는 해당 [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) 인스턴스와 연결 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c332b-126">The `ICLRTask` instance is associated with a corresponding [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance that represents the task for the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c332b-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c332b-127">Requirements</span></span>  
 <span data-ttu-id="c332b-128">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c332b-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c332b-129">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="c332b-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c332b-130">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c332b-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c332b-131">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c332b-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c332b-132">참조</span><span class="sxs-lookup"><span data-stu-id="c332b-132">See also</span></span>

- [<span data-ttu-id="c332b-133">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c332b-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="c332b-134">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c332b-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="c332b-135">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c332b-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="c332b-136">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c332b-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
