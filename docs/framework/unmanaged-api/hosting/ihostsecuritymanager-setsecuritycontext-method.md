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
ms.openlocfilehash: 676a1d50202333203c13fcf916dbb14a6d91fb8f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121440"
---
# <a name="ihostsecuritymanagersetsecuritycontext-method"></a><span data-ttu-id="5effe-102">IHostSecurityManager::SetSecurityContext 메서드</span><span class="sxs-lookup"><span data-stu-id="5effe-102">IHostSecurityManager::SetSecurityContext Method</span></span>
<span data-ttu-id="5effe-103">현재 실행 중인 스레드의 보안 컨텍스트를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5effe-103">Sets the security context of the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5effe-104">구문</span><span class="sxs-lookup"><span data-stu-id="5effe-104">Syntax</span></span>  
  
```cpp  
HRESULT SetSecurityContext (  
    [in]  EContextType eContextType,  
    [out] IHostSecurityContext** ppSecurityContext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5effe-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5effe-105">Parameters</span></span>  
 `eContextType`  
 <span data-ttu-id="5effe-106">진행 CLR (공용 언어 런타임)이 호스트에 배치 하는 컨텍스트 유형을 나타내는 [EContextType](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md) 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="5effe-106">[in] One of the [EContextType](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md) values, indicating what type of context the common language runtime (CLR) is placing on the host.</span></span>  
  
 `ppSecurityContext`  
 <span data-ttu-id="5effe-107">제한이 새 [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5effe-107">[out] A pointer to the address of a new [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5effe-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="5effe-108">Return Value</span></span>  
  
|<span data-ttu-id="5effe-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5effe-109">HRESULT</span></span>|<span data-ttu-id="5effe-110">설명</span><span class="sxs-lookup"><span data-stu-id="5effe-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5effe-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="5effe-111">S_OK</span></span>|<span data-ttu-id="5effe-112">`SetSecurityContext` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5effe-112">`SetSecurityContext` returned successfully.</span></span>|  
|<span data-ttu-id="5effe-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5effe-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5effe-114">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5effe-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5effe-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5effe-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5effe-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5effe-116">The call timed out.</span></span>|  
|<span data-ttu-id="5effe-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5effe-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5effe-118">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5effe-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5effe-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5effe-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5effe-120">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="5effe-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5effe-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5effe-121">E_FAIL</span></span>|<span data-ttu-id="5effe-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="5effe-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5effe-123">메서드가 E_FAIL을 반환 하는 경우 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5effe-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5effe-124">호스팅 메서드에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5effe-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5effe-125">주의</span><span class="sxs-lookup"><span data-stu-id="5effe-125">Remarks</span></span>  
 <span data-ttu-id="5effe-126">CLR은 몇 가지 시나리오에서 `SetSecurityContext`를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="5effe-126">The CLR calls `SetSecurityContext` in several scenarios.</span></span> <span data-ttu-id="5effe-127">클래스 및 모듈 생성자와 종료 자가 실행 되기 전에 CLR은 실행 오류 로부터 호스트를 보호 하기 위해 `SetSecurityContext`를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="5effe-127">Before it executes class and module constructors and finalizers, the CLR calls `SetSecurityContext` to protect the host from execution failures.</span></span> <span data-ttu-id="5effe-128">그런 다음 `SetSecurityContext`에 대 한 다른 호출을 사용 하 여 생성자 또는 종료자를 실행 한 후 보안 컨텍스트를 원래 상태로 다시 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5effe-128">It then resets the security context to its original state after execution of the constructor or finalizer, by using another call to `SetSecurityContext`.</span></span> <span data-ttu-id="5effe-129">I/o가 완료 되 면 비슷한 패턴이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="5effe-129">A similar pattern occurs with I/O completion.</span></span> <span data-ttu-id="5effe-130">호스트가 [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)를 구현 하는 경우 CLR은 [Iclrio Manager:: OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md)를 호출한 후에 `SetSecurityContext`를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="5effe-130">If the host implements [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md), the CLR calls `SetSecurityContext` after the host calls [ICLRIoCompletionManager::OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md).</span></span>  
  
 <span data-ttu-id="5effe-131">작업자 스레드의 비동기 지점에서 CLR은 호스트나 CLR이 스레드 풀을 구현 하는지 여부에 따라 <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> 또는 [IHostThreadPoolManager:: QueueUserWorkItem](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md)내에서 `SetSecurityContext`를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="5effe-131">At asynchronous points in worker threads, the CLR calls `SetSecurityContext` within <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> or within [IHostThreadPoolManager::QueueUserWorkItem](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md), depending on whether the host or the CLR is implementing the thread pool.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5effe-132">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5effe-132">Requirements</span></span>  
 <span data-ttu-id="5effe-133">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5effe-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5effe-134">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="5effe-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5effe-135">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5effe-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5effe-136">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5effe-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5effe-137">참조</span><span class="sxs-lookup"><span data-stu-id="5effe-137">See also</span></span>

- <xref:System.Threading.ThreadPool?displayProperty=nameWithType>
- [<span data-ttu-id="5effe-138">EContextType 열거형</span><span class="sxs-lookup"><span data-stu-id="5effe-138">EContextType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md)
- [<span data-ttu-id="5effe-139">ICLRIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5effe-139">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="5effe-140">IHostIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5effe-140">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
- [<span data-ttu-id="5effe-141">IHostSecurityContext 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5effe-141">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="5effe-142">IHostSecurityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5effe-142">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
- [<span data-ttu-id="5effe-143">IHostThreadPoolManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5effe-143">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
