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
ms.openlocfilehash: dadacaea2b8741afc7b8c51404e2604dc759a629
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95680380"
---
# <a name="ihostsecuritymanagersetsecuritycontext-method"></a><span data-ttu-id="40761-102">IHostSecurityManager::SetSecurityContext 메서드</span><span class="sxs-lookup"><span data-stu-id="40761-102">IHostSecurityManager::SetSecurityContext Method</span></span>

<span data-ttu-id="40761-103">현재 실행 중인 스레드의 보안 컨텍스트를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="40761-103">Sets the security context of the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40761-104">구문</span><span class="sxs-lookup"><span data-stu-id="40761-104">Syntax</span></span>  
  
```cpp  
HRESULT SetSecurityContext (  
    [in]  EContextType eContextType,  
    [out] IHostSecurityContext** ppSecurityContext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="40761-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="40761-105">Parameters</span></span>  

 `eContextType`  
 <span data-ttu-id="40761-106">진행 CLR (공용 언어 런타임)이 호스트에 배치 하는 컨텍스트 유형을 나타내는 [EContextType](econtexttype-enumeration.md) 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="40761-106">[in] One of the [EContextType](econtexttype-enumeration.md) values, indicating what type of context the common language runtime (CLR) is placing on the host.</span></span>  
  
 `ppSecurityContext`  
 <span data-ttu-id="40761-107">제한이 새 [IHostSecurityContext](ihostsecuritycontext-interface.md) 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="40761-107">[out] A pointer to the address of a new [IHostSecurityContext](ihostsecuritycontext-interface.md) object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="40761-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="40761-108">Return Value</span></span>  
  
|<span data-ttu-id="40761-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="40761-109">HRESULT</span></span>|<span data-ttu-id="40761-110">설명</span><span class="sxs-lookup"><span data-stu-id="40761-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="40761-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="40761-111">S_OK</span></span>|<span data-ttu-id="40761-112">`SetSecurityContext` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="40761-112">`SetSecurityContext` returned successfully.</span></span>|  
|<span data-ttu-id="40761-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="40761-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="40761-114">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40761-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="40761-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="40761-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="40761-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="40761-116">The call timed out.</span></span>|  
|<span data-ttu-id="40761-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="40761-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="40761-118">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="40761-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="40761-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="40761-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="40761-120">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="40761-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="40761-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="40761-121">E_FAIL</span></span>|<span data-ttu-id="40761-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="40761-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="40761-123">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="40761-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="40761-124">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="40761-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="40761-125">설명</span><span class="sxs-lookup"><span data-stu-id="40761-125">Remarks</span></span>  

 <span data-ttu-id="40761-126">CLR은 `SetSecurityContext` 여러 시나리오에서를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="40761-126">The CLR calls `SetSecurityContext` in several scenarios.</span></span> <span data-ttu-id="40761-127">CLR은 클래스 및 모듈 생성자와 종료자를 실행 하기 전에 `SetSecurityContext` 를 호출 하 여 호스트를 실행 오류 로부터 보호 합니다.</span><span class="sxs-lookup"><span data-stu-id="40761-127">Before it executes class and module constructors and finalizers, the CLR calls `SetSecurityContext` to protect the host from execution failures.</span></span> <span data-ttu-id="40761-128">그런 다음에 대 한 다른 호출을 사용 하 여 생성자 또는 종료자를 실행 한 후 보안 컨텍스트를 원래 상태로 다시 설정 `SetSecurityContext` 합니다.</span><span class="sxs-lookup"><span data-stu-id="40761-128">It then resets the security context to its original state after execution of the constructor or finalizer, by using another call to `SetSecurityContext`.</span></span> <span data-ttu-id="40761-129">I/o가 완료 되 면 비슷한 패턴이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="40761-129">A similar pattern occurs with I/O completion.</span></span> <span data-ttu-id="40761-130">호스트가 [IHostIoCompletionManager](ihostiocompletionmanager-interface.md)를 구현 하는 경우 CLR은 `SetSecurityContext` [Iclrio manager:: OnComplete](iclriocompletionmanager-oncomplete-method.md)를 호출한 후를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="40761-130">If the host implements [IHostIoCompletionManager](ihostiocompletionmanager-interface.md), the CLR calls `SetSecurityContext` after the host calls [ICLRIoCompletionManager::OnComplete](iclriocompletionmanager-oncomplete-method.md).</span></span>  
  
 <span data-ttu-id="40761-131">작업자 스레드의 비동기 지점에서 CLR은 `SetSecurityContext` <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> 호스트나 clr이 스레드 풀을 구현 하 고 있는지 여부에 따라 [IHostThreadPoolManager:: QueueUserWorkItem](ihostthreadpoolmanager-queueuserworkitem-method.md)내에서 또는 내에서를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="40761-131">At asynchronous points in worker threads, the CLR calls `SetSecurityContext` within <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> or within [IHostThreadPoolManager::QueueUserWorkItem](ihostthreadpoolmanager-queueuserworkitem-method.md), depending on whether the host or the CLR is implementing the thread pool.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40761-132">요구 사항</span><span class="sxs-lookup"><span data-stu-id="40761-132">Requirements</span></span>  

 <span data-ttu-id="40761-133">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="40761-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40761-134">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="40761-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="40761-135">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="40761-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="40761-136">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40761-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40761-137">참조</span><span class="sxs-lookup"><span data-stu-id="40761-137">See also</span></span>

- <xref:System.Threading.ThreadPool?displayProperty=nameWithType>
- [<span data-ttu-id="40761-138">EContextType 열거형</span><span class="sxs-lookup"><span data-stu-id="40761-138">EContextType Enumeration</span></span>](econtexttype-enumeration.md)
- [<span data-ttu-id="40761-139">ICLRIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="40761-139">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
- [<span data-ttu-id="40761-140">IHostIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="40761-140">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)
- [<span data-ttu-id="40761-141">IHostSecurityContext 인터페이스</span><span class="sxs-lookup"><span data-stu-id="40761-141">IHostSecurityContext Interface</span></span>](ihostsecuritycontext-interface.md)
- [<span data-ttu-id="40761-142">IHostSecurityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="40761-142">IHostSecurityManager Interface</span></span>](ihostsecuritymanager-interface.md)
- [<span data-ttu-id="40761-143">IHostThreadPoolManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="40761-143">IHostThreadPoolManager Interface</span></span>](ihostthreadpoolmanager-interface.md)
