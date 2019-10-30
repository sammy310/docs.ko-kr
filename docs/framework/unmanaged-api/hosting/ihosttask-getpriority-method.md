---
title: IHostTask::GetPriority 메서드
ms.date: 03/30/2017
api_name:
- IHostTask.GetPriority
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::GetPriority
helpviewer_keywords:
- GetPriority method [.NET Framework hosting]
- IHostTask::GetPriority method [.NET Framework hosting]
ms.assetid: 4b463cd6-77c1-4f9a-8518-346ad8fc4b70
topic_type:
- apiref
ms.openlocfilehash: 6c33fa6d2e6cb09f013c5334461e61235db549f7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121415"
---
# <a name="ihosttaskgetpriority-method"></a><span data-ttu-id="6993a-102">IHostTask::GetPriority 메서드</span><span class="sxs-lookup"><span data-stu-id="6993a-102">IHostTask::GetPriority Method</span></span>
<span data-ttu-id="6993a-103">현재 [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) 인스턴스가 나타내는 작업의 스레드 우선 순위 수준을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6993a-103">Gets the thread priority level of the task represented by the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6993a-104">구문</span><span class="sxs-lookup"><span data-stu-id="6993a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPriority (  
    [out] int *pPriority  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6993a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6993a-105">Parameters</span></span>  
 `pPriority`  
 <span data-ttu-id="6993a-106">제한이 현재 `IHostTask` 인스턴스로 표시 되는 작업의 스레드 우선 순위 수준을 나타내는 정수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6993a-106">[out] A pointer to an integer that indicates the thread priority level of the task represented by the current `IHostTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6993a-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="6993a-107">Return Value</span></span>  
  
|<span data-ttu-id="6993a-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6993a-108">HRESULT</span></span>|<span data-ttu-id="6993a-109">설명</span><span class="sxs-lookup"><span data-stu-id="6993a-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6993a-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="6993a-110">S_OK</span></span>|<span data-ttu-id="6993a-111">`GetPriority` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6993a-111">`GetPriority` returned successfully.</span></span>|  
|<span data-ttu-id="6993a-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6993a-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6993a-113">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6993a-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6993a-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6993a-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6993a-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6993a-115">The call timed out.</span></span>|  
|<span data-ttu-id="6993a-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6993a-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6993a-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6993a-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6993a-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6993a-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6993a-119">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="6993a-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6993a-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6993a-120">E_FAIL</span></span>|<span data-ttu-id="6993a-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="6993a-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6993a-122">메서드가 E_FAIL을 반환 하는 경우 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6993a-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6993a-123">호스팅 메서드에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6993a-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6993a-124">주의</span><span class="sxs-lookup"><span data-stu-id="6993a-124">Remarks</span></span>  
 <span data-ttu-id="6993a-125">스레드 우선 순위 수준 값은 Win32 `SetThreadPriority` 함수에 의해 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6993a-125">Thread priority level values are defined by the Win32 `SetThreadPriority` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6993a-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6993a-126">Requirements</span></span>  
 <span data-ttu-id="6993a-127">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6993a-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6993a-128">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="6993a-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6993a-129">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6993a-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6993a-130">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6993a-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6993a-131">참조</span><span class="sxs-lookup"><span data-stu-id="6993a-131">See also</span></span>

- [<span data-ttu-id="6993a-132">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6993a-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="6993a-133">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6993a-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="6993a-134">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6993a-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="6993a-135">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6993a-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
