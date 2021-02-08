---
description: '자세한 정보: IHostTask:: SetCLRTask 메서드'
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
ms.openlocfilehash: 381b7827f043b6ef1d4a6698f5eb103233c9af55
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784680"
---
# <a name="ihosttasksetclrtask-method"></a><span data-ttu-id="56ba0-103">IHostTask::SetCLRTask 메서드</span><span class="sxs-lookup"><span data-stu-id="56ba0-103">IHostTask::SetCLRTask Method</span></span>

<span data-ttu-id="56ba0-104">인스턴스를 `ICLRTask` 현재 [IHostTask](ihosttask-interface.md) 인스턴스와 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="56ba0-104">Associates an `ICLRTask` instance with the current [IHostTask](ihosttask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56ba0-105">구문</span><span class="sxs-lookup"><span data-stu-id="56ba0-105">Syntax</span></span>  
  
```cpp  
HRESULT SetCLRTask (  
    [in] ICLRTask *pCLRTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="56ba0-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="56ba0-106">Parameters</span></span>  

 `pCLRTask`  
 <span data-ttu-id="56ba0-107">진행 `ICLRTask` 현재 인스턴스와 연결할 인스턴스에 대 한 인터페이스 포인터 `IHostTask` 입니다.</span><span class="sxs-lookup"><span data-stu-id="56ba0-107">[in] An interface pointer to the `ICLRTask` instance to be associated with the current `IHostTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="56ba0-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="56ba0-108">Return Value</span></span>  
  
|<span data-ttu-id="56ba0-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="56ba0-109">HRESULT</span></span>|<span data-ttu-id="56ba0-110">설명</span><span class="sxs-lookup"><span data-stu-id="56ba0-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="56ba0-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="56ba0-111">S_OK</span></span>|<span data-ttu-id="56ba0-112">`SetCLRTask` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="56ba0-112">`SetCLRTask` returned successfully.</span></span>|  
|<span data-ttu-id="56ba0-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="56ba0-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="56ba0-114">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56ba0-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="56ba0-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="56ba0-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="56ba0-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="56ba0-116">The call timed out.</span></span>|  
|<span data-ttu-id="56ba0-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="56ba0-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="56ba0-118">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="56ba0-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="56ba0-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="56ba0-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="56ba0-120">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="56ba0-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="56ba0-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="56ba0-121">E_FAIL</span></span>|<span data-ttu-id="56ba0-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="56ba0-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="56ba0-123">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="56ba0-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="56ba0-124">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="56ba0-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="56ba0-125">설명</span><span class="sxs-lookup"><span data-stu-id="56ba0-125">Remarks</span></span>  

 <span data-ttu-id="56ba0-126">CLR은를 호출 `SetCLRTask` 하 여 `ICLRTask` 인스턴스를 현재 `IHostTask` 인스턴스와 연결 합니다 .이 인스턴스는 [IHostTaskManager:: createtask](ihosttaskmanager-createtask-method.md)를 호출 하 여 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="56ba0-126">The CLR calls `SetCLRTask` to associate an `ICLRTask` instance with the current `IHostTask` instance, which was created by a call to [IHostTaskManager::CreateTask](ihosttaskmanager-createtask-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="56ba0-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="56ba0-127">Requirements</span></span>  

 <span data-ttu-id="56ba0-128">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="56ba0-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="56ba0-129">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="56ba0-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="56ba0-130">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="56ba0-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="56ba0-131">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="56ba0-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56ba0-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="56ba0-132">See also</span></span>

- [<span data-ttu-id="56ba0-133">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="56ba0-133">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="56ba0-134">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="56ba0-134">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="56ba0-135">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="56ba0-135">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="56ba0-136">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="56ba0-136">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
