---
title: IHostSecurityManager::SetSecurityContext 메서드
ms.date: 03/30/2017
api_name:
- IHostSecurityManager.SetSecurityContext
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::SetSecurityContext
helpviewer_keywords:
- SetSecurityContext method [.NET Framework hosting]
- IHostSecurityManager::SetSecurityContext method [.NET Framework hosting]
ms.assetid: e4372384-ee69-48d7-97e0-8fab7866597a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3fa2df44d631b7e6c606ebb831f2915e9e649aab
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57480171"
---
# <a name="ihostsecuritymanagersetsecuritycontext-method"></a><span data-ttu-id="514e5-102">IHostSecurityManager::SetSecurityContext 메서드</span><span class="sxs-lookup"><span data-stu-id="514e5-102">IHostSecurityManager::SetSecurityContext Method</span></span>
<span data-ttu-id="514e5-103">현재 실행 중인 스레드의 보안 컨텍스트를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="514e5-103">Sets the security context of the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="514e5-104">구문</span><span class="sxs-lookup"><span data-stu-id="514e5-104">Syntax</span></span>  
  
```  
HRESULT SetSecurityContext (  
    [in]  EContextType eContextType,  
    [out] IHostSecurityContext** ppSecurityContext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="514e5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="514e5-105">Parameters</span></span>  
 `eContextType`  
 <span data-ttu-id="514e5-106">[in] 중 하나는 [EContextType](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md) 값을 호스트에 배치 되는 CLR (공용 언어 런타임) 컨텍스트의 형식을 나타내는입니다.</span><span class="sxs-lookup"><span data-stu-id="514e5-106">[in] One of the [EContextType](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md) values, indicating what type of context the common language runtime (CLR) is placing on the host.</span></span>  
  
 `ppSecurityContext`  
 <span data-ttu-id="514e5-107">[out] 새 주소에 대 한 포인터 [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="514e5-107">[out] A pointer to the address of a new [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="514e5-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="514e5-108">Return Value</span></span>  
  
|<span data-ttu-id="514e5-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="514e5-109">HRESULT</span></span>|<span data-ttu-id="514e5-110">설명</span><span class="sxs-lookup"><span data-stu-id="514e5-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="514e5-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="514e5-111">S_OK</span></span>|<span data-ttu-id="514e5-112">`SetSecurityContext` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="514e5-112">`SetSecurityContext` returned successfully.</span></span>|  
|<span data-ttu-id="514e5-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="514e5-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="514e5-114">CLR이 로드 된 프로세스에 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="514e5-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="514e5-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="514e5-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="514e5-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="514e5-116">The call timed out.</span></span>|  
|<span data-ttu-id="514e5-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="514e5-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="514e5-118">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="514e5-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="514e5-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="514e5-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="514e5-120">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="514e5-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="514e5-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="514e5-121">E_FAIL</span></span>|<span data-ttu-id="514e5-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="514e5-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="514e5-123">메서드 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="514e5-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="514e5-124">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="514e5-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="514e5-125">설명</span><span class="sxs-lookup"><span data-stu-id="514e5-125">Remarks</span></span>  
 <span data-ttu-id="514e5-126">CLR에서는 `SetSecurityContext` 여러 시나리오에서.</span><span class="sxs-lookup"><span data-stu-id="514e5-126">The CLR calls `SetSecurityContext` in several scenarios.</span></span> <span data-ttu-id="514e5-127">CLR은 호출 하는 클래스 및 모듈 생성자와 종료자를 실행 하기 전에 `SetSecurityContext` 호스트 실행 실패 로부터 보호 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="514e5-127">Before it executes class and module constructors and finalizers, the CLR calls `SetSecurityContext` to protect the host from execution failures.</span></span> <span data-ttu-id="514e5-128">그런 다음 다시 설정 보안 컨텍스트를 원래 상태로 생성자 또는 종료자를 실행 한 후에 다른 호출을 사용 하 여 `SetSecurityContext`입니다.</span><span class="sxs-lookup"><span data-stu-id="514e5-128">It then resets the security context to its original state after execution of the constructor or finalizer, by using another call to `SetSecurityContext`.</span></span> <span data-ttu-id="514e5-129">비슷한 패턴을 I/O 완료를 사용 하 여 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="514e5-129">A similar pattern occurs with I/O completion.</span></span> <span data-ttu-id="514e5-130">호스트 구현 하는 경우 [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md), CLR 호출 `SetSecurityContext` 호스트 호출한 후 [iclriocompletionmanager:: Oncomplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="514e5-130">If the host implements [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md), the CLR calls `SetSecurityContext` after the host calls [ICLRIoCompletionManager::OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md).</span></span>  
  
 <span data-ttu-id="514e5-131">작업자 스레드에서 비동기 지점에서 CLR은 호출 `SetSecurityContext` 내 <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> 안이나 [ihostthreadpoolmanager:: Queueuserworkitem](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md)호스트나 CLR 스레드 풀 구현 여부에 따라 합니다.</span><span class="sxs-lookup"><span data-stu-id="514e5-131">At asynchronous points in worker threads, the CLR calls `SetSecurityContext` within <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> or within [IHostThreadPoolManager::QueueUserWorkItem](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md), depending on whether the host or the CLR is implementing the thread pool.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="514e5-132">요구 사항</span><span class="sxs-lookup"><span data-stu-id="514e5-132">Requirements</span></span>  
 <span data-ttu-id="514e5-133">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="514e5-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="514e5-134">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="514e5-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="514e5-135">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="514e5-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="514e5-136">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="514e5-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="514e5-137">참고자료</span><span class="sxs-lookup"><span data-stu-id="514e5-137">See also</span></span>
- <xref:System.Threading.ThreadPool?displayProperty=nameWithType>
- [<span data-ttu-id="514e5-138">EContextType 열거형</span><span class="sxs-lookup"><span data-stu-id="514e5-138">EContextType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md)
- [<span data-ttu-id="514e5-139">ICLRIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="514e5-139">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="514e5-140">IHostIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="514e5-140">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
- [<span data-ttu-id="514e5-141">IHostSecurityContext 인터페이스</span><span class="sxs-lookup"><span data-stu-id="514e5-141">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="514e5-142">IHostSecurityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="514e5-142">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
- [<span data-ttu-id="514e5-143">IHostThreadPoolManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="514e5-143">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
