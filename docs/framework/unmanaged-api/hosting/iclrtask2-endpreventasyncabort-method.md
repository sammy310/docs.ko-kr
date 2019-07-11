---
title: ICLRTask2::EndPreventAsyncAbort 메서드
ms.date: 03/30/2017
api_name:
- ICLRTask2.EndPreventAsyncAbort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask2::EndPreventAsyncAbort
helpviewer_keywords:
- EndPreventAsyncAbort method [.NET Framework hosting]
- ICLRTask2::EndPreventAsyncAbort method [.NET Framework hosting]
ms.assetid: d8013659-e3df-44b3-814f-a6b534ce62f8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 36947eb33460fe3f15cf4ade1cad55cb5e77f1cc
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67770233"
---
# <a name="iclrtask2endpreventasyncabort-method"></a><span data-ttu-id="8a5bc-102">ICLRTask2::EndPreventAsyncAbort 메서드</span><span class="sxs-lookup"><span data-stu-id="8a5bc-102">ICLRTask2::EndPreventAsyncAbort Method</span></span>
<span data-ttu-id="8a5bc-103">새 또는 현재 스레드에서 보류 중인 스레드가 될 스레드 중단 요청을 중단 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a5bc-103">Allows new or pending thread abort requests to result in thread aborts on the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a5bc-104">구문</span><span class="sxs-lookup"><span data-stu-id="8a5bc-104">Syntax</span></span>  
  
```cpp  
HRESULT EndPreventAsyncAbort();  
```  
  
## <a name="return-value"></a><span data-ttu-id="8a5bc-105">반환 값</span><span class="sxs-lookup"><span data-stu-id="8a5bc-105">Return Value</span></span>  
 <span data-ttu-id="8a5bc-106">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="8a5bc-106">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="8a5bc-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8a5bc-107">HRESULT</span></span>|<span data-ttu-id="8a5bc-108">설명</span><span class="sxs-lookup"><span data-stu-id="8a5bc-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8a5bc-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="8a5bc-109">S_OK</span></span>|<span data-ttu-id="8a5bc-110">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8a5bc-110">The method completed successfully.</span></span>|  
|<span data-ttu-id="8a5bc-111">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="8a5bc-111">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="8a5bc-112">메서드는 현재 스레드가 아닌 스레드에서 호출 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8a5bc-112">The method was called on a thread which is not the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8a5bc-113">설명</span><span class="sxs-lookup"><span data-stu-id="8a5bc-113">Remarks</span></span>  
 <span data-ttu-id="8a5bc-114">현재 스레드에 대 한 하나에서이 메서드는 지연 스레드 중단 감소 카운터를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="8a5bc-114">Calling this method decrements the delay-thread-abort counter for the current thread by one.</span></span>  
  
 <span data-ttu-id="8a5bc-115">에 대 한 호출 [ICLRTask2::BeginPreventAsyncAbort](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md) 고 `EndPreventAsyncAbort` 중첩 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a5bc-115">Calls to [ICLRTask2::BeginPreventAsyncAbort](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md) and `EndPreventAsyncAbort` can be nested.</span></span> <span data-ttu-id="8a5bc-116">카운터는 0 보다 큰,으로 현재 스레드의 스레드 중단이 지연 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a5bc-116">As long as the counter is greater than zero, thread aborts for the current thread are delayed.</span></span>  
  
 <span data-ttu-id="8a5bc-117">이 기능을 통해 노출 되는 기능을 가상 컴퓨터 (VM)에서 내부적으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a5bc-117">The functionality that is exposed by this feature is used internally by the virtual machine (VM).</span></span> <span data-ttu-id="8a5bc-118">이러한 메서드를 잘못 사용 하면 VM에 지정 되지 않은 동작이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a5bc-118">Misuse of these methods may cause unspecified behavior in the VM.</span></span> <span data-ttu-id="8a5bc-119">예를 들어, 호출 `EndPreventAsyncAbort` 첫 번째 호출 하지 않고 `BeginPreventAsyncAbort` VM가 증가 이전 하는 경우 카운터를 0으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a5bc-119">For example, calling `EndPreventAsyncAbort` without first calling `BeginPreventAsyncAbort` could set the counter to zero when the VM has previously incremented it.</span></span> <span data-ttu-id="8a5bc-120">마찬가지로, 오버플로 대 한 내부 카운터 확인 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8a5bc-120">Similarly, the internal counter is not checked for overflow.</span></span> <span data-ttu-id="8a5bc-121">호스트와 VM에서 증가 하기 때문에 정수 한계 초과, 하는 경우의 결과 동작은 지정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8a5bc-121">If it exceeds its integral limit because it is incremented by both the host and the VM, the resulting behavior is unspecified.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a5bc-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8a5bc-122">Requirements</span></span>  
 <span data-ttu-id="8a5bc-123">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="8a5bc-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a5bc-124">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8a5bc-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8a5bc-125">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="8a5bc-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8a5bc-126">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a5bc-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a5bc-127">참고자료</span><span class="sxs-lookup"><span data-stu-id="8a5bc-127">See also</span></span>

- [<span data-ttu-id="8a5bc-128">BeginPreventAsyncAbort 메서드</span><span class="sxs-lookup"><span data-stu-id="8a5bc-128">BeginPreventAsyncAbort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md)
- [<span data-ttu-id="8a5bc-129">ICLRTask2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8a5bc-129">ICLRTask2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-interface.md)
- [<span data-ttu-id="8a5bc-130">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8a5bc-130">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="8a5bc-131">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8a5bc-131">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="8a5bc-132">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8a5bc-132">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="8a5bc-133">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8a5bc-133">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
