---
description: '자세히 알아보기: IHostSecurityManager:: SetSecurityContext 메서드'
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
ms.openlocfilehash: ee2de40e043e626aba1d75540faab3cae4c8fb7e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99671479"
---
# <a name="ihostsecuritymanagersetsecuritycontext-method"></a><span data-ttu-id="8f41a-103">IHostSecurityManager::SetSecurityContext 메서드</span><span class="sxs-lookup"><span data-stu-id="8f41a-103">IHostSecurityManager::SetSecurityContext Method</span></span>

<span data-ttu-id="8f41a-104">현재 실행 중인 스레드의 보안 컨텍스트를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f41a-104">Sets the security context of the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f41a-105">구문</span><span class="sxs-lookup"><span data-stu-id="8f41a-105">Syntax</span></span>  
  
```cpp  
HRESULT SetSecurityContext (  
    [in]  EContextType eContextType,  
    [out] IHostSecurityContext** ppSecurityContext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8f41a-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8f41a-106">Parameters</span></span>  

 `eContextType`  
 <span data-ttu-id="8f41a-107">진행 CLR (공용 언어 런타임)이 호스트에 배치 하는 컨텍스트 유형을 나타내는 [EContextType](econtexttype-enumeration.md) 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="8f41a-107">[in] One of the [EContextType](econtexttype-enumeration.md) values, indicating what type of context the common language runtime (CLR) is placing on the host.</span></span>  
  
 `ppSecurityContext`  
 <span data-ttu-id="8f41a-108">제한이 새 [IHostSecurityContext](ihostsecuritycontext-interface.md) 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="8f41a-108">[out] A pointer to the address of a new [IHostSecurityContext](ihostsecuritycontext-interface.md) object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8f41a-109">Return Value</span><span class="sxs-lookup"><span data-stu-id="8f41a-109">Return Value</span></span>  
  
|<span data-ttu-id="8f41a-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8f41a-110">HRESULT</span></span>|<span data-ttu-id="8f41a-111">설명</span><span class="sxs-lookup"><span data-stu-id="8f41a-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8f41a-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="8f41a-112">S_OK</span></span>|<span data-ttu-id="8f41a-113">`SetSecurityContext` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8f41a-113">`SetSecurityContext` returned successfully.</span></span>|  
|<span data-ttu-id="8f41a-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8f41a-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8f41a-115">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f41a-115">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8f41a-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8f41a-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8f41a-117">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8f41a-117">The call timed out.</span></span>|  
|<span data-ttu-id="8f41a-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8f41a-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8f41a-119">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8f41a-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8f41a-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8f41a-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8f41a-121">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="8f41a-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8f41a-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8f41a-122">E_FAIL</span></span>|<span data-ttu-id="8f41a-123">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="8f41a-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8f41a-124">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8f41a-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8f41a-125">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f41a-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8f41a-126">설명</span><span class="sxs-lookup"><span data-stu-id="8f41a-126">Remarks</span></span>  

 <span data-ttu-id="8f41a-127">CLR은 `SetSecurityContext` 여러 시나리오에서를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f41a-127">The CLR calls `SetSecurityContext` in several scenarios.</span></span> <span data-ttu-id="8f41a-128">CLR은 클래스 및 모듈 생성자와 종료자를 실행 하기 전에 `SetSecurityContext` 를 호출 하 여 호스트를 실행 오류 로부터 보호 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f41a-128">Before it executes class and module constructors and finalizers, the CLR calls `SetSecurityContext` to protect the host from execution failures.</span></span> <span data-ttu-id="8f41a-129">그런 다음에 대 한 다른 호출을 사용 하 여 생성자 또는 종료자를 실행 한 후 보안 컨텍스트를 원래 상태로 다시 설정 `SetSecurityContext` 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f41a-129">It then resets the security context to its original state after execution of the constructor or finalizer, by using another call to `SetSecurityContext`.</span></span> <span data-ttu-id="8f41a-130">I/o가 완료 되 면 비슷한 패턴이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f41a-130">A similar pattern occurs with I/O completion.</span></span> <span data-ttu-id="8f41a-131">호스트가 [IHostIoCompletionManager](ihostiocompletionmanager-interface.md)를 구현 하는 경우 CLR은 `SetSecurityContext` [Iclrio manager:: OnComplete](iclriocompletionmanager-oncomplete-method.md)를 호출한 후를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f41a-131">If the host implements [IHostIoCompletionManager](ihostiocompletionmanager-interface.md), the CLR calls `SetSecurityContext` after the host calls [ICLRIoCompletionManager::OnComplete](iclriocompletionmanager-oncomplete-method.md).</span></span>  
  
 <span data-ttu-id="8f41a-132">작업자 스레드의 비동기 지점에서 CLR은 `SetSecurityContext` <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> 호스트나 clr이 스레드 풀을 구현 하 고 있는지 여부에 따라 [IHostThreadPoolManager:: QueueUserWorkItem](ihostthreadpoolmanager-queueuserworkitem-method.md)내에서 또는 내에서를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f41a-132">At asynchronous points in worker threads, the CLR calls `SetSecurityContext` within <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> or within [IHostThreadPoolManager::QueueUserWorkItem](ihostthreadpoolmanager-queueuserworkitem-method.md), depending on whether the host or the CLR is implementing the thread pool.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f41a-133">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8f41a-133">Requirements</span></span>  

 <span data-ttu-id="8f41a-134">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8f41a-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f41a-135">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="8f41a-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8f41a-136">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f41a-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8f41a-137">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f41a-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f41a-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8f41a-138">See also</span></span>

- <xref:System.Threading.ThreadPool?displayProperty=nameWithType>
- [<span data-ttu-id="8f41a-139">EContextType 열거형</span><span class="sxs-lookup"><span data-stu-id="8f41a-139">EContextType Enumeration</span></span>](econtexttype-enumeration.md)
- [<span data-ttu-id="8f41a-140">ICLRIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8f41a-140">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
- [<span data-ttu-id="8f41a-141">IHostIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8f41a-141">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)
- [<span data-ttu-id="8f41a-142">IHostSecurityContext 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8f41a-142">IHostSecurityContext Interface</span></span>](ihostsecuritycontext-interface.md)
- [<span data-ttu-id="8f41a-143">IHostSecurityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8f41a-143">IHostSecurityManager Interface</span></span>](ihostsecuritymanager-interface.md)
- [<span data-ttu-id="8f41a-144">IHostThreadPoolManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8f41a-144">IHostThreadPoolManager Interface</span></span>](ihostthreadpoolmanager-interface.md)
