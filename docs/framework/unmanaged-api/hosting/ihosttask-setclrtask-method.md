---
title: IHostTask::SetCLRTask 메서드
ms.date: 03/30/2017
api_name:
- IHostTask.SetCLRTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::SetCLRTask
helpviewer_keywords:
- SetCLRTask method [.NET Framework hosting]
- IHostTask::SetCLRTask method [.NET Framework hosting]
ms.assetid: e9d39c80-41a1-49e7-bb5e-ea3433bfb5d7
topic_type:
- apiref
ms.openlocfilehash: e6b9a4015a6139d6c8d7101fa7811c7ad9134e4c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720466"
---
# <a name="ihosttasksetclrtask-method"></a><span data-ttu-id="8420b-102">IHostTask::SetCLRTask 메서드</span><span class="sxs-lookup"><span data-stu-id="8420b-102">IHostTask::SetCLRTask Method</span></span>

<span data-ttu-id="8420b-103">인스턴스를 `ICLRTask` 현재 [IHostTask](ihosttask-interface.md) 인스턴스와 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="8420b-103">Associates an `ICLRTask` instance with the current [IHostTask](ihosttask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8420b-104">구문</span><span class="sxs-lookup"><span data-stu-id="8420b-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCLRTask (  
    [in] ICLRTask *pCLRTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8420b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8420b-105">Parameters</span></span>  

 `pCLRTask`  
 <span data-ttu-id="8420b-106">진행 `ICLRTask` 현재 인스턴스와 연결할 인스턴스에 대 한 인터페이스 포인터 `IHostTask` 입니다.</span><span class="sxs-lookup"><span data-stu-id="8420b-106">[in] An interface pointer to the `ICLRTask` instance to be associated with the current `IHostTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8420b-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="8420b-107">Return Value</span></span>  
  
|<span data-ttu-id="8420b-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8420b-108">HRESULT</span></span>|<span data-ttu-id="8420b-109">설명</span><span class="sxs-lookup"><span data-stu-id="8420b-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8420b-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="8420b-110">S_OK</span></span>|<span data-ttu-id="8420b-111">`SetCLRTask` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8420b-111">`SetCLRTask` returned successfully.</span></span>|  
|<span data-ttu-id="8420b-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8420b-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8420b-113">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8420b-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8420b-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8420b-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8420b-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8420b-115">The call timed out.</span></span>|  
|<span data-ttu-id="8420b-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8420b-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8420b-117">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8420b-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8420b-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8420b-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8420b-119">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="8420b-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8420b-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8420b-120">E_FAIL</span></span>|<span data-ttu-id="8420b-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="8420b-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8420b-122">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8420b-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8420b-123">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8420b-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8420b-124">설명</span><span class="sxs-lookup"><span data-stu-id="8420b-124">Remarks</span></span>  

 <span data-ttu-id="8420b-125">CLR은를 호출 `SetCLRTask` 하 여 `ICLRTask` 인스턴스를 현재 `IHostTask` 인스턴스와 연결 합니다 .이 인스턴스는 [IHostTaskManager:: createtask](ihosttaskmanager-createtask-method.md)를 호출 하 여 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8420b-125">The CLR calls `SetCLRTask` to associate an `ICLRTask` instance with the current `IHostTask` instance, which was created by a call to [IHostTaskManager::CreateTask](ihosttaskmanager-createtask-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8420b-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8420b-126">Requirements</span></span>  

 <span data-ttu-id="8420b-127">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8420b-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8420b-128">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="8420b-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8420b-129">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8420b-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8420b-130">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8420b-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8420b-131">참조</span><span class="sxs-lookup"><span data-stu-id="8420b-131">See also</span></span>

- [<span data-ttu-id="8420b-132">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8420b-132">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="8420b-133">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8420b-133">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="8420b-134">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8420b-134">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="8420b-135">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8420b-135">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
