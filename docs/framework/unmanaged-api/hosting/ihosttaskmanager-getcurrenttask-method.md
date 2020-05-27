---
title: IHostTaskManager::GetCurrentTask 메서드
ms.date: 03/30/2017
api_name:
- IHostTaskManager.GetCurrentTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::GetCurrentTask
helpviewer_keywords:
- GetCurrentTask method, IHostTaskManager interface [.NET Framework hosting]
- IHostTaskManager::GetCurrentTask method [.NET Framework hosting]
ms.assetid: f17bca49-90bd-4dee-a5e1-b9a57ea46f85
topic_type:
- apiref
ms.openlocfilehash: 874951d6b5efed0dc08e6d0e166962767e295c3e
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842051"
---
# <a name="ihosttaskmanagergetcurrenttask-method"></a><span data-ttu-id="baf17-102">IHostTaskManager::GetCurrentTask 메서드</span><span class="sxs-lookup"><span data-stu-id="baf17-102">IHostTaskManager::GetCurrentTask Method</span></span>
<span data-ttu-id="baf17-103">이 호출이 수행 되는 운영 체제 스레드에서 현재 실행 중인 작업에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="baf17-103">Gets an interface pointer to the task that is currently executing on the operating system thread from which this call is made.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="baf17-104">구문</span><span class="sxs-lookup"><span data-stu-id="baf17-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentTask (  
    [out] IHostTask **pTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="baf17-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="baf17-105">Parameters</span></span>  
 `pTask`  
 <span data-ttu-id="baf17-106">제한이 현재 실행 중인 작업을 나타내는 [IHostTask](ihosttask-interface.md) 인스턴스의 주소에 대 한 포인터 이거나 현재 실행 중인 태스크가 없는 경우 null입니다.</span><span class="sxs-lookup"><span data-stu-id="baf17-106">[out] A pointer to the address of an [IHostTask](ihosttask-interface.md) instance that represents the currently executing task, or null, if no task is currently executing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="baf17-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="baf17-107">Return Value</span></span>  
  
|<span data-ttu-id="baf17-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="baf17-108">HRESULT</span></span>|<span data-ttu-id="baf17-109">Description</span><span class="sxs-lookup"><span data-stu-id="baf17-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="baf17-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="baf17-110">S_OK</span></span>|<span data-ttu-id="baf17-111">`GetCurrentTask`성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="baf17-111">`GetCurrentTask` returned successfully.</span></span>|  
|<span data-ttu-id="baf17-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="baf17-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="baf17-113">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="baf17-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="baf17-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="baf17-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="baf17-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="baf17-115">The call timed out.</span></span>|  
|<span data-ttu-id="baf17-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="baf17-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="baf17-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="baf17-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="baf17-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="baf17-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="baf17-119">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="baf17-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="baf17-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="baf17-120">E_FAIL</span></span>|<span data-ttu-id="baf17-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="baf17-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="baf17-122">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="baf17-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="baf17-123">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="baf17-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="baf17-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="baf17-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="baf17-125">`GetCurrentTask`는 호스트의 제어 외부에 있는 운영 체제 스레드에서 호출 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="baf17-125">`GetCurrentTask` was called on an operating system thread outside the control of the host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="baf17-126">설명</span><span class="sxs-lookup"><span data-stu-id="baf17-126">Remarks</span></span>  
 <span data-ttu-id="baf17-127">또한 호스트는 `pTask` 매개 변수를 null로 설정 하 여 CLR에서 시작 하지 않은 작업을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="baf17-127">The host can also set the `pTask` parameter to null to prevent a task that it did not initiate from entering the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="baf17-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="baf17-128">Requirements</span></span>  
 <span data-ttu-id="baf17-129">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="baf17-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="baf17-130">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="baf17-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="baf17-131">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="baf17-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="baf17-132">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="baf17-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="baf17-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="baf17-133">See also</span></span>

- [<span data-ttu-id="baf17-134">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="baf17-134">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="baf17-135">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="baf17-135">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="baf17-136">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="baf17-136">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="baf17-137">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="baf17-137">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
