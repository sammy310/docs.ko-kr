---
title: IHostTaskManager::BeginThreadAffinity 메서드
ms.date: 03/30/2017
api_name:
- IHostTaskManager.BeginThreadAffinity
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::BeginThreadAffinity
helpviewer_keywords:
- IHostTaskManager::BeginThreadAffinity method [.NET Framework hosting]
- BeginThreadAffinity method [.NET Framework hosting]
ms.assetid: fea3ab88-ce41-4c5a-847b-bb78cd748da6
topic_type:
- apiref
ms.openlocfilehash: 6f6d57a52d960c975d468f370477b5d7e29c3aa2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727343"
---
# <a name="ihosttaskmanagerbeginthreadaffinity-method"></a><span data-ttu-id="02092-102">IHostTaskManager::BeginThreadAffinity 메서드</span><span class="sxs-lookup"><span data-stu-id="02092-102">IHostTaskManager::BeginThreadAffinity Method</span></span>

<span data-ttu-id="02092-103">관리 코드에서 현재 작업을 다른 운영 체제 스레드로 이동 하지 않아야 하는 기간이 입력 되었음을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="02092-103">Notifies the host that managed code is entering a period in which the current task must not be moved to another operating system thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02092-104">구문</span><span class="sxs-lookup"><span data-stu-id="02092-104">Syntax</span></span>  
  
```cpp  
HRESULT BeginThreadAffinity ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="02092-105">Return Value</span><span class="sxs-lookup"><span data-stu-id="02092-105">Return Value</span></span>  
  
|<span data-ttu-id="02092-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="02092-106">HRESULT</span></span>|<span data-ttu-id="02092-107">설명</span><span class="sxs-lookup"><span data-stu-id="02092-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="02092-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="02092-108">S_OK</span></span>|<span data-ttu-id="02092-109">`BeginThreadAffinity` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="02092-109">`BeginThreadAffinity` returned successfully.</span></span>|  
|<span data-ttu-id="02092-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="02092-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="02092-111">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02092-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="02092-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="02092-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="02092-113">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="02092-113">The call timed out.</span></span>|  
|<span data-ttu-id="02092-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="02092-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="02092-115">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="02092-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="02092-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="02092-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="02092-117">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="02092-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="02092-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="02092-118">E_FAIL</span></span>|<span data-ttu-id="02092-119">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="02092-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="02092-120">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="02092-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="02092-121">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="02092-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="02092-122">설명</span><span class="sxs-lookup"><span data-stu-id="02092-122">Remarks</span></span>  

 <span data-ttu-id="02092-123">일반적으로 CLR은 `IHostTaskManager::BeginThreadAffinity` 에 대 한 호출 컨텍스트에서를 호출 <xref:System.Threading.Thread.BeginThreadAffinity%2A?displayProperty=nameWithType> 합니다.</span><span class="sxs-lookup"><span data-stu-id="02092-123">The CLR typically calls `IHostTaskManager::BeginThreadAffinity` in the context of a call to <xref:System.Threading.Thread.BeginThreadAffinity%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="02092-124">[IHostTaskManager:: EndThreadAffinity](ihosttaskmanager-endthreadaffinity-method.md)에 대해 해당 호출이 수행 될 때까지 현재 작업을 다시 예약 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="02092-124">The current task must not be rescheduled until a corresponding call is made to [IHostTaskManager::EndThreadAffinity](ihosttaskmanager-endthreadaffinity-method.md).</span></span> <span data-ttu-id="02092-125">작업은 전환할 수 있지만 다시 전환 되는 경우 전환 된 것과 동일한 운영 체제 스레드에 할당 되어야 합니다. `BeginThreadAffinity` 호출이 현재 작업을 참조 하기 때문에에 대 한 중첩 호출은 효과가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="02092-125">Tasks can be switched out, but when they are switched back in, they must be assigned to the same operating system thread from which they were switched out. Nested calls to `BeginThreadAffinity` have no effect, because the call refers to the current task.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02092-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="02092-126">Requirements</span></span>  

 <span data-ttu-id="02092-127">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="02092-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02092-128">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="02092-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="02092-129">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="02092-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="02092-130">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02092-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02092-131">참조</span><span class="sxs-lookup"><span data-stu-id="02092-131">See also</span></span>

- [<span data-ttu-id="02092-132">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="02092-132">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="02092-133">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="02092-133">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="02092-134">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="02092-134">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="02092-135">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="02092-135">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
