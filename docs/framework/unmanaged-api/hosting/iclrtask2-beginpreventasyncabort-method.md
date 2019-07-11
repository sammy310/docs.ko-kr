---
title: ICLRTask2::BeginPreventAsyncAbort 메서드
ms.date: 03/30/2017
api_name:
- ICLRTask2.BeginPreventAsyncAbort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask2::BeginPreventAsyncAbort
helpviewer_keywords:
- ICLRTask2::BeginPreventAsyncAbort method [.NET Framework hosting]
- BeginPreventAsyncAbort method [.NET Framework hosting]
ms.assetid: 75754c2f-38c7-4707-85fe-559db4542729
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 23ead080823ace1b091568108af8866dcbca14ec
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67770269"
---
# <a name="iclrtask2beginpreventasyncabort-method"></a><span data-ttu-id="2fa8a-102">ICLRTask2::BeginPreventAsyncAbort 메서드</span><span class="sxs-lookup"><span data-stu-id="2fa8a-102">ICLRTask2::BeginPreventAsyncAbort Method</span></span>
<span data-ttu-id="2fa8a-103">지연 새 스레드가 중단 요청을 현재 스레드의 스레드 중단이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fa8a-103">Delays new thread abort requests from resulting in thread aborts on the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2fa8a-104">구문</span><span class="sxs-lookup"><span data-stu-id="2fa8a-104">Syntax</span></span>  
  
```cpp  
HRESULT BeginPreventAsyncAbort();  
```  
  
## <a name="return-value"></a><span data-ttu-id="2fa8a-105">반환 값</span><span class="sxs-lookup"><span data-stu-id="2fa8a-105">Return Value</span></span>  
 <span data-ttu-id="2fa8a-106">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="2fa8a-106">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="2fa8a-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2fa8a-107">HRESULT</span></span>|<span data-ttu-id="2fa8a-108">설명</span><span class="sxs-lookup"><span data-stu-id="2fa8a-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2fa8a-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="2fa8a-109">S_OK</span></span>|<span data-ttu-id="2fa8a-110">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2fa8a-110">The method completed successfully.</span></span>|  
|<span data-ttu-id="2fa8a-111">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="2fa8a-111">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="2fa8a-112">메서드는 현재 스레드가 아닌 스레드에서 호출 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2fa8a-112">The method was called on a thread which is not the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2fa8a-113">설명</span><span class="sxs-lookup"><span data-stu-id="2fa8a-113">Remarks</span></span>  
 <span data-ttu-id="2fa8a-114">이 메서드를 호출 현재 스레드의 스레드 중단 지연 카운터를 씩 증가 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="2fa8a-114">Calling this method increments the delay-thread-abort counter for the current thread by one.</span></span>  
  
 <span data-ttu-id="2fa8a-115">에 대 한 호출 `BeginPreventAsyncAbort` 하 고 [ICLRTask2::EndPreventAsyncAbort](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-endpreventasyncabort-method.md) 중첩 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2fa8a-115">Calls to `BeginPreventAsyncAbort` and [ICLRTask2::EndPreventAsyncAbort](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-endpreventasyncabort-method.md) can be nested.</span></span> <span data-ttu-id="2fa8a-116">카운터는 0 보다 큰,으로 현재 스레드의 스레드 중단이 지연 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2fa8a-116">As long as the counter is greater than zero, thread aborts for the current thread are delayed.</span></span> <span data-ttu-id="2fa8a-117">경우이 호출은 호출 하 여 연결 하지는 `EndPreventAsyncAbort` 스레드 중단을 현재 스레드에 배달할 수 없는 상태에 도달할 가능성이 메서드.</span><span class="sxs-lookup"><span data-stu-id="2fa8a-117">If this call is not paired with a call to the `EndPreventAsyncAbort` method, it is possible to reach a state in which thread aborts cannot be delivered to the current thread.</span></span>  
  
 <span data-ttu-id="2fa8a-118">자체를 중단 하는 스레드에 대 한 지연 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2fa8a-118">The delay is not honored for a thread that aborts itself.</span></span>  
  
 <span data-ttu-id="2fa8a-119">이 기능을 통해 노출 되는 기능을 가상 컴퓨터 (VM)에서 내부적으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2fa8a-119">The functionality that is exposed by this feature is used internally by the virtual machine (VM).</span></span> <span data-ttu-id="2fa8a-120">이러한 메서드를 잘못 사용 하면 VM에 지정 되지 않은 동작이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2fa8a-120">Misuse of these methods may cause unspecified behavior in the VM.</span></span> <span data-ttu-id="2fa8a-121">예를 들어, 호출 `EndPreventAsyncAbort` 첫 번째 호출 하지 않고 `BeginPreventAsyncAbort` VM가 증가 이전 하는 경우 카운터를 0으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2fa8a-121">For example, calling `EndPreventAsyncAbort` without first calling `BeginPreventAsyncAbort` could set the counter to zero when the VM has previously incremented it.</span></span> <span data-ttu-id="2fa8a-122">마찬가지로, 오버플로 대 한 내부 카운터 확인 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2fa8a-122">Similarly, the internal counter is not checked for overflow.</span></span> <span data-ttu-id="2fa8a-123">호스트와 VM에서 증가 하기 때문에 정수 한계 초과, 하는 경우의 결과 동작은 지정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2fa8a-123">If it exceeds its integral limit because it is incremented by both the host and the VM, the resulting behavior is unspecified.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2fa8a-124">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2fa8a-124">Requirements</span></span>  
 <span data-ttu-id="2fa8a-125">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="2fa8a-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2fa8a-126">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2fa8a-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2fa8a-127">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="2fa8a-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2fa8a-128">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2fa8a-128">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fa8a-129">참고자료</span><span class="sxs-lookup"><span data-stu-id="2fa8a-129">See also</span></span>

- [<span data-ttu-id="2fa8a-130">EndPreventAsyncAbort 메서드</span><span class="sxs-lookup"><span data-stu-id="2fa8a-130">EndPreventAsyncAbort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-endpreventasyncabort-method.md)
- [<span data-ttu-id="2fa8a-131">ICLRTask2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2fa8a-131">ICLRTask2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-interface.md)
- [<span data-ttu-id="2fa8a-132">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2fa8a-132">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="2fa8a-133">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2fa8a-133">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="2fa8a-134">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2fa8a-134">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="2fa8a-135">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2fa8a-135">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
