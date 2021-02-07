---
description: '자세히 알아보기: ICLRTask2 인터페이스'
title: ICLRTask2 인터페이스
ms.date: 03/30/2017
api_name:
- ICLRTask2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask2
helpviewer_keywords:
- ICLRTask2 interface [.NET Framework hosting]
ms.assetid: b5a22ebc-0582-49de-91f9-97a3d9789290
topic_type:
- apiref
ms.openlocfilehash: 835b01e1c808c071e9393c5117d5e38415ec8eba
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99728640"
---
# <a name="iclrtask2-interface"></a><span data-ttu-id="0c2b7-103">ICLRTask2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0c2b7-103">ICLRTask2 Interface</span></span>

<span data-ttu-id="0c2b7-104">는 [ICLRTask](iclrtask-interface.md) 인터페이스의 모든 기능을 제공 합니다. 또한는 현재 스레드에서 스레드 중단이 지연 될 수 있도록 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c2b7-104">Provides all the functionality of the [ICLRTask](iclrtask-interface.md) interface; in addition, provides methods that allow thread aborts to be delayed on the current thread.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0c2b7-105">메서드</span><span class="sxs-lookup"><span data-stu-id="0c2b7-105">Methods</span></span>  
  
|<span data-ttu-id="0c2b7-106">메서드</span><span class="sxs-lookup"><span data-stu-id="0c2b7-106">Method</span></span>|<span data-ttu-id="0c2b7-107">설명</span><span class="sxs-lookup"><span data-stu-id="0c2b7-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0c2b7-108">BeginPreventAsyncAbort 메서드</span><span class="sxs-lookup"><span data-stu-id="0c2b7-108">BeginPreventAsyncAbort Method</span></span>](iclrtask2-beginpreventasyncabort-method.md)|<span data-ttu-id="0c2b7-109">현재 스레드에서 새 스레드 중단 요청을 지연 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="0c2b7-109">Delays new thread abort requests on the current thread.</span></span>|  
|[<span data-ttu-id="0c2b7-110">EndPreventAsyncAbort 메서드</span><span class="sxs-lookup"><span data-stu-id="0c2b7-110">EndPreventAsyncAbort Method</span></span>](iclrtask2-endpreventasyncabort-method.md)|<span data-ttu-id="0c2b7-111">새 스레드 또는 보류 중인 스레드 중단 요청을 허용 하 여 현재 스레드에 대 한 스레드 중단을 발생 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c2b7-111">Allows new or pending thread abort requests to result in thread aborts on the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0c2b7-112">설명</span><span class="sxs-lookup"><span data-stu-id="0c2b7-112">Remarks</span></span>  

 <span data-ttu-id="0c2b7-113">`ICLRTask2`인터페이스는 인터페이스를 상속 하 `ICLRTask` 고 호스트가 스레드 중단을 지연 하지 않아야 하는 코드 영역을 보호할 수 있도록 하는 메서드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c2b7-113">The `ICLRTask2` interface inherits the `ICLRTask` interface and adds methods that allow the host to delay thread aborts, to protect a region of code that must not fail.</span></span> <span data-ttu-id="0c2b7-114">를 호출 하면 `BeginPreventAsyncAbort` 현재 스레드에 대 한 지연 스레드 중단 카운터가 증가 하 고를 호출 하면 `EndPreventAsyncAbort` 이 카운터가 감소 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c2b7-114">Calling `BeginPreventAsyncAbort` increments the delay-thread-abort counter for the current thread, and calling `EndPreventAsyncAbort` decrements it.</span></span> <span data-ttu-id="0c2b7-115">및에 대 `BeginPreventAsyncAbort` 한 호출은 `EndPreventAsyncAbort` 중첩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c2b7-115">Calls to `BeginPreventAsyncAbort` and `EndPreventAsyncAbort` can be nested.</span></span> <span data-ttu-id="0c2b7-116">카운터가 0 보다 큰 경우 현재 스레드에 대 한 스레드 중단이 지연 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c2b7-116">As long as the counter is greater than zero, thread aborts for the current thread are delayed.</span></span>  
  
 <span data-ttu-id="0c2b7-117">및에 대 `BeginPreventAsyncAbort` 한 호출이 `EndPreventAsyncAbort` 페어링 되지 않은 경우 현재 스레드에 스레드 중단을 전달할 수 없는 상태에 도달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c2b7-117">If calls to `BeginPreventAsyncAbort` and `EndPreventAsyncAbort` are not paired, it is possible to reach a state in which thread aborts cannot be delivered to the current thread.</span></span>  
  
 <span data-ttu-id="0c2b7-118">자체를 중단 하는 스레드에는 지연이 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0c2b7-118">The delay is not honored for a thread that aborts itself.</span></span>  
  
 <span data-ttu-id="0c2b7-119">이 기능에 의해 노출 되는 기능은 VM (가상 컴퓨터)에서 내부적으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c2b7-119">The functionality that is exposed by this feature is used internally by the virtual machine (VM).</span></span> <span data-ttu-id="0c2b7-120">이러한 메서드를 잘못 지정 하면 VM에서 지정 되지 않은 동작이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c2b7-120">Misuse of these methods may cause unspecified behavior in the VM.</span></span> <span data-ttu-id="0c2b7-121">예를 들어를 `EndPreventAsyncAbort` 먼저 호출 하지 않고를 호출 하면 `BeginPreventAsyncAbort` VM이 이전에 증가 한 경우 카운터를 0으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c2b7-121">For example, calling `EndPreventAsyncAbort` without first calling `BeginPreventAsyncAbort` could set the counter to zero when the VM has previously incremented it.</span></span> <span data-ttu-id="0c2b7-122">마찬가지로 내부 카운터는 오버플로를 검사 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0c2b7-122">Similarly, the internal counter is not checked for overflow.</span></span> <span data-ttu-id="0c2b7-123">호스트와 VM이 모두 증가 하 여 정수 한도를 초과 하는 경우 결과 동작은 지정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0c2b7-123">If it exceeds its integral limit because it is incremented by both the host and the VM, the resulting behavior is unspecified.</span></span>  
  
 <span data-ttu-id="0c2b7-124">에서 상속 된 멤버 `ICLRTask` 와이 인터페이스의 다른 용도에 대 한 자세한 내용은 [ICLRTask](iclrtask-interface.md) 인터페이스를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0c2b7-124">For information about members inherited from `ICLRTask` and about the other uses of this interface, see the [ICLRTask](iclrtask-interface.md) interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c2b7-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0c2b7-125">Requirements</span></span>  

 <span data-ttu-id="0c2b7-126">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0c2b7-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c2b7-127">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="0c2b7-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0c2b7-128">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c2b7-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0c2b7-129">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c2b7-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c2b7-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0c2b7-130">See also</span></span>

- [<span data-ttu-id="0c2b7-131">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0c2b7-131">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="0c2b7-132">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0c2b7-132">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="0c2b7-133">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0c2b7-133">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="0c2b7-134">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0c2b7-134">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="0c2b7-135">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0c2b7-135">Hosting Interfaces</span></span>](hosting-interfaces.md)
