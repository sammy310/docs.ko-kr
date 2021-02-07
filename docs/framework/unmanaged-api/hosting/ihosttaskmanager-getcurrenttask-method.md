---
description: '자세히 알아보기: IHostTaskManager:: GetCurrentTask 메서드'
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
ms.openlocfilehash: 7e7e516fe4a706fce8b0302f318cfbb164a86eea
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753811"
---
# <a name="ihosttaskmanagergetcurrenttask-method"></a><span data-ttu-id="46efa-103">IHostTaskManager::GetCurrentTask 메서드</span><span class="sxs-lookup"><span data-stu-id="46efa-103">IHostTaskManager::GetCurrentTask Method</span></span>

<span data-ttu-id="46efa-104">이 호출이 수행 되는 운영 체제 스레드에서 현재 실행 중인 작업에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="46efa-104">Gets an interface pointer to the task that is currently executing on the operating system thread from which this call is made.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46efa-105">구문</span><span class="sxs-lookup"><span data-stu-id="46efa-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentTask (  
    [out] IHostTask **pTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="46efa-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="46efa-106">Parameters</span></span>  

 `pTask`  
 <span data-ttu-id="46efa-107">제한이 현재 실행 중인 작업을 나타내는 [IHostTask](ihosttask-interface.md) 인스턴스의 주소에 대 한 포인터 이거나 현재 실행 중인 태스크가 없는 경우 null입니다.</span><span class="sxs-lookup"><span data-stu-id="46efa-107">[out] A pointer to the address of an [IHostTask](ihosttask-interface.md) instance that represents the currently executing task, or null, if no task is currently executing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="46efa-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="46efa-108">Return Value</span></span>  
  
|<span data-ttu-id="46efa-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="46efa-109">HRESULT</span></span>|<span data-ttu-id="46efa-110">설명</span><span class="sxs-lookup"><span data-stu-id="46efa-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="46efa-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="46efa-111">S_OK</span></span>|<span data-ttu-id="46efa-112">`GetCurrentTask` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="46efa-112">`GetCurrentTask` returned successfully.</span></span>|  
|<span data-ttu-id="46efa-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="46efa-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="46efa-114">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46efa-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="46efa-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="46efa-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="46efa-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="46efa-116">The call timed out.</span></span>|  
|<span data-ttu-id="46efa-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="46efa-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="46efa-118">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="46efa-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="46efa-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="46efa-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="46efa-120">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="46efa-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="46efa-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="46efa-121">E_FAIL</span></span>|<span data-ttu-id="46efa-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="46efa-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="46efa-123">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="46efa-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="46efa-124">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="46efa-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="46efa-125">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="46efa-125">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="46efa-126">`GetCurrentTask` 는 호스트의 제어 외부에 있는 운영 체제 스레드에서 호출 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="46efa-126">`GetCurrentTask` was called on an operating system thread outside the control of the host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="46efa-127">설명</span><span class="sxs-lookup"><span data-stu-id="46efa-127">Remarks</span></span>  

 <span data-ttu-id="46efa-128">또한 호스트는 `pTask` 매개 변수를 null로 설정 하 여 CLR에서 시작 하지 않은 작업을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46efa-128">The host can also set the `pTask` parameter to null to prevent a task that it did not initiate from entering the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46efa-129">요구 사항</span><span class="sxs-lookup"><span data-stu-id="46efa-129">Requirements</span></span>  

 <span data-ttu-id="46efa-130">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="46efa-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46efa-131">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="46efa-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="46efa-132">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="46efa-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="46efa-133">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="46efa-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46efa-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="46efa-134">See also</span></span>

- [<span data-ttu-id="46efa-135">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="46efa-135">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="46efa-136">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="46efa-136">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="46efa-137">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="46efa-137">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="46efa-138">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="46efa-138">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
