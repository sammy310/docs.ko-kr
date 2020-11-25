---
title: IHostTaskManager::EndThreadAffinity 메서드
ms.date: 03/30/2017
api_name:
- IHostTaskManager.EndThreadAffinity
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::EndThreadAffinity
helpviewer_keywords:
- EndThreadAffinity method [.NET Framework hosting]
- IHostTaskManager::EndThreadAffinity method [.NET Framework hosting]
ms.assetid: 7738a904-0cd7-4fde-a3eb-2323a5533157
topic_type:
- apiref
ms.openlocfilehash: c662e242cf6745223b1e87716ce4f64971347d2a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731659"
---
# <a name="ihosttaskmanagerendthreadaffinity-method"></a><span data-ttu-id="76309-102">IHostTaskManager::EndThreadAffinity 메서드</span><span class="sxs-lookup"><span data-stu-id="76309-102">IHostTaskManager::EndThreadAffinity Method</span></span>

<span data-ttu-id="76309-103">이전에 [IHostTaskManager:: BeginThreadAffinity](ihosttaskmanager-beginthreadaffinity-method.md)를 호출한 후에 관리 코드가 현재 작업을 다른 운영 체제 스레드로 이동 하지 않아야 하는 기간을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="76309-103">Notifies the host that managed code is exiting the period in which the current task must not be moved to another operating system thread, following an earlier call to [IHostTaskManager::BeginThreadAffinity](ihosttaskmanager-beginthreadaffinity-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76309-104">구문</span><span class="sxs-lookup"><span data-stu-id="76309-104">Syntax</span></span>  
  
```cpp  
HRESULT EndThreadAffinity ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="76309-105">Return Value</span><span class="sxs-lookup"><span data-stu-id="76309-105">Return Value</span></span>  
  
|<span data-ttu-id="76309-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="76309-106">HRESULT</span></span>|<span data-ttu-id="76309-107">설명</span><span class="sxs-lookup"><span data-stu-id="76309-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="76309-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="76309-108">S_OK</span></span>|<span data-ttu-id="76309-109">`EndThreadAffinity` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="76309-109">`EndThreadAffinity` returned successfully.</span></span>|  
|<span data-ttu-id="76309-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="76309-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="76309-111">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76309-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="76309-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="76309-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="76309-113">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="76309-113">The call timed out.</span></span>|  
|<span data-ttu-id="76309-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="76309-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="76309-115">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="76309-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="76309-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="76309-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="76309-117">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="76309-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="76309-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="76309-118">E_FAIL</span></span>|<span data-ttu-id="76309-119">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="76309-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="76309-120">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="76309-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="76309-121">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="76309-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="76309-122">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="76309-122">E_UNEXPECTED</span></span>|<span data-ttu-id="76309-123">`EndThreadAffinity` 는에 대 한 이전 해당 호출 없이 호출 되었습니다 `BeginThreadAffinity` .</span><span class="sxs-lookup"><span data-stu-id="76309-123">`EndThreadAffinity` was called without an earlier corresponding call to `BeginThreadAffinity`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="76309-124">설명</span><span class="sxs-lookup"><span data-stu-id="76309-124">Remarks</span></span>  

 <span data-ttu-id="76309-125">CLR은를 `BeginThreadAffinity` 호출 하기 전에 현재 작업에 대해 해당 호출을 수행 `EndThreadAffinity` 합니다.</span><span class="sxs-lookup"><span data-stu-id="76309-125">The CLR makes a corresponding call to `BeginThreadAffinity` on the current task before calling `EndThreadAffinity`.</span></span> <span data-ttu-id="76309-126">이러한 상응 하는 호출이 없으면 호스트의 [IHostTaskManager](ihosttaskmanager-interface.md) 구현에서 E_UNEXPECTED을 반환 하 고 아무 작업도 수행 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76309-126">In the absence of such a corresponding call, the host's implementation of [IHostTaskManager](ihosttaskmanager-interface.md) should return E_UNEXPECTED, and take no action.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76309-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="76309-127">Requirements</span></span>  

 <span data-ttu-id="76309-128">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="76309-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76309-129">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="76309-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="76309-130">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="76309-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="76309-131">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76309-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76309-132">참조</span><span class="sxs-lookup"><span data-stu-id="76309-132">See also</span></span>

- <xref:System.Threading>
- [<span data-ttu-id="76309-133">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="76309-133">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="76309-134">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="76309-134">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="76309-135">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="76309-135">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="76309-136">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="76309-136">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
