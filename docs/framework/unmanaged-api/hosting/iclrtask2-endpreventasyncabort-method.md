---
description: '자세히 알아보기: ICLRTask2:: EndPreventAsyncAbort 메서드'
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
ms.openlocfilehash: 964a68c1ad6d5aa6a95560d2870e135640283590
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799501"
---
# <a name="iclrtask2endpreventasyncabort-method"></a><span data-ttu-id="67b1e-103">ICLRTask2::EndPreventAsyncAbort 메서드</span><span class="sxs-lookup"><span data-stu-id="67b1e-103">ICLRTask2::EndPreventAsyncAbort Method</span></span>

<span data-ttu-id="67b1e-104">새 스레드 또는 보류 중인 스레드 중단 요청을 허용 하 여 현재 스레드에 대 한 스레드 중단을 발생 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67b1e-104">Allows new or pending thread abort requests to result in thread aborts on the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67b1e-105">구문</span><span class="sxs-lookup"><span data-stu-id="67b1e-105">Syntax</span></span>  
  
```cpp  
HRESULT EndPreventAsyncAbort();  
```  
  
## <a name="return-value"></a><span data-ttu-id="67b1e-106">Return Value</span><span class="sxs-lookup"><span data-stu-id="67b1e-106">Return Value</span></span>  

 <span data-ttu-id="67b1e-107">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="67b1e-107">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="67b1e-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="67b1e-108">HRESULT</span></span>|<span data-ttu-id="67b1e-109">설명</span><span class="sxs-lookup"><span data-stu-id="67b1e-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="67b1e-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="67b1e-110">S_OK</span></span>|<span data-ttu-id="67b1e-111">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="67b1e-111">The method completed successfully.</span></span>|  
|<span data-ttu-id="67b1e-112">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="67b1e-112">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="67b1e-113">현재 스레드가 아닌 스레드에서 메서드가 호출 된 경우</span><span class="sxs-lookup"><span data-stu-id="67b1e-113">The method was called on a thread which is not the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="67b1e-114">설명</span><span class="sxs-lookup"><span data-stu-id="67b1e-114">Remarks</span></span>  

 <span data-ttu-id="67b1e-115">이 메서드를 호출 하면 현재 스레드에 대 한 지연 스레드 중단 카운터가 1 씩 감소 합니다.</span><span class="sxs-lookup"><span data-stu-id="67b1e-115">Calling this method decrements the delay-thread-abort counter for the current thread by one.</span></span>  
  
 <span data-ttu-id="67b1e-116">[ICLRTask2:: BeginPreventAsyncAbort](iclrtask2-beginpreventasyncabort-method.md) 에 대 한 호출은 `EndPreventAsyncAbort` 중첩 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67b1e-116">Calls to [ICLRTask2::BeginPreventAsyncAbort](iclrtask2-beginpreventasyncabort-method.md) and `EndPreventAsyncAbort` can be nested.</span></span> <span data-ttu-id="67b1e-117">카운터가 0 보다 큰 경우 현재 스레드에 대 한 스레드 중단이 지연 됩니다.</span><span class="sxs-lookup"><span data-stu-id="67b1e-117">As long as the counter is greater than zero, thread aborts for the current thread are delayed.</span></span>  
  
 <span data-ttu-id="67b1e-118">이 기능에 의해 노출 되는 기능은 VM (가상 컴퓨터)에서 내부적으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="67b1e-118">The functionality that is exposed by this feature is used internally by the virtual machine (VM).</span></span> <span data-ttu-id="67b1e-119">이러한 메서드를 잘못 지정 하면 VM에서 지정 되지 않은 동작이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67b1e-119">Misuse of these methods may cause unspecified behavior in the VM.</span></span> <span data-ttu-id="67b1e-120">예를 들어를 `EndPreventAsyncAbort` 먼저 호출 하지 않고를 호출 하면 `BeginPreventAsyncAbort` VM이 이전에 증가 한 경우 카운터를 0으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67b1e-120">For example, calling `EndPreventAsyncAbort` without first calling `BeginPreventAsyncAbort` could set the counter to zero when the VM has previously incremented it.</span></span> <span data-ttu-id="67b1e-121">마찬가지로 내부 카운터는 오버플로를 검사 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="67b1e-121">Similarly, the internal counter is not checked for overflow.</span></span> <span data-ttu-id="67b1e-122">호스트와 VM이 모두 증가 하 여 정수 한도를 초과 하는 경우 결과 동작은 지정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="67b1e-122">If it exceeds its integral limit because it is incremented by both the host and the VM, the resulting behavior is unspecified.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67b1e-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="67b1e-123">Requirements</span></span>  

 <span data-ttu-id="67b1e-124">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="67b1e-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67b1e-125">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="67b1e-125">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="67b1e-126">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="67b1e-126">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="67b1e-127">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67b1e-127">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67b1e-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="67b1e-128">See also</span></span>

- [<span data-ttu-id="67b1e-129">BeginPreventAsyncAbort 메서드</span><span class="sxs-lookup"><span data-stu-id="67b1e-129">BeginPreventAsyncAbort Method</span></span>](iclrtask2-beginpreventasyncabort-method.md)
- [<span data-ttu-id="67b1e-130">ICLRTask2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="67b1e-130">ICLRTask2 Interface</span></span>](iclrtask2-interface.md)
- [<span data-ttu-id="67b1e-131">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="67b1e-131">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="67b1e-132">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="67b1e-132">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="67b1e-133">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="67b1e-133">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="67b1e-134">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="67b1e-134">Hosting Interfaces</span></span>](hosting-interfaces.md)
