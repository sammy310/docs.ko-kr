---
description: '자세히 알아보기: IHostGCManager:: ThreadIsBlockingForSuspension 메서드'
title: IHostGCManager::ThreadIsBlockingForSuspension 메서드
ms.date: 03/30/2017
api_name:
- IHostGCManager.ThreadIsBlockingForSuspension
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostGCManager::ThreadIsBlockingForSuspension
helpviewer_keywords:
- IHostGCManager::ThreadIsBlockingForSuspension method [.NET Framework hosting]
- ThreadIsBlockingForSuspension method [.NET Framework hosting]
ms.assetid: 2657d45d-26d2-4d0a-8473-32b652e3321d
topic_type:
- apiref
ms.openlocfilehash: 9cb07b80fa9aad1ac289bc5a3abb5a4760f2bfc9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99708641"
---
# <a name="ihostgcmanagerthreadisblockingforsuspension-method"></a><span data-ttu-id="28d2b-103">IHostGCManager::ThreadIsBlockingForSuspension 메서드</span><span class="sxs-lookup"><span data-stu-id="28d2b-103">IHostGCManager::ThreadIsBlockingForSuspension Method</span></span>

<span data-ttu-id="28d2b-104">메서드 호출이 수행 된 스레드가 가비지 컬렉션에 대해 차단 하려고 함을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="28d2b-104">Notifies the host that the thread from which the method call was made is about to block for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28d2b-105">구문</span><span class="sxs-lookup"><span data-stu-id="28d2b-105">Syntax</span></span>  
  
```cpp  
HRESULT ThreadIsBlockingForSuspension ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="28d2b-106">Return Value</span><span class="sxs-lookup"><span data-stu-id="28d2b-106">Return Value</span></span>  
  
|<span data-ttu-id="28d2b-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="28d2b-107">HRESULT</span></span>|<span data-ttu-id="28d2b-108">설명</span><span class="sxs-lookup"><span data-stu-id="28d2b-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="28d2b-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="28d2b-109">S_OK</span></span>|<span data-ttu-id="28d2b-110">`ThreadIsBlockingForSuspension` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="28d2b-110">`ThreadIsBlockingForSuspension` returned successfully.</span></span>|  
|<span data-ttu-id="28d2b-111">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="28d2b-111">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="28d2b-112">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28d2b-112">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="28d2b-113">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="28d2b-113">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="28d2b-114">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="28d2b-114">The call timed out.</span></span>|  
|<span data-ttu-id="28d2b-115">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="28d2b-115">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="28d2b-116">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="28d2b-116">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="28d2b-117">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="28d2b-117">HOST_E_ABANDONED</span></span>|<span data-ttu-id="28d2b-118">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="28d2b-118">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="28d2b-119">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="28d2b-119">E_FAIL</span></span>|<span data-ttu-id="28d2b-120">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="28d2b-120">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="28d2b-121">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="28d2b-121">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="28d2b-122">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="28d2b-122">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="28d2b-123">설명</span><span class="sxs-lookup"><span data-stu-id="28d2b-123">Remarks</span></span>  

 <span data-ttu-id="28d2b-124">CLR은 일반적으로 `ThreadIsBlockForSuspension` 가비지 수집을 준비 하는 메서드를 호출 하 여 호스트에 관리 되지 않는 작업에 대 한 스레드를 다시 예약할 수 있는 기회를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="28d2b-124">The CLR typically calls the `ThreadIsBlockForSuspension` method in preparation for a garbage collection, to give the host an opportunity to reschedule the thread for unmanaged tasks.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="28d2b-125">호스트는를 호출한 후에만 작업을 다시 예약할 수 있습니다 `ThreadIsBlockingForSuspension` .</span><span class="sxs-lookup"><span data-stu-id="28d2b-125">The host can reschedule tasks only after a call to `ThreadIsBlockingForSuspension`.</span></span> <span data-ttu-id="28d2b-126">런타임에서 [SuspensionStarting](ihostgcmanager-suspensionstarting-method.md)를 호출한 후에는 호스트에서 작업을 다시 예약 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="28d2b-126">After the runtime calls [SuspensionStarting](ihostgcmanager-suspensionstarting-method.md), the host must not reschedule a task.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28d2b-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="28d2b-127">Requirements</span></span>  

 <span data-ttu-id="28d2b-128">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="28d2b-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28d2b-129">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="28d2b-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="28d2b-130">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="28d2b-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="28d2b-131">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28d2b-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28d2b-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="28d2b-132">See also</span></span>

- [<span data-ttu-id="28d2b-133">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="28d2b-133">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="28d2b-134">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="28d2b-134">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="28d2b-135">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="28d2b-135">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="28d2b-136">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="28d2b-136">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="28d2b-137">IHostGCManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="28d2b-137">IHostGCManager Interface</span></span>](ihostgcmanager-interface.md)
