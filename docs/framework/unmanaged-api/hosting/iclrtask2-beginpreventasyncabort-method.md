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
ms.openlocfilehash: 0da18c6850f393808d05dff8b1f19ac12b05bb86
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762892"
---
# <a name="iclrtask2beginpreventasyncabort-method"></a><span data-ttu-id="464df-102">ICLRTask2::BeginPreventAsyncAbort 메서드</span><span class="sxs-lookup"><span data-stu-id="464df-102">ICLRTask2::BeginPreventAsyncAbort Method</span></span>
<span data-ttu-id="464df-103">현재 스레드에 대 한 스레드 중단으로 인해 발생 하는 새 스레드 중단 요청을 지연 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="464df-103">Delays new thread abort requests from resulting in thread aborts on the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="464df-104">구문</span><span class="sxs-lookup"><span data-stu-id="464df-104">Syntax</span></span>  
  
```cpp  
HRESULT BeginPreventAsyncAbort();  
```  
  
## <a name="return-value"></a><span data-ttu-id="464df-105">Return Value</span><span class="sxs-lookup"><span data-stu-id="464df-105">Return Value</span></span>  
 <span data-ttu-id="464df-106">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="464df-106">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="464df-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="464df-107">HRESULT</span></span>|<span data-ttu-id="464df-108">Description</span><span class="sxs-lookup"><span data-stu-id="464df-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="464df-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="464df-109">S_OK</span></span>|<span data-ttu-id="464df-110">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="464df-110">The method completed successfully.</span></span>|  
|<span data-ttu-id="464df-111">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="464df-111">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="464df-112">현재 스레드가 아닌 스레드에서 메서드가 호출 된 경우</span><span class="sxs-lookup"><span data-stu-id="464df-112">The method was called on a thread which is not the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="464df-113">설명</span><span class="sxs-lookup"><span data-stu-id="464df-113">Remarks</span></span>  
 <span data-ttu-id="464df-114">이 메서드를 호출 하면 현재 스레드에 대 한 지연 스레드 중단 카운터가 1 씩 증가 합니다.</span><span class="sxs-lookup"><span data-stu-id="464df-114">Calling this method increments the delay-thread-abort counter for the current thread by one.</span></span>  
  
 <span data-ttu-id="464df-115">`BeginPreventAsyncAbort`및 [ICLRTask2:: EndPreventAsyncAbort](iclrtask2-endpreventasyncabort-method.md) 에 대 한 호출은 중첩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="464df-115">Calls to `BeginPreventAsyncAbort` and [ICLRTask2::EndPreventAsyncAbort](iclrtask2-endpreventasyncabort-method.md) can be nested.</span></span> <span data-ttu-id="464df-116">카운터가 0 보다 큰 경우 현재 스레드에 대 한 스레드 중단이 지연 됩니다.</span><span class="sxs-lookup"><span data-stu-id="464df-116">As long as the counter is greater than zero, thread aborts for the current thread are delayed.</span></span> <span data-ttu-id="464df-117">이 호출이 메서드 호출과 쌍을 이루지 않으면 `EndPreventAsyncAbort` 스레드 중단을 현재 스레드에 전달할 수 없는 상태에 도달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="464df-117">If this call is not paired with a call to the `EndPreventAsyncAbort` method, it is possible to reach a state in which thread aborts cannot be delivered to the current thread.</span></span>  
  
 <span data-ttu-id="464df-118">자체를 중단 하는 스레드에는 지연이 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="464df-118">The delay is not honored for a thread that aborts itself.</span></span>  
  
 <span data-ttu-id="464df-119">이 기능에 의해 노출 되는 기능은 VM (가상 컴퓨터)에서 내부적으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="464df-119">The functionality that is exposed by this feature is used internally by the virtual machine (VM).</span></span> <span data-ttu-id="464df-120">이러한 메서드를 잘못 지정 하면 VM에서 지정 되지 않은 동작이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="464df-120">Misuse of these methods may cause unspecified behavior in the VM.</span></span> <span data-ttu-id="464df-121">예를 들어를 `EndPreventAsyncAbort` 먼저 호출 하지 않고를 호출 하면 `BeginPreventAsyncAbort` VM이 이전에 증가 한 경우 카운터를 0으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="464df-121">For example, calling `EndPreventAsyncAbort` without first calling `BeginPreventAsyncAbort` could set the counter to zero when the VM has previously incremented it.</span></span> <span data-ttu-id="464df-122">마찬가지로 내부 카운터는 오버플로를 검사 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="464df-122">Similarly, the internal counter is not checked for overflow.</span></span> <span data-ttu-id="464df-123">호스트와 VM이 모두 증가 하 여 정수 한도를 초과 하는 경우 결과 동작은 지정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="464df-123">If it exceeds its integral limit because it is incremented by both the host and the VM, the resulting behavior is unspecified.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="464df-124">요구 사항</span><span class="sxs-lookup"><span data-stu-id="464df-124">Requirements</span></span>  
 <span data-ttu-id="464df-125">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="464df-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="464df-126">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="464df-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="464df-127">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="464df-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="464df-128">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="464df-128">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="464df-129">참조</span><span class="sxs-lookup"><span data-stu-id="464df-129">See also</span></span>

- [<span data-ttu-id="464df-130">EndPreventAsyncAbort 메서드</span><span class="sxs-lookup"><span data-stu-id="464df-130">EndPreventAsyncAbort Method</span></span>](iclrtask2-endpreventasyncabort-method.md)
- [<span data-ttu-id="464df-131">ICLRTask2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="464df-131">ICLRTask2 Interface</span></span>](iclrtask2-interface.md)
- [<span data-ttu-id="464df-132">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="464df-132">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="464df-133">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="464df-133">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="464df-134">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="464df-134">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="464df-135">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="464df-135">Hosting Interfaces</span></span>](hosting-interfaces.md)
