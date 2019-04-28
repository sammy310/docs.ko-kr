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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7eb5c7ec85c0adb301fb722155caaed3c14e0e19
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789469"
---
# <a name="ihosttaskmanagerbeginthreadaffinity-method"></a><span data-ttu-id="e53ff-102">IHostTaskManager::BeginThreadAffinity 메서드</span><span class="sxs-lookup"><span data-stu-id="e53ff-102">IHostTaskManager::BeginThreadAffinity Method</span></span>
<span data-ttu-id="e53ff-103">현재 작업 이동 하지 말아야 다른 운영 체제 스레드로 마침표를 입력 하는 관리 코드는 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="e53ff-103">Notifies the host that managed code is entering a period in which the current task must not be moved to another operating system thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e53ff-104">구문</span><span class="sxs-lookup"><span data-stu-id="e53ff-104">Syntax</span></span>  
  
```  
HRESULT BeginThreadAffinity ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="e53ff-105">반환 값</span><span class="sxs-lookup"><span data-stu-id="e53ff-105">Return Value</span></span>  
  
|<span data-ttu-id="e53ff-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e53ff-106">HRESULT</span></span>|<span data-ttu-id="e53ff-107">설명</span><span class="sxs-lookup"><span data-stu-id="e53ff-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e53ff-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="e53ff-108">S_OK</span></span>|<span data-ttu-id="e53ff-109">`BeginThreadAffinity` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e53ff-109">`BeginThreadAffinity` returned successfully.</span></span>|  
|<span data-ttu-id="e53ff-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e53ff-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e53ff-111">프로세스에는 CLR (공용 언어 런타임)에 로드 되지 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e53ff-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e53ff-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e53ff-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e53ff-113">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e53ff-113">The call timed out.</span></span>|  
|<span data-ttu-id="e53ff-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e53ff-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e53ff-115">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e53ff-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e53ff-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e53ff-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e53ff-117">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e53ff-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e53ff-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e53ff-118">E_FAIL</span></span>|<span data-ttu-id="e53ff-119">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="e53ff-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e53ff-120">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e53ff-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e53ff-121">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e53ff-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e53ff-122">설명</span><span class="sxs-lookup"><span data-stu-id="e53ff-122">Remarks</span></span>  
 <span data-ttu-id="e53ff-123">일반적으로 CLR에서 호출한 `IHostTaskManager::BeginThreadAffinity` 에 대 한 호출의 컨텍스트에서 <xref:System.Threading.Thread.BeginThreadAffinity%2A?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="e53ff-123">The CLR typically calls `IHostTaskManager::BeginThreadAffinity` in the context of a call to <xref:System.Threading.Thread.BeginThreadAffinity%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="e53ff-124">해당 호출 될 때까지 현재 작업을 예약할 수 있어야 합니다 [ihosttaskmanager:: Endthreadaffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-endthreadaffinity-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e53ff-124">The current task must not be rescheduled until a corresponding call is made to [IHostTaskManager::EndThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-endthreadaffinity-method.md).</span></span> <span data-ttu-id="e53ff-125">작업, 전환할 수 있지만 다시 전환 된 경우 올가 전환 된 동일한 운영 체제 스레드를 할당 받아야 합니다. 에 대 한 호출을 중첩 `BeginThreadAffinity` 호출 현재 작업에 참조 하기 때문에 아무런 변화가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e53ff-125">Tasks can be switched out, but when they are switched back in, they must be assigned to the same operating system thread from which they were switched out. Nested calls to `BeginThreadAffinity` have no effect, because the call refers to the current task.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e53ff-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e53ff-126">Requirements</span></span>  
 <span data-ttu-id="e53ff-127">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="e53ff-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e53ff-128">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e53ff-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e53ff-129">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="e53ff-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e53ff-130">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e53ff-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e53ff-131">참고자료</span><span class="sxs-lookup"><span data-stu-id="e53ff-131">See also</span></span>

- [<span data-ttu-id="e53ff-132">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e53ff-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="e53ff-133">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e53ff-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="e53ff-134">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e53ff-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="e53ff-135">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e53ff-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
